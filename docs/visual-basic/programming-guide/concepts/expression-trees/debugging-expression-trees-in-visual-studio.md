---
title: "Отладка деревьев выражений в Visual Studio (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84de749afad6abb748d0622561f8ee7cd399ed54
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="a9ae3-102">Отладка деревьев выражений в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9ae3-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="a9ae3-103">При отладке приложений можно анализировать структуру и содержимое деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="a9ae3-104">Чтобы получить краткий обзор структуру дерева выражений, можно использовать `DebugView` свойства, которое доступно только в режиме отладки.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="a9ae3-105">Дополнительные сведения об отладке см. в разделе [отладки в Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a9ae3-105">For more information about debugging, see [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="a9ae3-106">Для оптимизации представления содержимого деревьев выражений `DebugView` свойство использует визуализаторы Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="a9ae3-107">Дополнительные сведения см. в разделе [создать пользовательские визуализаторы](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span><span class="sxs-lookup"><span data-stu-id="a9ae3-107">For more information, see [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="a9ae3-108">Открытие визуализатора дерева выражений</span><span class="sxs-lookup"><span data-stu-id="a9ae3-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="a9ae3-109">Щелкните значок лупы рядом `DebugView` свойство дерева выражений в **подсказки**, **Контрольные значения** окна, **видимые** окна, или **локальные** окна.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="a9ae3-110">Откроется список визуализаторов.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="a9ae3-111">Щелкните визуализатор, который необходимо использовать.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="a9ae3-112">Тип каждого выражения отображается в визуализаторе, как описано в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="a9ae3-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="a9ae3-113">ParameterExpressions</span></span>  
 <span data-ttu-id="a9ae3-114"><xref:System.Linq.Expressions.ParameterExpression>имена переменных, отображаются с символом «$» в начале.</xref:System.Linq.Expressions.ParameterExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="a9ae3-115">Если параметр не имеет имени, то оно назначается автоматически, например `$var1` или `$var2`.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-116">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-116">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     <span data-ttu-id="a9ae3-117">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-117">`DebugView` property</span></span>  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     <span data-ttu-id="a9ae3-118">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-118">`DebugView` property</span></span>  
  
     `$var1`  
  
## <a name="constantexpressions"></a><span data-ttu-id="a9ae3-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="a9ae3-119">ConstantExpressions</span></span>  
 <span data-ttu-id="a9ae3-120">Для <xref:System.Linq.Expressions.ConstantExpression>объектов, представляющих целочисленные значения, строки, и `null`, отображается значение константы.</xref:System.Linq.Expressions.ConstantExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-121">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="a9ae3-122">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-122">`DebugView` property</span></span>  
  
     <span data-ttu-id="a9ae3-123">10</span><span class="sxs-lookup"><span data-stu-id="a9ae3-123">10</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     <span data-ttu-id="a9ae3-124">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-124">`DebugView` property</span></span>  
  
     <span data-ttu-id="a9ae3-125">10D</span><span class="sxs-lookup"><span data-stu-id="a9ae3-125">10D</span></span>  
  
## <a name="blockexpression"></a><span data-ttu-id="a9ae3-126">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="a9ae3-126">BlockExpression</span></span>  
 <span data-ttu-id="a9ae3-127">Если тип <xref:System.Linq.Expressions.BlockExpression>объекта отличается от типа последнего выражения в блоке, то он отображается в `DebugInfo` свойство в угловые скобки (\< и настроек).</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-127">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="a9ae3-128">В противном случае — тип <xref:System.Linq.Expressions.BlockExpression>объект не отображается.</xref:System.Linq.Expressions.BlockExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-128">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-129">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-129">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="a9ae3-130">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-130">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     <span data-ttu-id="a9ae3-131">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-131">`DebugView` property</span></span>  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a><span data-ttu-id="a9ae3-132">Лямбда-выражение</span><span class="sxs-lookup"><span data-stu-id="a9ae3-132">LambdaExpression</span></span>  
 <span data-ttu-id="a9ae3-133"><xref:System.Linq.Expressions.LambdaExpression>объекты отображаются вместе с их типами делегатов.</xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-133"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="a9ae3-134">Если лямбда-выражение не имеет имени, то оно назначается автоматически, например `#Lambda1` или `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-134">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-135">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-135">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     <span data-ttu-id="a9ae3-136">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-136">`DebugView` property</span></span>  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     <span data-ttu-id="a9ae3-137">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-137">`DebugView` property</span></span>  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a><span data-ttu-id="a9ae3-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="a9ae3-138">LabelExpression</span></span>  
 <span data-ttu-id="a9ae3-139">Если указать значение по умолчанию для <xref:System.Linq.Expressions.LabelExpression>объекта, то оно будет отображаться перед <xref:System.Linq.Expressions.LabelTarget>объекта.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression></span><span class="sxs-lookup"><span data-stu-id="a9ae3-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="a9ae3-140">`.Label` Маркер указывает на начало метки.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="a9ae3-141">`.LabelTarget` Маркера задает конечную цель перехода для целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="a9ae3-142">Если подпись не имеет имени, то оно назначается автоматически, например `#Label1` или `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-143">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-143">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     <span data-ttu-id="a9ae3-144">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-144">`DebugView` property</span></span>  
  
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
  
     <span data-ttu-id="a9ae3-145">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-145">`DebugView` property</span></span>  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a><span data-ttu-id="a9ae3-146">Проверяемые операторы</span><span class="sxs-lookup"><span data-stu-id="a9ae3-146">Checked Operators</span></span>  
 <span data-ttu-id="a9ae3-147">Проверяемые операторы отображаются с символом «#» перед оператором.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-147">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="a9ae3-148">Например, проверяемый оператор сложения отображается как `#+`.</span><span class="sxs-lookup"><span data-stu-id="a9ae3-148">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a9ae3-149">Примеры</span><span class="sxs-lookup"><span data-stu-id="a9ae3-149">Examples</span></span>  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     <span data-ttu-id="a9ae3-150">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-150">`DebugView` property</span></span>  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     <span data-ttu-id="a9ae3-151">Свойство `DebugView`</span><span class="sxs-lookup"><span data-stu-id="a9ae3-151">`DebugView` property</span></span>  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a><span data-ttu-id="a9ae3-152">См. также</span><span class="sxs-lookup"><span data-stu-id="a9ae3-152">See Also</span></span>  
 <span data-ttu-id="a9ae3-153">[Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="a9ae3-153">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="a9ae3-154"> [Отладка в Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="a9ae3-154"> [Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="a9ae3-155"> [Создание пользовательских визуализаторов](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span><span class="sxs-lookup"><span data-stu-id="a9ae3-155"> [Create Custom Visualizers](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
