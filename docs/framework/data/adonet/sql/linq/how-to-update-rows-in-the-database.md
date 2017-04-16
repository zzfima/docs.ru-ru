---
title: "Как обновлять строки в базе данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2b5c90f-6cc3-4128-bfab-1db488d5af26
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как обновлять строки в базе данных
Строки в базе данных можно обновить, изменив значения членов объектов, связанных с коллекцией [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601> и затем отправив эти изменения в базу данных. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует изменения в соответствующие команды операций SQL `UPDATE`.  
  
> [!NOTE]
>  Можно переопределить методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], используемые по умолчанию для операций `Insert`, `Update` и `Delete` базы данных.  Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] могут воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для разработки хранимых процедур, выполняющих те же задачи.  
  
 В следующих шагах предполагается, что подключение к базе данных Northwind выполняется с помощью допустимого объекта <xref:System.Data.Linq.DataContext>.  Дополнительные сведения см. в разделе [Как соединиться с базой данных](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### Чтобы обновить строку в базе данных, выполните следующие действия.  
  
1.  Отправьте в базу данных запрос на обновляемую строку.  
  
2.  Выполните необходимые изменения значений членов полученного объекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
3.  Отправьте изменения в базу данных.  
  
## Пример  
 В следующем примере выполняются запросы к базе данных для заказа № 11000, а затем изменяются значения `ShipName` и `ShipVia` полученного объекта `Order`.  И наконец, изменения этих членов отправляются в базу данных в качестве изменений столбцов `ShipName` и `ShipVia`.  
  
 [!code-csharp[System.Data.Linq.Table#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.Table#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#2)]  
  
## См. также  
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Как назначить хранимые процедуры для выполнения обновлений, вставок и удалений \(реляционный конструктор объектов\)](../Topic/How%20to:%20Assign%20stored%20procedures%20to%20perform%20updates,%20inserts,%20and%20deletes%20\(O-R%20Designer\).md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)