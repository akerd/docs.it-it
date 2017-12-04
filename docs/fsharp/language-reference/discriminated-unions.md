---
title: Unioni discriminate (F#)
description: 'Informazioni sull''utilizzo di F # unioni discriminate.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e2a011-c785-48c8-859f-79df7f3a0e29
ms.openlocfilehash: a374f521bcde7506bb3a9eebb627eaffcd8b94a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="discriminated-unions"></a><span data-ttu-id="1961b-104">Unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="1961b-104">Discriminated Unions</span></span>

<span data-ttu-id="1961b-105">Unioni discriminate forniscono supporto per i valori che possono essere uno dei numerosi casi denominati, ognuno con diversi valori e tipi potenzialmente.</span><span class="sxs-lookup"><span data-stu-id="1961b-105">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="1961b-106">Unioni discriminate sono utili per i dati eterogenei. dati che possono disporre di casi speciali, tra cui validi e casi di errore. dati variabili di tipo da un'istanza a un altro. e come alternativa per le gerarchie di oggetti piccoli.</span><span class="sxs-lookup"><span data-stu-id="1961b-106">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="1961b-107">Inoltre, discriminata ricorsiva unioni vengono utilizzate per rappresentare strutture di dati.</span><span class="sxs-lookup"><span data-stu-id="1961b-107">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="1961b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1961b-108">Syntax</span></span>

```fsharp
[ attributes ]
type type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a><span data-ttu-id="1961b-109">Note</span><span class="sxs-lookup"><span data-stu-id="1961b-109">Remarks</span></span>
<span data-ttu-id="1961b-110">Unioni discriminate sono simili ai tipi di unione in altri linguaggi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="1961b-110">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="1961b-111">Come con un tipo di unione in C++ o un tipo variant in Visual Basic, i dati archiviati nel valore non sono fisso; può essere una delle numerose opzioni distinte.</span><span class="sxs-lookup"><span data-stu-id="1961b-111">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="1961b-112">A differenza delle unioni in questi altri linguaggi, tuttavia, per ognuna delle possibili opzioni viene fornito un *identificatore case*.</span><span class="sxs-lookup"><span data-stu-id="1961b-112">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="1961b-113">Gli identificatori di case sono nomi per i vari tipi di valori possibili che possono essere oggetti di questo tipo; i valori sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="1961b-113">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="1961b-114">Se i valori non sono presenti, il caso è equivalente a un case di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1961b-114">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="1961b-115">Se sono presenti i valori, ogni valore può essere un singolo valore di un tipo specificato o una tupla che consente di aggregare più campi di tipo stesso o diversi.</span><span class="sxs-lookup"><span data-stu-id="1961b-115">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="1961b-116">A partire da F # 3.1, è possibile assegnare un nome a un singolo campo, ma il nome è facoltativo, anche se altri campi nel caso stesso nome.</span><span class="sxs-lookup"><span data-stu-id="1961b-116">As of F# 3.1, you can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="1961b-117">Ad esempio, si consideri la seguente dichiarazione di un tipo di forma.</span><span class="sxs-lookup"><span data-stu-id="1961b-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="1961b-118">Il codice precedente viene dichiarata un'unione discriminata forma, che può avere valori di uno qualsiasi dei tre casi: rettangolo, cerchio e prisma.</span><span class="sxs-lookup"><span data-stu-id="1961b-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="1961b-119">Ogni case è un set diverso di campi.</span><span class="sxs-lookup"><span data-stu-id="1961b-119">Each case has a different set of fields.</span></span> <span data-ttu-id="1961b-120">Il rettangolo di case ha due denominato campi, entrambi di tipo `float`, con la larghezza di nomi e la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="1961b-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="1961b-121">Nel caso del cerchio è solo un campo denominato, radius.</span><span class="sxs-lookup"><span data-stu-id="1961b-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="1961b-122">Il case prisma presenta tre campi, due dei quali (larghezza e altezza) sono denominati campi.</span><span class="sxs-lookup"><span data-stu-id="1961b-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="1961b-123">Campi senza nome sono indicati come campi di tipo anonimi.</span><span class="sxs-lookup"><span data-stu-id="1961b-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="1961b-124">Per creare oggetti, che fornisce valori per i campi denominati e anonimi, in base negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1961b-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="1961b-125">Questo codice viene illustrato che è possibile utilizzare i campi denominati durante l'inizializzazione o basarsi sull'ordine dei campi nella dichiarazione è sufficiente fornire i valori per ogni campo, a sua volta.</span><span class="sxs-lookup"><span data-stu-id="1961b-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="1961b-126">La chiamata al costruttore per `rect` nel codice precedente utilizza i campi, ma la chiamata al costruttore per `circ` utilizza l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="1961b-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="1961b-127">È possibile combinare i campi ordinati e denominata campi, come la costruzione di `prism`.</span><span class="sxs-lookup"><span data-stu-id="1961b-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="1961b-128">Il `option` tipo è un'unione discriminata semplice nella libreria di base F #.</span><span class="sxs-lookup"><span data-stu-id="1961b-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="1961b-129">Il `option` tipo è dichiarato come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1961b-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="1961b-130">Il codice precedente specifica che il tipo `Option` è un'unione discriminata che dispone di due casi, `Some` e `None`.</span><span class="sxs-lookup"><span data-stu-id="1961b-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="1961b-131">Il `Some` case ha un valore associato che è costituito da un campo anonimo il cui tipo è rappresentato dal parametro di tipo `'a`.</span><span class="sxs-lookup"><span data-stu-id="1961b-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="1961b-132">Il `None` case non ha alcun valore associato.</span><span class="sxs-lookup"><span data-stu-id="1961b-132">The `None` case has no associated value.</span></span> <span data-ttu-id="1961b-133">In questo modo il `option` tipo specifica un tipo generico che presenta un valore di un tipo o nessun valore.</span><span class="sxs-lookup"><span data-stu-id="1961b-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="1961b-134">Il tipo `Option` dispone anche di un alias del tipo di lettere minuscole, `option`, vale a dire utilizzati più frequentemente.</span><span class="sxs-lookup"><span data-stu-id="1961b-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="1961b-135">Gli identificatori di case è utilizzabile i costruttori per il tipo di unione discriminato.</span><span class="sxs-lookup"><span data-stu-id="1961b-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="1961b-136">Ad esempio, il codice seguente viene utilizzato per creare valori del `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="1961b-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="1961b-137">Gli identificatori di case vengono inoltre utilizzati nelle espressioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="1961b-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="1961b-138">In un modello di espressione di criteri, gli identificatori vengono forniti per i valori associati a singoli case.</span><span class="sxs-lookup"><span data-stu-id="1961b-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="1961b-139">Ad esempio, nel codice seguente, `x` è l'identificatore specificato il valore di cui è associato il `Some` case del `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="1961b-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="1961b-140">Nelle espressioni dei criteri, è possibile utilizzare i campi denominati per specificare le corrispondenze di unione discriminate.</span><span class="sxs-lookup"><span data-stu-id="1961b-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="1961b-141">Per il tipo di forma che è stato dichiarato in precedenza, è possibile utilizzare i campi denominati, come mostrato nel codice seguente per estrarre i valori dei campi.</span><span class="sxs-lookup"><span data-stu-id="1961b-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="1961b-142">In genere, gli identificatori di case possono essere utilizzati senza qualifica con il nome dell'unione.</span><span class="sxs-lookup"><span data-stu-id="1961b-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="1961b-143">Se si desidera il nome sempre essere qualificati con il nome dell'unione, è possibile applicare il [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attributo alla definizione del tipo di unione.</span><span class="sxs-lookup"><span data-stu-id="1961b-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="1961b-144">Rimozione del wrapping unioni discriminate</span><span class="sxs-lookup"><span data-stu-id="1961b-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="1961b-145">Nelle unioni discriminate di F # vengono spesso utilizzati nella modellazione di dominio per il wrapping di un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="1961b-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="1961b-146">È facile per estrarre il valore sottostante tramite anche i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="1961b-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="1961b-147">Non è necessario utilizzare un'espressione di corrispondenza per un singolo case:</span><span class="sxs-lookup"><span data-stu-id="1961b-147">You don't need to use a match expression for a single case:</span></span>
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="1961b-148">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="1961b-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="1961b-149">Unioni discriminate struct</span><span class="sxs-lookup"><span data-stu-id="1961b-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="1961b-150">A partire da F # 4.1, si può anche rappresentare unioni discriminate come struct.</span><span class="sxs-lookup"><span data-stu-id="1961b-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="1961b-151">Questa operazione viene eseguita con il `[<Struct>]` attributo.</span><span class="sxs-lookup"><span data-stu-id="1961b-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of string
    | Case2 of int
    | Case3 of double
```

<span data-ttu-id="1961b-152">Poiché questi sono tipi di valore e tipi di riferimento non esistono aggiuntivo unioni discriminate considerazioni confrontati con riferimento:</span><span class="sxs-lookup"><span data-stu-id="1961b-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="1961b-153">Essi vengono copiati come tipi di valore e hanno una semantica di tipo valore.</span><span class="sxs-lookup"><span data-stu-id="1961b-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="1961b-154">È possibile utilizzare una definizione di tipo ricorsivo con una struttura multicase unione le unioni.</span><span class="sxs-lookup"><span data-stu-id="1961b-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="1961b-155">È necessario fornire nomi univoci di case per uno struct multicase unione le unioni.</span><span class="sxs-lookup"><span data-stu-id="1961b-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="1961b-156">Utilizzo di unioni discriminate anziché gerarchie di oggetti</span><span class="sxs-lookup"><span data-stu-id="1961b-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>
<span data-ttu-id="1961b-157">È spesso possibile utilizzare un'unione discriminata come un'alternativa più semplice per una gerarchia di oggetti piccoli.</span><span class="sxs-lookup"><span data-stu-id="1961b-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="1961b-158">Ad esempio, è Impossibile utilizzare unione discriminata seguente invece di un `Shape` classe base che dispone di tipi derivati per cerchi, quadrati, e così via.</span><span class="sxs-lookup"><span data-stu-id="1961b-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="1961b-159">Invece di un metodo virtuale per calcolare un'area o perimetrale, come si utilizzerebbe in un'implementazione orientata agli oggetti, è possibile utilizzare criteri di ricerca di diramazione formule appropriate per calcolare le quantità.</span><span class="sxs-lookup"><span data-stu-id="1961b-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="1961b-160">Nell'esempio seguente, formule diverse vengono utilizzate per calcolare l'area, a seconda della forma.</span><span class="sxs-lookup"><span data-stu-id="1961b-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="1961b-161">L'output è indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1961b-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="1961b-162">Utilizzo di unioni discriminate per strutture di dati</span><span class="sxs-lookup"><span data-stu-id="1961b-162">Using Discriminated Unions for Tree Data Structures</span></span>
<span data-ttu-id="1961b-163">Unioni discriminate possono essere ricorsivo, vale a dire che l'unione stessa può essere incluso nel tipo di uno o più case.</span><span class="sxs-lookup"><span data-stu-id="1961b-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="1961b-164">Ricorsivo unioni discriminate possono essere utilizzate per creare strutture ad albero, che vengono usati per modellare espressioni nei linguaggi di programmazione.</span><span class="sxs-lookup"><span data-stu-id="1961b-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="1961b-165">Nel codice seguente, discriminata ricorsiva unione viene utilizzata per creare una struttura di dati della struttura ad albero binaria.</span><span class="sxs-lookup"><span data-stu-id="1961b-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="1961b-166">L'unione è costituito da due casi, `Node`, che è un nodo con un valore integer e sottoalberi destro e sinistro, e `Tip`, che termina l'albero.</span><span class="sxs-lookup"><span data-stu-id="1961b-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="1961b-167">Nel codice precedente, `resultSumTree` ha valore 10.</span><span class="sxs-lookup"><span data-stu-id="1961b-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="1961b-168">La figura seguente mostra la struttura ad albero `myTree`.</span><span class="sxs-lookup"><span data-stu-id="1961b-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Struttura ad albero per myTree](../media/TreeStructureDiagram.png)

<span data-ttu-id="1961b-170">Le unioni discriminate anche se i nodi nell'albero sono eterogenei.</span><span class="sxs-lookup"><span data-stu-id="1961b-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="1961b-171">Nel codice seguente, il tipo `Expression` rappresenta l'albero sintattico astratto di un'espressione in un semplice linguaggio di programmazione che supporta l'addizione e moltiplicazione di numeri e variabili.</span><span class="sxs-lookup"><span data-stu-id="1961b-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="1961b-172">Alcuni dei case di unione non sono ricorsivi e rappresentano numeri (`Number`) o variabili (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="1961b-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="1961b-173">Gli altri casi sono ricorsivi e rappresentano operazioni (`Add` e `Multiply`), in cui gli operandi sono anche le espressioni.</span><span class="sxs-lookup"><span data-stu-id="1961b-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="1961b-174">Il `Evaluate` funzione viene utilizzata un'espressione di corrispondenza per elaborare in modo ricorsivo l'albero della sintassi.</span><span class="sxs-lookup"><span data-stu-id="1961b-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="1961b-175">Quando viene eseguito questo codice, il valore di `result` è 5.</span><span class="sxs-lookup"><span data-stu-id="1961b-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="1961b-176">Attributi comuni</span><span class="sxs-lookup"><span data-stu-id="1961b-176">Common Attributes</span></span>

<span data-ttu-id="1961b-177">Gli attributi seguenti sono presente comunemente nelle unioni discriminate:</span><span class="sxs-lookup"><span data-stu-id="1961b-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* <span data-ttu-id="1961b-178">`[Struct]`(F # 4.1 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="1961b-178">`[Struct]` (F# 4.1 and higher)</span></span>

## <a name="see-also"></a><span data-ttu-id="1961b-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1961b-179">See Also</span></span>
[<span data-ttu-id="1961b-180">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="1961b-180">F# Language Reference</span></span>](index.md)