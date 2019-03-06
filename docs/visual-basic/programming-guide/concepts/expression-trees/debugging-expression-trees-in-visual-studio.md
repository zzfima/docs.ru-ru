---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: fb5905c3c1124dd64371216bddda0a17235abdce
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364727"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="9122c-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9122c-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="9122c-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="9122c-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="9122c-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое доступно только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="9122c-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="9122c-105">Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9122c-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>

<span data-ttu-id="9122c-106">Для оптимизации представления содержимого деревьев выражений свойство `DebugView` использует визуализаторы Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9122c-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="9122c-107">Дополнительные сведения см. в статье, посвященной [созданию пользовательских визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="9122c-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="9122c-108">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="9122c-108">To open a visualizer for an expression tree</span></span>

1. <span data-ttu-id="9122c-109">Щелкните значок лупы рядом с именем свойства `DebugView` дерева выражения в окне **Советы**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="9122c-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>

    <span data-ttu-id="9122c-110">Откроется список визуализаторов.</span><span class="sxs-lookup"><span data-stu-id="9122c-110">A list of visualizers is displayed.</span></span>

2. <span data-ttu-id="9122c-111">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="9122c-111">Click the visualizer you want to use.</span></span>

<span data-ttu-id="9122c-112">Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="9122c-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="9122c-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="9122c-113">ParameterExpressions</span></span>

<span data-ttu-id="9122c-114">В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".</span><span class="sxs-lookup"><span data-stu-id="9122c-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="9122c-115">Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="9122c-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-116">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="9122c-117">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-117">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="9122c-118">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-118">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="9122c-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="9122c-119">ConstantExpressions</span></span>
 <span data-ttu-id="9122c-120">Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.</span><span class="sxs-lookup"><span data-stu-id="9122c-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-121">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="9122c-122">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-122">`DebugView` property</span></span>

    <span data-ttu-id="9122c-123">10</span><span class="sxs-lookup"><span data-stu-id="9122c-123">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="9122c-124">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-124">`DebugView` property</span></span>

    <span data-ttu-id="9122c-125">10D</span><span class="sxs-lookup"><span data-stu-id="9122c-125">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="9122c-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="9122c-126">BlockExpression</span></span>

<span data-ttu-id="9122c-127">Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >).</span><span class="sxs-lookup"><span data-stu-id="9122c-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="9122c-128">В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.</span><span class="sxs-lookup"><span data-stu-id="9122c-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-129">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="9122c-130">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-130">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="9122c-131">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-131">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="9122c-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="9122c-132">LambdaExpression</span></span>

<span data-ttu-id="9122c-133">Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="9122c-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="9122c-134">Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="9122c-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-135">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="9122c-136">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-136">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="9122c-137">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-137">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="9122c-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="9122c-138">LabelExpression</span></span>

<span data-ttu-id="9122c-139">Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="9122c-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="9122c-140">Маркер `.Label` указывает начало метки.</span><span class="sxs-lookup"><span data-stu-id="9122c-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="9122c-141">Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="9122c-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="9122c-142">Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="9122c-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-143">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="9122c-144">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-144">`DebugView` property</span></span>

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    <span data-ttu-id="9122c-145">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-145">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="9122c-146">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="9122c-146">Checked Operators</span></span>

<span data-ttu-id="9122c-147">Проверяемые операторы отображаются с символом # перед оператором.</span><span class="sxs-lookup"><span data-stu-id="9122c-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="9122c-148">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="9122c-148">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="9122c-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="9122c-149">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="9122c-150">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-150">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="9122c-151">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="9122c-151">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="9122c-152">См. также</span><span class="sxs-lookup"><span data-stu-id="9122c-152">See also</span></span>

- <span data-ttu-id="9122c-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="9122c-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="9122c-154">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9122c-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="9122c-155">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="9122c-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
