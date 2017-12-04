---
title: Metodi (F#)
description: "Informazioni su come un metodo di F # è una funzione associata a un tipo che consentono di esporre e implementare le funzionalità e il comportamento degli oggetti e tipi."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1febab3b-c922-49c6-889f-c22db107710c
ms.openlocfilehash: dae31abe6bb0773671b889646c9cceb410a492cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="methods"></a><span data-ttu-id="d20ce-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d20ce-104">Methods</span></span>

<span data-ttu-id="d20ce-105">Oggetto *metodo* è una funzione che è associata a un tipo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-105">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="d20ce-106">Nella programmazione orientata agli oggetti, metodi vengono utilizzati per esporre e implementare le funzionalità e il comportamento degli oggetti e tipi.</span><span class="sxs-lookup"><span data-stu-id="d20ce-106">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>


## <a name="syntax"></a><span data-ttu-id="d20ce-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d20ce-107">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-nameparameter-list [ : return-type ]=
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member self-identifier.method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member [inline] self-identifier.method-name : type-signature
[ attributes ]
default member [inline] self-identifier.method-nameparameter-list[ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue([ default-value ])>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="d20ce-108">Note</span><span class="sxs-lookup"><span data-stu-id="d20ce-108">Remarks</span></span>
<span data-ttu-id="d20ce-109">Nella sintassi precedente, è possibile visualizzare le varie forme di dichiarazioni e definizioni.</span><span class="sxs-lookup"><span data-stu-id="d20ce-109">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="d20ce-110">In più corpi di metodo, un'interruzione di riga segue il segno di uguale (=) e l'intero corpo del metodo è rientrato.</span><span class="sxs-lookup"><span data-stu-id="d20ce-110">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="d20ce-111">Gli attributi possono essere applicati a qualsiasi dichiarazione di metodo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-111">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="d20ce-112">Essi precedono la sintassi per una definizione di metodo e in genere sono elencati in una riga separata.</span><span class="sxs-lookup"><span data-stu-id="d20ce-112">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="d20ce-113">Per altre informazioni, vedere [Attributi](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d20ce-113">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="d20ce-114">Metodi possono essere contrassegnati `inline`.</span><span class="sxs-lookup"><span data-stu-id="d20ce-114">Methods can be marked `inline`.</span></span> <span data-ttu-id="d20ce-115">Per informazioni su `inline`, vedere [Funzioni inline](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d20ce-115">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="d20ce-116">I metodi non inline possono essere utilizzato in modo ricorsivo all'interno del tipo; non è necessario utilizzare in modo esplicito il `rec` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d20ce-116">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>


## <a name="instance-methods"></a><span data-ttu-id="d20ce-117">Metodi di istanza</span><span class="sxs-lookup"><span data-stu-id="d20ce-117">Instance Methods</span></span>
<span data-ttu-id="d20ce-118">I metodi di istanza vengono dichiarati con la `member` (parola chiave) e un *autoidentificatore*, seguito da un punto (.) e il nome di metodo e i parametri.</span><span class="sxs-lookup"><span data-stu-id="d20ce-118">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="d20ce-119">Come accade per `let` associazioni, la *elenco di parametri* può essere un modello.</span><span class="sxs-lookup"><span data-stu-id="d20ce-119">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="d20ce-120">Metodo parametri tra parentesi nel formato di tupla, ovvero i metodi modo vengono visualizzati in genere, racchiudere in F # quando vengono creati in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d20ce-120">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="d20ce-121">Tuttavia, currying (parametri separati da spazi) è inoltre comune e supportati anche altri modelli.</span><span class="sxs-lookup"><span data-stu-id="d20ce-121">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="d20ce-122">Nell'esempio seguente viene illustrata la definizione e utilizzo di un metodo di istanza non astratte.</span><span class="sxs-lookup"><span data-stu-id="d20ce-122">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="d20ce-123">All'interno di metodi di istanza, non utilizzare l'autoidentificatore per accedere ai campi definiti tramite associazioni let.</span><span class="sxs-lookup"><span data-stu-id="d20ce-123">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="d20ce-124">Utilizzare l'autoidentificatore per l'accesso ad altri membri e proprietà.</span><span class="sxs-lookup"><span data-stu-id="d20ce-124">Use the self identifier when accessing other members and properties.</span></span>


## <a name="static-methods"></a><span data-ttu-id="d20ce-125">Metodi statici</span><span class="sxs-lookup"><span data-stu-id="d20ce-125">Static Methods</span></span>
<span data-ttu-id="d20ce-126">La parola chiave `static` viene utilizzata per specificare che un metodo può essere chiamato senza un'istanza e non è associata a un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="d20ce-126">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="d20ce-127">In caso contrario, i metodi sono metodi di istanza.</span><span class="sxs-lookup"><span data-stu-id="d20ce-127">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="d20ce-128">L'esempio nella sezione successiva mostra i campi dichiarati con la `let` (parola chiave), i membri della proprietà è dichiarata con la `member` (parola chiave) e un metodo statico dichiarato con il `static` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d20ce-128">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="d20ce-129">Nell'esempio seguente viene illustrata la definizione e l'utilizzo di metodi statici.</span><span class="sxs-lookup"><span data-stu-id="d20ce-129">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="d20ce-130">Si presume che queste definizioni di metodo nel `SomeType` classe nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="d20ce-130">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="d20ce-131">Metodi virtuali e astratti</span><span class="sxs-lookup"><span data-stu-id="d20ce-131">Abstract and Virtual Methods</span></span>
<span data-ttu-id="d20ce-132">La parola chiave `abstract` indica che un metodo dispone di uno slot di distribuzione virtuale e potrebbe non avere una definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="d20ce-132">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="d20ce-133">Oggetto *slot di invio virtuale* è una voce in una tabella gestita internamente di funzioni che è utilizzata in fase di esecuzione per cercare di funzione virtuale chiamate in un tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="d20ce-133">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="d20ce-134">Il meccanismo di distribuzione virtuale è il meccanismo che implementa *polimorfismo*, un'importante funzionalità di programmazione orientata a oggetti.</span><span class="sxs-lookup"><span data-stu-id="d20ce-134">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="d20ce-135">È una classe che ha almeno un metodo astratto senza una definizione di un *classe astratta*, il che significa che è possibile creare nessuna istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="d20ce-135">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="d20ce-136">Per ulteriori informazioni sulle classi astratte, vedere [classi astratte](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="d20ce-136">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="d20ce-137">Le dichiarazioni di metodo astratto non includono un corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-137">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="d20ce-138">Al contrario, il nome del metodo è seguito da due punti (:) e una firma di tipo per il metodo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-138">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="d20ce-139">La firma del tipo di un metodo corrisponde a quello mostrata da IntelliSense quando si posiziona il puntatore del mouse sul nome di un metodo nell'Editor di codice di Visual Studio, ad eccezione senza nomi di parametro.</span><span class="sxs-lookup"><span data-stu-id="d20ce-139">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="d20ce-140">Le firme di tipo vengono visualizzate dall'interprete, fsi.exe, anche quando si lavora in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-140">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="d20ce-141">La firma del tipo di un metodo viene creata elencando i tipi di parametri, seguiti dal tipo restituito, con simboli di separatore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d20ce-141">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="d20ce-142">Parametri sottoposti a currying sono separati da `->` e parametri di tupla sono separati da `*`.</span><span class="sxs-lookup"><span data-stu-id="d20ce-142">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="d20ce-143">Il valore restituito è sempre separato dagli argomenti da un `->` simbolo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-143">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="d20ce-144">Possono utilizzare le parentesi per raggruppare parametri complessi, ad esempio quando un tipo di funzione è un parametro, o per indicare quando una tupla viene considerata come un singolo parametro anziché come due parametri.</span><span class="sxs-lookup"><span data-stu-id="d20ce-144">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="d20ce-145">È anche possibile assegnare i metodi astratti definizioni predefinite aggiungendo la definizione per la classe e utilizzando il `default` (parola chiave), come mostrato nel blocco di sintassi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d20ce-145">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="d20ce-146">Un metodo astratto che dispone di una definizione nella stessa classe è equivalente a un metodo virtuale in altri linguaggi .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d20ce-146">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="d20ce-147">Se esiste una definizione, il `abstract` (parola chiave) crea un nuovo slot di distribuzione nella tabella di funzioni virtuali per la classe.</span><span class="sxs-lookup"><span data-stu-id="d20ce-147">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="d20ce-148">Indipendentemente dal fatto che una classe base implementa i metodi astratti, le classi derivate possono fornire le implementazioni dei metodi astratti.</span><span class="sxs-lookup"><span data-stu-id="d20ce-148">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="d20ce-149">Per implementare un metodo astratto in una classe derivata, definire un metodo che presenta lo stesso nome e firma nella classe derivata, ma utilizzare il `override` o `default` (parola chiave) e fornire il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="d20ce-149">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="d20ce-150">Le parole chiave `override` e `default` esattamente lo stesso significato.</span><span class="sxs-lookup"><span data-stu-id="d20ce-150">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="d20ce-151">Utilizzare `override` se il nuovo metodo esegue l'override di un'implementazione della classe base; utilizzare `default` quando si crea un'implementazione della stessa classe come astratta dichiarazione originale.</span><span class="sxs-lookup"><span data-stu-id="d20ce-151">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="d20ce-152">Non utilizzare il `abstract` (parola chiave) sul metodo che implementa il metodo che è stato dichiarato nella classe base astratto.</span><span class="sxs-lookup"><span data-stu-id="d20ce-152">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="d20ce-153">Nell'esempio seguente viene illustrato un metodo astratto `Rotate` che ha un'implementazione predefinita, l'equivalente di un metodo virtuale .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d20ce-153">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="d20ce-154">Nell'esempio seguente viene illustrata una classe derivata che esegue l'override di un metodo della classe base.</span><span class="sxs-lookup"><span data-stu-id="d20ce-154">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="d20ce-155">In questo caso, la sostituzione modifica il comportamento in modo che il metodo non esegue alcuna operazione.</span><span class="sxs-lookup"><span data-stu-id="d20ce-155">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="d20ce-156">Metodi di overload</span><span class="sxs-lookup"><span data-stu-id="d20ce-156">Overloaded Methods</span></span>
<span data-ttu-id="d20ce-157">Metodi di overload sono metodi che dispongono di nomi identici in un determinato tipo, ma che dispongono di argomenti diversi.</span><span class="sxs-lookup"><span data-stu-id="d20ce-157">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="d20ce-158">In F #, gli argomenti facoltativi vengono normalmente utilizzati invece i metodi di overload.</span><span class="sxs-lookup"><span data-stu-id="d20ce-158">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="d20ce-159">Metodi di overload, tuttavia, sono consentiti nella lingua, condizione che gli argomenti sono in formato di tupla, non a currying</span><span class="sxs-lookup"><span data-stu-id="d20ce-159">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="d20ce-160">Argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="d20ce-160">Optional Arguments</span></span>

<span data-ttu-id="d20ce-161">A partire da F # 4.1, è anche possibile argomenti facoltativi con un valore di parametro predefinito nei metodi.</span><span class="sxs-lookup"><span data-stu-id="d20ce-161">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="d20ce-162">Si tratta per facilitare l'interoperabilità con codice c#.</span><span class="sxs-lookup"><span data-stu-id="d20ce-162">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="d20ce-163">Nell'esempio seguente viene illustrata la sintassi:</span><span class="sxs-lookup"><span data-stu-id="d20ce-163">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="d20ce-164">Si noti che il valore passato per `DefaultParameterValue` deve corrispondere al tipo di input.</span><span class="sxs-lookup"><span data-stu-id="d20ce-164">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="d20ce-165">Nell'esempio precedente, è un `int`.</span><span class="sxs-lookup"><span data-stu-id="d20ce-165">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="d20ce-166">Il tentativo di passare un valore non intero in `DefaultParameterValue` comporterebbe un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d20ce-166">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="d20ce-167">Esempio: Proprietà e metodi</span><span class="sxs-lookup"><span data-stu-id="d20ce-167">Example: Properties and Methods</span></span>
<span data-ttu-id="d20ce-168">Nell'esempio seguente contiene un tipo che include esempi di campi, funzioni private, proprietà e un metodo statico.</span><span class="sxs-lookup"><span data-stu-id="d20ce-168">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="d20ce-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d20ce-169">See Also</span></span>
[<span data-ttu-id="d20ce-170">Membri</span><span class="sxs-lookup"><span data-stu-id="d20ce-170">Members</span></span>](index.md)