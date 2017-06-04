---
title: "Загрузка DataSet из XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Загрузка DataSet из XML
Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML\-потока или XML\-документа.  Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.  
  
 Для заполнения объекта <xref:System.Data.DataSet> данными из XML следует использовать метод **ReadXml** объекта <xref:System.Data.DataSet>.  Метод **ReadXml** считывает данные из файла, потока или объекта **XmlReader**, а в качестве аргумента принимает источник XML и еще один дополнительный аргумент, **XmlReadMode**.  \(Дополнительные сведения о **XmlReader** см. в разделе [NIB: Reading XML Data with XmlTextReader](http://msdn.microsoft.com/ru-ru/762c069b-b50c-41b8-936e-39eacfb0d540).\) Метод **ReadXml** считывает содержимое XML\-потока или XML\-документа и загружает данные в <xref:System.Data.DataSet>.  Он также создаст реляционную схему <xref:System.Data.DataSet> в зависимости от указанного значения **XmlReadMode**, а также от наличия или отсутствия реляционной схемы.  
  
 В следующей таблице описаны параметры для аргумента **XmlReadMode**.  
  
|Параметр|Описание|  
|--------------|--------------|  
|**Auto**|Это значение по умолчанию.  Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.<br /><br /> -   Если код XML относится к типу DiffGram, используется значение **DiffGram**.<br />-   Если набор данных <xref:System.Data.DataSet> содержит схему или XML\-код содержит встроенную схему, используется значение **ReadSchema**.<br />-   Если набор данных <xref:System.Data.DataSet> не содержит схему и XML\-код не содержит встроенную схему, используется значение **InferSchema**.<br /><br /> Если известен формат считанного XML\-кода, для достижения наибольшей производительности рекомендуется явно задавать значение аргумента **XmlReadMode**, а не принимать значение **Auto**, заданное по умолчанию.|  
|**ReadSchema**|Считывает любую встроенную схему и загружает данные и схему.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>.  Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение.  Возможность изменить схему существующей таблицы с помощью метода **XmlReadMode.ReadSchema** отсутствует.<br /><br /> Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.<br /><br /> Встроенная схема может быть определена с помощью схемы на языке XSD.  Дополнительные сведения о записи встроенной схемы в виде схемы XML см. в разделе [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>.  Любые данные, не совпадающие с существующей схемой, удаляются.  Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.<br /><br /> Если данные относятся к типу DiffGram, значение **IgnoreSchema** предоставляет такие же функциональные возможности, что и **DiffGram**.|  
|**InferSchema**|Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML\-данных, а затем загружает данные.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы.  Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы.  Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.<br /><br /> Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML\-документа, см. в разделе [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Считывает данные DiffGram и добавляет их в текущую схему.  В данных **DiffGram** производится слияние новых строк с существующими строками, в которых совпадают уникальные идентифицирующие значения.  См. подраздел «Слияние данных из XML» в конце данного раздела.  Дополнительные сведения о DiffGram см. в разделе [Объекты DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Fragment**|Продолжает считывание нескольких XML\-фрагментов до достижения конца потока.  Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы.  Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.|  
  
> [!NOTE]
>  Если после передачи объекта **XmlReader** в метод **ReadXml** обнаруживается, что этот объект является позиционированной частью пути в XML\-документе, метод **ReadXml** производит считывание до следующего узла элемента и рассматривает его в качестве корневого элемента, считывая только до конца узла элемента.  Это действие не применяется, если указан метод **XmlReadMode.Fragment**.  
  
## Сущности DTD  
 Если XML содержит сущности, заданные в схеме определения DTD, то возникает исключение при попытке загрузки набора данных <xref:System.Data.DataSet> путем передачи имени файла, потока или не выполняющего проверку правильности объекта **XmlReader** в **ReadXml**.  Вместо этого необходимо создать объект **XmlValidatingReader**, присвоив аргументу **EntityHandling** значение **EntityHandling.ExpandEntities**, и передать объект **XmlValidatingReader** в метод **ReadXml**.  Объект **XmlValidatingReader** развертывает сущности до его считывания в набор данных <xref:System.Data.DataSet>.  
  
 В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML\-потока.  В первом примере показана передача имени файла методу **ReadXml**.  Во втором примере показана загрузка строки, содержащей XML\-код, с помощью объекта <xref:System.IO.StringReader>.  
  
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
>  При попытке вызвать метод **ReadXml** для загрузки файла с очень большими размерами может оказаться, что производительность является низкой.  Чтобы обеспечить наилучшую производительность при использовании метода **ReadXml** применительно к файлу большого размера, вызывайте метод <xref:System.Data.DataTable.BeginLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet> и затем вызывайте метод **ReadXml**.  Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.  
  
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
>  Если схема XSD для набора данных <xref:System.Data.DataSet> включает пространство имен **targetNamespace**, то данные не могут быть считаны, поэтому при вызове метода **ReadXml** для загрузки в набор данных <xref:System.Data.DataSet> XML\-кода, содержащего элементы без указанного пространства имен, может возникнуть исключение.  В данном случае для считывания элементов с неполными именами в схеме XSD следует установить значение **elementFormDefault** равным «qualified».  Например:  
  
```  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## Слияние данных из XML  
 Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML\-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>.  Метод **ReadXml** не переносит слиянием из XML\-кода в набор данных <xref:System.Data.DataSet> никаких данных из строк с совпадающими первичными ключами.  Для перезаписи существующих данных в строках новыми данными из XML\-кода следует использовать метод **ReadXml** для создания нового набора данных <xref:System.Data.DataSet>, а затем использовать метод <xref:System.Data.DataSet.Merge%2A>, чтобы выполнить слияние набора данных <xref:System.Data.DataSet> с существующим набором данных <xref:System.Data.DataSet>.  Обратите внимание, что при загрузке данных DiffGram с использованием метода **ReadXML** со значением параметра **XmlReadMode**, равным **DiffGram**, происходит слияние строк, имеющих одинаковый уникальный идентификатор.  
  
## См. также  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=fullName>   
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [Объекты DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)   
 [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [Вывод реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)