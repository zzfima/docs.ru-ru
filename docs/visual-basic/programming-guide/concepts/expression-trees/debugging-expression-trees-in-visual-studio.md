---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 2addba2654067eaaf6c621c927e0992308879ae4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="0b32e-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b32e-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="0b32e-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="0b32e-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="0b32e-104">Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое доступно только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="0b32e-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="0b32e-105">Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="0b32e-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="0b32e-106">Для оптимизации представления содержимого деревьев выражений свойство `DebugView` использует визуализаторы Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b32e-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="0b32e-107">Дополнительные сведения см. в статье, посвященной [созданию пользовательских визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="0b32e-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="0b32e-108">Открытие визуализатора дерева выражения</span><span class="sxs-lookup"><span data-stu-id="0b32e-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="0b32e-109">Щелкните значок лупы рядом с именем свойства `DebugView` дерева выражения в окне **Советы**, **Контрольные значения**, **Видимые** или **Локальные**.</span><span class="sxs-lookup"><span data-stu-id="0b32e-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="0b32e-110">Откроется список визуализаторов.</span><span class="sxs-lookup"><span data-stu-id="0b32e-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="0b32e-111">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="0b32e-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="0b32e-112">Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="0b32e-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="0b32e-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="0b32e-113">ParameterExpressions</span></span>  
 <span data-ttu-id="0b32e-114">В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".</span><span class="sxs-lookup"><span data-stu-id="0b32e-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="0b32e-115">Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="0b32e-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="0b32e-117">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="0b32e-118">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="0b32e-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="0b32e-119">ConstantExpressions</span></span>  
 <span data-ttu-id="0b32e-120">Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.</span><span class="sxs-lookup"><span data-stu-id="0b32e-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="0b32e-122">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="0b32e-123">10</span><span class="sxs-lookup"><span data-stu-id="0b32e-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="0b32e-124">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="0b32e-125">10D</span><span class="sxs-lookup"><span data-stu-id="0b32e-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="0b32e-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="0b32e-126">BlockExpression</span></span>  
 <span data-ttu-id="0b32e-127">Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >).</span><span class="sxs-lookup"><span data-stu-id="0b32e-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="0b32e-128">В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.</span><span class="sxs-lookup"><span data-stu-id="0b32e-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="0b32e-130">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="0b32e-131">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="0b32e-132">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="0b32e-132">LambdaExpression</span></span>  
 <span data-ttu-id="0b32e-133">Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="0b32e-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="0b32e-134">Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="0b32e-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="0b32e-136">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="0b32e-137">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="0b32e-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="0b32e-138">LabelExpression</span></span>  
 <span data-ttu-id="0b32e-139">Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="0b32e-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="0b32e-140">Маркер `.Label` указывает начало метки.</span><span class="sxs-lookup"><span data-stu-id="0b32e-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="0b32e-141">Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="0b32e-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="0b32e-142">Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="0b32e-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="0b32e-144">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-144">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     <span data-ttu-id="0b32e-145">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="0b32e-146">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="0b32e-146">Checked Operators</span></span>  
 <span data-ttu-id="0b32e-147">Проверяемые операторы отображаются с символом # перед оператором.</span><span class="sxs-lookup"><span data-stu-id="0b32e-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="0b32e-148">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="0b32e-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0b32e-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="0b32e-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="0b32e-150">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="0b32e-151">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="0b32e-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="0b32e-152">См. также</span><span class="sxs-lookup"><span data-stu-id="0b32e-152">See Also</span></span>  
 <span data-ttu-id="0b32e-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0b32e-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>  
 [<span data-ttu-id="0b32e-154">Отладка в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0b32e-154">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)  
 [<span data-ttu-id="0b32e-155">Создание настраиваемых визуализаторов</span><span class="sxs-lookup"><span data-stu-id="0b32e-155">Create Custom Visualizers</span></span>](/visualstudio/debugger/create-custom-visualizers-of-data)
