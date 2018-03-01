---
title: "Пошаговое руководство. Запросы по связям (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: fef9880d5f9fa652eab2eb0d17bbf782dc64773d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a><span data-ttu-id="55909-102">Пошаговое руководство. Запросы по связям (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55909-102">Walkthrough: Querying Across Relationships (Visual Basic)</span></span>
<span data-ttu-id="55909-103">В этом пошаговом руководстве демонстрируется использование [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *ассоциации* для представления связей внешних ключей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="55909-103">This walkthrough demonstrates the use of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associations* to represent foreign-key relationships in the database.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="55909-104">Это пошаговое руководство было написано с помощью параметров разработки Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="55909-104">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="55909-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="55909-105">Prerequisites</span></span>  
 <span data-ttu-id="55909-106">Необходимо выполнить [Пошаговое руководство: простая модель объекта и запрос (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md).</span><span class="sxs-lookup"><span data-stu-id="55909-106">You must have completed [Walkthrough: Simple Object Model and Query (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md).</span></span> <span data-ttu-id="55909-107">На этом пошаговом руководстве основано руководство, описываемое в данном разделе. В частности на компьютере должен иметься файл northwnd.mdf в папке c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="55909-107">This walkthrough builds on that one, including the presence of the northwnd.mdf file in c:\linqtest.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="55909-108">Обзор</span><span class="sxs-lookup"><span data-stu-id="55909-108">Overview</span></span>  
 <span data-ttu-id="55909-109">Данное пошаговое руководство состоит из трех основных задач.</span><span class="sxs-lookup"><span data-stu-id="55909-109">This walkthrough consists of three main tasks:</span></span>  
  
-   <span data-ttu-id="55909-110">Добавление класса сущности, который представляет таблицу "Orders" в базе данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="55909-110">Adding an entity class to represent the Orders table in the sample Northwind database.</span></span>  
  
-   <span data-ttu-id="55909-111">Добавление примечаний к классу `Customer`, чтобы расширить связи между классами `Customer` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="55909-111">Supplementing annotations to the `Customer` class to enhance the relationship between the `Customer` and `Order` classes.</span></span>  
  
-   <span data-ttu-id="55909-112">Создание и выполнение запроса для тестирования процесса получения сведений класса `Order` с помощью класса `Customer`.</span><span class="sxs-lookup"><span data-stu-id="55909-112">Creating and running a query to test the process of obtaining `Order` information by using the `Customer` class.</span></span>  
  
## <a name="mapping-relationships-across-tables"></a><span data-ttu-id="55909-113">Сопоставление связей между таблицами</span><span class="sxs-lookup"><span data-stu-id="55909-113">Mapping Relationships across Tables</span></span>  
 <span data-ttu-id="55909-114">После определения класса `Customer` создайте определение класса сущностей `Order`, включающее следующий код, который указывает, что свойство `Orders.Customer` связано как внешний ключ со свойством `Customers.CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="55909-114">After the `Customer` class definition, create the `Order` entity class definition that includes the following code, which indicates that `Orders.Customer` relates as a foreign key to `Customers.CustomerID`.</span></span>  
  
#### <a name="to-add-the-order-entity-class"></a><span data-ttu-id="55909-115">Добавление класса сущностей "Order"</span><span class="sxs-lookup"><span data-stu-id="55909-115">To add the Order entity class</span></span>  
  
-   <span data-ttu-id="55909-116">Введите или вставьте следующий код после определения класса `Customer`.</span><span class="sxs-lookup"><span data-stu-id="55909-116">Type or paste the following code after the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a><span data-ttu-id="55909-117">Добавление примечаний к классу "Customer"</span><span class="sxs-lookup"><span data-stu-id="55909-117">Annotating the Customer Class</span></span>  
 <span data-ttu-id="55909-118">На этом этапе добавляются примечания к классу `Customer`, чтобы указать его связь с классом `Order`.</span><span class="sxs-lookup"><span data-stu-id="55909-118">In this step, you annotate the `Customer` class to indicate its relationship to the `Order` class.</span></span> <span data-ttu-id="55909-119">(Это добавление не является обязательным, поскольку для создания связи достаточно создать определение связи в любом направлении.</span><span class="sxs-lookup"><span data-stu-id="55909-119">(This addition is not strictly necessary, because defining the relationship in either direction is sufficient to create the link.</span></span> <span data-ttu-id="55909-120">Однако добавление этого примечания позволит с легкостью переходить по объектам в любом направлении.)</span><span class="sxs-lookup"><span data-stu-id="55909-120">But adding this annotation does enable you to easily navigate objects in either direction.)</span></span>  
  
#### <a name="to-annotate-the-customer-class"></a><span data-ttu-id="55909-121">Добавление примечаний к классу "Customer"</span><span class="sxs-lookup"><span data-stu-id="55909-121">To annotate the Customer class</span></span>  
  
-   <span data-ttu-id="55909-122">Введите или вставьте следующий код в класс `Customer`.</span><span class="sxs-lookup"><span data-stu-id="55909-122">Type or paste the following code into the `Customer` class:</span></span>  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a><span data-ttu-id="55909-123">Создание и выполнение запроса в рамках связи "Customer-Order"</span><span class="sxs-lookup"><span data-stu-id="55909-123">Creating and Running a Query across the Customer-Order Relationship</span></span>  
 <span data-ttu-id="55909-124">Теперь можно получить доступ к объектам `Order` непосредственно из объектов `Customer` или в обратном направлении.</span><span class="sxs-lookup"><span data-stu-id="55909-124">You can now access `Order` objects directly from the `Customer` objects, or in the opposite order.</span></span> <span data-ttu-id="55909-125">Нет необходимости явно *соединения* между клиентами и заказами.</span><span class="sxs-lookup"><span data-stu-id="55909-125">You do not need an explicit *join* between customers and orders.</span></span>  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a><span data-ttu-id="55909-126">Получение доступа к объектам "Order" с помощью объектов "Customer"</span><span class="sxs-lookup"><span data-stu-id="55909-126">To access Order objects by using Customer objects</span></span>  
  
1.  <span data-ttu-id="55909-127">Измените метод `Sub Main` посредством ввода или вставки в метод следующего кода:</span><span class="sxs-lookup"><span data-stu-id="55909-127">Modify the `Sub Main` method by typing or pasting the following code into the method:</span></span>  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2.  <span data-ttu-id="55909-128">Нажмите клавишу F5, чтобы начать отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="55909-128">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="55909-129">В окне сообщения отобразятся два имени, и в окне "Консоль" появится созданный код SQL.</span><span class="sxs-lookup"><span data-stu-id="55909-129">Two names appear in the message box, and the Console window shows the generated SQL code.</span></span>  
  
3.  <span data-ttu-id="55909-130">Закройте окно сообщения, чтобы остановить отладку.</span><span class="sxs-lookup"><span data-stu-id="55909-130">Close the message box to stop debugging.</span></span>  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a><span data-ttu-id="55909-131">Создание строго типизированного представления базы данных</span><span class="sxs-lookup"><span data-stu-id="55909-131">Creating a Strongly Typed View of Your Database</span></span>  
 <span data-ttu-id="55909-132">Общая процедура становится гораздо проще, если в начале использовать строго типизированное представление базы данных.</span><span class="sxs-lookup"><span data-stu-id="55909-132">It is much easier to start with a strongly typed view of your database.</span></span> <span data-ttu-id="55909-133">Задавая строгую типизацию объекта <xref:System.Data.Linq.DataContext>, можно избежать вызовов метода <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="55909-133">By strongly typing the <xref:System.Data.Linq.DataContext> object, you do not need calls to <xref:System.Data.Linq.DataContext.GetTable%2A>.</span></span> <span data-ttu-id="55909-134">Строго типизированные таблицы можно использовать в запросах только при использовании строго типизированного объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="55909-134">You can use strongly typed tables in all your queries when you use the strongly typed <xref:System.Data.Linq.DataContext> object.</span></span>  
  
 <span data-ttu-id="55909-135">В представленных ниже шагах создается объект `Customers` в качестве строго типизированной таблицы, которая сопоставляется с таблицей "Customers" в базе данных.</span><span class="sxs-lookup"><span data-stu-id="55909-135">In the following steps, you will create `Customers` as a strongly typed table that maps to the Customers table in the database.</span></span>  
  
#### <a name="to-strongly-type-the-datacontext-object"></a><span data-ttu-id="55909-136">Установка строгой типизации объекта "DataContext"</span><span class="sxs-lookup"><span data-stu-id="55909-136">To strongly type the DataContext object</span></span>  
  
1.  <span data-ttu-id="55909-137">Добавьте следующий код непосредственно перед объявлением класса `Customer`.</span><span class="sxs-lookup"><span data-stu-id="55909-137">Add the following code above the `Customer` class declaration.</span></span>  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2.  <span data-ttu-id="55909-138">Измените метод `Sub Main`, чтобы использовать строго типизированный объект <xref:System.Data.Linq.DataContext>, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="55909-138">Modify `Sub Main` to use the strongly typed <xref:System.Data.Linq.DataContext> as follows:</span></span>  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3.  <span data-ttu-id="55909-139">Нажмите клавишу F5, чтобы начать отладку приложения.</span><span class="sxs-lookup"><span data-stu-id="55909-139">Press F5 to debug your application.</span></span>  
  
     <span data-ttu-id="55909-140">В окне «Консоль"» отобразится следующее.</span><span class="sxs-lookup"><span data-stu-id="55909-140">The Console window output is:</span></span>  
  
     `ID=WHITC`  
  
4.  <span data-ttu-id="55909-141">Чтобы закрыть приложение, в окне "Консоль" нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="55909-141">Press Enter in the Console window to close the application.</span></span>  
  
5.  <span data-ttu-id="55909-142">На **файл** меню, нажмите кнопку **сохранить все** Если вы хотите сохранить это приложение.</span><span class="sxs-lookup"><span data-stu-id="55909-142">On the **File** menu, click **Save All** if you want to save this application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="55909-143">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="55909-143">Next Steps</span></span>  
 <span data-ttu-id="55909-144">Следующего пошагового руководства ([Пошаговое руководство: управление данными (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)) демонстрирует способ обработки данных.</span><span class="sxs-lookup"><span data-stu-id="55909-144">The next walkthrough ([Walkthrough: Manipulating Data (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)) demonstrates how to manipulate data.</span></span> <span data-ttu-id="55909-145">Для этого пошагового руководства не требуется сохранять два пошаговых руководства, которые уже выполнены в этой серии.</span><span class="sxs-lookup"><span data-stu-id="55909-145">That walkthrough does not require that you save the two walkthroughs in this series that you have already completed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55909-146">См. также</span><span class="sxs-lookup"><span data-stu-id="55909-146">See Also</span></span>  
 [<span data-ttu-id="55909-147">Обучение с использованием пошаговых руководств</span><span class="sxs-lookup"><span data-stu-id="55909-147">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
