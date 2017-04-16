---
title: "Как вставлять строки в базу данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44d99680-69c7-4879-a732-f6771b334211
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вставлять строки в базу данных
Строки в базу данных можно вставить, добавив объекты в связанные коллекции [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> и затем отправив эти изменения в базу данных. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует изменения в соответствующие команды SQL `INSERT`.  
  
> [!NOTE]
>  Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.  Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.  
  
 В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.  Дополнительные сведения см. в разделе [Как соединиться с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### Вставка строки в базу данных  
  
1.  Создайте новый объект, содержащий столбец данных для отправки.  
  
2.  Добавьте новый объект в коллекцию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] `Table`, связанную с целевой таблицей в базе данных.  
  
3.  Отправьте изменение в базу данных.  
  
## Пример  
 В следующем примере кода создается новый объект с типом `Order` и заполняется соответствующими значениями.  Затем новый объект добавляется в коллекцию `Order`.  И наконец, изменение отправляется в базу данных в виде новой строки в таблице`Orders`.  
  
 [!code-csharp[System.Data.Linq.Table#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.Table#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#1)]  
  
## См. также  
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Методы DataContext \(реляционный конструктор объектов\)](../Topic/DataContext%20Methods%20\(O-R%20Designer\).md)   
 [Как назначить хранимые процедуры для выполнения обновлений, вставок и удалений \(реляционный конструктор объектов\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)