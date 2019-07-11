---
title: Практическое руководство. Как обновлять строки в базе данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
ms.openlocfilehash: 30654a10382c8cc1bf99af320e3a6a493982219b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743134"
---
# <a name="how-to-update-rows-in-the-database"></a><span data-ttu-id="0f2a1-102">Практическое руководство. Как обновлять строки в базе данных</span><span class="sxs-lookup"><span data-stu-id="0f2a1-102">How to: Update Rows in the Database</span></span>
<span data-ttu-id="0f2a1-103">Вы можете обновить строки в базе данных, изменив значения членов объектов, связанных с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекции и затем отправив эти изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-103">You can update rows in a database by modifying member values of the objects associated with the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0f2a1-104">Преобразует изменения в соответствующие SQL `UPDATE` команды.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-104">translates your changes into the appropriate SQL `UPDATE` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f2a1-105">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="0f2a1-106">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0f2a1-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="0f2a1-107">Реляционный конструктор объектов позволяют разработчикам, с помощью Visual Studio для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-107">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="0f2a1-108">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="0f2a1-109">Дополнительные сведения см. в разделе [Практическое руководство. Соединение с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="0f2a1-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-update-a-row-in-the-database"></a><span data-ttu-id="0f2a1-110">Чтобы обновить строку в базе данных, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-110">To update a row in the database</span></span>  
  
1. <span data-ttu-id="0f2a1-111">Отправьте в базу данных запрос на обновляемую строку.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-111">Query the database for the row to be updated.</span></span>  
  
2. <span data-ttu-id="0f2a1-112">Выполните необходимые изменения значений членов полученного объекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f2a1-112">Make desired changes to member values in the resulting [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object.</span></span>  
  
3. <span data-ttu-id="0f2a1-113">Отправьте изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-113">Submit the changes to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2a1-114">Пример</span><span class="sxs-lookup"><span data-stu-id="0f2a1-114">Example</span></span>  
 <span data-ttu-id="0f2a1-115">В следующем примере выполняются запросы к базе данных для заказа № 11000, а затем изменяются значения `ShipName` и `ShipVia` полученного объекта `Order`.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-115">The following example queries the database for order #11000, and then changes the values of `ShipName` and `ShipVia` in the resulting `Order` object.</span></span> <span data-ttu-id="0f2a1-116">И наконец, изменения этих членов отправляются в базу данных в качестве изменений столбцов `ShipName` и `ShipVia`.</span><span class="sxs-lookup"><span data-stu-id="0f2a1-116">Finally, the changes to these member values are submitted to the database as changes in the `ShipName` and `ShipVia` columns.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0f2a1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0f2a1-117">See also</span></span>

- [<span data-ttu-id="0f2a1-118">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="0f2a1-118">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="0f2a1-119">Практическое руководство. Назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="0f2a1-119">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="0f2a1-120">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="0f2a1-120">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
