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
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="3e2f1-102">Запись сведений о схеме набора данных как XSD</span><span class="sxs-lookup"><span data-stu-id="3e2f1-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="3e2f1-103">Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML-документ с взаимосвязанными данными или без них.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="3e2f1-104">XML-схемы, которые могут записываться в файл, поток, <xref:System.Xml.XmlWriter>, или строку; она может использоваться для создания строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="3e2f1-105">Дополнительные сведения о строго типизированных **DataSet** объектов, в разделе [типизированных наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="3e2f1-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="3e2f1-106">Можно указать, как столбец таблицы представляется в XML-схемы с помощью **ColumnMapping** свойство <xref:System.Data.DataColumn> объекта.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="3e2f1-107">Дополнительные сведения см. в разделе «Сопоставления столбцов XML-элементы, атрибуты и текст» в [запись содержимого набора данных как XML-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="3e2f1-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="3e2f1-108">Для записи схемы **набора данных** в виде схемы XML, в файл, поток, или **XmlWriter**, используйте **WriteXmlSchema** метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="3e2f1-109">**WriteXmlSchema** принимает один параметр, указывающий место назначения результирующей схемы XML.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="3e2f1-110">В следующем примере кода демонстрируется способ записи схемы XML объекта **DataSet** в файл путем передачи строки, содержащей имя файла и <xref:System.IO.StreamWriter> объекта.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="3e2f1-111">Для получения схемы объекта **DataSet** и ее записи в виде строки схемы XML, используйте **GetXmlSchema** метода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3e2f1-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e2f1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3e2f1-112">See Also</span></span>  
 [<span data-ttu-id="3e2f1-113">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="3e2f1-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="3e2f1-114">Запись содержимого DataSet как данных XML</span><span class="sxs-lookup"><span data-stu-id="3e2f1-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="3e2f1-115">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="3e2f1-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="3e2f1-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="3e2f1-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="3e2f1-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3e2f1-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
