---
title: "Запись содержимого набора как данных XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Запись содержимого набора как данных XML
В ADO.NET можно записать XML-представление <xref:System.Data.DataSet>, со схемой или без нее. Если информация схемы встраивается внутрь XML, она записываются на языке XSD. Схема содержит определения таблиц для <xref:System.Data.DataSet> а также определения связей и ограничений.  
  
 При <xref:System.Data.DataSet> записывается как XML-данные, строки в <xref:System.Data.DataSet> записываются в своей текущей версии. Тем не менее <xref:System.Data.DataSet> может быть записан как DiffGram, чтобы текущий и исходные значения строки будут включены.  
  
 XML-представление <xref:System.Data.DataSet> могут записываться в файл, поток, **XmlWriter**, или строку. Эти возможности обеспечивают большую гибкость способа переноса XML-представление <xref:System.Data.DataSet>. Чтобы получить XML-представление <xref:System.Data.DataSet> как строка, используйте **GetXml** метода, как показано в следующем примере.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** возвращает XML-представление <xref:System.Data.DataSet> без сведений о схеме. Для записи сведений о схеме из <xref:System.Data.DataSet> (в виде схемы XML) в строку используйте **GetXmlSchema**.  
  
 Для записи <xref:System.Data.DataSet> в файл, поток, или **XmlWriter**, используйте **WriteXml** метод. Первый параметр, передаваемый **WriteXml** место назначения вывода XML. Например, передается строка, содержащая имя файла **System.IO.TextWriter** объекта и т. д. Можно передать необязательный второй параметр **XmlWriteMode** чтобы указать, как должны быть записаны выходные данные XML.  
  
 Ниже приведены параметры для **XmlWriteMode**.  
  
|Параметр XmlWriteMode|Описание|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> как XML-данных без схемы XML. Это значение по умолчанию.|  
|**WriteSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> как XML-данных с реляционной структурой в виде встроенной схемы XML.|  
|**DiffGram**|Записывает весь <xref:System.Data.DataSet> как DiffGram, включая исходные и текущие значения. Дополнительные сведения см. в разделе [дельты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 При записи XML-представление <xref:System.Data.DataSet> , содержащий **DataRelation** объектов, вы скорее всего понадобятся результирующий XML дочерние строки для каждой связи были вложены в соответствующие родительские элементы. Для этого задайте **Nested** свойство **DataRelation** для **true** при добавлении **DataRelation** для <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 Ниже приведены два примера создания XML-представление <xref:System.Data.DataSet> в файл. В первом примере имя файла для результирующего XML передается как строка, **WriteXml**. Во втором примере передается **System.IO.StreamWriter** объекта.  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a>Сопоставление столбцов с XML-элементами, атрибутами и текстом  
 Можно указать, как столбец таблицы представляется в формате XML с помощью **ColumnMapping** свойство **DataColumn** объекта. В следующей таблице показаны различные **MappingType** значения для **ColumnMapping** свойство столбца таблицы, а результирующий XML.  
  
|Значение MappingType|Описание|  
|-----------------------|-----------------|  
|**Элемент**|Это значение по умолчанию. Столбец записывается как XML-элемент, где ColumnName - имя элемента, а содержимое столбца записывается как текст элемента. Пример:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Атрибут**|Столбец записывается как XML-атрибут XML-элемента для текущей строки, где ColumnName - это имя атрибута, а содержимое столбца записывается как значение атрибута. Например:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Содержимое столбца записывается как текст в XML-элементе для текущей строки. Пример:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Обратите внимание, что **SimpleContent** нельзя задать для столбца таблицы, которая имеет **элемент** столбцы или вложенные связи.|  
|**Скрытые**|Столбец не записывается в выводимый XML.|  
  
## <a name="see-also"></a>См. также  
 [Использование XML в набор данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Дельты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Запись сведений о схеме набора данных как XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)   
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Управляемые поставщики ADO.NET и Центр разработчиков DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)