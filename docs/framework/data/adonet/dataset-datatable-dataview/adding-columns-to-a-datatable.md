---
title: "Добавление столбцов к DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Добавление столбцов к DataTable
<xref:System.Data.DataTable> содержит коллекцию объектов <xref:System.Data.DataColumn>, на которые ссылается свойство **Columns** таблицы.  Эта коллекция столбцов наряду с ограничениями определяет схему, или структуру, таблицы.  
  
 Создаются объекты **DataColumn** в таблице, используя конструктор **DataColumn** или вызывая метод **Add** свойства **Columns** таблицы, которая является объектом <xref:System.Data.DataColumnCollection>.  Метод **Add** принимает необязательные аргументы **ColumnName**, **DataType** и **Expression** и создает новый **DataColumn** как член коллекции.  Он также принимает существующий объект **DataColumn** и добавляет его в коллекцию, а также возвращает ссылку на добавленный **DataColumn**, если требуется.  Так как объекты **DataTable** не являются специфичными для какого\-либо источника данных, типы .NET Framework используются при задании типов данных для **DataColumn**.  
  
 В следующем примере добавляются четыре столбца к объекту **DataTable**.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 Обратите внимание, что в данном примере свойства для столбца **CustID** установлены так, что не позволяют значениям **DBNull** и значениям ограничений быть уникальными.  Но если столбец **CustID** определяется как столбец первичного ключа таблицы, свойство **AllowDBNull** будет автоматически установлено в **false**, а свойство **Unique** будет автоматически установлено в **true**.  Для получения дополнительной информации см. [Определение первичных ключей](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
> [!CAUTION]
>  Если для столбца не предоставляется имя, ему присваивается имя по умолчанию Column*N* с увеличивающимся суффиксом N, начиная с «Column1», когда столбец добавляется в **DataColumnCollection**.  При предоставлении имени столбца мы рекомендуем избегать такого соглашения об именах, как «Column*N*», т. к. предоставляемое имя может вступить в конфликт с существующим именем по умолчанию столбца в **DataColumnCollection**.  Если указанное имя уже существует, вызывается исключение.  
  
 Если элемент <xref:System.Xml.XLinq.XElement> используется в качестве <xref:System.Data.DataColumn.DataType%2A> объекта <xref:System.Data.DataColumn> в <xref:System.Data.DataTable>, то XML\-сериализация не будет работать при считывании данных.  Например, если документ <xref:System.Xml.XmlDocument> записывается методом `DataTable.WriteXml`, то во время сериализации в XML\-код создается дополнительный родительский узел в элементе <xref:System.Xml.XLinq.XElement>.  Чтобы избежать этой проблемы, используйте тип <xref:System.Data.SqlTypes.SqlXml> вместо <xref:System.Xml.XLinq.XElement>.  Методы `ReadXml` и `WriteXml` правильно работают с <xref:System.Data.SqlTypes.SqlXml>.  
  
## См. также  
 <xref:System.Data.DataColumn>   
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataTable>   
 [Определение схемы DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)