---
title: "Возможности LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 26d20a220f1d88cee0b577d112048c8bb0e84285
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="4f1f3-102">Возможности LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4f1f3-102">What You Can Do With LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f1f3-103"> поддерживает все основные возможности, необходимые для разработчиков на SQL.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-103"> supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="4f1f3-104">Можно запрашивать данные, вставлять, обновлять и удалять сведения из таблиц.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-104">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="4f1f3-105">Выбор</span><span class="sxs-lookup"><span data-stu-id="4f1f3-105">Selecting</span></span>  
 <span data-ttu-id="4f1f3-106">Выборка (*проекция*) достигается написанием запроса [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] на выбранном языке программирования, последующим выполнением этого запроса и получением результатов.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-106">Selecting (*projection*) is achieved by just writing a [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] query in your own programming language, and then executing that query to retrieve the results.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f1f3-107"> автоматически преобразует все необходимые операции в привычные операции SQL.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-107"> itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="4f1f3-108">Для получения дополнительной информации см. [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="4f1f3-108">For more information, see [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="4f1f3-109">В следующем примере извлекаются названий компаний клиентов из Лондона, которые затем отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-109">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="4f1f3-110">Вставка</span><span class="sxs-lookup"><span data-stu-id="4f1f3-110">Inserting</span></span>  
 <span data-ttu-id="4f1f3-111">Для выполнения SQL `Insert`просто нужно добавить объекты в созданную объектную модель и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-111">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="4f1f3-112">В следующем примере новый клиент и сведения о нем добавляются в таблицу `Customers` с помощью метода <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-112">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="4f1f3-113">Updating</span><span class="sxs-lookup"><span data-stu-id="4f1f3-113">Updating</span></span>  
 <span data-ttu-id="4f1f3-114">Чтобы `Update` запись в базе данных, сначала следует извлечь элемент и изменить его непосредственно в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-114">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="4f1f3-115">После изменения объекта вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext> , чтобы обновить базу данных.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-115">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="4f1f3-116">В следующем примере извлекаются все клиенты из Лондона.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-116">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="4f1f3-117">Затем название города меняется с "Лондон" на "Лондон - Метро".</span><span class="sxs-lookup"><span data-stu-id="4f1f3-117">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="4f1f3-118">Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для отправления изменений в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-118">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="4f1f3-119">Удаление</span><span class="sxs-lookup"><span data-stu-id="4f1f3-119">Deleting</span></span>  
 <span data-ttu-id="4f1f3-120">Чтобы `Delete` элемент, удалите его из коллекции, в которую он входит, а затем вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext> , чтобы применить изменение.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-120">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="4f1f3-121">не распознает операции каскадного удаления.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-121"> does not recognize cascade-delete operations.</span></span> <span data-ttu-id="4f1f3-122">Если вы хотите удалить строку в таблице, имеющей ограничения см. в разделе [как: удаление строк из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="4f1f3-122">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="4f1f3-123">В следующем примере из базы данных извлекается клиент, `CustomerID` которого равен `98128` .</span><span class="sxs-lookup"><span data-stu-id="4f1f3-123">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="4f1f3-124">Затем, после подтверждения извлечения строки клиента, вызывается метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> , необходимый для удаления объекта из коллекции.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-124">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="4f1f3-125">Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для передачи удаления в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4f1f3-125">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4f1f3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4f1f3-126">See Also</span></span>  
 [<span data-ttu-id="4f1f3-127">Руководство по программированию</span><span class="sxs-lookup"><span data-stu-id="4f1f3-127">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="4f1f3-128">LINQ to SQL модель объектов</span><span class="sxs-lookup"><span data-stu-id="4f1f3-128">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="4f1f3-129">Начало работы</span><span class="sxs-lookup"><span data-stu-id="4f1f3-129">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
