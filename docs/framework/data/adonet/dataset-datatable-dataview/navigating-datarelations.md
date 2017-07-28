---
title: "Перемещение по связям DataRelations | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Перемещение по связям DataRelations
Одно из основных назначений объекта <xref:System.Data.DataRelation> состоит в обеспечении переходов от одного объекта <xref:System.Data.DataTable> к другому в пределах <xref:System.Data.DataSet>.  Это позволяет получать все связанные объекты <xref:System.Data.DataRow> в одном объекте **DataTable** при указании единственного значения **DataRow** из связанного объекта **DataTable**.  Например, после установления связи **DataRelation** между таблицей заказчиков и таблицей заказов можно получить все строки с заказами для конкретной строки заказчика с помощью метода **GetChildRows**.  
  
 В следующем примере кода создается связь **DataRelation** между таблицей **Customers** и таблицей **Orders** набора данных **DataSet** и возвращаются все заказы для каждого заказчика.  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 Следующий пример основан на предыдущем примере; в нем четыре таблицы связываются друг с другом и происходит переход по этим связям.  Как и в предыдущем примере, значение **CustomerID** связывает таблицу **Customers** с таблицей **Orders**.  Для каждого заказчика в таблице **Customers** определяются все дочерние строки в таблице **Orders** для получения данных о количестве заказов конкретного заказчика и значений **OrderID** этих заказов.  
  
 В расширенном примере также осуществляется возврат значений из таблиц **OrderDetails** и **Products**.  Между таблицей **Orders** и таблицей **OrderDetails** с помощью значений **OrderID** устанавливается связь, позволяющая определить для каждого клиентского заказа, какие продукты были заказаны и в каком количестве.  Таблица **OrderDetails** содержит только значение **ProductID** каждого заказанного продукта, поэтому для возврата значений **ProductName** устанавливается связь таблицы **OrderDetails** с таблицей **Products** с помощью значений **ProductID**.  В этой связи таблица **Products** является родительской, а таблица **OrderDetails** \- дочерней.  В результате этого при выполнении итераций по строкам таблицы **OrderDetails** вызывается метод **GetParentRow** для получения связанного значения **ProductName**.  
  
 Обратите внимание на то, что при создании связи **DataRelation** для таблиц **Customers** и **Orders** значение для флага **createConstraints** не задается \(значение по умолчанию равно **true**\).  При этом предполагается, что все строки в таблице **Orders** имеют значение **CustomerID**, которое существует в родительской таблице **Customers**.  Если одно из значений **CustomerID**, существующих в таблице **Orders**, не существует в таблице **Customers**, то объект <xref:System.Data.ForeignKeyConstraint> вызывает исключение.  
  
 Если дочерний столбец может содержать значения, которые не содержатся в родительском столбце, задайте значение флага **createConstraints**, равное **false**, при добавлении связи **DataRelation**.  В этом примере флаг **createConstraints** устанавливается в значение **false** для связи **DataRelation** между таблицей **Orders** и таблицей **OrderDetails**.  Это позволяет возвращать в приложении все записи из таблицы **OrderDetails** и только подмножество записей из таблицы **Orders**, не вызывая исключения во время выполнения.  В этом расширенном образце вывод формируется в следующем формате.  
  
```  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 Следующий пример кода представляет собой расширенный образец, в котором возвращаются значения из таблиц **OrderDetails** и **Products**, причем возвращается только подмножество записей из таблицы **Orders**.  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## См. также  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)