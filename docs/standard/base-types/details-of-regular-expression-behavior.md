---
title: Dettagli sul comportamento delle espressioni regolari
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, behavior
- .NET Framework regular expressions, behavior
ms.assetid: 0ee1a6b8-caac-41d2-917f-d35570021b10
caps.latest.revision: "27"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac5ddfb0ac7ae83537717e9bd0cd46eb629641fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="details-of-regular-expression-behavior"></a>Dettagli sul comportamento delle espressioni regolari
Motore delle espressioni regolari di .NET Framework è un backtracking matcher di espressione regolare che include un motore non deterministiche Finite Automaton NFA () tradizionali, ad esempio utilizzato da Perl, Python, Emacs e Tcl. Ciò lo distingue dai motori delle espressioni regolari puri DFA (Deterministic Finite Automaton), più veloci ma più limitati, come quelli usati in awk, egrep o lex. Lo distingue anche dai motori NFA POSIX, standardizzati ma più lenti. Nella sezione seguente vengono descritti i tre tipi di motori di espressione regolare e viene spiegato perché le espressioni regolari in .NET Framework vengono implementate tramite un motore NFA tradizionale.  
  
## <a name="benefits-of-the-nfa-engine"></a>Vantaggi del motore NFA  
 Quando i motori DFA eseguono criteri di ricerca, l'ordine di elaborazione è basato sulla stringa di input. Il motore inizia all'inizio della stringa di input e procede in sequenza per determinare se il carattere successivo corrisponde al criterio di espressione regolare. È in grado di garantire la corrispondenza con la stringa più lunga possibile. Poiché non testano mai due volte lo stesso carattere, i motori DFA non supportano il backtracking. Tuttavia, poiché un motore DFA contiene solo stati finiti, non è in grado di trovare corrispondenze con i backreference e dato che non crea un'espansione esplicita, non è in grado di acquisire sottoespressioni.  
  
 A differenza dei motori DFA, quando i motori NFA tradizionali eseguono criteri di ricerca, l'ordine di elaborazione dipende dal criterio di espressione regolare. Durante l'elaborazione di un elemento di linguaggio specifico, il motore usa la corrispondenza greedy, ossia trova la corrispondenza con la maggior parte possibile della stringa di input. Ma salva anche il proprio stato dopo aver trovato la corrispondenza con una sottoespressione. Se la ricerca di una corrispondenza ha esito negativo, il motore torna allo stato salvato in modo da tentare altre corrispondenze. Questo processo di abbandono una corrispondenza di sottoespressione riuscita, in modo che inoltre possono corrispondere a elementi di linguaggio successivi nell'espressione regolare è noto come *backtracking*. I motori NFA usano il backtracking per testare tutte le possibili espansioni di un'espressione regolare in un ordine specifico e accettano la prima corrispondenza. Poiché un motore NFA tradizionale crea un'espansione specifica dell'espressione regolare per trovare una corrispondenza, è in grado di acquisire corrispondenze di sottoespressioni e backreference corrispondenti. Tuttavia, dato che un motore NFA tradizionale usa il backtracking, è possibile che visiti lo stesso stato più volte se arriva allo stato attraverso percorsi diversi. Di conseguenza, può diventare estremamente lento nel peggiore dei casi. Un motore NFA tradizionale accetta la prima corrispondenza trovata, quindi tralascia altre corrispondenze che potrebbero essere più lunghe.  
  
 I motori NFA POSIX sono come i motori NFA tradizionali, ad eccezione del fatto che continuano a eseguire il backtracking fino a quando possono di aver trovato la corrispondenza più lunga possibile. Di conseguenza, un motore NFA POSIX è più lento rispetto a un motore NFA tradizionale e quando si usa un motore NFA POSIX, non è possibile preferire una corrispondenza più breve rispetto a una più lunga modificando l'ordine di ricerca di backtracking.  
  
 I motori NFA tradizionali sono i preferiti dei programmatori perché offrono un maggiore controllo sulla corrispondenza delle stringhe rispetto ai motori DFA o NFA POSIX. Benché nel peggiore dei casi possano essere lenti, è possibile impostarli in modo che trovino le corrispondenze in tempo lineare o polinomiale usando criteri che riducono le ambiguità e limitano il backtracking. In altre parole, anche se la potenza e la flessibilità dei motori NFA possono influire negativamente sulle prestazioni, nella maggior parte dei casi questi motori offrono prestazioni da buone ad accettabili se un'espressione regolare è ben scritta e si evitano situazioni in cui il backtracking peggiora notevolmente le prestazioni.  
  
> [!NOTE]
>  Per informazioni sulla riduzione delle prestazioni causata da un utilizzo eccessivo del backtracking e sulle modalità di elaborazione di un'espressione regolare per risolverli, vedere [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## <a name="net-framework-engine-capabilities"></a>Funzionalità del motore di .NET Framework  
 Per sfruttare i vantaggi di un motore NFA tradizionale, il motore delle espressioni regolari .NET Framework include un set completo di costrutti che consentono ai programmatori di guidare il motore del backtracking. Tali costrutti possono essere usati per trovare più rapidamente le corrispondenze o per favorire espansioni specifiche rispetto ad altre.  
  
 Di seguito sono elencate altre caratteristiche del motore delle espressioni regolari di .NET Framework:  
  
-   Quantificatori lenti: `??`, `*?`, `+?`, `{`  *n*  `,` *m*`}?`. Questi costrutti indicano al motore di backtracking di cercare prima il numero minimo di ripetizioni. Al contrario, i normali quantificatori greedy tentano di trovare prima il numero massimo di ripetizioni. L'esempio che segue illustrata la differenza tra i due tipi. Un'espressione regolare trova la corrispondenza con una frase che termina con un numero e un gruppo di acquisizione deve estrarre tale numero. L'espressione regolare `.+(\d+)\.` include il quantificatore greedy `.+`, che fa in modo che il motore delle espressioni regolari acquisisca solo l'ultima cifra del numero. Al contrario, l'espressione regolare `.+?(\d+)\.` include il quantificatore lazy `.+?`, che fa in modo che il motore delle espressioni regolari acquisisca l'intero numero.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lazy1.cs#1)]
     [!code-vb[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lazy1.vb#1)]  
  
     Le versioni greedy e lazy di questa espressione regolare vengono definite come illustrato nella tabella seguente.'  
  
    |Criterio|Descrizione|  
    |-------------|-----------------|  
    |`.+` (quantificatore greedy)|Trova almeno un'occorrenza di qualsiasi carattere. In questo modo il motore delle espressioni regolari considera soddisfatta la corrispondenza con l'intera stringa ed esegue il backtracking, necessario per verificare le corrispondenze con il resto del criterio.|  
    |`.+?` (quantificatore lazy)|Trova almeno un'occorrenza di qualsiasi carattere, ma accetta la corrispondenza con il minor numero possibile di caratteri.|  
    |`(\d+)`|Trova la corrispondenza con almeno un carattere alfanumerico e la assegna al primo gruppo di acquisizione.|  
    |`\.`|Trova la corrispondenza con un punto.|  
  
     Per ulteriori informazioni sui quantificatori lazy, vedere [quantificatori](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
-   Lookahead positiva: `(?=` *sottoespressione*`)`. Questa funzionalità consente al motore di backtracking tornare alla stessa posizione nel testo dopo aver trovato la corrispondenza con una sottoespressione. È utile per eseguire una ricerca in tutto il testo verificando più criteri a partire dalla stessa posizione. Ciò consente anche al motore di verificare che una sottostringa esista alla fine della corrispondenza senza includere la sottostringa nel testo di cui è stata trovata la corrispondenza. Nell'esempio seguente il lookahead positivo viene usato per estrarre le parole di una frase che non sono seguite da simboli di punteggiatura.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead1.cs#2)]
     [!code-vb[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead1.vb#2)]  
  
     L'espressione regolare `\b[A-Z]+\b(?=\P{P})` viene definita come illustrato nella tabella seguente.  
  
    |Criterio|Descrizione|  
    |-------------|-----------------|  
    |`\b`|Inizia la corrispondenza sul confine di parola.|  
    |`[A-Z]+`|Trova la corrispondenza con qualsiasi carattere alfabetico una o più volte. Poiché il <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> metodo viene chiamato con il <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> opzione, il confronto è tra maiuscole e minuscole.|  
    |`\b`|Termina la corrispondenza sul confine di parola.|  
    |`(?=\P{P})`|Esegue il lookahead per determinare se il carattere successivo è un simbolo di punteggiatura. In caso contrario, la corrispondenza ha esito positivo.|  
  
     Per ulteriori informazioni sulle asserzioni lookahead positive, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Lookahead negative: `(?!` *sottoespressione*`)`. Questa funzionalità aggiunge la capacità di considerare soddisfatta la corrispondenza con un'espressione solo se non trova la corrispondenza con una sottoespressione. Ciò risulta particolarmente utile per abbreviare una ricerca, poiché spesso è più semplice formulare un'espressione per un caso da eliminare che un'espressione che individua i casi da includere. Ad esempio, è difficile scrivere un'espressione per le parole che non iniziano con "non". Nell'esempio seguente viene usato il lookahead negativo per escluderle.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead2.cs#3)]
     [!code-vb[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead2.vb#3)]  
  
     Il criterio di ricerca di espressioni regolari `\b(?!non)\w+\b` è definito nel modo illustrato nella tabella seguente.  
  
    |Criterio|Descrizione|  
    |-------------|-----------------|  
    |`\b`|Inizia la corrispondenza sul confine di parola.|  
    |`(?!non)`|Esegue il lookahead per verificare che la stringa corrente non inizi con "non". In caso contrario, la corrispondenza ha esito negativo.|  
    |`(\w+)`|Trova la corrispondenza di uno o più caratteri alfanumerici.|  
    |`\b`|Termina la corrispondenza sul confine di parola.|  
  
     Per ulteriori informazioni sulle asserzioni lookahead negative, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Valutazione condizionale: `(?(` *espressione*`)`*Sì*`|`*non* `)` e `(?(` *nome*`)`*Sì*`|`*non*`)`, dove *espressione* è una sottoespressione di corrispondenza, *nome* è il nome di un gruppo di acquisizione, *Sì* è la stringa di corrispondenza se *espressione* viene trovata una corrispondenza o *nome* è un valore valido, gruppo acquisito non vuoto, e *non* è la sottoespressione per trovare la corrispondenza se *espressione* non trova corrispondenza o *nome* non è un gruppo acquisito valido e non vuoto. Questa funzionalità consente al motore di eseguire la ricerca usando più di un criterio alternativo, in base al risultato della corrispondenza di una sottoespressione precedente o al risultato di un'asserzione di larghezza zero. Ciò offre una forma più efficace di backreference che consente, ad esempio, di trovare la corrispondenza con una sottoespressione in base al fatto che sia stata trovata o meno la corrispondenza con una sottoespressione precedente. L'espressione regolare nell'esempio seguente trova la corrispondenza con paragrafi destinati all'uso sia pubblico che interno. I paragrafi destinati solo all'uso interno iniziano con un tag `<PRIVATE>`. Il criterio di espressione regolare `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` usa la valutazione condizionale per assegnare il contenuto dei paragrafi destinati all'uso pubblico e all'uso interno a gruppi di acquisizione separati. I paragrafi possono quindi essere gestiti in modo diverso.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/conditional1.cs#4)]
     [!code-vb[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/conditional1.vb#4)]  
  
     Il criterio di ricerca di espressioni regolari è definito nel modo illustrato nella tabella seguente.  
  
    |Criterio|Descrizione|  
    |-------------|-----------------|  
    |`^`|Inizia la corrispondenza all'inizio di una riga.|  
    |`(?<Pvt>\<PRIVATE\>\s)?`|Trova la corrispondenza con zero o un'occorrenza della stringa `<PRIVATE>` seguita da un carattere di spazio vuoto. Assegna la corrispondenza a un gruppo di acquisizione denominato `Pvt`.|  
    |`(?(Pvt)((\w+\p{P}?\s)+)`|Se il gruppo di acquisizione `Pvt` esiste, trova una o più occorrenze di uno o più caratteri alfanumerici seguiti da zero o un separatore di punteggiatura seguito da un carattere di spazio vuoto. Assegna la sottostringa al primo gruppo di acquisizione.|  
    |`&#124;((\w+\p{P}?\s)+))`|Se il gruppo di acquisizione `Pvt` non esiste, trova una o più occorrenze di uno o più caratteri alfanumerici seguiti da zero o un separatore di punteggiatura seguito da un carattere di spazio vuoto. Assegna la sottostringa al terzo gruppo di acquisizione.|  
    |`\r?$`|Trova la corrispondenza alla fine di una riga o alla fine della stringa.|  
  
     Per ulteriori informazioni sulla valutazione condizionale, vedere [costrutti di alternanza](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md).  
  
-   Le definizioni di gruppo di bilanciamento del carico: `(?<` *nome1*`-`*nome2* `>` *sottoespressione*`)`. Questa funzionalità consente al motore delle espressioni regolari di tenere traccia dei costrutti annidati, ad esempio parentesi o parentesi quadre di apertura e chiusura. Per un esempio, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Sottoespressioni di non backtracking (nota anche come sottoespressioni): `(?>` *sottoespressione*`)`. Questa funzionalità consente al motore di backtracking di garantire che una sottoespressione corrisponda solo alla prima corrispondenza trovata per tale sottoespressione, come se l'espressione venisse eseguita indipendentemente dall'espressione che la contiene. Se non si usa questo costrutto, il backtracking dall'espressione più ampia può modificare il comportamento di una sottoespressione. Ad esempio, l'espressione regolare `(a+)\w` trova la corrispondenza con uno o più caratteri "a", insieme a un carattere alfanumerico che segue la sequenza di caratteri "a", e assegna la sequenza di caratteri "a" al primo gruppo di acquisizione. Se però anche l'ultimo carattere della stringa di input è "a", l'elemento di linguaggio `\w` ne determina la corrispondenza e il carattere non viene incluso nel gruppo acquisito.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking2.vb#7)]  
  
     L'espressione regolare `((?>a+))\w` evita questo comportamento. Poiché la corrispondenza di tutti i caratteri "a" consecutivi viene determinata senza backtracking, il primo gruppo di acquisizione include tutti i caratteri "a" consecutivi. Se i caratteri "a" non sono seguiti da almeno un carattere diverso da "a", la corrispondenza ha esito negativo.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking1.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking1.vb#8)]  
  
     Per ulteriori informazioni sulle sottoespressioni non di backtracking, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Destra a sinistra di ricerca, che viene specificato, indicando il <xref:System.Text.RegularExpressions.RegexOptions.RightToLeft?displayProperty=nameWithType> opzione un <xref:System.Text.RegularExpressions.Regex> metodo corrispondente dell'istanza di costruttore di classe o static. Questa funzionalità è utile durante la ricerca da destra verso sinistra anziché da sinistra verso destra oppure nei casi in cui risulta più efficace iniziare una corrispondenza nella parte destra del criterio anziché in quella sinistra. Come illustrato nell'esempio seguente, l'uso della corrispondenza da destra a sinistra può modificare il comportamento dei quantificatori greedy. Nell'esempio vengono condotte due ricerche di una frase che termina con un numero. La ricerca da sinistra a destra che usa il quantificatore greedy `+` trova la corrispondenza con una delle sei cifre nella frase, mentre la ricerca da destra a sinistra trova la corrispondenza con tutte le sei cifre. Per una descrizione del criterio di espressione regolare, vedere l'esempio che illustra i quantificatori lazy in precedenza in questa sezione.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/rtl1.cs#6)]
     [!code-vb[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/rtl1.vb#6)]  
  
     Per altre informazioni sulla corrispondenza da destra a sinistra, vedere [Opzioni di espressioni regolari](../../../docs/standard/base-types/regular-expression-options.md).  
  
-   Lookbehind positive e negative: `(?<=` *sottoespressione* `)` per lookbehind positivo e `(?<!` *sottoespressione* `)` per lookbehind negativo. Questa funzionalità è simile a lookahead, illustrata in precedenza in questo argomento. Poiché il motore delle espressioni regolari consente la corrispondenza da destra a sinistra completa, le espressioni regolari consentono lookbehind illimitati. Il lookbehind positivo e negativo consente inoltre di evitare l'annidamento di quantificatori quando la sottoespressione annidata è un superset di un'espressione esterna. Le espressioni regolari con tali quantificatori spesso influiscono negativamente sulle prestazioni. L'esempio seguente, ad esempio, verifica se una stringa inizia e termina con un carattere alfanumerico e se qualsiasi altro carattere nella stringa appartiene a un subset più ampio. Il criterio costituisce una parte dell'espressione regolare usata per convalidare gli indirizzi di posta elettronica. Per altre informazioni, vedere [Procedura: Verificare che le stringhe siano nel formato di posta elettronica valido](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookbehind1.cs#5)]
     [!code-vb[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookbehind1.vb#5)]  
  
     L'espressione regolare `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` è definita nel modo illustrato nella tabella seguente.  
  
    |Criterio|Descrizione|  
    |-------------|-----------------|  
    |`^`|Inizia la ricerca della corrispondenza all'inizio della stringa.|  
    |`[A-Z0-9]`|Trova la corrispondenza con qualsiasi carattere numerico o alfanumerico. Il confronto non rileva la differenza tra maiuscole e minuscole.|  
    |`([-!#$%&'.*+/=?^`{}&#124;~\w])*`|Corrisponde a zero o più occorrenze di qualsiasi carattere alfanumerico o i caratteri seguenti:-,!, #, $, % &, ',., *, +, /, =,?, ^, ', {,}, &#124; o ~.|  
    |`(?<=[A-Z0-9])`|Esegue il lookbehind al carattere precedente, che deve essere numerico o alfanumerico. Il confronto non rileva la differenza tra maiuscole e minuscole.|  
    |`$`|Terminare la corrispondenza alla fine della stringa.|  
  
     Per ulteriori informazioni su lookbehind positive e negative, vedere [costrutti di raggruppamento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Informazioni su come il backtracking delle espressioni regolari si dirama per trovare corrispondenze alternative.|  
|[Compilazione e riutilizzo](../../../docs/standard/base-types/compilation-and-reuse-in-regular-expressions.md)|Informazioni sulla compilazione e sul riutilizzo di espressioni regolari per ottimizzare le prestazioni.|  
|[Thread safety](../../../docs/standard/base-types/thread-safety-in-regular-expressions.md)|Informazioni sulla modalità di thread safety delle espressioni regolari in cui viene spiegato quando è necessario sincronizzare l'accesso a oggetti di espressione regolare.|  
|[Espressioni regolari di .NET Framework](../../../docs/standard/base-types/regular-expressions.md)|Panoramica dell'aspetto del linguaggio di programmazione delle espressioni regolari.|  
|[Modello a oggetti delle espressioni regolari](../../../docs/standard/base-types/the-regular-expression-object-model.md)|Esempi di codice e informazioni che illustrano l'uso delle classi di espressioni regolari.|  
|[Esempi di espressioni regolari](../../../docs/standard/base-types/regular-expression-examples.md)|Esempi di codice che illustrano l'uso delle espressioni regolari nelle applicazioni comuni.|  
|[Linguaggio di espressioni regolari - Riferimento rapido](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Informazioni su set di caratteri, operatori e costrutti che è possibile usare per definire le espressioni regolari.|  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Text.RegularExpressions?displayProperty=nameWithType>
