---
title: Запись сведений о схеме набора данных как XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 2a59a9fc1c3b2f52543f4cc69de22a5703fa9b8b
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862778"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="49491-102">Запись сведений о схеме набора данных как XSD</span><span class="sxs-lookup"><span data-stu-id="49491-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="49491-103">Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML-документ с взаимосвязанными данными или без них.</span><span class="sxs-lookup"><span data-stu-id="49491-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="49491-104">XML-схемы могут записываться в файл, поток, <xref:System.Xml.XmlWriter>, или строку; это полезно для создания строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="49491-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="49491-105">Дополнительные сведения о строго типизированных **набора данных** объектов, см. в разделе [типизированных наборов DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="49491-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="49491-106">Можно указать, как столбец таблицы представляется в XML-схемы с помощью **ColumnMapping** свойство <xref:System.Data.DataColumn> объекта.</span><span class="sxs-lookup"><span data-stu-id="49491-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="49491-107">Дополнительные сведения см. в разделе «Сопоставление столбцов с XML-элементов, атрибутов и текст» в [запись содержимого набора данных как XML-данные](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="49491-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="49491-108">Чтобы записать схему набора **набора данных** виде схемы XML, в файл, поток, или **XmlWriter**, использовать **WriteXmlSchema** метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="49491-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="49491-109">**WriteXmlSchema** принимает один параметр, указывающий место назначения результирующей схемы XML.</span><span class="sxs-lookup"><span data-stu-id="49491-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="49491-110">В следующих примерах кода показано, как для записи XML-схемы **набора данных** в файл, передав строку, содержащую имя файла и <xref:System.IO.StreamWriter> объекта.</span><span class="sxs-lookup"><span data-stu-id="49491-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="49491-111">Для получения схемы объекта **набора данных** и его записи в виде строки схемы XML, используйте **GetXmlSchema** метод, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="49491-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="49491-112">См. также</span><span class="sxs-lookup"><span data-stu-id="49491-112">See Also</span></span>  
 [<span data-ttu-id="49491-113">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="49491-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="49491-114">Запись содержимого DataSet как данных XML</span><span class="sxs-lookup"><span data-stu-id="49491-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="49491-115">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="49491-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="49491-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="49491-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="49491-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="49491-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
