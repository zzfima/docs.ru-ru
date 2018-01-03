---
title: "Практическое руководство. Обновление строк в базе данных"
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
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8999b85da3f7d32cc1c64899dce5cdfeeafbefd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="1ef40-102">Практическое руководство. Обновление строк в базе данных</span><span class="sxs-lookup"><span data-stu-id="1ef40-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="1ef40-103">Строки в базе данных можно обновить, изменив значения членов объектов, связанных с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекции и затем отправив эти изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="1ef40-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="1ef40-104">Преобразует изменения в соответствующие SQL `UPDATE` команд.</span><span class="sxs-lookup"><span data-stu-id="1ef40-104"> translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ef40-105">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="1ef40-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="1ef40-106">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="1ef40-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="1ef40-107">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.</span><span class="sxs-lookup"><span data-stu-id="1ef40-107">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="1ef40-108">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1ef40-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="1ef40-109">Дополнительные сведения см. в разделе [как: подключение к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="1ef40-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="1ef40-110">Чтобы обновить строку в базе данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1ef40-110">To update a row in the database</span></span>  
  
1.  <span data-ttu-id="1ef40-111">Отправьте в базу данных запрос на обновляемую строку.</span><span class="sxs-lookup"><span data-stu-id="1ef40-111">Query the database for the row to be updated.</span></span>  
  
2.  <span data-ttu-id="1ef40-112">Выполните необходимые изменения значений членов полученного объекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ef40-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3.  <span data-ttu-id="1ef40-113">Отправьте изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="1ef40-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ef40-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1ef40-114">Example</span></span>  
 <span data-ttu-id="1ef40-115">В следующем примере выполняются запросы к базе данных для заказа № 11000, а затем изменяются значения `ShipName` и `ShipVia` полученного объекта `Order`.</span><span class="sxs-lookup"><span data-stu-id="1ef40-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="1ef40-116">И наконец, изменения этих членов отправляются в базу данных в качестве изменений столбцов `ShipName` и `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="1ef40-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1ef40-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1ef40-117">See Also</span></span>  
 [<span data-ttu-id="1ef40-118">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="1ef40-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="1ef40-119">Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)</span><span class="sxs-lookup"><span data-stu-id="1ef40-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="1ef40-120">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="1ef40-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
