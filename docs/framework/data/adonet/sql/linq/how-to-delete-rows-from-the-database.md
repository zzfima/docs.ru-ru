---
title: Практическое руководство. Удаление строк из базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 179656fbecdc8efbef323c1882d756dea564c152
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360456"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="66855-102">Практическое руководство. Удаление строк из базы данных</span><span class="sxs-lookup"><span data-stu-id="66855-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="66855-103">Можно удалить строки в базе данных путем удаления соответствующего [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты из их коллекции, связанной с таблицей.</span><span class="sxs-lookup"><span data-stu-id="66855-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="66855-104"> Преобразует изменения в соответствующие SQL `DELETE` команд.</span><span class="sxs-lookup"><span data-stu-id="66855-104"> translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="66855-105"> не поддерживает или не распознает операции каскадного удаления.</span><span class="sxs-lookup"><span data-stu-id="66855-105"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="66855-106">Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любую из следующих задач.</span><span class="sxs-lookup"><span data-stu-id="66855-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
-   <span data-ttu-id="66855-107">Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="66855-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
-   <span data-ttu-id="66855-108">Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.</span><span class="sxs-lookup"><span data-stu-id="66855-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="66855-109">В противном случае создается исключение.</span><span class="sxs-lookup"><span data-stu-id="66855-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="66855-110">См. второй пример кода далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="66855-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66855-111">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="66855-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="66855-112">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="66855-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="66855-113">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="66855-113">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="66855-114">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="66855-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="66855-115">Дополнительные сведения см. в разделе [как: подключение к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="66855-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="66855-116">Удаление строки в базе данных</span><span class="sxs-lookup"><span data-stu-id="66855-116">To delete a row in the database</span></span>  
  
1.  <span data-ttu-id="66855-117">Отправьте в базу данных запрос на удаляемую строку.</span><span class="sxs-lookup"><span data-stu-id="66855-117">Query the database for the row to be deleted.</span></span>  
  
2.  <span data-ttu-id="66855-118">Вызовите метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="66855-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3.  <span data-ttu-id="66855-119">Отправьте изменение в базу данных.</span><span class="sxs-lookup"><span data-stu-id="66855-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66855-120">Пример</span><span class="sxs-lookup"><span data-stu-id="66855-120">Example</span></span>  
 <span data-ttu-id="66855-121">В первом примере кода в базу данных отправляется запрос на сведения о заказе "Order #11000", помечаются сведения для удаления, а изменения отправляются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="66855-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="66855-122">Пример</span><span class="sxs-lookup"><span data-stu-id="66855-122">Example</span></span>  
 <span data-ttu-id="66855-123">Целью второго примера является удаление заказа (с номером 10250).</span><span class="sxs-lookup"><span data-stu-id="66855-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="66855-124">Код сначала проверяет таблицу `OrderDetails` на наличие в ней дочерних элементов удаляемого заказа.</span><span class="sxs-lookup"><span data-stu-id="66855-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="66855-125">Если в таблице есть дочерние элементы заказа, сначала они, а затем сам заказ помечаются для удаления.</span><span class="sxs-lookup"><span data-stu-id="66855-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="66855-126"><xref:System.Data.Linq.DataContext> располагает фактические действия по удалению в надлежащей последовательности, чтобы команды удаления, отправляемые в базу данных, подчинялись ее ограничениям.</span><span class="sxs-lookup"><span data-stu-id="66855-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="66855-127">См. также</span><span class="sxs-lookup"><span data-stu-id="66855-127">See Also</span></span>  
 [<span data-ttu-id="66855-128">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="66855-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="66855-129">Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)</span><span class="sxs-lookup"><span data-stu-id="66855-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="66855-130">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="66855-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
