---
title: Загрузка набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151069"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="a7cb4-102">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="a7cb4-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="a7cb4-103">Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML-потока или XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="a7cb4-104">Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="a7cb4-105">Для заполнения <xref:System.Data.DataSet> данных xML используйте метод **ReadXml** <xref:System.Data.DataSet> объекта.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="a7cb4-106">Метод **ReadXml** читает из файла, потока или **XmlReader,** и принимает в качестве аргументов источник XML плюс дополнительный аргумент **XmlReadMode.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="a7cb4-107">Для получения дополнительной информации о **XmlReader,** [см. Чтение данных XML с XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7cb4-107">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="a7cb4-108">Метод **ReadXml** считывает содержимое потока xML или <xref:System.Data.DataSet> документа и загружает данные.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-108">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="a7cb4-109">Это также создаст реляционную <xref:System.Data.DataSet> схему в зависимости от **XmlReadMode** указаны и является ли реляционная схема уже существует.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-109">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="a7cb4-110">В следующей таблице описаны варианты аргумента **XmlReadMode.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-110">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="a7cb4-111">Параметр</span><span class="sxs-lookup"><span data-stu-id="a7cb4-111">Option</span></span>|<span data-ttu-id="a7cb4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a7cb4-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="a7cb4-113">**Автоматически**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-113">**Auto**</span></span>|<span data-ttu-id="a7cb4-114">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-114">This is the default.</span></span> <span data-ttu-id="a7cb4-115">Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-115">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="a7cb4-116">- Если XML является DiffGram, **DiffGram** используется.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-116">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="a7cb4-117">- Если <xref:System.Data.DataSet> содержит схему или XML содержит вливую схему, **используется ReadSchema.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-117">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="a7cb4-118">- Если <xref:System.Data.DataSet> не содержит схемы и XML не содержит вливую схему, используется **InferSchema.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-118">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="a7cb4-119">Если вы знаете формат чтения XML, для лучшей производительности рекомендуется установить явный **XmlReadMode**, а не принимать **Auto** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-119">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="a7cb4-120">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-120">**ReadSchema**</span></span>|<span data-ttu-id="a7cb4-121">Считывает любую встроенную схему и загружает данные и схему.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-121">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="a7cb4-122">Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-122">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a7cb4-123">Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-123">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="a7cb4-124">Вы не сможете изменить схему существующей таблицы с помощью **XmlReadMode.ReadSchema**.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-124">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="a7cb4-125">Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-125">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="a7cb4-126">Встроенная схема может быть определена с помощью схемы на языке XSD.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-126">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="a7cb4-127">Подробнее о написании встроенной схемы xML Schema можно узнать из [XML Schema (XSD).](deriving-dataset-relational-structure-from-xml-schema-xsd.md)</span><span class="sxs-lookup"><span data-stu-id="a7cb4-127">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="a7cb4-128">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-128">**IgnoreSchema**</span></span>|<span data-ttu-id="a7cb4-129">Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-129">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="a7cb4-130">Любые данные, не совпадающие с существующей схемой, удаляются.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-130">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="a7cb4-131">Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-131">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="a7cb4-132">Если данные DiffGram, **IgnoreSchema** имеет ту же функциональность, что и **DiffGram** *.*</span><span class="sxs-lookup"><span data-stu-id="a7cb4-132">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="a7cb4-133">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-133">**InferSchema**</span></span>|<span data-ttu-id="a7cb4-134">Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML-данных, а затем загружает данные.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-134">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="a7cb4-135">Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-135">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="a7cb4-136">Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-136">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="a7cb4-137">Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-137">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="a7cb4-138">Подробную информацию о том, как **ReadXmlSchema** выносит схему из документа XML, [см. Вывод о соотношении DataSet от XML.](inferring-dataset-relational-structure-from-xml.md)</span><span class="sxs-lookup"><span data-stu-id="a7cb4-138">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="a7cb4-139">**Diffgram**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-139">**DiffGram**</span></span>|<span data-ttu-id="a7cb4-140">Считывает данные DiffGram и добавляет их в текущую схему.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-140">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="a7cb4-141">**DiffGram** объединяет новые строки с существующими строками, где совпадают значения уникальных идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-141">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="a7cb4-142">См. подраздел «Слияние данных из XML» в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-142">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="a7cb4-143">Для получения дополнительной информации о DiffGrams, [см.](diffgrams.md)</span><span class="sxs-lookup"><span data-stu-id="a7cb4-143">For more information about DiffGrams, see [DiffGrams](diffgrams.md).</span></span>|  
|<span data-ttu-id="a7cb4-144">**Фрагмент**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-144">**Fragment**</span></span>|<span data-ttu-id="a7cb4-145">Продолжает считывание нескольких XML-фрагментов до достижения конца потока.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-145">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="a7cb4-146">Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-146">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="a7cb4-147">Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-147">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a7cb4-148">Если вы передаете **XmlReader** **на ReadXml,** который расположен часть пути в документ XML, **ReadXml** будет читать следующий узел элемента и будет рассматривать его как корневой элемент, читая до конца элемента узла только.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-148">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="a7cb4-149">Это не применяется, если вы **укажете XmlReadMode.Фрагмент**.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-149">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="a7cb4-150">Сущности DTD</span><span class="sxs-lookup"><span data-stu-id="a7cb4-150">DTD Entities</span></span>  
 <span data-ttu-id="a7cb4-151">Если XML содержит сущности, определенные в схеме определения типа документа (DTD), будет <xref:System.Data.DataSet> брошено исключение, если вы попытаетесь загрузить имя файла, поток или невалифицирующее **XmlReader** на **ReadXml.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-151">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="a7cb4-152">Вместо этого, вы должны создать **XmlValidatingReader**, с **EntityHandling** набор **EntityHandling.ExpandEntities**, и передать **XmlValidatingReader** **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-152">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="a7cb4-153">**XmlValidatingReader** расширит сущности до того, как будет прочитан <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-153">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="a7cb4-154">В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML-потока.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-154">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="a7cb4-155">Первый пример показывает, что имя файла передается методу **ReadXml.**</span><span class="sxs-lookup"><span data-stu-id="a7cb4-155">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="a7cb4-156">Во втором примере показана загрузка строки, содержащей XML-код, с помощью объекта <xref:System.IO.StringReader>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-156">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> <span data-ttu-id="a7cb4-157">Если вы называете **ReadXml** для загрузки очень большого файла, вы можете столкнуться с медленной производительностью.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-157">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="a7cb4-158">Чтобы обеспечить наилучшую производительность для **ReadXml**, на большом файле, позвоните метод <xref:System.Data.DataTable.BeginLoadData%2A> для каждой таблицы в <xref:System.Data.DataSet>, а затем вызов **ReadXml**.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-158">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="a7cb4-159">Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-159">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> <span data-ttu-id="a7cb4-160">Если схема XSD для <xref:System.Data.DataSet> вашего включает в себя **targetNamespace,** данные могут не быть прочитаны, <xref:System.Data.DataSet> и вы можете столкнуться с исключениями, при вызове **ReadXml** для загрузки с XML, который содержит элементы без квалификационного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-160">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="a7cb4-161">Чтобы прочитать неквалифицированные элементы в этом случае, установите **элементFormDefault,** равный «квалифицированной» в вашей схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-161">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="a7cb4-162">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7cb4-162">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="a7cb4-163">Слияние данных из XML</span><span class="sxs-lookup"><span data-stu-id="a7cb4-163">Merging Data from XML</span></span>  
 <span data-ttu-id="a7cb4-164">Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-164">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a7cb4-165">**ReadXml** не сливается с <xref:System.Data.DataSet> XML в любую информацию о строке с соответствующими первичными ключами.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-165">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="a7cb4-166">Чтобы перезаписать существующую информацию о строках с новой <xref:System.Data.DataSet>информацией <xref:System.Data.DataSet.Merge%2A> от <xref:System.Data.DataSet> XML, <xref:System.Data.DataSet>используйте **ReadXml** для создания нового, а затем нового в существующую.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-166">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a7cb4-167">Обратите внимание, что загрузка DiffGram с помощью **ReadXML** с **XmlReadMode** **DiffGram** объединит строки, которые имеют тот же уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="a7cb4-167">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7cb4-168">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7cb4-168">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a7cb4-169">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="a7cb4-169">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a7cb4-170">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="a7cb4-170">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="a7cb4-171">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="a7cb4-171">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="a7cb4-172">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="a7cb4-172">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a7cb4-173">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="a7cb4-173">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a7cb4-174">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="a7cb4-174">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a7cb4-175">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a7cb4-175">ADO.NET Overview</span></span>](../ado-net-overview.md)
