---
title: "Запись сведений схемы DataSet в виде XSD | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Запись сведений схемы DataSet в виде XSD
Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML\-документ с взаимосвязанными данными или без них.  Схема XML может быть записана в файл, поток, объект <xref:System.Xml.XmlWriter> или строку. Это удобно при создании объекта **DataSet** со строгой типизацией.  Дополнительные сведения о строго типизированных объектах **DataSet** см. в разделе [Типизированные объекты DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 С помощью свойства **ColumnMapping** объекта <xref:System.Data.DataColumn> можно задать способ представления столбца таблицы в схеме XML.  Дополнительные сведения см. в подразделе «Сопоставление столбцов с XML\- элементами, XML\-атрибутами и текстом» раздела [Запись содержимого DataSet в виде XML\-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Для записи схемы **DataSet** в файл, поток или объект **XmlWriter** в виде схемы XML следует использовать метод **WriteXmlSchema** объекта **DataSet**.  Метод **WriteXmlSchema** принимает один параметр, указывающий место назначения результирующей схемы XML.  В следующих примерах кода демонстрируется способ записи схемы XML объекта **DataSet** в файл путем передачи строки, содержащей имя файла, и объекта <xref:System.IO.StreamWriter>.  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 Для получения схемы объекта **DataSet** и ее записи в виде строки схемы XML следует использовать метод **GetXmlSchema**, как показано в следующем примере.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## См. также  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Запись содержимого DataSet в виде XML\-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)   
 [Типизированные объекты DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)