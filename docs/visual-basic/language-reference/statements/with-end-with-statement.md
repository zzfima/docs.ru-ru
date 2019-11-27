---
title: Оператор With…End With
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: eb8790d0d8f82232a4b10e4e0e30165745c065c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352738"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="72ccd-102">Оператор With... End With (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72ccd-102">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="72ccd-103">Выполняет последовательность операторов, которые многократно ссылаются на единственный объект или структуру, чтобы операторы могли использовать упрощенный синтаксис доступ к членам объекта или структуры.</span><span class="sxs-lookup"><span data-stu-id="72ccd-103">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="72ccd-104">При использовании структуры можно только считывать значения членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="72ccd-104">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="72ccd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72ccd-105">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="72ccd-106">Части</span><span class="sxs-lookup"><span data-stu-id="72ccd-106">Parts</span></span>

|<span data-ttu-id="72ccd-107">Термин</span><span class="sxs-lookup"><span data-stu-id="72ccd-107">Term</span></span>|<span data-ttu-id="72ccd-108">Определение</span><span class="sxs-lookup"><span data-stu-id="72ccd-108">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="72ccd-109">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="72ccd-109">Required.</span></span> <span data-ttu-id="72ccd-110">Выражение, результатом которого является объект.</span><span class="sxs-lookup"><span data-stu-id="72ccd-110">An expression that evaluates to an object.</span></span> <span data-ttu-id="72ccd-111">Выражение может быть произвольно сложным и вычисляется только один раз.</span><span class="sxs-lookup"><span data-stu-id="72ccd-111">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="72ccd-112">Результатом выражения могут быть данные любого типа, включая простейшие типы.</span><span class="sxs-lookup"><span data-stu-id="72ccd-112">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="72ccd-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="72ccd-113">Optional.</span></span> <span data-ttu-id="72ccd-114">Один или несколько операторов между `With` и `End With`, которые могут ссылаться на члены объекта, создаваемого при вычислении выражения `objectExpression`.</span><span class="sxs-lookup"><span data-stu-id="72ccd-114">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="72ccd-115">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="72ccd-115">Required.</span></span> <span data-ttu-id="72ccd-116">Завершает определение блока `With`.</span><span class="sxs-lookup"><span data-stu-id="72ccd-116">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72ccd-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="72ccd-117">Remarks</span></span>

<span data-ttu-id="72ccd-118">С помощью `With...End With` можно выполнять последовательность операторов с указанным объектом без необходимости многократного указания имени объекта.</span><span class="sxs-lookup"><span data-stu-id="72ccd-118">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="72ccd-119">В блоке операторов `With` члены объекта можно указывать начиная с точки, как если бы перед ней стоял объект оператора `With`.</span><span class="sxs-lookup"><span data-stu-id="72ccd-119">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="72ccd-120">Например, чтобы изменить несколько свойств одного объекта, поместите операторы присваивания свойств внутрь блока `With...End With` и укажите объект лишь один раз, а не по одному разу для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="72ccd-120">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="72ccd-121">Если код обращается к одному и тому же объекту в нескольких операторах, оператор `With` обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="72ccd-121">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="72ccd-122">Не требуется многократно вычислять сложное выражение или присваивать результат временной переменной, чтобы несколько раз сослаться на членов объекта.</span><span class="sxs-lookup"><span data-stu-id="72ccd-122">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="72ccd-123">За счет исключения повторяющихся определяющих выражений код становится более понятным.</span><span class="sxs-lookup"><span data-stu-id="72ccd-123">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="72ccd-124">Тип данных у `objectExpression` может быть любым типом класса или структуры или даже простейшим типом Visual Basic (например `Integer`).</span><span class="sxs-lookup"><span data-stu-id="72ccd-124">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="72ccd-125">При результат вычисления выражения `objectExpression` не является объектом, можно только считывать значения его членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="72ccd-125">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="72ccd-126">Это та же самая ошибка, которая возникает, если сразу после вызова метода, возвращающего структуру, попытаться обратиться к члену результата функции и присвоить ему значение, например `GetAPoint().x = 1`.</span><span class="sxs-lookup"><span data-stu-id="72ccd-126">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="72ccd-127">Проблема в обоих случаях заключается в том, что структура существует только в стеке вызовов — в таких ситуациях не существует способа записи измененного члена структуры в некоторое расположение таким образом, чтобы весь остальной код программы мог видеть это изменение.</span><span class="sxs-lookup"><span data-stu-id="72ccd-127">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="72ccd-128">Выражение `objectExpression` вычисляется один раз при входе в блок.</span><span class="sxs-lookup"><span data-stu-id="72ccd-128">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="72ccd-129">Переназначение выражения `objectExpression` изнутри блока `With` невозможно.</span><span class="sxs-lookup"><span data-stu-id="72ccd-129">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="72ccd-130">Внутри блока `With` к методам и свойствам только указанного объекта можно обращаться без их полного описания.</span><span class="sxs-lookup"><span data-stu-id="72ccd-130">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="72ccd-131">Можно использовать методы и свойства других объектов, однако необходимо полностью указывать их имена.</span><span class="sxs-lookup"><span data-stu-id="72ccd-131">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="72ccd-132">Оператор `With...End With` можно разместить внутри другого такого оператора.</span><span class="sxs-lookup"><span data-stu-id="72ccd-132">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="72ccd-133">Вложенные операторы `With...End With` могут быть сложны для понимания, если указываемые объекты не очевидны из контекста.</span><span class="sxs-lookup"><span data-stu-id="72ccd-133">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="72ccd-134">Необходимо указывать полную ссылку на объект, находящийся во внешнем блоке `With`, при ссылке на него из внутреннего блока `With`.</span><span class="sxs-lookup"><span data-stu-id="72ccd-134">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="72ccd-135">Переходы внутрь блока операторов `With` из другой части программы запрещены.</span><span class="sxs-lookup"><span data-stu-id="72ccd-135">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="72ccd-136">Если блок не содержит цикла, операторы выполняются только один раз.</span><span class="sxs-lookup"><span data-stu-id="72ccd-136">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="72ccd-137">Возможно вложение структур управления различных типов.</span><span class="sxs-lookup"><span data-stu-id="72ccd-137">You can nest different kinds of control structures.</span></span> <span data-ttu-id="72ccd-138">Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="72ccd-138">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="72ccd-139">Ключевое слово `With` можно также использовать в инициализаторах объектов.</span><span class="sxs-lookup"><span data-stu-id="72ccd-139">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="72ccd-140">Дополнительные сведения и примеры см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="72ccd-140">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="72ccd-141">Если блок `With` используется исключительно для инициализации свойств или полей только что созданного экземпляра объекта, рекомендуется использовать для этой цели инициализатор объекта.</span><span class="sxs-lookup"><span data-stu-id="72ccd-141">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="72ccd-142">Пример</span><span class="sxs-lookup"><span data-stu-id="72ccd-142">Example</span></span>

<span data-ttu-id="72ccd-143">В следующем примере в каждом блоке `With` выполняется несколько операторов для одного объекта.</span><span class="sxs-lookup"><span data-stu-id="72ccd-143">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="72ccd-144">Пример</span><span class="sxs-lookup"><span data-stu-id="72ccd-144">Example</span></span>

<span data-ttu-id="72ccd-145">В следующем примере показаны вложенные операторы `With…End With`:</span><span class="sxs-lookup"><span data-stu-id="72ccd-145">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="72ccd-146">Во вложенном операторе `With` этот синтаксис относится к внутреннему объекту.</span><span class="sxs-lookup"><span data-stu-id="72ccd-146">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="72ccd-147">См. также</span><span class="sxs-lookup"><span data-stu-id="72ccd-147">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="72ccd-148">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="72ccd-148">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="72ccd-149">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="72ccd-149">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="72ccd-150">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="72ccd-150">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
