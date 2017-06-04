---
title: "Добавление объектов DataRelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Добавление объектов DataRelation
В наборе <xref:System.Data.DataSet> с несколькими объектами <xref:System.Data.DataTable> можно использовать объекты <xref:System.Data.DataRelation> для связи таблиц друг с другом, для перехода по таблицам, а также для возвращения дочерних или родительских строк из связанной таблицы.  
  
 Для создания объекта **DataRelation** требуются следующие аргументы: имя создаваемого объекта **DataRelation** и массив из одной или нескольких ссылок <xref:System.Data.DataColumn> на столбцы, которые выступают в роли родительских или дочерних столбцов в этой связи.  После создания объекта **DataRelation** его можно использовать, чтобы переходить между таблицами, а также получать значения.  
  
 По умолчанию при добавлении объекта **DataRelation** в объект <xref:System.Data.DataSet> в родительскую таблицу добавляется <xref:System.Data.UniqueConstraint>, а в дочернюю \- <xref:System.Data.ForeignKeyConstraint>.  Дополнительные сведения об этих ограничениях по умолчанию см. в разделе [Ограничения DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 В следующем примере кода с помощью двух объектов <xref:System.Data.DataTable> в объекте <xref:System.Data.DataSet> создается объект **DataRelation**.  Каждая таблица <xref:System.Data.DataTable> содержит столбец **CustID**, который играет роль связи между двумя объектами <xref:System.Data.DataTable>.  В этом примере один объект **DataRelation** добавляется в коллекцию **Relations** объекта <xref:System.Data.DataSet>.  Первый аргумент в этом примере задает имя создаваемого объекта **DataRelation**.  Второй аргумент задает родительский столбец **DataColumn**, а третий аргумент задает дочерний столбец **DataColumn**.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 Объект **DataRelation** также имеет свойство **Nested**, которое при значении **true** делает строки из дочерней таблицы вложенными в связанную строку родительской таблицы, если они написаны как элементы XML при помощи <xref:System.Data.DataSet.WriteXml%2A>.  Для получения дополнительной информации см. [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## См. также  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)