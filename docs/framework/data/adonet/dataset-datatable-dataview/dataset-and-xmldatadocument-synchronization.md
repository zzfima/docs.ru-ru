---
title: Синхронизация набора данных и XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: ea597d7caca3174b17ce16a1e9d70c022e3e75c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879818"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="722d8-102">Синхронизация набора данных и XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="722d8-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="722d8-103">ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных.</span><span class="sxs-lookup"><span data-stu-id="722d8-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="722d8-104">Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="722d8-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="722d8-105">Исторически эти два представления данных использовались раздельно.</span><span class="sxs-lookup"><span data-stu-id="722d8-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="722d8-106">Тем не менее, платформа .NET обеспечивает динамический синхронный доступ реляционные и иерархические представления данных с помощью **набора данных** объекта и <xref:System.Xml.XmlDataDocument> соответственно.</span><span class="sxs-lookup"><span data-stu-id="722d8-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="722d8-107">Когда **набора данных** синхронизируется с **XmlDataDocument**, оба они работают с одного набора данных.</span><span class="sxs-lookup"><span data-stu-id="722d8-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="722d8-108">Это означает, что если изменения были сделаны **набора данных**, это изменение будет отражено в **XmlDataDocument**и наоборот.</span><span class="sxs-lookup"><span data-stu-id="722d8-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="722d8-109">Связь между **набора данных** и **XmlDataDocument** создает большую гибкость, позволяя одного приложения, использование одного набора данных, для доступа к полный комплект служб на основе вокруг **набора данных** (например, элементы управления Web Forms и Windows Forms и конструкторы Visual Studio .NET), а также набор служб XML, включая Extensible Stylesheet Language (XSL), путь к XML и XSL Transformations (XSLT) Язык (XPath).</span><span class="sxs-lookup"><span data-stu-id="722d8-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="722d8-110">Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.</span><span class="sxs-lookup"><span data-stu-id="722d8-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="722d8-111">Существует несколько способов, которые можно синхронизировать **набора данных** с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="722d8-112">Можно выполнить следующие действия: </span><span class="sxs-lookup"><span data-stu-id="722d8-112">You can:</span></span>  
  
- <span data-ttu-id="722d8-113">Заполнение **набора данных** со схемой (то есть, реляционной структурой) и данных, а затем синхронизировать его с новым **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="722d8-114">Это обеспечивает иерархическое представление существующих реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="722d8-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="722d8-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="722d8-115">For example:</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema and data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema and data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    ```  
  
- <span data-ttu-id="722d8-116">Заполнение **набора данных** только со схемой (например, строго типизированным **набора данных**), синхронизируйте его с **XmlDataDocument**, а затем загрузить  **XmlDataDocument** из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="722d8-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="722d8-117">Это обеспечивает реляционное представление существующих иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="722d8-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="722d8-118">Имена таблиц и имена столбцов в вашей **набора данных** схемы должны совпадать с именами XML-элементов, которые вы их нужно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="722d8-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="722d8-119">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="722d8-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="722d8-120">Обратите внимание, что схема **набора данных** должна соответствовать XML-элементов, которые вы хотите предоставить в реляционном представлении только.</span><span class="sxs-lookup"><span data-stu-id="722d8-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="722d8-121">Таким образом, может существовать очень большой XML-документ и очень малое реляционное «окно» для этого документа.</span><span class="sxs-lookup"><span data-stu-id="722d8-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="722d8-122">**XmlDataDocument** сохраняет весь документ XML, даже если **набора данных** предоставляет только небольшая часть.</span><span class="sxs-lookup"><span data-stu-id="722d8-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="722d8-123">(Подробный пример этого см. в разделе [синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="722d8-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="722d8-124">В следующем примере кода показаны действия по созданию **набора данных** и заполнения его схемы, а затем его синхронизации с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="722d8-125">Обратите внимание, что **набора данных** схема должна соответствовать только элементы из **XmlDataDocument** , которому требуется предоставить доступ с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
    ```vb  
    Dim dataSet As DataSet = New DataSet  
  
    ' Add code here to populate the DataSet with schema, but not data.  
  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    DataSet dataSet = new DataSet();  
  
    // Add code here to populate the DataSet with schema, but not data.  
  
    XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
     <span data-ttu-id="722d8-126">Не удается загрузить **XmlDataDocument** Если синхронизируется с **набора данных** , содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="722d8-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="722d8-127">В таком случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="722d8-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="722d8-128">Создайте новый **XmlDataDocument** и загрузить его из XML-документа и затем получить доступ к реляционному представлению данных с помощью **набора данных** свойство **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="722d8-129">Необходимо задать схему **набора данных** перед просмотром данных в **XmlDataDocument** с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="722d8-130">Опять же, имена таблиц и имена столбцов в вашей **набора данных** схемы должны совпадать с именами XML-элементов, которые вы их нужно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="722d8-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="722d8-131">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="722d8-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="722d8-132">В следующем примере кода показано, как получить доступ к реляционному представлению данных в **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
    ```vb  
    Dim xmlDoc As XmlDataDocument = New XmlDataDocument  
    Dim dataSet As DataSet = xmlDoc.DataSet  
  
    ' Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml")  
    ```  
  
    ```csharp  
    XmlDataDocument xmlDoc = new XmlDataDocument();  
    DataSet dataSet = xmlDoc.DataSet;  
  
    // Add code here to create the schema of the DataSet to view the data.  
  
    xmlDoc.Load("XMLDocument.xml");  
    ```  
  
 <span data-ttu-id="722d8-133">Еще одно преимущество синхронизации **XmlDataDocument** с **набора данных** является, то сохраняется точность XML-документа.</span><span class="sxs-lookup"><span data-stu-id="722d8-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="722d8-134">Если **набора данных** заполняется из XML-документа с помощью **ReadXml**, когда данные записываются обратно в XML-документа с помощью **WriteXml** может значительно отличаться от исходный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="722d8-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="722d8-135">Это обусловлено **набора данных** не сохраняет элементов форматирования, например пробелы или иерархических данных, например порядок элементов, из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="722d8-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="722d8-136">**Набора данных** также не содержит элементы из XML-документа, которые были пропущены, поскольку они не соответствует схеме **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="722d8-137">Синхронизация **XmlDataDocument** с **набора данных** позволяет форматирование и иерархическую структуру элементов исходного XML-документа в **XmlDataDocument**, хотя **набора данных** содержит только данные и схему сведения, относящиеся к **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="722d8-138">При синхронизации **набора данных** с **XmlDataDocument**, результаты могут отличаться в зависимости от того, нужно ли вашей <xref:System.Data.DataRelation> объекты являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="722d8-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="722d8-139">Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="722d8-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="722d8-140">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="722d8-140">In This Section</span></span>  
 [<span data-ttu-id="722d8-141">Синхронизация DataSet с XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="722d8-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="722d8-142">Демонстрирует синхронизацию строго типизированный **набора данных**, с минимальной схемой, с помощью **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="722d8-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="722d8-143">Выполнение запроса XPath к DataSet</span><span class="sxs-lookup"><span data-stu-id="722d8-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="722d8-144">Демонстрирует выполнение запроса XPath на содержание **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="722d8-145">Применение преобразования XSLT к DataSet</span><span class="sxs-lookup"><span data-stu-id="722d8-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="722d8-146">Демонстрирует применение преобразования XSLT к содержимому **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="722d8-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="722d8-147">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="722d8-147">Related Sections</span></span>  
 [<span data-ttu-id="722d8-148">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="722d8-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="722d8-149">Описывает способ **набора данных** взаимодействие с XML в качестве источника данных, включая загрузку и сохранение содержимого **набора данных** как XML-данных.</span><span class="sxs-lookup"><span data-stu-id="722d8-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="722d8-150">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="722d8-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="722d8-151">Обсуждается важность вложенных **DataRelation** объектов при представлении содержимого **набора данных** как XML-данных и описывается создание этих связей.</span><span class="sxs-lookup"><span data-stu-id="722d8-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="722d8-152">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="722d8-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="722d8-153">Описывает **набора данных** и способы ее использования для управления данными приложения и взаимодействия с источниками данных, включая реляционные базы данных и XML.</span><span class="sxs-lookup"><span data-stu-id="722d8-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="722d8-154">Содержит справочную информацию о **XmlDataDocument** класса.</span><span class="sxs-lookup"><span data-stu-id="722d8-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="722d8-155">См. также</span><span class="sxs-lookup"><span data-stu-id="722d8-155">See also</span></span>

- [<span data-ttu-id="722d8-156">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="722d8-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
