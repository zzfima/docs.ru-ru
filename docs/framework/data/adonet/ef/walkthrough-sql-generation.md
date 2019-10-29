---
title: Пошаговое руководство. Создание кода SQL
ms.date: 03/30/2017
ms.assetid: 16c38aaa-9927-4f3c-ab0f-81636cce57a3
ms.openlocfilehash: 2684acd39ae9651407023e8b5c73f02eadb97547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040503"
---
# <a name="walkthrough-sql-generation"></a><span data-ttu-id="976d1-102">Пошаговое руководство. Создание кода SQL</span><span class="sxs-lookup"><span data-stu-id="976d1-102">Walkthrough: SQL Generation</span></span>

<span data-ttu-id="976d1-103">В этом разделе показано, как в [примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)происходит создание SQL.</span><span class="sxs-lookup"><span data-stu-id="976d1-103">This topic illustrates how SQL generation occurs in the [Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0).</span></span> <span data-ttu-id="976d1-104">В следующем запросе Entity SQL используется модель, которая прилагается к образцу поставщика.</span><span class="sxs-lookup"><span data-stu-id="976d1-104">The following Entity SQL query uses the model that is included with the sample provider:</span></span>

```sql
SELECT  j1.ProductId, j1.ProductName, j1.CategoryName, j2.ShipCountry, j2.ProductId
FROM (  SELECT P.ProductName, P.ProductId, P.Category.CategoryName
        FROM NorthwindEntities.Products AS P) as j1
INNER JOIN (SELECT OD.ProductId, OD.Order.ShipCountry as ShipCountry
            FROM NorthwindEntities.OrderDetails AS OD) as j2
            ON j1.ProductId == j2.ProductId
```

<span data-ttu-id="976d1-105">Запрос формирует следующее выходное дерево команд, которое передается поставщику.</span><span class="sxs-lookup"><span data-stu-id="976d1-105">The query produces the following output command tree that is passed to the provider:</span></span>

```output
DbQueryCommandTree
|_Parameters
|_Query : Collection{Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]}
  |_Project
    |_Input : 'Join4'
    | |_InnerJoin
    |   |_Left : 'Join1'
    |   | |_LeftOuterJoin
    |   |   |_Left : 'Extent1'
    |   |   | |_Scan : dbo.Products
    |   |   |_Right : 'Extent2'
    |   |   | |_Scan : dbo.Categories
    |   |   |_JoinCondition
    |   |     |_
    |   |       |_Var(Extent1).CategoryID
    |   |       |_=
    |   |       |_Var(Extent2).CategoryID
    |   |_Right : 'Join3'
    |   | |_LeftOuterJoin
    |   |   |_Left : 'Extent3'
    |   |   | |_Scan : dbo.OrderDetails
    |   |   |_Right : 'Join2'
    |   |   | |_LeftOuterJoin
    |   |   |   |_Left : 'Extent4'
    |   |   |   | |_Scan : dbo.Orders
    |   |   |   |_Right : 'Extent5'
    |   |   |   | |_Scan : dbo.InternationalOrders
    |   |   |   |_JoinCondition
    |   |   |     |_
    |   |   |       |_Var(Extent4).OrderID
    |   |   |       |_=
    |   |   |       |_Var(Extent5).OrderID
    |   |   |_JoinCondition
    |   |     |_
    |   |       |_Var(Extent3).OrderID
    |   |       |_=
    |   |       |_Var(Join2).Extent4.OrderID
    |   |_JoinCondition
    |     |_
    |       |_Var(Join1).Extent1.ProductID
    |       |_=
    |       |_Var(Join3).Extent3.ProductID
    |_Projection
      |_NewInstance : Record['C1'=Edm.Int32, 'ProductID'=Edm.Int32, 'ProductName'=Edm.String, 'CategoryName'=Edm.String, 'ShipCountry'=Edm.String, 'ProductID1'=Edm.Int32]
        |_Column : 'C1'
        | |_1
        |_Column : 'ProductID'
        | |_Var(Join4).Join1.Extent1.ProductID
        |_Column : 'ProductName'
        | |_Var(Join4).Join1.Extent1.ProductName
        |_Column : 'CategoryName'
        | |_Var(Join4).Join1.Extent2.CategoryName
        |_Column : 'ShipCountry'
        | |_Var(Join4).Join3.Join2.Extent4.ShipCountry
        |_Column : 'ProductID1'
          |_Var(Join4).Join3.Extent3.ProductID
```

 <span data-ttu-id="976d1-106">В этом разделе описывается порядок перевода выходного дерева команд в следующие инструкции SQL.</span><span class="sxs-lookup"><span data-stu-id="976d1-106">This topic describes how to translate this output command tree into the following SQL statements.</span></span>

```sql
SELECT
1 AS [C1],
[Extent1].[ProductID] AS [ProductID],
[Extent1].[ProductName] AS [ProductName],
[Extent2].[CategoryName] AS [CategoryName],
[Join3].[ShipCountry] AS [ShipCountry],
[Join3].[ProductID] AS [ProductID1]
FROM   [dbo].[Products] AS [Extent1]
LEFT OUTER JOIN [dbo].[Categories] AS [Extent2] ON [Extent1].[CategoryID] = [Extent2].[CategoryID]
INNER JOIN
(SELECT [Extent3].[OrderID] AS [OrderID1], [Extent3].[ProductID] AS [ProductID], [Extent3].[UnitPrice] AS [UnitPrice], [Extent3].[Quantity] AS [Quantity], [Extent3].[Discount] AS [Discount], [Join2].[OrderID2], [Join2].[CustomerID], [Join2].[EmployeeID], [Join2].[OrderDate], [Join2].[RequiredDate], [Join2].[ShippedDate], [Join2].[Freight], [Join2].[ShipName], [Join2].[ShipAddress], [Join2].[ShipCity], [Join2].[ShipRegion], [Join2].[ShipPostalCode], [Join2].[ShipCountry], [Join2].[OrderID3], [Join2].[CustomsDescription], [Join2].[ExciseTax]
FROM  [dbo].[OrderDetails] AS [Extent3]
LEFT OUTER JOIN
      (SELECT [Extent4].[OrderID] AS [OrderID2], [Extent4].[CustomerID] AS [CustomerID], [Extent4].[EmployeeID] AS [EmployeeID], [Extent4].[OrderDate] AS [OrderDate], [Extent4].[RequiredDate] AS [RequiredDate], [Extent4].[ShippedDate] AS [ShippedDate], [Extent4].[Freight] AS [Freight], [Extent4].[ShipName] AS [ShipName], [Extent4].[ShipAddress] AS [ShipAddress], [Extent4].[ShipCity] AS [ShipCity], [Extent4].[ShipRegion] AS [ShipRegion], [Extent4].[ShipPostalCode] AS [ShipPostalCode], [Extent4].[ShipCountry] AS [ShipCountry], [Extent5].[OrderID] AS [OrderID3], [Extent5].[CustomsDescription] AS [CustomsDescription], [Extent5].[ExciseTax] AS [ExciseTax]
FROM  [dbo].[Orders] AS [Extent4]
LEFT OUTER JOIN [dbo].[InternationalOrders] AS [Extent5] ON [Extent4].[OrderID] = [Extent5].[OrderID]
      ) AS [Join2] ON [Extent3].[OrderID] = [Join2].[OrderID2]
   ) AS [Join3] ON [Extent1].[ProductID] = [Join3].[ProductID]
```

## <a name="first-phase-of-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="976d1-107">Первый этап формирования кода SQL: обход дерева выражений</span><span class="sxs-lookup"><span data-stu-id="976d1-107">First Phase of SQL Generation: Visiting the Expression Tree</span></span>

<span data-ttu-id="976d1-108">На следующем рисунке показано начальное пустое состояние посетителя.</span><span class="sxs-lookup"><span data-stu-id="976d1-108">The following figure illustrates the initial empty state of the visitor.</span></span>  <span data-ttu-id="976d1-109">В рамках данного раздела описываются только свойства, требуемые для наглядности пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="976d1-109">Throughout this topic, only the properties relevant to the walkthrough explanation are shown.</span></span>

<span data-ttu-id="976d1-110">![Схема](./media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span><span class="sxs-lookup"><span data-stu-id="976d1-110">![Diagram](./media/430180f5-4fb9-4bc3-8589-d566512d9703.gif "430180f5-4fb9-4bc3-8589-d566512d9703")</span></span>

<span data-ttu-id="976d1-111">При посещении узла проекта поверх ввода (Join4) вызывается метод VisitInputExpression, активизирующий посещение Join4 методом VisitJoinExpression.</span><span class="sxs-lookup"><span data-stu-id="976d1-111">When the Project  node is visited, VisitInputExpression is called over its input (Join4), which triggers the visit of Join4 by the method VisitJoinExpression.</span></span> <span data-ttu-id="976d1-112">Поскольку это самое верхнее соединение, параметр IsParentAJoin возвращает значение false, а новый объект SqlSelectStatement (SelectStatement0) создается и передается в стек инструкций SELECT.</span><span class="sxs-lookup"><span data-stu-id="976d1-112">Because this is a topmost join, IsParentAJoin returns false and a new SqlSelectStatement (SelectStatement0) is created and pushed on the SELECT statement stack.</span></span> <span data-ttu-id="976d1-113">Кроме того, в таблицу символов вводится новая область (scope0).</span><span class="sxs-lookup"><span data-stu-id="976d1-113">Also, a new scope (scope0) is entered in the symbol table.</span></span> <span data-ttu-id="976d1-114">Перед посещением первого (левого) входного сигнала соединения в стек IsParentAJoin передается значение true.</span><span class="sxs-lookup"><span data-stu-id="976d1-114">Before the first (left) input of the join is visited, 'true' is pushed on the IsParentAJoin stack.</span></span> <span data-ttu-id="976d1-115">Перед посещением Join1, левого входного сигнала Join4, посетитель входит в состояние, показанное на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="976d1-115">Right before Join1, which is the left input of Join4, is visited, the state of the visitor is as shown in the next figure.</span></span>

<span data-ttu-id="976d1-116">![Схема](./media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span><span class="sxs-lookup"><span data-stu-id="976d1-116">![Diagram](./media/406d4f5f-6166-44ea-8e74-c5001d5d5d79.gif "406d4f5f-6166-44ea-8e74-c5001d5d5d79")</span></span>

<span data-ttu-id="976d1-117">Когда метод посещения соединения вызывается по отношению к Join4, IsParentAJoin принимает значение true, таким образом, текущая инструкция выбора SelectStatement0 используется повторно.</span><span class="sxs-lookup"><span data-stu-id="976d1-117">When the join visit method is invoked over Join4, IsParentAJoin is true, thus it reuses the current select statement SelectStatement0.</span></span> <span data-ttu-id="976d1-118">Вводится новая область (scope1).</span><span class="sxs-lookup"><span data-stu-id="976d1-118">A new scope is entered (scope1).</span></span> <span data-ttu-id="976d1-119">Перед посещением левого дочернего элемента Extent1 в стек IsParentAJoin передается еще одно значение true.</span><span class="sxs-lookup"><span data-stu-id="976d1-119">Before visiting its left child, Extent1, another true is pushed on the IsParentAJoin stack.</span></span>

<span data-ttu-id="976d1-120">При посещении Extent1, поскольку IsParentAJoin возвращает значение true, он возвращает SqlBuilder, содержащий «[dbo].[Products]».</span><span class="sxs-lookup"><span data-stu-id="976d1-120">When Extent1 is visited, because IsParentAJoin returns true, it returns a SqlBuilder containing "[dbo].[Products]".</span></span> <span data-ttu-id="976d1-121">Элемент управления возвращается методу, посещающему Join4.</span><span class="sxs-lookup"><span data-stu-id="976d1-121">The control returns to the method visiting Join4.</span></span> <span data-ttu-id="976d1-122">Из IsParentAJoin удаляется запись, вызывается метод ProcessJoinInputResult, прибавляющий результат посещения Extent1 к предложению From инструкции SelectStatement0.</span><span class="sxs-lookup"><span data-stu-id="976d1-122">An entry is popped from IsParentAJoin, and ProcessJoinInputResult is called, which appends the result of visiting Extent1 to the From clause of SelectStatement0.</span></span> <span data-ttu-id="976d1-123">Создается новый символ from, symbol_Extent1, для входного сигнала. Он добавляется к FromExtents инструкции SelectStatement0, а к предложению from добавляются «As» и symbol_Extent1.</span><span class="sxs-lookup"><span data-stu-id="976d1-123">A new from symbol, symbol_Extent1, for the input binding name "Extent1" is created, added to the FromExtents of SelectStatement0, and also "As" and  symbol_Extent1 are appended to the from clause.</span></span> <span data-ttu-id="976d1-124">К AllExtentNames добавляется новая запись со значением 0 для «Extent1».</span><span class="sxs-lookup"><span data-stu-id="976d1-124">A new entry is added to AllExtentNames for "Extent1" with the value of 0.</span></span> <span data-ttu-id="976d1-125">В символьную таблицу текущей области добавляется новая запись, чтобы связать «Extent1» с его символом symbol_Extent1.</span><span class="sxs-lookup"><span data-stu-id="976d1-125">A new entry is added to the current scope in the symbol table to associate "Extent1" with its symbol symbol_Extent1.</span></span> <span data-ttu-id="976d1-126">Symbol_Extent1 также добавляется к AllJoinExtents инструкции SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="976d1-126">Symbol_Extent1 is also added to the AllJoinExtents of the SqlSelectStatement.</span></span>

<span data-ttu-id="976d1-127">Перед посещением правого входного сигнала Join1 к предложению From инструкции SelectStatement0. добавляется «LEFT OUTER JOIN».</span><span class="sxs-lookup"><span data-stu-id="976d1-127">Before the right input of Join1 is visited, "LEFT OUTER JOIN" is added to the From clause of SelectStatement0.</span></span> <span data-ttu-id="976d1-128">Поскольку правый входной сигнал является выражением Scan, в стек IsParentAJoin снова передается значение true.</span><span class="sxs-lookup"><span data-stu-id="976d1-128">Because the right input is a Scan expression, true is again pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="976d1-129">Состояние перед посещением правого входного сигнала показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="976d1-129">The state before visiting the right input as shown in the next figure.</span></span>

<span data-ttu-id="976d1-130">![Схема](./media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span><span class="sxs-lookup"><span data-stu-id="976d1-130">![Diagram](./media/ca62c31b-7ff6-4836-b209-e16166304fdc.gif "ca62c31b-7ff6-4836-b209-e16166304fdc")</span></span>

<span data-ttu-id="976d1-131">Правый входной сигнал обрабатывается так же, как и левый.</span><span class="sxs-lookup"><span data-stu-id="976d1-131">The right input is processed in the same way as the left input.</span></span> <span data-ttu-id="976d1-132">Состояние после посещения правого входного сигнала показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="976d1-132">The state after visiting the right input is shown in the next figure.</span></span>

<span data-ttu-id="976d1-133">![Схема](./media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span><span class="sxs-lookup"><span data-stu-id="976d1-133">![Diagram](./media/cd2afa99-7256-4c63-aaa9-c2d13f18a3d8.gif "cd2afa99-7256-4c63-aaa9-c2d13f18a3d8")</span></span>

<span data-ttu-id="976d1-134">Следующее значение false передается в стек IsParentAJoin, и обрабатывается условие соединения Var(Extent1).CategoryID == Var(Extent2).CategoryID.</span><span class="sxs-lookup"><span data-stu-id="976d1-134">Next "false" is pushed on the IsParentAJoin stack and the join condition Var(Extent1).CategoryID == Var(Extent2).CategoryID is processed.</span></span> <span data-ttu-id="976d1-135">Var (Extent1) разрешается в \<symbol_Extent1 > после поиска в таблице символов.</span><span class="sxs-lookup"><span data-stu-id="976d1-135">Var(Extent1) is resolved to \<symbol_Extent1> after a look up in the symbol table.</span></span> <span data-ttu-id="976d1-136">Так как экземпляр разрешается в простой символ, в результате обработки var (Extent1). КодТипа, Склбуилдер с \<symbol1 >». КодТипа».</span><span class="sxs-lookup"><span data-stu-id="976d1-136">Because the instance is resolved to a simple Symbol, as a result of processing Var(Extent1).CategoryID, a SqlBuilder with \<symbol1>."CategoryID" is returned.</span></span> <span data-ttu-id="976d1-137">Схожим образом обрабатывается другая сторона сравнения, результат посещения условия соединения добавляется к предложению FROM инструкции SelectStatement1, а из стека IsParentAJoin удаляется значение false.</span><span class="sxs-lookup"><span data-stu-id="976d1-137">Similarly the other side of the comparison is processed, and the result of visiting the join condition is appended to the FROM clause of SelectStatement1 and the value "false" is popped from the IsParentAJoin stack.</span></span>

<span data-ttu-id="976d1-138">На этом обработка Join1 завершается, а область удаляется из символьной таблицы.</span><span class="sxs-lookup"><span data-stu-id="976d1-138">With this, Join1 has completely been processed, and a scope is popped from the symbol table.</span></span>

<span data-ttu-id="976d1-139">Элемент управления возвращается к обработке Join4, родительского элемента Join1.</span><span class="sxs-lookup"><span data-stu-id="976d1-139">Control returns to processing Join4, the parent of Join1.</span></span> <span data-ttu-id="976d1-140">Так как дочерний элемент повторно использовал инструкцию SELECT, экстенты Join1 заменяются одним символом объединения \<joinSymbol_Join1 >.</span><span class="sxs-lookup"><span data-stu-id="976d1-140">Because the child reused the Select statement, the Join1 extents are replaced with a single Join symbol \<joinSymbol_Join1>.</span></span> <span data-ttu-id="976d1-141">Кроме того, в таблицу символов добавляется новая запись для связывания Join1 с >ом \<joinSymbol_Join1.</span><span class="sxs-lookup"><span data-stu-id="976d1-141">Also a new entry is added to the symbol table to associate Join1 with \<joinSymbol_Join1>.</span></span>

<span data-ttu-id="976d1-142">Следующим обрабатывается узел Join3 - второй дочерний элемент Join4.</span><span class="sxs-lookup"><span data-stu-id="976d1-142">The next node to be processed is Join3, the second child of Join4.</span></span> <span data-ttu-id="976d1-143">Поскольку он правый, в стек IsParentAJoin передается значение false.</span><span class="sxs-lookup"><span data-stu-id="976d1-143">As it is a right child, "false" is pushed to the IsParentAJoin stack.</span></span> <span data-ttu-id="976d1-144">Состояние посетителя в этот момент показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="976d1-144">The state of the visitor at this point is illustrated in the next figure.</span></span>

<span data-ttu-id="976d1-145">![Схема](./media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span><span class="sxs-lookup"><span data-stu-id="976d1-145">![Diagram](./media/1ec61ed3-fcdd-4649-9089-24385be7e423.gif "1ec61ed3-fcdd-4649-9089-24385be7e423")</span></span>

<span data-ttu-id="976d1-146">Для Join3 IsParentAJoin возвращает значение false, требует начать новую инструкцию SqlSelectStatement (SelectStatement1) и передать ее в стек.</span><span class="sxs-lookup"><span data-stu-id="976d1-146">For Join3, IsParentAJoin returns false and needs to start a new SqlSelectStatement (SelectStatement1) and push it on the stack.</span></span> <span data-ttu-id="976d1-147">Обработка продолжается, как и с предыдущими соединениями, новая область передается в стек, и проводится обработка дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="976d1-147">Processing continues as it did with the previous the previous joins, a new scope is pushed on the stack and the children are processed.</span></span> <span data-ttu-id="976d1-148">Область (Extent3) является левым дочерним элементом, а соединение (Join2) - правым, которое также требует начать новую инструкцию SqlSelectStatement: SelectStatement2.</span><span class="sxs-lookup"><span data-stu-id="976d1-148">The left child is an Extent (Extent3) and the right child is a join (Join2) which also needs to start a new SqlSelectStatement: SelectStatement2.</span></span> <span data-ttu-id="976d1-149">Дочерние элементы Join2 также являются областями, и они собраны в инструкции SelectStatement2.</span><span class="sxs-lookup"><span data-stu-id="976d1-149">The children on Join2 are Extents as well and are aggregated into SelectStatement2.</span></span>

<span data-ttu-id="976d1-150">Состояние посетителя после посещения Join2, но перед выполнением последующей обработки (ProcessJoinInputResult) показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="976d1-150">The state of the visitor right after Join2 is visited, but before its post-processing (ProcessJoinInputResult) is done is shown in the next figure:</span></span>

<span data-ttu-id="976d1-151">![Схема](./media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span><span class="sxs-lookup"><span data-stu-id="976d1-151">![Diagram](./media/7510346f-8b09-4c99-b411-40af239c3c4d.gif "7510346f-8b09-4c99-b411-40af239c3c4d")</span></span>

<span data-ttu-id="976d1-152">На предыдущем рисунке инструкция SelectStatement2 показана в формате с плавающей запятой, поскольку она удалена из стека, но еще не обработана родительским элементом.</span><span class="sxs-lookup"><span data-stu-id="976d1-152">In the previous figure, SelectStatement2 is shown as free floating because it was popped out of the stack, but not yet post processed by the parent.</span></span> <span data-ttu-id="976d1-153">Его нужно добавить к части FROM родительского элемента, но оно не является законченной инструкцией SQL без предложения SELECT.</span><span class="sxs-lookup"><span data-stu-id="976d1-153">It needs to be added to the FROM part of the parent, but it is not a complete SQL statement without a SELECT clause.</span></span> <span data-ttu-id="976d1-154">Поэтому в этот момент по умолчанию столбцы (все столбцы, созданные его входными сигналами) добавляются к списку выбора методом AddDefaultColumns.</span><span class="sxs-lookup"><span data-stu-id="976d1-154">So, at this point, the default columns (all the columns produced by its inputs) are added to the select list by the method AddDefaultColumns.</span></span> <span data-ttu-id="976d1-155">AddDefaultColumns проходит по символам из FromExtents и для каждого символа добавляет все столбцы, внесенные в область.</span><span class="sxs-lookup"><span data-stu-id="976d1-155">AddDefaultColumns iterates over the symbols in FromExtents and for each symbol adds all the columns brought in scope.</span></span> <span data-ttu-id="976d1-156">В случае простого символа выполняется проверка типа символа для извлечения всех его свойств, которые нужно добавить.</span><span class="sxs-lookup"><span data-stu-id="976d1-156">For a simple symbol, it looks at the symbol type to retrieve all its properties to be added.</span></span> <span data-ttu-id="976d1-157">Он также вносит имена столбцов в словарь AllColumnNames.</span><span class="sxs-lookup"><span data-stu-id="976d1-157">It also populates the AllColumnNames dictionary with the column names.</span></span> <span data-ttu-id="976d1-158">Завершенная инструкция SelectStatement2 прибавляется к предложению FROM инструкции SelectStatement1.</span><span class="sxs-lookup"><span data-stu-id="976d1-158">The completed SelectStatement2 is appended to the FROM clause of SelectStatement1.</span></span>

<span data-ttu-id="976d1-159">Затем создается новый символ соединения для представления Join2. Он помечается как вложенное соединение, добавляется к AllJoinExtents инструкции SelectStatement1 и в таблицу символов.</span><span class="sxs-lookup"><span data-stu-id="976d1-159">Next, a new join symbol is created to represent Join2, it is marked as a nested join and added to the AllJoinExtents of SelectStatement1 and added to the symbol table.</span></span>  <span data-ttu-id="976d1-160">Теперь условие соединения Join3, Var(Extent3).OrderID = Var(Join2).Extent4.OrderID, необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="976d1-160">Now the join condition of Join3, Var(Extent3).OrderID =  Var(Join2).Extent4.OrderID, needs to be processed.</span></span> <span data-ttu-id="976d1-161">Обработка левой стороны схожа с условием соединения Join1.</span><span class="sxs-lookup"><span data-stu-id="976d1-161">Processing of the left hand side is similar to the join condition of Join1.</span></span> <span data-ttu-id="976d1-162">Тем не менее обработка правой стороны «Var(Join2).Extent4.OrderID» отличается, поскольку требуется объединение соединения.</span><span class="sxs-lookup"><span data-stu-id="976d1-162">However, the processing of the right and side "Var(Join2).Extent4.OrderID" is different because join flattening is required.</span></span>

<span data-ttu-id="976d1-163">На следующем рисунке показано состояние посетителя прямо перед обработкой DbPropertyExpression «Var(Join2).Extent4.OrderID».</span><span class="sxs-lookup"><span data-stu-id="976d1-163">The next figure shows the state of the visitor right before the DbPropertyExpression "Var(Join2).Extent4.OrderID" is processed.</span></span>

<span data-ttu-id="976d1-164">Рассмотрим порядок посещения «Var(Join2).Extent4.OrderID».</span><span class="sxs-lookup"><span data-stu-id="976d1-164">Consider how "Var(Join2).Extent4.OrderID" is visited.</span></span> <span data-ttu-id="976d1-165">Сначала посещается свойство экземпляра «Var(Join2).Extent4», которое является очередным DbPropertyExpression и посещает в первую очередь свой экземпляр «Var(Join2)».</span><span class="sxs-lookup"><span data-stu-id="976d1-165">First, the instance property "Var(Join2).Extent4" is visited, which is another DbPropertyExpression and first visits its instance "Var(Join2)".</span></span> <span data-ttu-id="976d1-166">В самой верхней области в таблице символов "Join2" разрешается в \<joinSymbol_join2 >.</span><span class="sxs-lookup"><span data-stu-id="976d1-166">In the top most scope in the symbol table, "Join2" resolves to \<joinSymbol_join2>.</span></span> <span data-ttu-id="976d1-167">В методе посещения для обработки DbPropertyExpression «Var(Join2).Extent4» отмечает, что при посещении экземпляра был возвращен символ соединения и требуется объединение.</span><span class="sxs-lookup"><span data-stu-id="976d1-167">In the visit method for DbPropertyExpression processing "Var(Join2).Extent4" notice that a join symbol was returned when visiting the instance and flattening is required.</span></span>

<span data-ttu-id="976d1-168">Так как это вложенное соединение, мы будем искать свойство «Extent4» в словаре Наметоекстент символа объединения, разрешать его \<symbol_Extent4 > и возвращать новый SymbolPair (\<joinSymbol_join2 >, \<symbol_Extent4 >).</span><span class="sxs-lookup"><span data-stu-id="976d1-168">Since it is a nested join, we look up the property "Extent4" in the NameToExtent dictionary of the join symbol, resolve it to \<symbol_Extent4> and return a new SymbolPair(\<joinSymbol_join2>, \<symbol_Extent4>).</span></span> <span data-ttu-id="976d1-169">Так как пара символов возвращается при обработке экземпляра "var (Join2)". Extent4. OrderID "свойство OrderID разрешается из Колумнпарт этой пары символов (\<symbol_Extent4 >), которая содержит список столбцов экстента, который он представляет.</span><span class="sxs-lookup"><span data-stu-id="976d1-169">Since a symbol pair is returned from the processing of the instance of "Var(Join2).Extent4.OrderID",  the property "OrderID" is resolved from the ColumnPart of that symbol pair (\<symbol_Extent4>), which has a list of the columns of the extent it represents.</span></span> <span data-ttu-id="976d1-170">Итак, «var (Join2). Extent4. OrderID разрешается в {\<joinSymbol_Join2 >, ".", \<symbol_OrderID >}.</span><span class="sxs-lookup"><span data-stu-id="976d1-170">So, "Var(Join2).Extent4.OrderID" is resolved to { \<joinSymbol_Join2>, ".", \<symbol_OrderID>}.</span></span>

<span data-ttu-id="976d1-171">Условие соединения Join4 обрабатывается схожим образом.</span><span class="sxs-lookup"><span data-stu-id="976d1-171">The join condition of Join4 is similarly processed.</span></span> <span data-ttu-id="976d1-172">Элемент управления возвращается к методу VisitInputExpression, обрабатывавшему самый верхний проект.</span><span class="sxs-lookup"><span data-stu-id="976d1-172">The control returns to the VisitInputExpression method that processed the top most project.</span></span> <span data-ttu-id="976d1-173">Судя по FromExtents возвращенного SelectStatement0, входной сигнал идентифицируется как соединение, удаляет исходные области и замещает их новой областью с символом Join.</span><span class="sxs-lookup"><span data-stu-id="976d1-173">Looking at the FromExtents of the returned SelectStatement0, the input is identified as a join, and removes the original extents and replaces them with a new extent with just the Join symbol.</span></span> <span data-ttu-id="976d1-174">Также происходит обновление таблицы символов и обработка следующей части проекции проекта.</span><span class="sxs-lookup"><span data-stu-id="976d1-174">The symbol table is also updated and next the projection part of the Project is processed.</span></span> <span data-ttu-id="976d1-175">Разрешение свойств и объединение областей соединения происходит, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="976d1-175">The resolving of the properties and the flattening of the join extents is as described earlier.</span></span>

<span data-ttu-id="976d1-176">![Схема](./media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span><span class="sxs-lookup"><span data-stu-id="976d1-176">![Diagram](./media/9456d6a9-ea2e-40ae-accc-a10e18e28b81.gif "9456d6a9-ea2e-40ae-accc-a10e18e28b81")</span></span>

<span data-ttu-id="976d1-177">Наконец, создается следующая инструкция SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="976d1-177">Finally, the following SqlSelectStatement is produced:</span></span>

```sql
SELECT:
  "1", " AS ", "[C1]",
  <symbol_Extent1>, ".", "[ProductID]", " AS ", "[ProductID]",
  <symbol_Extent1>, ".", "[ProductName]", " AS ", "[ProductName]",
  <symbol_Extent2>, ".", "[CategoryName]", " AS ", "[CategoryName]",
  <joinSymbol_Join3>, ".", <symbol_ShipCountry>, " AS ", "[ShipCountry]",
  <joinSymbol_Join3>, ".", <symbol_ProductID>, " AS ", "[ProductID1]"
FROM: "[dbo].[Products]", " AS ", <symbol_Extent1>,
        "LEFT OUTER JOIN ""[dbo].[Categories]", " AS ", <symbol_Extent2>, " ON ", <symbol_Extent1>, ".", "[CategoryID]", " = ", <symbol_Extent2>, ".", "[CategoryID]",
        "INNER JOIN ",
        " (", SELECT:
           <symbol_Extent3>, ".", "[OrderID]", " AS ", <symbol_OrderID>, ",
              <symbol_Extent3>, ".", "[ProductID]", " AS ", <symbol_ProductID>, ...,
         <joinSymbol_Join2>, ".", <symbol_OrderID_2>, ", ",
           <joinSymbol_Join2>, ".", <symbol_CustomerID>, ....,
        <joinSymbol_Join2>, ".", <symbol_OrderID_3>,
<joinSymbol_Join2>, ".", <symbol_CustomsDescription>,
<joinSymbol_Join2>, ".", <symbol_ExciseTax>
FROM: "[dbo].[OrderDetails]", " AS ", <symbol_Extent3>,
"LEFT OUTER JOIN ",
" (", SELECT:
<symbol_Extent4>, ".", "[OrderID]", " AS ", <symbol_OrderID_2>,
<symbol_Extent4>, ".", "[CustomerID]", " AS ", <symbol_CustomerID>, ...
<symbol_Extent5>, ".", "[OrderID]", " AS ", <symbol_OrderID_3>,
<symbol_Extent5>, ".", "[CustomsDescription]", " AS ", <symbol_CustomsDescription>,
<symbol_Extent5>, ".", "[ExciseTax]", " AS ", <symbol_ExciseTax>
FROM: "[dbo].[Orders]", " AS ", <symbol_Extent4>,
"LEFT OUTER JOIN ", , "[dbo].[InternationalOrders]", " AS ", <symbol_Extent5>,
" ON ", <symbol_Extent4>, ".", "[OrderID]", " = ", , <symbol_Extent5>, ".", "[OrderID]"
" )", " AS ", <joinSymbol_Join2>, " ON ", , , <symbol_Extent3>, ".", "[OrderID]", " = ", , <joinSymbol_Join2>, ".", <symbol_OrderID_2>
" )", " AS ", <joinSymbol_Join3>, " ON ", , , <symbol_Extent1>, ".", "[ProductID]", " = ", , <joinSymbol_Join3>, ".", <symbol_ProductID>
```

### <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="976d1-178">Второй этап формирования SQL: создание строковой команды</span><span class="sxs-lookup"><span data-stu-id="976d1-178">Second Phase of SQL Generation: Generating the String Command</span></span>

<span data-ttu-id="976d1-179">На втором этапе создаются фактические имена символов. Внимание уделяется только символам, представляющим столбцы под названиями «OrderID», поскольку в данном случае необходимо разрешить конфликт.</span><span class="sxs-lookup"><span data-stu-id="976d1-179">The second phase produces actual names for the symbols, and we only focus on the symbols representing columns named "OrderID", as in this case a conflict needs to be resolved.</span></span> <span data-ttu-id="976d1-180">Они выделены в инструкции SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="976d1-180">These are highlighted in the SqlSelectStatement.</span></span> <span data-ttu-id="976d1-181">Следует отметить, что показанные на рисунке суффиксы служат только для того, чтобы подчеркнуть наличие разных экземпляров, но не для представления новых имен, поскольку на этой стадии им еще не были приписаны окончательные имена (возможно, отличные от исходных).</span><span class="sxs-lookup"><span data-stu-id="976d1-181">Note that the suffixes used in the figure are only to emphasize that these are different instances, not to represent any new names, as at this stage their final names (possibly different form the original names) have not been assigned yet.</span></span>

<span data-ttu-id="976d1-182">Первый найденный символ, который необходимо переименовать, \<symbol_OrderID >.</span><span class="sxs-lookup"><span data-stu-id="976d1-182">The first symbol found that needs to be renamed is \<symbol_OrderID>.</span></span> <span data-ttu-id="976d1-183">Ему присваивается новое имя «OrderID1», 1 отмечается как последний использованный суффикс для «OrderID», а символ отмечается как не требующий переименования.</span><span class="sxs-lookup"><span data-stu-id="976d1-183">Its new name is assigned as "OrderID1", 1 is marked as the last used suffix for "OrderID" and the symbol is marked as not needing renaming.</span></span> <span data-ttu-id="976d1-184">После этого будет найден первый способ использования \<symbol_OrderID_2 >.</span><span class="sxs-lookup"><span data-stu-id="976d1-184">Next, the first usage of \<symbol_OrderID_2> is found.</span></span> <span data-ttu-id="976d1-185">Он переименовывается с использованием следующего свободного суффикса («OrderID2») и вновь отмечается как не требующий переименования, чтобы при следующем использовании оно не производилось.</span><span class="sxs-lookup"><span data-stu-id="976d1-185">It is renamed to use the next available suffix ("OrderID2") and again marked as not needing renaming, so that next time it is used it does not get renamed.</span></span> <span data-ttu-id="976d1-186">Это делается и для \<symbol_OrderID_3 >.</span><span class="sxs-lookup"><span data-stu-id="976d1-186">This is done for \<symbol_OrderID_3> too.</span></span>

<span data-ttu-id="976d1-187">В конце второго этапа создается окончательная инструкция SQL.</span><span class="sxs-lookup"><span data-stu-id="976d1-187">At the end of the second phase, the final SQL statement is generated.</span></span>

## <a name="see-also"></a><span data-ttu-id="976d1-188">См. также</span><span class="sxs-lookup"><span data-stu-id="976d1-188">See also</span></span>

- [<span data-ttu-id="976d1-189">Создание кода SQL в образце поставщика</span><span class="sxs-lookup"><span data-stu-id="976d1-189">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)
