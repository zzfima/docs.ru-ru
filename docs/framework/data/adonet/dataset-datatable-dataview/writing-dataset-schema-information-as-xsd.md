---
title: Запись сведений о схеме набора данных как XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: b2012b32b0751bc093b9b3267cbbfc2e1a408156
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761003"
---
# <a name="writing-dataset-schema-information-as-xsd"></a>Запись сведений о схеме набора данных как XSD
Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML-документ с взаимосвязанными данными или без них. XML-схемы, которые могут записываться в файл, поток, <xref:System.Xml.XmlWriter>, или строку; она может использоваться для создания строго типизированного **набора данных**. Дополнительные сведения о строго типизированных **DataSet** объектов, в разделе [типизированных наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).  
  
 Можно указать, как столбец таблицы представляется в XML-схемы с помощью **ColumnMapping** свойство <xref:System.Data.DataColumn> объекта. Дополнительные сведения см. в разделе «Сопоставления столбцов XML-элементы, атрибуты и текст» в [запись содержимого набора данных как XML-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).  
  
 Для записи схемы **набора данных** в виде схемы XML, в файл, поток, или **XmlWriter**, используйте **WriteXmlSchema** метод **набора данных**. **WriteXmlSchema** принимает один параметр, указывающий место назначения результирующей схемы XML. В следующем примере кода демонстрируется способ записи схемы XML объекта **DataSet** в файл путем передачи строки, содержащей имя файла и <xref:System.IO.StreamWriter> объекта.  
  
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
  
 Для получения схемы объекта **DataSet** и ее записи в виде строки схемы XML, используйте **GetXmlSchema** метода, как показано в следующем примере.  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a>См. также  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Запись содержимого DataSet как данных XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [Типизированные наборы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
