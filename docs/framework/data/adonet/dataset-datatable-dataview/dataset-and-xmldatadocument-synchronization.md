---
title: Синхронизация набора данных и XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: 3bbe28423385cae0f09f301c03b2b1a59edf101d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205068"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a><span data-ttu-id="20891-102">Синхронизация набора данных и XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="20891-102">DataSet and XmlDataDocument Synchronization</span></span>
<span data-ttu-id="20891-103">ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных.</span><span class="sxs-lookup"><span data-stu-id="20891-103">The ADO.NET <xref:System.Data.DataSet> provides you with a relational representation of data.</span></span> <span data-ttu-id="20891-104">Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20891-104">For hierarchical data access, you can use the XML classes available in the .NET Framework.</span></span> <span data-ttu-id="20891-105">Исторически эти два представления данных использовались раздельно.</span><span class="sxs-lookup"><span data-stu-id="20891-105">Historically, these two representations of data have been used separately.</span></span> <span data-ttu-id="20891-106">Однако .NET Framework обеспечивает синхронный доступ в режиме реального времени к реляционным и иерархическим представлениям данных через объект **DataSet** и <xref:System.Xml.XmlDataDocument> объект соответственно.</span><span class="sxs-lookup"><span data-stu-id="20891-106">However, the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the **DataSet** object and the <xref:System.Xml.XmlDataDocument> object, respectively.</span></span>  
  
 <span data-ttu-id="20891-107">Если **набор данных** синхронизирован с **XmlDataDocument**, то оба объекта работают с одним набором данных.</span><span class="sxs-lookup"><span data-stu-id="20891-107">When a **DataSet** is synchronized with an **XmlDataDocument**, both objects are working with a single set of data.</span></span> <span data-ttu-id="20891-108">Это означает, что если в **набор данных**внесено изменение, это изменение будет отражено в **объекте XmlDataDocument**и наоборот.</span><span class="sxs-lookup"><span data-stu-id="20891-108">This means that if a change is made to the **DataSet**, the change will be reflected in the **XmlDataDocument**, and vice versa.</span></span> <span data-ttu-id="20891-109">Связь между набором **данных** и объектом **XmlDataDocument** создает большую гибкость, позволяя единому приложению использовать единый набор данных для доступа ко всему набору служб, созданных на основе **набора данных** (например, веб-формы и Windows Forms элементы управления и конструкторы Visual Studio .NET), а также набор служб XML, включая расширенный язык таблиц стилей (XSL), преобразования XSL (XSLT) и язык XML Path (XPath).</span><span class="sxs-lookup"><span data-stu-id="20891-109">The relationship between the **DataSet** and the **XmlDataDocument** creates great flexibility by allowing a single application, using a single set of data, to access the entire suite of services built around the **DataSet** (such as Web Forms and Windows Forms controls, and Visual Studio .NET designers), as well as the suite of XML services including Extensible Stylesheet Language (XSL), XSL Transformations (XSLT), and XML Path Language (XPath).</span></span> <span data-ttu-id="20891-110">Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.</span><span class="sxs-lookup"><span data-stu-id="20891-110">You do not have to choose which set of services to target with the application; both are available.</span></span>  
  
 <span data-ttu-id="20891-111">Существует несколько способов синхронизации **набора данных** с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-111">There are several ways that you can synchronize a **DataSet** with an **XmlDataDocument**.</span></span> <span data-ttu-id="20891-112">Можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="20891-112">You can:</span></span>  
  
- <span data-ttu-id="20891-113">Заполните **набор данных** схемой (то есть реляционной структурой) и данными, а затем синхронизируйте его с новым **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-113">Populate a **DataSet** with schema (that is, a relational structure) and data and then synchronize it with a new **XmlDataDocument**.</span></span> <span data-ttu-id="20891-114">Это обеспечивает иерархическое представление существующих реляционных данных.</span><span class="sxs-lookup"><span data-stu-id="20891-114">This provides a hierarchical view of existing relational data.</span></span> <span data-ttu-id="20891-115">Например:</span><span class="sxs-lookup"><span data-stu-id="20891-115">For example:</span></span>  
  
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
  
- <span data-ttu-id="20891-116">Заполнить **набор данных** только схемой (например, строго типизированным **набором данных**), синхронизировать его с **XmlDataDocument**, а затем загрузить **XmlDataDocument** из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="20891-116">Populate a **DataSet** with schema only (such as a strongly typed **DataSet**), synchronize it with an **XmlDataDocument**, and then load the **XmlDataDocument** from an XML document.</span></span> <span data-ttu-id="20891-117">Это обеспечивает реляционное представление существующих иерархических данных.</span><span class="sxs-lookup"><span data-stu-id="20891-117">This provides a relational view of existing hierarchical data.</span></span> <span data-ttu-id="20891-118">Имена таблиц и столбцов в схеме **набора данных** должны совпадать с именами XML-элементов, с которыми они должны быть синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="20891-118">The table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="20891-119">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="20891-119">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="20891-120">Обратите внимание, что схема **набора данных** должна соответствовать только тем XML-элементам, которые необходимо предоставить в реляционном представлении.</span><span class="sxs-lookup"><span data-stu-id="20891-120">Note that the schema of the **DataSet** only needs to match the XML elements that you want to expose in your relational view.</span></span> <span data-ttu-id="20891-121">Таким образом, может существовать очень большой XML-документ и очень малое реляционное «окно» для этого документа.</span><span class="sxs-lookup"><span data-stu-id="20891-121">This way, you can have a very large XML document and a very small relational "window" on that document.</span></span> <span data-ttu-id="20891-122">Объект **XmlDataDocument** сохраняет весь XML-документ, несмотря на то, что **набор данных** предоставляет только небольшую часть.</span><span class="sxs-lookup"><span data-stu-id="20891-122">The **XmlDataDocument** preserves the entire XML document even though the **DataSet** only exposes a small portion of it.</span></span> <span data-ttu-id="20891-123">(Подробный пример см. в разделе [синхронизация набора данных с XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span><span class="sxs-lookup"><span data-stu-id="20891-123">(For a detailed example of this, see [Synchronizing a DataSet with an XmlDataDocument](synchronizing-a-dataset-with-an-xmldatadocument.md).)</span></span>  
  
     <span data-ttu-id="20891-124">В следующем примере кода показаны шаги для создания **набора данных** и заполнения его схемы, а затем выполняется его синхронизация с **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-124">The following code example shows the steps for creating a **DataSet** and populating its schema, then synchronizing it with an **XmlDataDocument**.</span></span> <span data-ttu-id="20891-125">Обратите внимание, что схема **набора данных** должна соответствовать только элементам объекта **XmlDataDocument** , которые необходимо предоставить с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-125">Note that the **DataSet** schema only needs to match the elements from the **XmlDataDocument** that you want to expose using the **DataSet**.</span></span>  
  
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
  
     <span data-ttu-id="20891-126">Невозможно загрузить объект **XmlDataDocument** , если он синхронизирован с набором данных, содержащим данные.</span><span class="sxs-lookup"><span data-stu-id="20891-126">You cannot load an **XmlDataDocument** if it is synchronized with a **DataSet** that contains data.</span></span> <span data-ttu-id="20891-127">В таком случае возникнет исключение.</span><span class="sxs-lookup"><span data-stu-id="20891-127">An exception will be thrown.</span></span>  
  
- <span data-ttu-id="20891-128">Создайте новый объект **XmlDataDocument** и загрузите его из XML-документа, а затем получите доступ к реляционному представлению данных с помощью свойства **DataSet** объекта **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-128">Create a new **XmlDataDocument** and load it from an XML document, and then access the relational view of the data using the **DataSet** property of the **XmlDataDocument**.</span></span> <span data-ttu-id="20891-129">Необходимо задать схему **набора данных** , прежде чем можно будет просматривать любые данные в **объекте XmlDataDocument** с помощью **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-129">You need to set the schema of the **DataSet** before you can view any of the data in the **XmlDataDocument** using the **DataSet**.</span></span> <span data-ttu-id="20891-130">Имена таблиц и столбцов в схеме **набора данных** опять же должны совпадать с именами XML-элементов, с которыми они должны быть синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="20891-130">Again, the table names and column names in your **DataSet** schema must match the names of the XML elements that you want them synchronized with.</span></span> <span data-ttu-id="20891-131">Это соответствие с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="20891-131">This matching is case-sensitive.</span></span>  
  
     <span data-ttu-id="20891-132">В следующем примере кода показано, как получить доступ к реляционному представлению данных в **объекте XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-132">The following code example shows how to access the relational view of the data in an **XmlDataDocument**.</span></span>  
  
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
  
 <span data-ttu-id="20891-133">Другое преимущество синхронизации **XmlDataDocument** с **набором данных** заключается в том, что сохраняется достоверность XML-документа.</span><span class="sxs-lookup"><span data-stu-id="20891-133">Another advantage of synchronizing an **XmlDataDocument** with a **DataSet** is that the fidelity of an XML document is preserved.</span></span> <span data-ttu-id="20891-134">Если **набор данных** заполняется из XML-документа с помощью метода **ReadXml**, то при записи данных обратно в виде XML-документа с помощью метода **WriteXml** он может значительно отличаться от исходного XML-документа.</span><span class="sxs-lookup"><span data-stu-id="20891-134">If the **DataSet** is populated from an XML document using **ReadXml**, when the data is written back as an XML document using **WriteXml** it may differ dramatically from the original XML document.</span></span> <span data-ttu-id="20891-135">Это обусловлено тем, что **набор данных** не поддерживает форматирование, например, пробелы или иерархические данные, например порядок элементов, из XML-документа.</span><span class="sxs-lookup"><span data-stu-id="20891-135">This is because the **DataSet** does not maintain formatting, such as white space, or hierarchical information, such as element order, from the XML document.</span></span> <span data-ttu-id="20891-136">**Набор данных** также не содержит элементов из XML-документа, которые были пропущены, так как они не соответствуют схеме **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-136">The **DataSet** also does not contain elements from the XML document that were ignored because they did not match the schema of the **Dataset**.</span></span> <span data-ttu-id="20891-137">Синхронизация объекта **XmlDataDocument** с набором **данных** позволяет поддерживать форматирование и иерархическую структуру элементов исходного XML-документа в **объекте XmlDataDocument**, в то время как **набор данных** содержит только данные и сведения о схеме, соответствующие **набору данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-137">Synchronizing an **XmlDataDocument** with a **DataSet** allows the formatting and hierarchical element structure of the original XML document to be maintained in the **XmlDataDocument**, while the **DataSet** contains only data and schema information appropriate to the **DataSet**.</span></span>  
  
 <span data-ttu-id="20891-138">При синхронизации **набора данных** с **XmlDataDocument**результаты могут различаться в зависимости от того, являются ли <xref:System.Data.DataRelation> объекты вложенными.</span><span class="sxs-lookup"><span data-stu-id="20891-138">When synchronizing a **DataSet** with an **XmlDataDocument**, results may differ depending on whether or not your <xref:System.Data.DataRelation> objects are nested.</span></span> <span data-ttu-id="20891-139">Дополнительные сведения см. в разделе [вложенность связей](nesting-datarelations.md)данных.</span><span class="sxs-lookup"><span data-stu-id="20891-139">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20891-140">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="20891-140">In This Section</span></span>  
 [<span data-ttu-id="20891-141">Синхронизация DataSet с XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="20891-141">Synchronizing a DataSet with an XmlDataDocument</span></span>](synchronizing-a-dataset-with-an-xmldatadocument.md)  
 <span data-ttu-id="20891-142">Демонстрирует синхронизацию строго типизированного **набора данных**с минимальной схемой с помощью **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="20891-142">Demonstrates synchronizing a strongly typed **DataSet**, with minimal schema, with an **XmlDataDocument**.</span></span>  
  
 [<span data-ttu-id="20891-143">Выполнение запроса XPath к DataSet</span><span class="sxs-lookup"><span data-stu-id="20891-143">Performing an XPath Query on a DataSet</span></span>](performing-an-xpath-query-on-a-dataset.md)  
 <span data-ttu-id="20891-144">Демонстрирует выполнение запроса XPath к содержимому **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-144">Demonstrates performing an XPath query on the contents of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="20891-145">Применение преобразования XSLT к DataSet</span><span class="sxs-lookup"><span data-stu-id="20891-145">Applying an XSLT Transform to a DataSet</span></span>](applying-an-xslt-transform-to-a-dataset.md)  
 <span data-ttu-id="20891-146">Демонстрирует применение преобразования XSLT к содержимому **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="20891-146">Demonstrates applying an XSLT transform to the contents of a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="20891-147">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="20891-147">Related Sections</span></span>  
 [<span data-ttu-id="20891-148">Использование XML в наборах данных</span><span class="sxs-lookup"><span data-stu-id="20891-148">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="20891-149">Описывает взаимодействие **набора** данных с XML в качестве источника данных, включая загрузку и сохранение содержимого **набора данных** в виде XML-данных.</span><span class="sxs-lookup"><span data-stu-id="20891-149">Describes how the **DataSet** interacts with XML as a data source, including loading and persisting the contents of a **DataSet** as XML data.</span></span>  
  
 [<span data-ttu-id="20891-150">Вложенность объектов DataRelation</span><span class="sxs-lookup"><span data-stu-id="20891-150">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="20891-151">Описывает важность вложенных объектов **DataRelation** , когда представляет содержимое **набора** данных в виде XML-данных, и описывает создание этих связей.</span><span class="sxs-lookup"><span data-stu-id="20891-151">Discusses the importance of nested **DataRelation** objects when representing the contents of a **DataSet** as XML data, and describes how to create these relations.</span></span>  
  
 [<span data-ttu-id="20891-152">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="20891-152">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="20891-153">Описывает **набор данных** и способ его использования для управления данными приложения и взаимодействия с источниками данных, включая реляционные базы данных и XML.</span><span class="sxs-lookup"><span data-stu-id="20891-153">Describes the **DataSet** and how to use it to manage application data and to interact with data sources including relational databases and XML.</span></span>  
  
 <xref:System.Xml.XmlDataDocument>  
 <span data-ttu-id="20891-154">Содержит справочные сведения о классе **XmlDataDocument** .</span><span class="sxs-lookup"><span data-stu-id="20891-154">Contains reference information about the **XmlDataDocument** class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20891-155">См. также</span><span class="sxs-lookup"><span data-stu-id="20891-155">See also</span></span>

- [<span data-ttu-id="20891-156">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20891-156">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
