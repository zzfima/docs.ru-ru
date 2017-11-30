---
title: "Операции вставки, обновления и удаления"
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
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: adbe7faa50b06c330b942b451d5a4a0bd832cde3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="insert-update-and-delete-operations"></a><span data-ttu-id="eaec0-102">Операции вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="eaec0-102">Insert, Update, and Delete Operations</span></span>
<span data-ttu-id="eaec0-103">В `Insert` операции `Update`, `Delete` и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняются путем добавления, изменения и удаления объектов в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="eaec0-103">You perform `Insert`, `Update`, and `Delete` operations in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] by adding, changing, and removing objects in your object model.</span></span> <span data-ttu-id="eaec0-104">По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует действия в язык SQL и отправляет изменения в базу данных.</span><span class="sxs-lookup"><span data-stu-id="eaec0-104">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates your actions to SQL and submits the changes to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="eaec0-105">предоставляет максимальную гибкость при сохранении и управлении изменениями, внесенными в объекты.</span><span class="sxs-lookup"><span data-stu-id="eaec0-105"> offers maximum flexibility in manipulating and persisting changes that you made to your objects.</span></span> <span data-ttu-id="eaec0-106">Как только будут доступны объекты сущности (либо при извлечении их с помощью запроса, либо при создании заново), их можно изменить как обычные объекты в приложении.</span><span class="sxs-lookup"><span data-stu-id="eaec0-106">As soon as entity objects are available (either by retrieving them through a query or by constructing them anew), you can change them as typical objects in your application.</span></span> <span data-ttu-id="eaec0-107">То есть можно изменить их значения, их можно добавить в коллекцию и можно удалить их из нее.</span><span class="sxs-lookup"><span data-stu-id="eaec0-107">That is, you can change their values, you can add them to your collections, and you can remove them from your collections.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="eaec0-108"> отслеживает изменения и готов отправить их обратно в базу данных, когда будет вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="eaec0-108"> tracks your changes and is ready to transmit them back to the database when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="eaec0-109"> не поддерживает или не распознает операции каскадного удаления.</span><span class="sxs-lookup"><span data-stu-id="eaec0-109"> does not support or recognize cascade-delete operations.</span></span> <span data-ttu-id="eaec0-110">Если вы хотите удалить строку в таблице с ограничениями для нее, следует либо задать `ON DELETE CASCADE` правило в ограничении внешнего ключа в базе данных, или используйте собственный код, чтобы сначала удалить дочерние объекты, которые препятствуют удалению родительского объекта.</span><span class="sxs-lookup"><span data-stu-id="eaec0-110">If you want to delete a row in a table that has constraints against it, you must either set the `ON DELETE CASCADE` rule in the foreign-key constraint in the database, or use your own code to first delete the child objects that prevent the parent object from being deleted.</span></span> <span data-ttu-id="eaec0-111">В противном случае создается исключение.</span><span class="sxs-lookup"><span data-stu-id="eaec0-111">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="eaec0-112">Дополнительные сведения см. в разделе [как: удаление строк из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span><span class="sxs-lookup"><span data-stu-id="eaec0-112">For more information, see [How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="eaec0-113">В следующих фрагментах используются классы `Customer` и `Order` из образца базы данных "Борей".</span><span class="sxs-lookup"><span data-stu-id="eaec0-113">The following excerpts use the `Customer` and `Order` classes from the Northwind sample database.</span></span> <span data-ttu-id="eaec0-114">Для краткости определения классов не показаны.</span><span class="sxs-lookup"><span data-stu-id="eaec0-114">Class definitions are not shown for brevity.</span></span>  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 <span data-ttu-id="eaec0-115">При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически создает и выполняет команды SQL, необходимые для передачи изменений обратно в базу данных.</span><span class="sxs-lookup"><span data-stu-id="eaec0-115">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] automatically generates and executes the SQL commands that it must have to transmit your changes back to the database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eaec0-116">Это поведение можно переопределить использованием собственной настраиваемой логики, обычно за счет хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="eaec0-116">You can override this behavior by using your own custom logic, typically by way of a stored procedure.</span></span> <span data-ttu-id="eaec0-117">Дополнительные сведения см. в разделе [обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="eaec0-117">For more information, see [Responsibilities of the Developer In Overriding Default Behavior](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).</span></span>  
>   
>  <span data-ttu-id="eaec0-118">Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут для выполнения этой задачи воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур.</span><span class="sxs-lookup"><span data-stu-id="eaec0-118">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for this purpose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaec0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="eaec0-119">See Also</span></span>  
 [<span data-ttu-id="eaec0-120">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="eaec0-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="eaec0-121">Настройка вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="eaec0-121">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
