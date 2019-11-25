---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: d834f0c4517f4ff9fe8645257d5a947c03893881
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968395"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="b3355-102">Загрузка сведений о схеме набора данных из XML</span><span class="sxs-lookup"><span data-stu-id="b3355-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="b3355-103">Схема <xref:System.Data.DataSet> (ее таблиц, столбцов, связей и ограничений) может быть определена программным способом, созданными методами **Fill** или **FillSchema** <xref:System.Data.Common.DataAdapter>или загруженными из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="b3355-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="b3355-104">Чтобы загрузить сведения о схеме **набора данных** из XML-документа, можно использовать метод **ReadXmlSchema** или **инферксмлсчема** **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b3355-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b3355-105">**ReadXmlSchema** позволяет загружать или выводить сведения о схеме **набора данных** из документа, содержащего схему XSD, или XML-документ со встроенной схемой XML.</span><span class="sxs-lookup"><span data-stu-id="b3355-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="b3355-106">**Инферксмлсчема** позволяет вывести схему из XML-документа, игнорируя определенные заданное пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="b3355-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3355-107">Упорядочивание таблиц в **наборе данных** может не сохраняться при использовании веб-служб или сериализации XML для перемещения **набора данных** , созданного в памяти, с помощью конструкций XSD (например, вложенных связей).</span><span class="sxs-lookup"><span data-stu-id="b3355-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="b3355-108">Таким образом, получатель **набора данных** не должен зависеть от упорядочения таблиц в этом случае.</span><span class="sxs-lookup"><span data-stu-id="b3355-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="b3355-109">Однако порядок таблиц всегда сохраняется, если схема перемещаемого **набора данных** СЧИТЫВАЕТСЯ из XSD-файлов, а не создается в памяти.</span><span class="sxs-lookup"><span data-stu-id="b3355-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="b3355-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="b3355-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="b3355-111">Чтобы загрузить схему **набора данных** из XML-документа без загрузки данных, можно использовать метод **ReadXmlSchema** **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b3355-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b3355-112">**ReadXmlSchema** создает схему **набора данных** , определенную с помощью схемы языка определения схемы XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="b3355-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="b3355-113">Метод **ReadXmlSchema** принимает один аргумент имени файла, потока или **XmlReader** , содержащий XML-документ для загрузки.</span><span class="sxs-lookup"><span data-stu-id="b3355-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="b3355-114">XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные.</span><span class="sxs-lookup"><span data-stu-id="b3355-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="b3355-115">Дополнительные сведения о создании встроенной схемы в виде схемы XML см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="b3355-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="b3355-116">Если XML-документ, переданный в **ReadXmlSchema** , не содержит встроенных сведений о схеме, **ReadXmlSchema** будет выводить схему из элементов XML-документа.</span><span class="sxs-lookup"><span data-stu-id="b3355-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="b3355-117">Если **набор данных** уже содержит схему, то текущая схема будет расширена путем добавления новых таблиц, если они еще не существуют.</span><span class="sxs-lookup"><span data-stu-id="b3355-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="b3355-118">Новые столбцы не будут добавляться к существующим таблицам.</span><span class="sxs-lookup"><span data-stu-id="b3355-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="b3355-119">Если добавляемый столбец уже существует в **наборе данных** , но имеет несовместимый тип со столбцом, найденным в XML, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="b3355-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="b3355-120">Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, см. в разделе вывод [реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b3355-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="b3355-121">Хотя **ReadXmlSchema** загружает или выводит только схему **набора данных**, метод **ReadXml** **набора данных** загружает и определяет схему и данные, содержащиеся в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="b3355-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="b3355-122">Дополнительные сведения см. [в разделе Загрузка набора данных из XML](loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b3355-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="b3355-123">В следующих примерах кода показано, как загрузить схему **набора данных** из XML-документа или потока.</span><span class="sxs-lookup"><span data-stu-id="b3355-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="b3355-124">В первом примере показано имя файла схемы XML, передаваемое методу **ReadXmlSchema** .</span><span class="sxs-lookup"><span data-stu-id="b3355-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="b3355-125">Во втором примере показан объект **System. IO. StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="b3355-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="b3355-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="b3355-126">InferXmlSchema</span></span>  
 <span data-ttu-id="b3355-127">Также можно указать **набору данных** , что его схема будет изменяться из XML-документа с помощью метода **инферксмлсчема** **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="b3355-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="b3355-128">**Инферксмлсчема** функционирует так же, как и метода **ReadXml** с параметром **XmlReadMode** **инферсчема** (загружает данные и выводит схему), а **ReadXmlSchema** , если считываемый документ не содержит встроенной схемы.</span><span class="sxs-lookup"><span data-stu-id="b3355-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="b3355-129">Однако **инферксмлсчема** предоставляет дополнительную возможность, позволяющую указывать определенные пространства имен XML, которые будут игнорироваться при выводимой схеме.</span><span class="sxs-lookup"><span data-stu-id="b3355-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="b3355-130">**Инферксмлсчема** принимает два обязательных аргумента: расположение XML-документа, определяемое именем файла, потоком или **XmlReader**; и строковый массив пространств имен XML, которые будут игнорироваться операцией.</span><span class="sxs-lookup"><span data-stu-id="b3355-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="b3355-131">Например, рассмотрим следующий XML-код:</span><span class="sxs-lookup"><span data-stu-id="b3355-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="b3355-132">В связи с атрибутами, указанными для элементов в предыдущем XML-документе, метод **ReadXmlSchema** и метод **ReadXml** с параметром **XmlReadMode** **инферсчема** будут создавать таблицы для каждого элемента в документе: **категории**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**и больше не **поддерживаются**.</span><span class="sxs-lookup"><span data-stu-id="b3355-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="b3355-133">(Дополнительные сведения см. [в разделе выведение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md).) Однако более подходящей структурой является создание только таблиц **Categories** и **Products** , а затем создание столбцов **CategoryID**, **CategoryName**и **Description** в таблице **Categories** , а также столбцов **ProductID**, **ReorderLevel**и **неподдерживаемые** столбцы таблицы **Products** .</span><span class="sxs-lookup"><span data-stu-id="b3355-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="b3355-134">Чтобы убедиться, что выводимая схема не пропускает атрибуты, указанные в XML-элементах, используйте метод **инферксмлсчема** и укажите пространство имен XML для **оффицедата** , которое будет игнорироваться, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b3355-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3355-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b3355-135">See also</span></span>

- [<span data-ttu-id="b3355-136">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="b3355-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="b3355-137">Наследование реляционной структуры DataSet от схемы XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b3355-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="b3355-138">Определение реляционной структуры DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="b3355-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="b3355-139">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="b3355-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="b3355-140">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="b3355-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b3355-141">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b3355-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
