---
title: Синхронизация набора данных и XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: cb16d4fae5dc153361fe2cb31cfd6af9b4b83c68
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="4ecdf-102">Синхронизация набора данных и XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="4ecdf-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="4ecdf-103">ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="4ecdf-104">Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="4ecdf-105">Исторически эти два представления данных использовались раздельно.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="4ecdf-106">Тем не менее, платформа .NET Framework обеспечивает динамический синхронный доступ в реляционном и иерархическом представлении данных с помощью **DataSet** объекта и <xref:System.Xml.XmlDataDocument> соответственно.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="4ecdf-107">Когда **DataSet** синхронизируется с **XmlDataDocument**, оба они работают с одним набором данных.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="4ecdf-108">Это означает, что при внесении изменений в **DataSet**, изменения будут отражены в **XmlDataDocument**и наоборот.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="4ecdf-109">Связь между **DataSet** и **XmlDataDocument** создает большую гибкость, позволяя одного приложения, использование одного набора данных, для доступа к полный набор служб, встроенных вокруг **набора данных** (такие как Web Forms и Windows Forms и конструкторов Visual Studio .NET), а также набор служб XML, включая Extensible Stylesheet Language (XSL), преобразованиям XSL (XSLT) и пути XML Language (XPath).</span><span class="sxs-lookup"><span data-stu-id="4ecdf-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="4ecdf-110">Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="4ecdf-111">Существует несколько способов, которые можно синхронизировать **DataSet** с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="4ecdf-112">Можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-112">You can:</span></span>  
  
-   <span data-ttu-id="4ecdf-113">Заполнение **DataSet** со схемой (то есть, реляционной структурой) и данными, а затем синхронизировать его с новым **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="4ecdf-114">Это обеспечивает иерархическое представление существующих реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="4ecdf-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="4ecdf-115">For example:</span></span>  
  
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
  
-   <span data-ttu-id="4ecdf-116">Заполнение **набора данных** только со схемой (например, строго типизированным **набора данных**), синхронизируйте его с **XmlDataDocument**и затем загружать  **XmlDataDocument** из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="4ecdf-117">Это обеспечивает реляционное представление существующих иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="4ecdf-118">Имена таблиц и имена столбцов в вашей **DataSet** схемы должны совпадать с именами элементов XML, то их нужно синхронизировать.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="4ecdf-119">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="4ecdf-120">Обратите внимание, что схема **набора данных** должна соответствовать XML-элементы, которые требуется предоставить в реляционное представление только.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="4ecdf-121">Таким образом, может существовать очень большой XML-документ и очень малое реляционное «окно» для этого документа.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="4ecdf-122">**XmlDataDocument** позволяет сохранить весь документ XML, даже если **DataSet** предоставляет только малую часть.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="4ecdf-123">(Пример этого см. в разделе [синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="4ecdf-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="4ecdf-124">В следующем примере кода показаны шаги создания **DataSet** и заполнения его схемы, а затем его синхронизации с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="4ecdf-125">Обратите внимание, что **DataSet** схема должна соответствовать только элементам из **XmlDataDocument** , которому требуется предоставить доступ с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="4ecdf-126">Не удается загрузить **XmlDataDocument** , если он синхронизирован с **набора данных** , содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="4ecdf-127">В таком случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-127">An exception will be thrown.</span></span>  
  
-   <span data-ttu-id="4ecdf-128">Создайте новый **XmlDataDocument** и загрузить его из XML-документ и затем получить доступ к реляционному представлению данных с помощью **DataSet** свойство **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="4ecdf-129">Необходимо задать схему **DataSet** перед просмотром данных в **XmlDataDocument** с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="4ecdf-130">Опять же, имена таблиц и имена столбцов в вашей **DataSet** схемы должны совпадать с именами элементов XML, с которыми их нужно синхронизировать с.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="4ecdf-131">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="4ecdf-132">В следующем примере кода показано, как получить доступ к реляционному представлению данных в **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="4ecdf-133">Еще одно преимущество синхронизации **XmlDataDocument** с **DataSet** — точном сохранении XML-документа.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="4ecdf-134">Если **DataSet** заполнен из XML-документа с помощью **ReadXml**, если данные обратной записи как XML-документа с помощью **WriteXml** он может значительно отличаться от исходный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="4ecdf-135">Это вызвано **набора данных** не сохраняет элементов форматирования, например пробелы или иерархических данных, например порядок элементов из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="4ecdf-136">**DataSet** также не содержит элементов из XML-документа, которые были пропущены, поскольку они не соответствует схеме **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="4ecdf-137">Синхронизация **XmlDataDocument** с **DataSet** позволяет сохранить форматирование и иерархическую структуру элементов исходного XML-документа в **XmlDataDocument**, пока **DataSet** содержит только данные и сведения схемы, подходящие для **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="4ecdf-138">При синхронизации **DataSet** с **XmlDataDocument**, результаты могут отличаться в зависимости от того, нужно ли ваш <xref:System.Data.DataRelation> вложенные объекты.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="4ecdf-139">Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="4ecdf-139">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ecdf-140">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ecdf-140">In This Section</span></span>  
 [<span data-ttu-id="4ecdf-141">Синхронизация DataSet с XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="4ecdf-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="4ecdf-142">Демонстрирует синхронизацию строго типизированного **DataSet**, с минимальной схемой, с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="4ecdf-143">Выполнение запроса XPath к DataSet</span><span class="sxs-lookup"><span data-stu-id="4ecdf-143">Performing an XPath Query on a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="4ecdf-144">Демонстрирует выполнение запроса XPath к содержимому **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="4ecdf-145">Применение преобразования XSLT к DataSet</span><span class="sxs-lookup"><span data-stu-id="4ecdf-145">Applying an XSLT Transform to a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="4ecdf-146">Демонстрирует применение XSLT-преобразования к содержимому **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ecdf-147">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4ecdf-147">Related Sections</span></span>  
 [<span data-ttu-id="4ecdf-148">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="4ecdf-148">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="4ecdf-149">Описывает способ **DataSet** взаимодействует с XML в качестве источника данных, включая загрузку и сохранение содержимого **набора данных** как XML-данных.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="4ecdf-150">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="4ecdf-150">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 <span data-ttu-id="4ecdf-151">Объясняет значение вложенных **DataRelation** при представлении содержимого **DataSet** как XML-данных и описывает создание этих связей.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="4ecdf-152">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="4ecdf-152">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="4ecdf-153">Описывает **набора данных** и способ его использования для управления данными приложения и взаимодействия с источниками данных, включая реляционные базы данных и XML.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="4ecdf-154">Содержит справочные сведения о **XmlDataDocument** класса.</span><span class="sxs-lookup"><span data-stu-id="4ecdf-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ecdf-155">См. также</span><span class="sxs-lookup"><span data-stu-id="4ecdf-155">See Also</span></span>  
 [<span data-ttu-id="4ecdf-156">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4ecdf-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
