---
title: "Отладка деревьев выражений в Visual Studio (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d74df8ba339526e20850cd8b8f1a4b37c20e22ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="dad25-102">Отладка деревьев выражений в Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="dad25-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="dad25-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="dad25-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="dad25-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое доступно только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="dad25-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="dad25-105">Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="dad25-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="dad25-106">Для оптимизации представления содержимого деревьев выражений свойство `DebugView` использует визуализаторы Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dad25-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="dad25-107">Дополнительные сведения см. в статье, посвященной [созданию пользовательских визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="dad25-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="dad25-108">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="dad25-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="dad25-109">Щелкните значок лупы рядом с именем свойства `DebugView` дерева выражения в окне **Советы**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="dad25-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="dad25-110">Откроется список визуализаторов.</span><span class="sxs-lookup"><span data-stu-id="dad25-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="dad25-111">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="dad25-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="dad25-112">Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="dad25-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="dad25-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="dad25-113">ParameterExpressions</span></span>  
 <span data-ttu-id="dad25-114">В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".</span><span class="sxs-lookup"><span data-stu-id="dad25-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="dad25-115">Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="dad25-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dad25-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-116">Examples</span></span>  
  
|<span data-ttu-id="dad25-117">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-117">Expression</span></span>|<span data-ttu-id="dad25-118">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="dad25-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="dad25-119">ConstantExpressions</span></span>  
 <span data-ttu-id="dad25-120">Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.</span><span class="sxs-lookup"><span data-stu-id="dad25-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="dad25-121">Для числовых типов, имеющих стандартные суффиксы, такие как литералы C#, суффикс добавляется к значению.</span><span class="sxs-lookup"><span data-stu-id="dad25-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="dad25-122">В следующей таблице показаны суффиксы для различных числовых типов.</span><span class="sxs-lookup"><span data-stu-id="dad25-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="dad25-123">Тип</span><span class="sxs-lookup"><span data-stu-id="dad25-123">Type</span></span>|<span data-ttu-id="dad25-124">Суффикс</span><span class="sxs-lookup"><span data-stu-id="dad25-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="dad25-125">U</span><span class="sxs-lookup"><span data-stu-id="dad25-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="dad25-126">L</span><span class="sxs-lookup"><span data-stu-id="dad25-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="dad25-127">UL</span><span class="sxs-lookup"><span data-stu-id="dad25-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="dad25-128">D</span><span class="sxs-lookup"><span data-stu-id="dad25-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="dad25-129">C</span><span class="sxs-lookup"><span data-stu-id="dad25-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="dad25-130">M</span><span class="sxs-lookup"><span data-stu-id="dad25-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="dad25-131">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-131">Examples</span></span>  
  
|<span data-ttu-id="dad25-132">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-132">Expression</span></span>|<span data-ttu-id="dad25-133">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="dad25-134">10</span><span class="sxs-lookup"><span data-stu-id="dad25-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="dad25-135">10D</span><span class="sxs-lookup"><span data-stu-id="dad25-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="dad25-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="dad25-136">BlockExpression</span></span>  
 <span data-ttu-id="dad25-137">Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >).</span><span class="sxs-lookup"><span data-stu-id="dad25-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="dad25-138">В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.</span><span class="sxs-lookup"><span data-stu-id="dad25-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dad25-139">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-139">Examples</span></span>  
  
|<span data-ttu-id="dad25-140">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-140">Expression</span></span>|<span data-ttu-id="dad25-141">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="dad25-142">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="dad25-142">LambdaExpression</span></span>  
 <span data-ttu-id="dad25-143">Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="dad25-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="dad25-144">Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="dad25-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dad25-145">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-145">Examples</span></span>  
  
|<span data-ttu-id="dad25-146">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-146">Expression</span></span>|<span data-ttu-id="dad25-147">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="dad25-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="dad25-148">LabelExpression</span></span>  
 <span data-ttu-id="dad25-149">Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="dad25-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="dad25-150">Маркер `.Label` указывает начало метки.</span><span class="sxs-lookup"><span data-stu-id="dad25-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="dad25-151">Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="dad25-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="dad25-152">Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="dad25-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dad25-153">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-153">Examples</span></span>  
  
|<span data-ttu-id="dad25-154">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-154">Expression</span></span>|<span data-ttu-id="dad25-155">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="dad25-156">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="dad25-156">Checked Operators</span></span>  
 <span data-ttu-id="dad25-157">Проверяемые операторы отображаются с символом # перед оператором.</span><span class="sxs-lookup"><span data-stu-id="dad25-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="dad25-158">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="dad25-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dad25-159">Примеры</span><span class="sxs-lookup"><span data-stu-id="dad25-159">Examples</span></span>  
  
|<span data-ttu-id="dad25-160">Выражение</span><span class="sxs-lookup"><span data-stu-id="dad25-160">Expression</span></span>|<span data-ttu-id="dad25-161">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="dad25-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="dad25-162">См. также</span><span class="sxs-lookup"><span data-stu-id="dad25-162">See Also</span></span>  
 <span data-ttu-id="dad25-163">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (C#))</span><span class="sxs-lookup"><span data-stu-id="dad25-163">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)</span></span>  
 [<span data-ttu-id="dad25-164">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dad25-164">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="dad25-165">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="dad25-165">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
