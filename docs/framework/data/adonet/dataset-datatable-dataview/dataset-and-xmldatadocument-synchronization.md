---
title: "Синхронизация DataSet и XmlDataDocument | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0ce3793d-54b2-47e4-8cf7-b0591cc4dd21
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Синхронизация DataSet и XmlDataDocument
ADO.NET <xref:System.Data.DataSet> обеспечивает реляционное представление данных.  Для доступа к иерархическим данным можно использовать классы XML, доступные на платформе .NET Framework.  Исторически эти два представления данных использовались раздельно.  Однако платформа .NET Framework обеспечивает динамический синхронный доступ, как к реляционным, так и иерархическим представлениям данных через объект **DataSet** и объект <xref:System.Xml.XmlDataDocument> соответственно.  
  
 Когда объект **DataSet** синхронизирован с объектом **XmlDataDocument**, оба они работают с одним набором данных.  Это означает, что при изменении в объекте **DataSet** изменения отражаются в **XmlDataDocument** и наоборот.  Взаимосвязь между объектами **DataSet** и **XmlDataDocument** обеспечивает высокую гибкость, так как одно приложение, использующее один набор данных, может обращаться ко всему комплексу служб, построенных на основе **DataSet** \(например, элементов управления Web Forms и Windows Forms, конструкторов Visual Studio .NET\), а также комплексу XML\-служб, в том числе расширяемому языку таблицы стилей \(XSL\), преобразованиям XSL \(XSLT\) и языку XML Path \(XPath\).  Не обязательно выбирать конкретный набор служб для приложения. Доступны оба.  
  
 Есть несколько способов синхронизации **DataSet** с **XmlDataDocument**.  Можно выполнить следующие действия.  
  
-   Заполнить объект **DataSet** схемой \(то есть, реляционной структурой\) и данными, а затем синхронизировать его с новым объектом **XmlDataDocument**.  Это обеспечивает иерархическое представление существующих реляционных данных.  Например:  
  
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
  
-   Заполните объект **DataSet** только схемой \(например, строго типизированным **DataSet**\), синхронизируйте его с **XmlDataDocument**, а затем загрузите объект **XmlDataDocument** из XML\-документа.  Это обеспечивает реляционное представление существующих иерархических данных.  Имена таблиц и имена столбцов в схеме **DataSet** должны соответствовать именам XML\-элементов, с которыми их нужно синхронизировать.  Это соответствие с учетом регистра.  
  
     Обратите внимание, что схема **DataSet** должна соответствовать только XML\-элементам, которые нужно показать в реляционном представлении.  Таким образом, может существовать очень большой XML\-документ и очень малое реляционное «окно» для этого документа.  Объект **XmlDataDocument** сохраняет XML\-документ целиком, даже притом, что в объекте **DataSet** показана лишь малая его часть.  \(Подробный пример см. в разделе [Синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md).\)  
  
     В следующем примере кода показаны шаги создания объекта **DataSet** и заполнения его схемы, а затем его синхронизации с объектом **XmlDataDocument**.  Обратите внимание, что схема **DataSet** должна соответствовать только элементам из **XmlDataDocument**, которые нужно показать с помощью объекта **DataSet**.  
  
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
  
     Нельзя загрузить объект **XmlDataDocument**, если он синхронизирован с объектом **DataSet**, в котором есть данные.  В таком случае возникнет исключение.  
  
-   Создайте новый объект **XmlDataDocument** и загрузите его из XML\-документа, затем обратитесь к реляционному представлению данных с помощью свойства **DataSet** объекта **XmlDataDocument**.  Необходимо установить схему **DataSet** до того, как появится возможность просмотреть любые данные в **XmlDataDocument** с помощью **DataSet**.  Отметим еще раз: имена таблиц и имена столбцов в схеме **DataSet** должны соответствовать именам XML\-элементов, с которыми их нужно синхронизировать.  Это соответствие с учетом регистра.  
  
     В следующем примере кода показано обращение к реляционному представлению данных в объекте **XmlDataDocument**.  
  
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
  
 Еще одно преимущество синхронизации **XmlDataDocument** с **DataSet** заключается в точном сохранении XML\-документа.  Если объект **DataSet** заполнен из XML\-документа с помощью **ReadXml**, то при обратной записи данных как XML\-документа с использованием **WriteXml** отличия от исходного XML\-документа могут быть существенными.  Причина в том, что **DataSet** не сохраняет элементов форматирования XML\-документа, в частности, пробелов или иерархических данных, например порядок элементов.  Объект **DataSet** также не содержит элементов из XML\-документа, которые были пропущены, поскольку не соответствуют схеме **Dataset**.  Синхронизация объекта **XmlDataDocument** с **DataSet** позволяет сохранить форматирование и иерархическую структуру элементов исходного XML\-документа в объекте **XmlDataDocument**, а объект **DataSet** содержит данные и сведения схемы, подходящие для объекта **DataSet**.  
  
 При синхронизации объекта **DataSet** с объектом **XmlDataDocument** могут быть получены различные результаты в зависимости от того, используются ли вложенные объекты <xref:System.Data.DataRelation>.  Для получения дополнительной информации см. [Вложенность объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).  
  
## В этом подразделе  
 [Синхронизация DataSet с XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/synchronizing-a-dataset-with-an-xmldatadocument.md)  
 Демонстрирует синхронизацию строго типизированного объекта **DataSet** с минимальной схемой, с объектом **XmlDataDocument**.  
  
 [Выполнение запроса XPath над DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/performing-an-xpath-query-on-a-dataset.md)  
 Демонстрирует выполнение запроса XPath к содержимому **DataSet**.  
  
 [Применение XSLT\-преобразования к набору данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/applying-an-xslt-transform-to-a-dataset.md)  
 Демонстрирует применение XSLT\-преобразования к содержимому **DataSet**.  
  
## Связанные подразделы  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает взаимодействие объекта **DataSet** с XML как источником данных, в том числе загрузку и сохранение содержимого объекта **DataSet** как XML\-данных.  
  
 [Вложенность объектов DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 Показывает важность вложенных объектов **DataRelation** при представлении содержимого объекта **DataSet** как XML\-данных и описывает создание этих связей.  
  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Описывает объект **DataSet** и использование его для управления данными приложений и взаимодействием с источниками данных, в том числе с реляционными базами данных и XML.  
  
 [Класс XmlDataDocument](frlrfSystemXmlXmlDataDocumentClassTopic)  
 Содержит справочные сведения о классе **XmlDataDocument**.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)