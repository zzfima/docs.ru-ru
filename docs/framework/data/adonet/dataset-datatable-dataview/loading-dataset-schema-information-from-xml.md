---
title: "Загрузка сведений о схеме DataSet из XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Загрузка сведений о схеме DataSet из XML
Схема <xref:System.Data.DataSet> \(с таблицами, столбцами, связями и ограничениями\) может быть определена программно, путем создания с помощью методов **Fill** или **FillSchema** объекта <xref:System.Data.Common.DataAdapter>, или загружена из XML\-документа.  Для загрузки сведений о схеме **DataSet** из XML\-документа можно использовать метод **ReadXmlSchema** или метод **InferXmlSchema** объекта **DataSet**.  **ReadXmlSchema** дает возможность загружать или выводить сведения о схеме **DataSet** из документа, содержащего схему на языке XSD, или из XML\-документа со встроенной схемой XML.  **InferXmlSchema** дает возможность выводить схему из XML\-документа, не учитывая некоторые указанные пространства имен XML.  
  
> [!NOTE]
>  Упорядочение таблицы в **DataSet** может не сохраниться при использовании веб\-служб или XML\-сериализации для передачи набора данных **DataSet**, созданного в памяти с помощью конструкций XSD \(таких как вложенные связи\).  Таким образом, в этом случае дальнейшие действия получателя объекта **DataSet** не должны зависеть от существующего упорядочения таблицы.  Однако упорядочение таблицы всегда сохраняется, если переданная схема **DataSet** была считана из XSD\-файлов, а не создана в памяти.  
  
## ReadXmlSchema  
 Для загрузки схемы **DataSet** из XML\-документа без загрузки других данных используется метод **ReadXmlSchema** **DataSet**.  Метод **ReadXmlSchema** создает схему **DataSet**, определенную с помощью схемы на языке XSD.  
  
 Метод **ReadXmlSchema** принимает один аргумент, представляющий собой имя файла, поток или объект **XmlReader**, содержащий XML\-документ, который необходимо загрузить.  XML\-документ может содержать либо только схему, либо схему со встроенными XML\-элементами, содержащими данные.  Дополнительные сведения о записи встроенной схемы в виде схемы XML см. в разделе [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Если XML\-документ, переданный **ReadXmlSchema**, не содержит сведений о встроенной схеме, **ReadXmlSchema** выведет схему из элементов в XML\-документе.  Если **DataSet** уже содержит схему, текущая схема будет расширена путем добавления новых таблиц, если они еще не существуют.  Новые столбцы не будут добавляться к существующим таблицам.  Если добавленный столбец уже существует в **DataSet**, но имеет тип, несовместимый со столбцом, содержащимся в XML, возникает исключение.  Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML\-документа, см. в разделе [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Хотя **ReadXmlSchema** загружает или выводит только схему **DataSet**, метод **ReadXml** **DataSet** загружает или выводит и схему, и данные, содержащиеся в XML\-документе.  Для получения дополнительной информации см. [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Следующие примеры кода показывают способ загрузки схемы **DataSet** из XML\-документа или потока.  Первый пример показывает имя файла схемы XML, переданный методу **ReadXmlSchema**.  Второй пример показывает **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
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
  
## InferXmlSchema  
 Можно также дать указание объекту **DataSet** вывести свою схему из XML\-документа с помощью метода **InferXmlSchema** объекта **DataSet**.  Метод **InferXmlSchema** действует так же, как метод **ReadXml** со значением **XmlReadMode** параметра **InferSchema** \(загружает данные, а также формирует схему\) и метод **ReadXmlSchema**, если считанный документ не содержит встроенной схемы.  Но метод **InferXmlSchema** предоставляет дополнительную возможность, позволяя пропускать определенные пространства имен XML при формировании схемы.  Метод **InferXmlSchema** принимает два обязательных аргумента: местоположение XML\-документа, заданное по имени файла, потока или объекта **XmlReader**, и строковый массив пространств имен XML, которые не должны использоваться в этой операции.  
  
 Например, рассмотрим следующий XML\-код:  
  
```  
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
  
 Атрибуты, заданные для элементов в предыдущем XML\-документе, заданы таким образом, что и метод **ReadXmlSchema**, и метод **ReadXml** со значением **XmlReadMode** аргумента **InferSchema** создают таблицы для каждого элемента в документе: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel** и **Discontinued**.  \(Дополнительные сведения см. в разделе [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).\) Однако более подходящей могла бы стать структура, в которой создаются только таблицы **Categories** и **Products**, затем столбцы **CategoryID**, **CategoryName** и **Description** в таблице **Categories** и, наконец, столбцы **ProductID**, **ReorderLevel** и **Discontinued** в таблице **Products**.  Для обеспечения того, чтобы в сформированной схеме были пропущены атрибуты, заданные в XML\-элементах, можно применить метод **InferXmlSchema** и указать пропускаемое пространство имен XML для **officedata**, как показано в следующем примере.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## См. также  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)