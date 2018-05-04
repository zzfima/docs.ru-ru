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
# <a name="dataset-and-xmldatadocument-synchronization"></a>Синхронизация набора данных и XmlDataDocument
ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных. Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework. Исторически эти два представления данных использовались раздельно. Тем не менее, платформа .NET Framework обеспечивает динамический синхронный доступ в реляционном и иерархическом представлении данных с помощью **DataSet** объекта и <xref:System.Xml.XmlDataDocument> соответственно.  
  
 Когда **DataSet** синхронизируется с **XmlDataDocument**, оба они работают с одним набором данных. Это означает, что при внесении изменений в **DataSet**, изменения будут отражены в **XmlDataDocument**и наоборот. Связь между **DataSet** и **XmlDataDocument** создает большую гибкость, позволяя одного приложения, использование одного набора данных, для доступа к полный набор служб, встроенных вокруг **набора данных** (такие как Web Forms и Windows Forms и конструкторов Visual Studio .NET), а также набор служб XML, включая Extensible Stylesheet Language (XSL), преобразованиям XSL (XSLT) и пути XML Language (XPath). Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.  
  
 Существует несколько способов, которые можно синхронизировать **DataSet** с **XmlDataDocument**. Можно выполнить следующие действия.  
  
-   Заполнение **DataSet** со схемой (то есть, реляционной структурой) и данными, а затем синхронизировать его с новым **XmlDataDocument**. Это обеспечивает иерархическое представление существующих реляционных данных. Пример:  
  
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
  
-   Заполнение **набора данных** только со схемой (например, строго типизированным **набора данных**), синхронизируйте его с **XmlDataDocument**и затем загружать  **XmlDataDocument** из XML-документа. Это обеспечивает реляционное представление существующих иерархических данных. Имена таблиц и имена столбцов в вашей **DataSet** схемы должны совпадать с именами элементов XML, то их нужно синхронизировать. Это соответствие с учетом регистра.  
  
     Обратите внимание, что схема **набора данных** должна соответствовать XML-элементы, которые требуется предоставить в реляционное представление только. Таким образом, может существовать очень большой XML-документ и очень малое реляционное «окно» для этого документа. **XmlDataDocument** позволяет сохранить весь документ XML, даже если **DataSet** предоставляет только малую часть. (Пример этого см. в разделе [синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).)  
  
     В следующем примере кода показаны шаги создания **DataSet** и заполнения его схемы, а затем его синхронизации с **XmlDataDocument**. Обратите внимание, что **DataSet** схема должна соответствовать только элементам из **XmlDataDocument** , которому требуется предоставить доступ с помощью **набора данных**.  
  
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
  
     Не удается загрузить **XmlDataDocument** , если он синхронизирован с **набора данных** , содержащий данные. В таком случае возникнет исключение.  
  
-   Создайте новый **XmlDataDocument** и загрузить его из XML-документ и затем получить доступ к реляционному представлению данных с помощью **DataSet** свойство **XmlDataDocument**. Необходимо задать схему **DataSet** перед просмотром данных в **XmlDataDocument** с помощью **набора данных**. Опять же, имена таблиц и имена столбцов в вашей **DataSet** схемы должны совпадать с именами элементов XML, с которыми их нужно синхронизировать с. Это соответствие с учетом регистра.  
  
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
  
 Еще одно преимущество синхронизации **XmlDataDocument** с **DataSet** — точном сохранении XML-документа. Если **DataSet** заполнен из XML-документа с помощью **ReadXml**, если данные обратной записи как XML-документа с помощью **WriteXml** он может значительно отличаться от исходный XML-документ. Это вызвано **набора данных** не сохраняет элементов форматирования, например пробелы или иерархических данных, например порядок элементов из XML-документа. **DataSet** также не содержит элементов из XML-документа, которые были пропущены, поскольку они не соответствует схеме **набора данных**. Синхронизация **XmlDataDocument** с **DataSet** позволяет сохранить форматирование и иерархическую структуру элементов исходного XML-документа в **XmlDataDocument**, пока **DataSet** содержит только данные и сведения схемы, подходящие для **набора данных**.  
  
 При синхронизации **DataSet** с **XmlDataDocument**, результаты могут отличаться в зависимости от того, нужно ли ваш <xref:System.Data.DataRelation> вложенные объекты. Дополнительные сведения см. в разделе [вложение отношений DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Демонстрирует синхронизацию строго типизированного **DataSet**, с минимальной схемой, с **XmlDataDocument**.  
  
 [Выполнение запроса XPath к DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Демонстрирует выполнение запроса XPath к содержимому **набора данных**.  
  
 [Применение преобразования XSLT к DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Демонстрирует применение XSLT-преобразования к содержимому **набора данных**.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает способ **DataSet** взаимодействует с XML в качестве источника данных, включая загрузку и сохранение содержимого **набора данных** как XML-данных.  
  
 [Вложенность объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Объясняет значение вложенных **DataRelation** при представлении содержимого **DataSet** как XML-данных и описывает создание этих связей.  
  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает **набора данных** и способ его использования для управления данными приложения и взаимодействия с источниками данных, включая реляционные базы данных и XML.  
  
 <xref:System.Xml.XmlDataDocument>  
 Содержит справочные сведения о **XmlDataDocument** класса.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
