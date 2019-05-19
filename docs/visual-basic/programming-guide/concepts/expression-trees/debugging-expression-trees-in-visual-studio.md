---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879827"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="394a5-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="394a5-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="394a5-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="394a5-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="394a5-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать `DebugView` свойства, которое представляет деревья выражений, используя специальный синтаксис, описанный [ниже](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="394a5-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="394a5-105">(Обратите внимание, что `DebugView` доступна только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="394a5-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView дерева выражения в отладчике Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="394a5-107">Так как `DebugView` представляет собой строку, можно использовать [встроенные визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) на его просмотр по нескольким строкам, выбрав **визуализатор текста** щелкните значок лупы рядом с полем `DebugView` Метка.</span><span class="sxs-lookup"><span data-stu-id="394a5-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Применяется к результаты «DebugView» средство визуализации текста](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="394a5-109">Кроме того, можно установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений:</span><span class="sxs-lookup"><span data-stu-id="394a5-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="394a5-110">[Для чтения выражения](https://github.com/agileobjects/ReadableExpressions) ([лицензии MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступный по адресу [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображает дерево выражения в виде C# кода:</span><span class="sxs-lookup"><span data-stu-id="394a5-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Для чтения выражения визуализатора](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="394a5-112">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензии MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), который обеспечивает графическое представление дерева выражения, его свойства и связанные объекты; и может преобразовать дерево выражения, с помощью кода Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="394a5-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Визуализатор ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="394a5-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="394a5-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="394a5-115">Щелкните значок лупы рядом с дерева выражения в **подсказок по данным**, **Watch** окне **"Видимые"** окна, или **"Локальные"** окна.</span><span class="sxs-lookup"><span data-stu-id="394a5-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="394a5-116">Отображается список доступных визуализаторы.:</span><span class="sxs-lookup"><span data-stu-id="394a5-116">A list of available visualizers is displayed.:</span></span> 

      ![Открытие визуализаторы из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="394a5-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="394a5-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="394a5-119">`DebugView` Синтаксис</span><span class="sxs-lookup"><span data-stu-id="394a5-119">`DebugView` syntax</span></span> 

<span data-ttu-id="394a5-120">Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="394a5-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="394a5-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="394a5-121">ParameterExpressions</span></span>

<span data-ttu-id="394a5-122">В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".</span><span class="sxs-lookup"><span data-stu-id="394a5-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="394a5-123">Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="394a5-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="394a5-125">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="394a5-126">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="394a5-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="394a5-127">ConstantExpressions</span></span>
 <span data-ttu-id="394a5-128">Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.</span><span class="sxs-lookup"><span data-stu-id="394a5-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="394a5-130">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-130">`DebugView` property</span></span>

    <span data-ttu-id="394a5-131">10</span><span class="sxs-lookup"><span data-stu-id="394a5-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="394a5-132">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-132">`DebugView` property</span></span>

    <span data-ttu-id="394a5-133">10D</span><span class="sxs-lookup"><span data-stu-id="394a5-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="394a5-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="394a5-134">BlockExpression</span></span>

<span data-ttu-id="394a5-135">Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >).</span><span class="sxs-lookup"><span data-stu-id="394a5-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="394a5-136">В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.</span><span class="sxs-lookup"><span data-stu-id="394a5-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-137">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="394a5-138">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="394a5-139">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="394a5-140">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="394a5-140">LambdaExpression</span></span>

<span data-ttu-id="394a5-141">Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="394a5-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="394a5-142">Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="394a5-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="394a5-144">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="394a5-145">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="394a5-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="394a5-146">LabelExpression</span></span>

<span data-ttu-id="394a5-147">Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="394a5-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="394a5-148">Маркер `.Label` указывает начало метки.</span><span class="sxs-lookup"><span data-stu-id="394a5-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="394a5-149">Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="394a5-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="394a5-150">Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="394a5-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-151">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="394a5-152">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-152">`DebugView` property</span></span>

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

    <span data-ttu-id="394a5-153">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="394a5-154">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="394a5-154">Checked Operators</span></span>

<span data-ttu-id="394a5-155">Проверяемые операторы отображаются с символом # перед оператором.</span><span class="sxs-lookup"><span data-stu-id="394a5-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="394a5-156">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="394a5-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="394a5-157">Примеры</span><span class="sxs-lookup"><span data-stu-id="394a5-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="394a5-158">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="394a5-159">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="394a5-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="394a5-160">См. также</span><span class="sxs-lookup"><span data-stu-id="394a5-160">See also</span></span>

- <span data-ttu-id="394a5-161">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="394a5-161">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="394a5-162">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="394a5-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="394a5-163">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="394a5-163">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
