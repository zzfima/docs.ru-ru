---
title: "Практическое руководство. Вставка строк в базу данных"
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
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2b51ba8191ddd1b0e70c483970133cfe22d321a1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-insert-rows-into-the-database"></a><span data-ttu-id="0ce9d-102">Практическое руководство. Вставка строк в базу данных</span><span class="sxs-lookup"><span data-stu-id="0ce9d-102">How to: Insert Rows Into the Database</span></span>
<span data-ttu-id="0ce9d-103">Строки в базу данных можно вставить, добавив объекты в связанные [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> коллекции и затем отправив эти изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-103">You insert rows into a database by adding objects to the associated [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> collection and then submitting the changes to the database.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0ce9d-104">Преобразует изменения в соответствующие SQL `INSERT` команд.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-104"> translates your changes into the appropriate SQL `INSERT` commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ce9d-105">Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-105">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="0ce9d-106">Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0ce9d-106">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="0ce9d-107">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-107">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
 <span data-ttu-id="0ce9d-108">В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-108">The following steps assume that a valid <xref:System.Data.Linq.DataContext> connects you to the Northwind database.</span></span> <span data-ttu-id="0ce9d-109">Дополнительные сведения см. в разделе [как: подключение к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="0ce9d-109">For more information, see [How to: Connect to a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).</span></span>  
  
### <a name="to-insert-a-row-into-the-database"></a><span data-ttu-id="0ce9d-110">Вставка строки в базу данных</span><span class="sxs-lookup"><span data-stu-id="0ce9d-110">To insert a row into the database</span></span>  
  
1.  <span data-ttu-id="0ce9d-111">Создайте новый объект, содержащий столбец данных для отправки.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-111">Create a new object that includes the column data to be submitted.</span></span>  
  
2.  <span data-ttu-id="0ce9d-112">Добавьте новый объект в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` коллекцию, связанную с целевой таблицей в базе данных.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-112">Add the new object to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table` collection associated with the target table in the database.</span></span>  
  
3.  <span data-ttu-id="0ce9d-113">Отправьте изменение в базу данных.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-113">Submit the change to the database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ce9d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="0ce9d-114">Example</span></span>  
 <span data-ttu-id="0ce9d-115">В следующем примере кода создается новый объект с типом `Order` и заполняется соответствующими значениями.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-115">The following code example creates a new object of type `Order` and populates it with appropriate values.</span></span> <span data-ttu-id="0ce9d-116">Затем новый объект добавляется в коллекцию `Order`.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-116">It then adds the new object to the `Order` collection.</span></span> <span data-ttu-id="0ce9d-117">И наконец, изменение отправляется в базу данных в виде новой строки в таблице`Orders`.</span><span class="sxs-lookup"><span data-stu-id="0ce9d-117">Finally, it submits the change to the database as a new row in the `Orders` table.</span></span>  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ce9d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0ce9d-118">See Also</span></span>  
 [<span data-ttu-id="0ce9d-119">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="0ce9d-119">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [<span data-ttu-id="0ce9d-120">Методы DataContext (O/R-конструктор)</span><span class="sxs-lookup"><span data-stu-id="0ce9d-120">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="0ce9d-121">Как: назначение хранимых процедур для выполнения обновления, вставки и удаления (конструктор O/R)</span><span class="sxs-lookup"><span data-stu-id="0ce9d-121">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
 [<span data-ttu-id="0ce9d-122">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="0ce9d-122">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
