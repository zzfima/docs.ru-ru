---
title: "Операции вставки, обновления и удаления | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Операции вставки, обновления и удаления
В `Insert` операции `Update`, `Delete` и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняются путем добавления, изменения и удаления объектов в объектной модели.  По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует действия в язык SQL и отправляет изменения в базу данных.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет максимальную гибкость при сохранении и управлении изменениями, внесенными в объекты.  Как только будут доступны объекты сущности \(либо при извлечении их с помощью запроса, либо при создании заново\), их можно изменить как обычные объекты в приложении.  Это означает, что можно изменить их значения, добавить в коллекцию или удалить из нее.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отслеживает изменения и готов отправить их обратно в базу данных, когда будет вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает или не распознает операции каскадного удаления.  Если необходимо удалить строку в таблице с ограничениями для нее, следует либо задать в базе данных правило `ON DELETE CASCADE` в ограничении внешнего ключа, либо использовать собственный код для предварительного удаления этих дочерних объектов, которые препятствуют удалению родительского. В противном случае создается исключение.  Дополнительные сведения см. в разделе [Как удалять строки из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 В следующих фрагментах используются классы `Customer` и `Order` из образца базы данных "Борей".  Для краткости определения классов не показаны.  
  
 [!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
 [!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]  
  
 При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически создает и выполняет команды SQL, необходимые для передачи изменений обратно в базу данных.  
  
> [!NOTE]
>  Это поведение можно переопределить использованием собственной настраиваемой логики, обычно за счет хранимой процедуры.  Дополнительные сведения см. в разделе [Обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
>   
>  Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут для выполнения этой задачи воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур.  
  
## См. также  
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)