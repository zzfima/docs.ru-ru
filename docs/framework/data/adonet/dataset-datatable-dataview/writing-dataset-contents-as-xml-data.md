---
title: Запись содержимого набора как данных XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: dae044a9d7802e858f1f24dd4aa0f1de8f6cba7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158956"
---
# <a name="writing-dataset-contents-as-xml-data"></a>Запись содержимого набора как данных XML
В ADO.NET можно записать XML-представление объекта <xref:System.Data.DataSet> вместе со схемой или без нее. Если информация схемы встраивается внутрь XML, она записываются на языке XSD. Схема содержит определения таблиц для <xref:System.Data.DataSet>, а также определения связей и ограничений.  
  
 Если <xref:System.Data.DataSet> записан как XML-данные, строки в <xref:System.Data.DataSet> записываются в своей текущей версии. Однако <xref:System.Data.DataSet> может быть записан как DiffGram, так что будут включены и текущие, и исходные данные строк.  
  
 XML-представление <xref:System.Data.DataSet> могут записываться в файл, поток, **XmlWriter**, или строка. Эти возможности обеспечивают большую гибкость способа переноса XML-представления для <xref:System.Data.DataSet>. Чтобы получить XML-представление <xref:System.Data.DataSet> как строку, используйте **GetXml** метод, как показано в следующем примере.  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 **GetXml** возвращает XML-представление <xref:System.Data.DataSet> без сведений о схеме. Для записи сведений о схеме из <xref:System.Data.DataSet> (в виде XML-схемы) в строку, используйте **GetXmlSchema**.  
  
 Для записи <xref:System.Data.DataSet> в файл, поток, или **XmlWriter**, использовать **WriteXml** метод. Первый параметр, передаваемый **WriteXml** — место назначения выходных данных XML. Например, передается строка, содержащая имя файла, **System.IO.TextWriter** объекта и т. д. Можно передать необязательный второй параметр **XmlWriteMode** для указания, как должны записываться выходные данные XML.  
  
 В следующей таблице показаны параметры для **XmlWriteMode**.  
  
|Параметр XmlWriteMode|Описание|  
|-------------------------|-----------------|  
|**IgnoreSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> как XML-данные, без схемы XML. Это значение по умолчанию.|  
|**WriteSchema**|Записывает текущее содержимое <xref:System.Data.DataSet> в виде XML-данных с реляционной структурой в виде встроенной схемы XML.|  
|**DiffGram**|Записывает весь <xref:System.Data.DataSet> как DiffGram, включая исходные и текущие значения. Дополнительные сведения см. в разделе [дельт](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
  
 При записи XML-представление <xref:System.Data.DataSet> , содержащий **DataRelation** объектов, вы, вероятно, пожелают результирующем XML-КОДЕ дочерние строки для каждой связи были вложены в соответствующие родительские элементы. Для этого необходимо задать **Nested** свойство **DataRelation** для **true** при добавлении **DataRelation** для <xref:System.Data.DataSet>. Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
 Далее даются два примера того, как записать в файл XML-представление для <xref:System.Data.DataSet>. Первый пример передает имя файла для итогового XML как строку **WriteXml**. Во втором примере передается **System.IO.StreamWriter** объекта.  
  
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
 Можно указать, как столбец таблицы представляется в XML с помощью **ColumnMapping** свойство **DataColumn** объекта. В следующей таблице показаны различные **MappingType** значений в параметре **ColumnMapping** свойства столбца таблицы и получаемый код XML.  
  
|Значение MappingType|Описание|  
|-----------------------|-----------------|  
|**Элемент**|Это значение по умолчанию. Столбец записывается как XML-элемент, где ColumnName - имя элемента, а содержимое столбца записывается как текст элемента. Пример:<br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**Атрибут**|Столбец записывается как XML-атрибут XML-элемента для текущей строки, где ColumnName - это имя атрибута, а содержимое столбца записывается как значение атрибута. Пример:<br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**SimpleContent**|Содержимое столбца записывается как текст в XML-элементе для текущей строки. Пример:<br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> Обратите внимание, что **SimpleContent** невозможно задать для столбца таблицы, имеющей **элемент** столбцы или вложенные связи.|  
|**Hidden**|Столбец не записывается в выводимый XML.|  
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [Вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [Запись сведений о схеме набора данных как XSD](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
