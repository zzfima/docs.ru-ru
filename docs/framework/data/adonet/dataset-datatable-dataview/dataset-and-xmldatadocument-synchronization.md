---
title: Синхронизация набора данных и XmlDataDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
ms.openlocfilehash: ea597d7caca3174b17ce16a1e9d70c022e3e75c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164740"
---
# <a name="dataset-and-xmldatadocument-synchronization"></a>Синхронизация набора данных и XmlDataDocument
ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных. Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework. Исторически эти два представления данных использовались раздельно. Тем не менее, платформа .NET обеспечивает динамический синхронный доступ реляционные и иерархические представления данных с помощью **набора данных** объекта и <xref:System.Xml.XmlDataDocument> соответственно.  
  
 Когда **набора данных** синхронизируется с **XmlDataDocument**, оба они работают с одного набора данных. Это означает, что если изменения были сделаны **набора данных**, это изменение будет отражено в **XmlDataDocument**и наоборот. Связь между **набора данных** и **XmlDataDocument** создает большую гибкость, позволяя одного приложения, использование одного набора данных, для доступа к полный комплект служб на основе вокруг **набора данных** (например, элементы управления Web Forms и Windows Forms и конструкторы Visual Studio .NET), а также набор служб XML, включая Extensible Stylesheet Language (XSL), путь к XML и XSL Transformations (XSLT) Язык (XPath). Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.  
  
 Существует несколько способов, которые можно синхронизировать **набора данных** с **XmlDataDocument**. Можно выполнить следующие действия:   
  
-   Заполнение **набора данных** со схемой (то есть, реляционной структурой) и данных, а затем синхронизировать его с новым **XmlDataDocument**. Это обеспечивает иерархическое представление существующих реляционных данных. Пример:  
  
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
  
-   Заполнение **набора данных** только со схемой (например, строго типизированным **набора данных**), синхронизируйте его с **XmlDataDocument**, а затем загрузить  **XmlDataDocument** из XML-документа. Это обеспечивает реляционное представление существующих иерархических данных. Имена таблиц и имена столбцов в вашей **набора данных** схемы должны совпадать с именами XML-элементов, которые вы их нужно синхронизировать. Это соответствие с учетом регистра.  
  
     Обратите внимание, что схема **набора данных** должна соответствовать XML-элементов, которые вы хотите предоставить в реляционном представлении только. Таким образом, может существовать очень большой XML-документ и очень малое реляционное «окно» для этого документа. **XmlDataDocument** сохраняет весь документ XML, даже если **набора данных** предоставляет только небольшая часть. (Подробный пример этого см. в разделе [синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     В следующем примере кода показаны действия по созданию **набора данных** и заполнения его схемы, а затем его синхронизации с **XmlDataDocument**. Обратите внимание, что **набора данных** схема должна соответствовать только элементы из **XmlDataDocument** , которому требуется предоставить доступ с помощью **набора данных**.  
  
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
  
     Не удается загрузить **XmlDataDocument** Если синхронизируется с **набора данных** , содержащий данные. В таком случае возникнет исключение.  
  
-   Создайте новый **XmlDataDocument** и загрузить его из XML-документа и затем получить доступ к реляционному представлению данных с помощью **набора данных** свойство **XmlDataDocument**. Необходимо задать схему **набора данных** перед просмотром данных в **XmlDataDocument** с помощью **набора данных**. Опять же, имена таблиц и имена столбцов в вашей **набора данных** схемы должны совпадать с именами XML-элементов, которые вы их нужно синхронизировать. Это соответствие с учетом регистра.  
  
     В следующем примере кода показано, как получить доступ к реляционному представлению данных в **XmlDataDocument**.  
  
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
  
 Еще одно преимущество синхронизации **XmlDataDocument** с **набора данных** является, то сохраняется точность XML-документа. Если **набора данных** заполняется из XML-документа с помощью **ReadXml**, когда данные записываются обратно в XML-документа с помощью **WriteXml** может значительно отличаться от исходный XML-документ. Это обусловлено **набора данных** не сохраняет элементов форматирования, например пробелы или иерархических данных, например порядок элементов, из XML-документа. **Набора данных** также не содержит элементы из XML-документа, которые были пропущены, поскольку они не соответствует схеме **набора данных**. Синхронизация **XmlDataDocument** с **набора данных** позволяет форматирование и иерархическую структуру элементов исходного XML-документа в **XmlDataDocument**, хотя **набора данных** содержит только данные и схему сведения, относящиеся к **набора данных**.  
  
 При синхронизации **набора данных** с **XmlDataDocument**, результаты могут отличаться в зависимости от того, нужно ли вашей <xref:System.Data.DataRelation> объекты являются вложенными. Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Синхронизация набора данных с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Демонстрирует синхронизацию строго типизированный **набора данных**, с минимальной схемой, с помощью **XmlDataDocument**.  
  
 [Выполнение запроса XPath к набору данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Демонстрирует выполнение запроса XPath на содержание **набора данных**.  
  
 [Применение преобразования XSLT к набору данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Демонстрирует применение преобразования XSLT к содержимому **набора данных**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает способ **набора данных** взаимодействие с XML в качестве источника данных, включая загрузку и сохранение содержимого **набора данных** как XML-данных.  
  
 [Вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Обсуждается важность вложенных **DataRelation** объектов при представлении содержимого **набора данных** как XML-данных и описывается создание этих связей.  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает **набора данных** и способы ее использования для управления данными приложения и взаимодействия с источниками данных, включая реляционные базы данных и XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Содержит справочную информацию о **XmlDataDocument** класса.  
  
## <a name="see-also"></a>См. также

- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
