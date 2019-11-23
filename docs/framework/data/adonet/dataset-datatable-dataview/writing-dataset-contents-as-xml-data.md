---
title: Запись содержимого набора как данных XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: 9a63e79b2fce137ba9d21db861850a471cb42b9f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833968"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Запись содержимого набора как данных XML
В ADO.NET можно записать XML-представление объекта <xref:System.Data.DataSet> вместе со схемой или без нее. Если информация схемы встраивается внутрь XML, она записываются на языке XSD. Схема содержит определения таблиц для <xref:System.Data.DataSet>, а также определения связей и ограничений.  
  
 Если <xref:System.Data.DataSet> записан как XML-данные, строки в <xref:System.Data.DataSet> записываются в своей текущей версии. Однако <xref:System.Data.DataSet> может быть записан как DiffGram, так что будут включены и текущие, и исходные данные строк.  
  
 XML-представление <xref:System.Data.DataSet> может быть записано в файл, в поток, в **XmlWriter**или в строку. Эти возможности обеспечивают большую гибкость способа переноса XML-представления для <xref:System.Data.DataSet>. Чтобы получить XML-представление <xref:System.Data.DataSet> в виде строки, используйте метод **getXML** , как показано в следующем примере.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXML** возвращает XML-представление <xref:System.Data.DataSet> без сведений о схеме. Чтобы записать сведения о схеме из <xref:System.Data.DataSet> (в виде XML-схемы) в строку **, используйте параметр**GetSchema.  
  
 Чтобы записать <xref:System.Data.DataSet> в файл, поток или **XmlWriter**, используйте метод **WriteXml** . Первым параметром, который передается в **WriteXml** , является назначение выходных данных в формате XML. Например, передайте строку, содержащую имя файла, объект **System. IO. TextWriter** и т. д. Можно передать необязательный второй параметр **ксмлвритемоде** , чтобы указать способ записи выходных данных XML.  
  
 В следующей таблице показаны параметры для **ксмлвритемоде**.  
  
|Параметр XmlWriteMode|Описание|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> как XML-данные, без схемы XML. Это значение по умолчанию.|  
|**WriteSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> в виде XML-данных с реляционной структурой в виде встроенной схемы XML.|  
|**DiffGram**|Записывает весь <xref:System.Data.DataSet> как DiffGram, включая исходные и текущие значения. Дополнительные сведения см. в разделе [дельтами](diffgrams.md).|  
  
 При записи XML-представления <xref:System.Data.DataSet>, содержащего объекты **DataRelation** , скорее всего потребуется, чтобы РЕЗУЛЬТИРУЮЩий XML содержал дочерние строки каждой связи, вложенные в соответствующие им родительские элементы. Для этого присвойте свойству **Nested** объекта **DataRelation** значение **true** при добавлении объекта **DataRelation** в <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [вложенность связей](nesting-datarelations.md)данных.  
  
 Ниже приведены два примера того, как записать XML-представление <xref:System.Data.DataSet> в файл. В первом примере имя файла для результирующего XML передается в **WriteXml**в виде строки. Во втором примере передается объект **System. IO. StreamWriter** .
  
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
 Можно указать способ представления столбца таблицы в XML с помощью свойства **ColumnMapping** объекта **DataColumn** . В следующей таблице показаны различные значения **MappingType** для свойства **ColumnMapping** столбца таблицы и результирующий XML.  
  
|Значение MappingType|Описание|  
|-----------------------|-----------------|  
|**Элемент**|Это значение по умолчанию. Столбец записывается как XML-элемент, где ColumnName - имя элемента, а содержимое столбца записывается как текст элемента. Например:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Атрибут**|Столбец записывается как XML-атрибут XML-элемента для текущей строки, где ColumnName - это имя атрибута, а содержимое столбца записывается как значение атрибута. Например:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Содержимое столбца записывается как текст в XML-элементе для текущей строки. Например:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Обратите внимание, что значение **SimpleContent** не может быть задано для столбца таблицы, имеющей столбцы **элементов** или вложенные отношения.|  
|**Служеб**|Столбец не записывается в выводимый XML.|  
  
## <a name="see-also"></a>См. также:

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [Вложенность объектов DataRelation](nesting-datarelations.md)
- [Запись сведений о схеме DataSet как XSD](writing-dataset-schema-information-as-xsd.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
