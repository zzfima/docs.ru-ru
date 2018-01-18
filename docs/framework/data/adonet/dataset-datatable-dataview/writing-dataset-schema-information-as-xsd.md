---
title: "Запись сведений о схеме набора данных как XSD"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bea961310c838068a54f15f7b05186ab56721dc2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="6b70d-102">Запись сведений о схеме набора данных как XSD</span><span class="sxs-lookup"><span data-stu-id="6b70d-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="6b70d-103">Можно записать схему набора данных <xref:System.Data.DataSet> в виде схемы на языке XSD, чтобы можно было передать ее в XML-документ с взаимосвязанными данными или без них.</span><span class="sxs-lookup"><span data-stu-id="6b70d-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="6b70d-104">XML-схемы, которые могут записываться в файл, поток, <xref:System.Xml.XmlWriter>, или строку; она может использоваться для создания строго типизированного **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6b70d-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="6b70d-105">Дополнительные сведения о строго типизированных **DataSet** объектов, в разделе [типизированных наборов данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="6b70d-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="6b70d-106">Можно указать, как столбец таблицы представляется в XML-схемы с помощью **ColumnMapping** свойство <xref:System.Data.DataColumn> объекта.</span><span class="sxs-lookup"><span data-stu-id="6b70d-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="6b70d-107">Дополнительные сведения см. в разделе «Сопоставления столбцов XML-элементы, атрибуты и текст» в [запись содержимого набора данных как XML-данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="6b70d-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="6b70d-108">Для записи схемы **набора данных** в виде схемы XML, в файл, поток, или **XmlWriter**, используйте **WriteXmlSchema** метод **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="6b70d-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="6b70d-109">**WriteXmlSchema** принимает один параметр, указывающий место назначения результирующей схемы XML.</span><span class="sxs-lookup"><span data-stu-id="6b70d-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="6b70d-110">В следующем примере кода демонстрируется способ записи схемы XML объекта **DataSet** в файл путем передачи строки, содержащей имя файла и <xref:System.IO.StreamWriter> объекта.</span><span class="sxs-lookup"><span data-stu-id="6b70d-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="6b70d-111">Для получения схемы объекта **DataSet** и ее записи в виде строки схемы XML, используйте **GetXmlSchema** метода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6b70d-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b70d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6b70d-112">See Also</span></span>  
 [<span data-ttu-id="6b70d-113">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="6b70d-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="6b70d-114">Запись содержимого DataSet как данных XML</span><span class="sxs-lookup"><span data-stu-id="6b70d-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="6b70d-115">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="6b70d-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="6b70d-116">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="6b70d-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="6b70d-117">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6b70d-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
