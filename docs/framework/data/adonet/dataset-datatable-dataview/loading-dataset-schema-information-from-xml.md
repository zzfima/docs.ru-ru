---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151056"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="eef5a-102">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="eef5a-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="eef5a-103">Схема <xref:System.Data.DataSet> a (ее таблицы, столбцы, связи и ограничения) может быть определена программно, создана методами <xref:System.Data.Common.DataAdapter> **заполнения** или **заполнения,** или загружена из документа XML.</span><span class="sxs-lookup"><span data-stu-id="eef5a-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="eef5a-104">Для загрузки информации о схеме **DataSet** из документа XML можно использовать либо **ReadXmlSchema,** либо метод **InferXmlSchema** **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="eef5a-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="eef5a-105">**ReadXmlSchema** позволяет загружать или выгонить информацию о схеме **DataSet** из документа, содержащего схему определения XML Schema (XSD) или документ XML с inline XML Schema.</span><span class="sxs-lookup"><span data-stu-id="eef5a-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="eef5a-106">**InferXmlSchema** позволяет вывести схему из документа XML, игнорируя некоторые указанные пространства имен XML.</span><span class="sxs-lookup"><span data-stu-id="eef5a-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eef5a-107">Заказ таблицы в **DataSet** может быть не сохранен при использовании Web-сервисов или сериализации XML для передачи **DataSet,** созданного в памяти с помощью конструкций XSD (например, вложенных связей).</span><span class="sxs-lookup"><span data-stu-id="eef5a-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="eef5a-108">Таким образом, получатель **DataSet** не должен зависеть от заказа таблицы в этом случае.</span><span class="sxs-lookup"><span data-stu-id="eef5a-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="eef5a-109">Однако заказ таблицвсегдасохраняется, если схема передачи **DataSet** была прочитана из файлов XSD, а не создавалась в памяти.</span><span class="sxs-lookup"><span data-stu-id="eef5a-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="eef5a-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="eef5a-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="eef5a-111">Для загрузки схемы **DataSet** из документа XML без загрузки данных можно использовать метод **ReadXmlSchema** **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="eef5a-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="eef5a-112">**ReadXmlSchema** создает схему **DataSet,** определяемую с помощью схемы определения XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="eef5a-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="eef5a-113">Метод **ReadXmlSchema** требует загрузки одного аргумента имени файла, потока или **XmlReader,** содержащего xML-документ.</span><span class="sxs-lookup"><span data-stu-id="eef5a-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="eef5a-114">XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные.</span><span class="sxs-lookup"><span data-stu-id="eef5a-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="eef5a-115">Подробнее о написании встроенной схемы xML Schema можно узнать из [XML Schema (XSD).](deriving-dataset-relational-structure-from-xml-schema-xsd.md)</span><span class="sxs-lookup"><span data-stu-id="eef5a-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="eef5a-116">Если документ XML, переданный **ReadXmlSchema,** не содержит информации о вливной схеме, **ReadXmlSchema** выдвинет схему из элементов в документе XML.</span><span class="sxs-lookup"><span data-stu-id="eef5a-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="eef5a-117">Если **DataSet** уже содержит схему, текущая схема будет расширена путем добавления новых таблиц, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="eef5a-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="eef5a-118">Новые столбцы не будут добавляться к существующим таблицам.</span><span class="sxs-lookup"><span data-stu-id="eef5a-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="eef5a-119">Если добавленная колонка уже существует в **DataSet,** но имеет несовместимый тип с столбцом, найденным в XML, выбрасывается исключение.</span><span class="sxs-lookup"><span data-stu-id="eef5a-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="eef5a-120">Подробную информацию о том, как **ReadXmlSchema** выносит схему из документа XML, [см. Вывод о соотношении DataSet от XML.](inferring-dataset-relational-structure-from-xml.md)</span><span class="sxs-lookup"><span data-stu-id="eef5a-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="eef5a-121">Хотя **ReadXmlSchema** загружает или выносит только схему **DataSet,** метод **ReadXml** **DataSet** загружает или выносит как схему, так и данные, содержащиеся в документе XML.</span><span class="sxs-lookup"><span data-stu-id="eef5a-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="eef5a-122">Для получения дополнительной информации [см. Загрузка Набора данных из XML](loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="eef5a-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="eef5a-123">Следующие примеры кода показывают, как загрузить схему **DataSet** из документа или потока XML.</span><span class="sxs-lookup"><span data-stu-id="eef5a-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="eef5a-124">На первом примере показано, что имя файла XML Schema передается методу **ReadXmlSchema.**</span><span class="sxs-lookup"><span data-stu-id="eef5a-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="eef5a-125">Второй пример показывает **System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="eef5a-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a><span data-ttu-id="eef5a-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="eef5a-126">InferXmlSchema</span></span>  
 <span data-ttu-id="eef5a-127">Можно также поручить **DataSet** сделать вывод о своей схеме из документа XML с помощью метода **InferXmlSchema** **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="eef5a-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="eef5a-128">**InferXmlSchema** функционирует так же, как и **ReadXml** с **XmlReadMode** **InferSchema** (загружает данные, а также выводы схемы), и **ReadXmlSchema,** если считывается документ не содержит водной схемы.</span><span class="sxs-lookup"><span data-stu-id="eef5a-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="eef5a-129">Тем не менее, **InferXmlSchema** предоставляет дополнительную возможность, позволяющую указывать определенные пространства имен XML, которые будут проигнорированы при выводе схемы.</span><span class="sxs-lookup"><span data-stu-id="eef5a-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="eef5a-130">**InferXmlSchema** принимает два необходимых аргумента: расположение документа XML, указанного именем файла, потоком или **XmlReader;** и строки массива XML пространства имен, которые будут проигнорированы операцией.</span><span class="sxs-lookup"><span data-stu-id="eef5a-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="eef5a-131">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="eef5a-131">For example, consider the following XML:</span></span>  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>
  <Description od:adotype="203">Soft drinks and teas</Description>
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>
  <ReorderLevel od:adotype="3">10</ReorderLevel>
  <Discontinued od:adotype="11">0</Discontinued>
</Products>  
</NewDataSet>  
```  
  
 <span data-ttu-id="eef5a-132">Из-за атрибутов, указанных для элементов в предыдущем документе XML, как метод **ReadXmlSchema,** так и метод **ReadXml** с **XmlReadMode** **of InferSchema** создадут таблицы для каждого элемента в документе: **Категории** **, CategoryID**, **CategoryName**, **Описание**, **Продукты,** **ProductID,** **ReorderLevel**, и **Прекращение**.</span><span class="sxs-lookup"><span data-stu-id="eef5a-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="eef5a-133">(Для получения дополнительной [информации см. Вывод на соотношения DataSet от XML.)](inferring-dataset-relational-structure-from-xml.md) Однако более подходящей структурой было бы создание только таблиц **категорий** и **продуктов,** а затем создание **categoryID,** **CategoryName**и столбцов **описания** в таблице **Категорий** и **ProductID,** **ReorderLevel**и **Discontinued** столбцы в таблице **Продуктов.**</span><span class="sxs-lookup"><span data-stu-id="eef5a-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="eef5a-134">Для обеспечения того, чтобы выведенная схема игнорировала атрибуты, указанные в элементах XML, используйте метод **InferXmlSchema** и укажите пространство имен XML для того, чтобы **данные officedata** были проигнорированы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="eef5a-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="eef5a-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="eef5a-135">See also</span></span>

- [<span data-ttu-id="eef5a-136">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="eef5a-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="eef5a-137">Наследование реляционной структуры набора данных от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="eef5a-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="eef5a-138">Определение реляционной структуры набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="eef5a-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="eef5a-139">Загрузка набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="eef5a-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="eef5a-140">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="eef5a-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="eef5a-141">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eef5a-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
