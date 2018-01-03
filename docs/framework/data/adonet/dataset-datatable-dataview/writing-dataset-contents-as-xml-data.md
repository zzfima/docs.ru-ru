---
title: "Запись содержимого набора как данных XML"
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
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c28dee75d5371da50dec1d3b73ec6c305176582
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="17456-102">Запись содержимого набора как данных XML</span><span class="sxs-lookup"><span data-stu-id="17456-102">Writing DataSet Contents as XML Data</span></span>
<span data-ttu-id="17456-103">В ADO.NET можно записать XML-представление объекта <xref:System.Data.DataSet> вместе со схемой или без нее.</span><span class="sxs-lookup"><span data-stu-id="17456-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="17456-104">Если информация схемы встраивается внутрь XML, она записываются на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="17456-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="17456-105">Схема содержит определения таблиц для <xref:System.Data.DataSet>, а также определения связей и ограничений.</span><span class="sxs-lookup"><span data-stu-id="17456-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="17456-106">Если <xref:System.Data.DataSet> записан как XML-данные, строки в <xref:System.Data.DataSet> записываются в своей текущей версии.</span><span class="sxs-lookup"><span data-stu-id="17456-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="17456-107">Однако <xref:System.Data.DataSet> может быть записан как DiffGram, так что будут включены и текущие, и исходные данные строк.</span><span class="sxs-lookup"><span data-stu-id="17456-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="17456-108">XML-представление <xref:System.Data.DataSet> могут записываться в файл, поток, **XmlWriter**, или строка.</span><span class="sxs-lookup"><span data-stu-id="17456-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="17456-109">Эти возможности обеспечивают большую гибкость способа переноса XML-представления для <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="17456-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="17456-110">Чтобы получить XML-представление <xref:System.Data.DataSet> как строку, используется **GetXml** метода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="17456-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="17456-111">**GetXml** возвращает XML-представление <xref:System.Data.DataSet> без данных схемы.</span><span class="sxs-lookup"><span data-stu-id="17456-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="17456-112">Для записи сведений о схеме из <xref:System.Data.DataSet> (в виде схемы XML) в строку используйте **GetXmlSchema**.</span><span class="sxs-lookup"><span data-stu-id="17456-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="17456-113">Для записи <xref:System.Data.DataSet> в файл, поток, или **XmlWriter**, используйте **WriteXml** метод.</span><span class="sxs-lookup"><span data-stu-id="17456-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="17456-114">Первый параметр, передаваемый **WriteXml** копируются выходные данные XML.</span><span class="sxs-lookup"><span data-stu-id="17456-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="17456-115">Например, передается строка, содержащая имя файла **System.IO.TextWriter** объекта и т. д.</span><span class="sxs-lookup"><span data-stu-id="17456-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="17456-116">Можно передать необязательный второй параметр **XmlWriteMode** для указания, как должны записываться выходные данные XML.</span><span class="sxs-lookup"><span data-stu-id="17456-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="17456-117">В следующей таблице показаны параметры для **XmlWriteMode**.</span><span class="sxs-lookup"><span data-stu-id="17456-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="17456-118">Параметр XmlWriteMode</span><span class="sxs-lookup"><span data-stu-id="17456-118">XmlWriteMode option</span></span>|<span data-ttu-id="17456-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="17456-119">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="17456-120">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="17456-120">**IgnoreSchema**</span></span>|<span data-ttu-id="17456-121">Записывает текущее содержимое <xref:System.Data.DataSet> как XML-данные, без схемы XML.</span><span class="sxs-lookup"><span data-stu-id="17456-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="17456-122">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17456-122">This is the default.</span></span>|  
|<span data-ttu-id="17456-123">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="17456-123">**WriteSchema**</span></span>|<span data-ttu-id="17456-124">Записывает текущее содержимое <xref:System.Data.DataSet> в виде XML-данных с реляционной структурой в виде встроенной схемы XML.</span><span class="sxs-lookup"><span data-stu-id="17456-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="17456-125">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="17456-125">**DiffGram**</span></span>|<span data-ttu-id="17456-126">Записывает весь <xref:System.Data.DataSet> как DiffGram, включая исходные и текущие значения.</span><span class="sxs-lookup"><span data-stu-id="17456-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="17456-127">Дополнительные сведения см. в разделе [дельты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="17456-127">For more information, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
  
 <span data-ttu-id="17456-128">При записи XML-представление <xref:System.Data.DataSet> , содержащий **DataRelation** объектов, скорее всего, вы будете результирующем XML-КОДЕ дочерние строки для каждой связи были вложены в соответствующие родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17456-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="17456-129">Чтобы сделать это, задайте **Nested** свойство **DataRelation** для **true** при добавлении **DataRelation** для <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="17456-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="17456-130">Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="17456-130">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="17456-131">Далее даются два примера того, как записать в файл XML-представление для <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="17456-131">Following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="17456-132">Первый пример передает имя файла для результирующего XML как строка, **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="17456-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="17456-133">Во втором примере передается **System.IO.StreamWriter** объекта.</span><span class="sxs-lookup"><span data-stu-id="17456-133">The second example passes a **System.IO.StreamWriter** object.</span></span>  
  
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
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="17456-134">Сопоставление столбцов с XML-элементами, атрибутами и текстом</span><span class="sxs-lookup"><span data-stu-id="17456-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  
 <span data-ttu-id="17456-135">Можно указать, как столбец таблицы представляется в формате XML с помощью **ColumnMapping** свойство **DataColumn** объекта.</span><span class="sxs-lookup"><span data-stu-id="17456-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="17456-136">В следующей таблице показаны различные **MappingType** значения для **ColumnMapping** свойство столбца таблицы, а результирующий XML.</span><span class="sxs-lookup"><span data-stu-id="17456-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="17456-137">Значение MappingType</span><span class="sxs-lookup"><span data-stu-id="17456-137">MappingType value</span></span>|<span data-ttu-id="17456-138">Описание:</span><span class="sxs-lookup"><span data-stu-id="17456-138">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="17456-139">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="17456-139">**Element**</span></span>|<span data-ttu-id="17456-140">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="17456-140">This is the default.</span></span> <span data-ttu-id="17456-141">Столбец записывается как XML-элемент, где ColumnName - имя элемента, а содержимое столбца записывается как текст элемента.</span><span class="sxs-lookup"><span data-stu-id="17456-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="17456-142">Пример:</span><span class="sxs-lookup"><span data-stu-id="17456-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="17456-143">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="17456-143">**Attribute**</span></span>|<span data-ttu-id="17456-144">Столбец записывается как XML-атрибут XML-элемента для текущей строки, где ColumnName - это имя атрибута, а содержимое столбца записывается как значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="17456-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="17456-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="17456-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="17456-146">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="17456-146">**SimpleContent**</span></span>|<span data-ttu-id="17456-147">Содержимое столбца записывается как текст в XML-элементе для текущей строки.</span><span class="sxs-lookup"><span data-stu-id="17456-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="17456-148">Пример:</span><span class="sxs-lookup"><span data-stu-id="17456-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="17456-149">Обратите внимание, что **SimpleContent** нельзя задать для столбца таблицы, которая имеет **элемент** столбцы или вложенные связи.</span><span class="sxs-lookup"><span data-stu-id="17456-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="17456-150">**Скрытые**</span><span class="sxs-lookup"><span data-stu-id="17456-150">**Hidden**</span></span>|<span data-ttu-id="17456-151">Столбец не записывается в выводимый XML.</span><span class="sxs-lookup"><span data-stu-id="17456-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17456-152">См. также</span><span class="sxs-lookup"><span data-stu-id="17456-152">See Also</span></span>  
 [<span data-ttu-id="17456-153">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="17456-153">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="17456-154">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="17456-154">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [<span data-ttu-id="17456-155">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="17456-155">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="17456-156">Запись сведений о схеме DataSet как XSD</span><span class="sxs-lookup"><span data-stu-id="17456-156">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)  
 [<span data-ttu-id="17456-157">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="17456-157">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="17456-158">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="17456-158">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
