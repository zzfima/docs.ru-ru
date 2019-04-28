---
title: Практическое руководство. Как удалить строки из базы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 401d445e49e3712b8c59fa9bc9a2e53500a5db16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903907"
---
# <a name="how-to-delete-rows-from-the-database"></a><span data-ttu-id="976d2-102">Практическое руководство. Как удалить строки из базы данных</span><span class="sxs-lookup"><span data-stu-id="976d2-102">How to: Delete Rows From the Database</span></span>
<span data-ttu-id="976d2-103">Можно удалить строки в базе данных, удалив соответствующий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты из их коллекции, связанной с таблицей.</span><span class="sxs-lookup"><span data-stu-id="976d2-103">You can delete rows in a database by removing the corresponding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] objects from their table-related collection.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="976d2-104">Преобразует изменения в соответствующие SQL `DELETE` команды.</span><span class="sxs-lookup"><span data-stu-id="976d2-104">translates your changes to the appropriate SQL `DELETE` commands.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="976d2-105">не поддерживает или не распознает операции каскадного удаления.</span><span class="sxs-lookup"><span data-stu-id="976d2-105">does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="976d2-106">Если требуется удалить строку в таблице, имеющей ограничения, необходимо выполнить любую из следующих задач.</span><span class="sxs-lookup"><span data-stu-id="976d2-106">If you want to delete a row in a table that has constraints against it, you must complete either of the following tasks:</span></span>  
  
- <span data-ttu-id="976d2-107">Установите правило `ON DELETE CASCADE` в ограничении внешнего ключа в базе данных.</span><span class="sxs-lookup"><span data-stu-id="976d2-107">Set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database.</span></span>  
  
- <span data-ttu-id="976d2-108">Используйте собственный код, чтобы сначала удалить дочерние объекты, не допускающие удаление родительского объекта.</span><span class="sxs-lookup"><span data-stu-id="976d2-108">Use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span>  
  
 <span data-ttu-id="976d2-109">В противном случае создается исключение.</span><span class="sxs-lookup"><span data-stu-id="976d2-109">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="976d2-110">См. второй пример кода далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="976d2-110">See the second code example later in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="976d2-111">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="976d2-111">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="976d2-112">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="976d2-112">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="976d2-113">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="976d2-113">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="976d2-114">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="976d2-114">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="976d2-115">Дополнительные сведения см. в разделе [Как Соединение с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="976d2-115">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-delete-a-row-in-the-database"></a><span data-ttu-id="976d2-116">Удаление строки в базе данных</span><span class="sxs-lookup"><span data-stu-id="976d2-116">To delete a row in the database</span></span>  
  
1. <span data-ttu-id="976d2-117">Отправьте в базу данных запрос на удаляемую строку.</span><span class="sxs-lookup"><span data-stu-id="976d2-117">Query the database for the row to be deleted.</span></span>  
  
2. <span data-ttu-id="976d2-118">Вызовите метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.</span><span class="sxs-lookup"><span data-stu-id="976d2-118">Call the <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> method.</span></span>  
  
3. <span data-ttu-id="976d2-119">Отправьте изменение в базу данных.</span><span class="sxs-lookup"><span data-stu-id="976d2-119">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="976d2-120">Пример</span><span class="sxs-lookup"><span data-stu-id="976d2-120">Example</span></span>  
 <span data-ttu-id="976d2-121">В первом примере кода в базу данных отправляется запрос на сведения о заказе "Order #11000", помечаются сведения для удаления, а изменения отправляются в базу данных.</span><span class="sxs-lookup"><span data-stu-id="976d2-121">This first code example queries the database for order details that belong to Order #11000, marks these order details for deletion, and submits these changes to the database.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="976d2-122">Пример</span><span class="sxs-lookup"><span data-stu-id="976d2-122">Example</span></span>  
 <span data-ttu-id="976d2-123">Целью второго примера является удаление заказа (с номером 10250).</span><span class="sxs-lookup"><span data-stu-id="976d2-123">In this second example, the objective is to remove an order (#10250).</span></span> <span data-ttu-id="976d2-124">Код сначала проверяет таблицу `OrderDetails` на наличие в ней дочерних элементов удаляемого заказа.</span><span class="sxs-lookup"><span data-stu-id="976d2-124">The code first examines the `OrderDetails` table to see whether the order to be removed has children there.</span></span> <span data-ttu-id="976d2-125">Если в таблице есть дочерние элементы заказа, сначала они, а затем сам заказ помечаются для удаления.</span><span class="sxs-lookup"><span data-stu-id="976d2-125">If the order has children, first the children and then the order are marked for removal.</span></span> <span data-ttu-id="976d2-126"><xref:System.Data.Linq.DataContext> располагает фактические действия по удалению в надлежащей последовательности, чтобы команды удаления, отправляемые в базу данных, подчинялись ее ограничениям.</span><span class="sxs-lookup"><span data-stu-id="976d2-126">The <xref:System.Data.Linq.DataContext> puts the actual deletes in correct order so that delete commands sent to the database abide by the database constraints.</span></span>  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="976d2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="976d2-127">See also</span></span>

- [<span data-ttu-id="976d2-128">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="976d2-128">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="976d2-129">Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="976d2-129">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="976d2-130">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="976d2-130">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
