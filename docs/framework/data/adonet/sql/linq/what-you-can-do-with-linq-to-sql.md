---
title: "Возможности LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Возможности LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает все основные возможности, необходимые для разработчиков на SQL. Можно запрашивать данные, вставлять, обновлять и удалять сведения из таблиц.  
  
## Выбор  
 Выборка \(*проекция*\) достигается написанием запроса [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] на выбранном языке программирования, последующим выполнением этого запроса и получением результатов.[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] автоматически преобразует все необходимые операции в привычные операции SQL. Для получения дополнительной информации см. [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
 В следующем примере извлекаются названий компаний клиентов из Лондона, которые затем отображаются в окне консоли.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## Вставка  
 Для выполнения SQL `Insert` просто нужно добавить объекты в созданную объектную модель и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext>.  
  
 В следующем примере новый клиент и сведения о нем добавляются в таблицу `Customers` с помощью метода <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## Updating  
 Чтобы `Update` запись в базе данных, сначала следует извлечь элемент и изменить его непосредственно в объектной модели. После изменения объекта вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext>, чтобы обновить базу данных.  
  
 В следующем примере извлекаются все клиенты из Лондона. Затем название города меняется с "Лондон" на "Лондон \- Метро". Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для отправления изменений в базу данных.  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## Удаление  
 Чтобы `Delete` элемент, удалите его из коллекции, в которую он входит, а затем вызовите метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> в <xref:System.Data.Linq.DataContext>, чтобы применить изменение.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не распознает операции каскадного удаления. Если требуется удалить строку в таблице, имеющей ограничения, см. раздел [Как удалять строки из базы данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
 В следующем примере из базы данных извлекается клиент, `CustomerID` которого равен `98128`. Затем, после подтверждения извлечения строки клиента, вызывается метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>, необходимый для удаления объекта из коллекции. Наконец, вызывается метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для передачи удаления в базу данных.  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## См. также  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)   
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)   
 [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)