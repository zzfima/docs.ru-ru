---
title: Практическое руководство. Как вставить строки в базу данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
ms.openlocfilehash: cc9f276cc278d4a9c376d72f1ab38d89ea6dd5b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169602"
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="cc1b3-102">Практическое руководство. Как вставить строки в базу данных</span><span class="sxs-lookup"><span data-stu-id="cc1b3-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="cc1b3-103">Вставка строк в базу данных, добавив объекты в связанный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекции и затем отправив эти изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="cc1b3-104">Преобразует изменения в соответствующие SQL `INSERT` команды.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-104">translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc1b3-105">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="cc1b3-106">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b3-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="cc1b3-107">С помощью Visual Studio разработчики могут использовать [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур для той же цели.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-107">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="cc1b3-108">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="cc1b3-109">Дополнительные сведения см. в разделе [Как Соединение с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="cc1b3-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="cc1b3-110">Вставка строки в базу данных</span><span class="sxs-lookup"><span data-stu-id="cc1b3-110">To insert a row into the database</span></span>  
  
1.  <span data-ttu-id="cc1b3-111">Создайте новый объект, содержащий столбец данных для отправки.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2.  <span data-ttu-id="cc1b3-112">Добавьте новый объект, который [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` коллекцию, связанную с целевой таблицей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3.  <span data-ttu-id="cc1b3-113">Отправьте изменение в базу данных.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc1b3-114">Пример</span><span class="sxs-lookup"><span data-stu-id="cc1b3-114">Example</span></span>  
 <span data-ttu-id="cc1b3-115">В следующем примере кода создается новый объект с типом `Order` и заполняется соответствующими значениями.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="cc1b3-116">Затем новый объект добавляется в коллекцию `Order`.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="cc1b3-117">И наконец, изменение отправляется в базу данных в виде новой строки в таблице`Orders`.</span><span class="sxs-lookup"><span data-stu-id="cc1b3-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cc1b3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cc1b3-118">See also</span></span>

- [<span data-ttu-id="cc1b3-119">Практическое руководство. Как управлять конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="cc1b3-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [<span data-ttu-id="cc1b3-120">Методы DataContext (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="cc1b3-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="cc1b3-121">Практическое руководство. назначение хранимых процедур для выполнения обновлений, вставок и удалений (реляционный конструктор объектов)</span><span class="sxs-lookup"><span data-stu-id="cc1b3-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [<span data-ttu-id="cc1b3-122">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="cc1b3-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
