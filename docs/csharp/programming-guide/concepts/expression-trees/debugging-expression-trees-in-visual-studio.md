---
title: Отладка деревьев выражений в Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877173"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="2ab26-102">Отладка деревьев выражений в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="2ab26-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="2ab26-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="2ab26-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="2ab26-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое представляет деревья выражений, используя специальный синтаксис, описанный [ниже](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="2ab26-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="2ab26-105">(Обратите внимание, что `DebugView` доступен только в режиме отладки.)</span><span class="sxs-lookup"><span data-stu-id="2ab26-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView дерева выражения в отладчике Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="2ab26-107">Так как `DebugView` представляет собой строку, можно использовать [встроенный визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) для его просмотра по нескольким строкам, выбрав **визуализатор текста** из меню со значком лупы рядом с меткой `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="2ab26-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Визуализатор текста применяется к результатам DebugView](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="2ab26-109">Или вы можете установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений:</span><span class="sxs-lookup"><span data-stu-id="2ab26-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="2ab26-110">[Выражения для чтения](https://github.com/agileobjects/ReadableExpressions) ([лицензия MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступная в [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображают дерево выражения в виде кода C#:</span><span class="sxs-lookup"><span data-stu-id="2ab26-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Визуализатор выражений для чтения](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="2ab26-112">[Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензия MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) предоставляет графическое представление дерева выражения, его свойства и связанные объекты:</span><span class="sxs-lookup"><span data-stu-id="2ab26-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![Визуализатор ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="2ab26-114">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="2ab26-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="2ab26-115">Щелкните значок лупы рядом с деревом выражения в окне **Подсказки по данным**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="2ab26-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="2ab26-116">Отображается список доступных визуализаторов:</span><span class="sxs-lookup"><span data-stu-id="2ab26-116">A list of available visualizers is displayed.:</span></span> 

      ![Открытие визуализаторов из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="2ab26-118">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="2ab26-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="2ab26-119">Синтаксис `DebugView`</span><span class="sxs-lookup"><span data-stu-id="2ab26-119">`DebugView` syntax</span></span> 

<span data-ttu-id="2ab26-120">Каждый тип выражения отображается по свойству `DebugView`, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="2ab26-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="2ab26-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="2ab26-121">ParameterExpressions</span></span>  
 <span data-ttu-id="2ab26-122">В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".</span><span class="sxs-lookup"><span data-stu-id="2ab26-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="2ab26-123">Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="2ab26-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="2ab26-124">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-124">Examples</span></span>  
  
|<span data-ttu-id="2ab26-125">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-125">Expression</span></span>|<span data-ttu-id="2ab26-126">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="2ab26-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="2ab26-127">ConstantExpressions</span></span>  
 <span data-ttu-id="2ab26-128">Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.</span><span class="sxs-lookup"><span data-stu-id="2ab26-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="2ab26-129">Для числовых типов, имеющих стандартные суффиксы, такие как литералы C#, суффикс добавляется к значению.</span><span class="sxs-lookup"><span data-stu-id="2ab26-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="2ab26-130">В следующей таблице показаны суффиксы для различных числовых типов.</span><span class="sxs-lookup"><span data-stu-id="2ab26-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="2ab26-131">Тип</span><span class="sxs-lookup"><span data-stu-id="2ab26-131">Type</span></span>|<span data-ttu-id="2ab26-132">Суффикс</span><span class="sxs-lookup"><span data-stu-id="2ab26-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="2ab26-133">U</span><span class="sxs-lookup"><span data-stu-id="2ab26-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="2ab26-134">L</span><span class="sxs-lookup"><span data-stu-id="2ab26-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="2ab26-135">UL</span><span class="sxs-lookup"><span data-stu-id="2ab26-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="2ab26-136">D</span><span class="sxs-lookup"><span data-stu-id="2ab26-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="2ab26-137">C</span><span class="sxs-lookup"><span data-stu-id="2ab26-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="2ab26-138">M</span><span class="sxs-lookup"><span data-stu-id="2ab26-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="2ab26-139">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-139">Examples</span></span>  
  
|<span data-ttu-id="2ab26-140">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-140">Expression</span></span>|<span data-ttu-id="2ab26-141">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="2ab26-142">10</span><span class="sxs-lookup"><span data-stu-id="2ab26-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="2ab26-143">10D</span><span class="sxs-lookup"><span data-stu-id="2ab26-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="2ab26-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="2ab26-144">BlockExpression</span></span>  
 <span data-ttu-id="2ab26-145">Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >).</span><span class="sxs-lookup"><span data-stu-id="2ab26-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="2ab26-146">В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.</span><span class="sxs-lookup"><span data-stu-id="2ab26-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="2ab26-147">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-147">Examples</span></span>  
  
|<span data-ttu-id="2ab26-148">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-148">Expression</span></span>|<span data-ttu-id="2ab26-149">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="2ab26-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="2ab26-150">LambdaExpression</span></span>  
 <span data-ttu-id="2ab26-151">Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="2ab26-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="2ab26-152">Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="2ab26-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="2ab26-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-153">Examples</span></span>  
  
|<span data-ttu-id="2ab26-154">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-154">Expression</span></span>|<span data-ttu-id="2ab26-155">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="2ab26-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="2ab26-156">LabelExpression</span></span>  
 <span data-ttu-id="2ab26-157">Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="2ab26-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="2ab26-158">Маркер `.Label` указывает начало метки.</span><span class="sxs-lookup"><span data-stu-id="2ab26-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="2ab26-159">Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="2ab26-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="2ab26-160">Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="2ab26-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="2ab26-161">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-161">Examples</span></span>  
  
|<span data-ttu-id="2ab26-162">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-162">Expression</span></span>|<span data-ttu-id="2ab26-163">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="2ab26-164">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="2ab26-164">Checked Operators</span></span>  
 <span data-ttu-id="2ab26-165">Проверяемые операторы отображаются с символом # перед оператором.</span><span class="sxs-lookup"><span data-stu-id="2ab26-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="2ab26-166">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="2ab26-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="2ab26-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="2ab26-167">Examples</span></span>  
  
|<span data-ttu-id="2ab26-168">Выражение</span><span class="sxs-lookup"><span data-stu-id="2ab26-168">Expression</span></span>|<span data-ttu-id="2ab26-169">Свойство`DebugView` </span><span class="sxs-lookup"><span data-stu-id="2ab26-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="2ab26-170">См. также</span><span class="sxs-lookup"><span data-stu-id="2ab26-170">See also</span></span>

- <span data-ttu-id="2ab26-171">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (C#))</span><span class="sxs-lookup"><span data-stu-id="2ab26-171">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)</span></span>
- [<span data-ttu-id="2ab26-172">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2ab26-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- [<span data-ttu-id="2ab26-173">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="2ab26-173">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
