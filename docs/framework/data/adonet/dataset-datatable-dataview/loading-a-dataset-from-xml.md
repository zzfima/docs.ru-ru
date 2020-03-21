---
title: Загрузка набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151069"
---
# <a name="loading-a-dataset-from-xml"></a>Загрузка набора данных из XML
Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML-потока или XML-документа. Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.  
  
 Для заполнения <xref:System.Data.DataSet> данных xML используйте метод **ReadXml** <xref:System.Data.DataSet> объекта. Метод **ReadXml** читает из файла, потока или **XmlReader,** и принимает в качестве аргументов источник XML плюс дополнительный аргумент **XmlReadMode.** Для получения дополнительной информации о **XmlReader,** [см. Чтение данных XML с XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Метод **ReadXml** считывает содержимое потока xML или <xref:System.Data.DataSet> документа и загружает данные. Это также создаст реляционную <xref:System.Data.DataSet> схему в зависимости от **XmlReadMode** указаны и является ли реляционная схема уже существует.  
  
 В следующей таблице описаны варианты аргумента **XmlReadMode.**  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Автоматически**|Это значение по умолчанию. Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.<br /><br /> - Если XML является DiffGram, **DiffGram** используется.<br />- Если <xref:System.Data.DataSet> содержит схему или XML содержит вливую схему, **используется ReadSchema.**<br />- Если <xref:System.Data.DataSet> не содержит схемы и XML не содержит вливую схему, используется **InferSchema.**<br /><br /> Если вы знаете формат чтения XML, для лучшей производительности рекомендуется установить явный **XmlReadMode**, а не принимать **Auto** по умолчанию.|  
|**ReadSchema**|Считывает любую встроенную схему и загружает данные и схему.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>. Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение. Вы не сможете изменить схему существующей таблицы с помощью **XmlReadMode.ReadSchema**.<br /><br /> Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.<br /><br /> Встроенная схема может быть определена с помощью схемы на языке XSD. Подробнее о написании встроенной схемы xML Schema можно узнать из [XML Schema (XSD).](deriving-dataset-relational-structure-from-xml-schema-xsd.md)|  
|**IgnoreSchema**|Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>. Любые данные, не совпадающие с существующей схемой, удаляются. Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.<br /><br /> Если данные DiffGram, **IgnoreSchema** имеет ту же функциональность, что и **DiffGram** *.*|  
|**InferSchema**|Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML-данных, а затем загружает данные.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы. Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы. Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.<br /><br /> Подробную информацию о том, как **ReadXmlSchema** выносит схему из документа XML, [см. Вывод о соотношении DataSet от XML.](inferring-dataset-relational-structure-from-xml.md)|  
|**Diffgram**|Считывает данные DiffGram и добавляет их в текущую схему. **DiffGram** объединяет новые строки с существующими строками, где совпадают значения уникальных идентификаторов. См. подраздел «Слияние данных из XML» в конце данного раздела. Для получения дополнительной информации о DiffGrams, [см.](diffgrams.md)|  
|**Фрагмент**|Продолжает считывание нескольких XML-фрагментов до достижения конца потока. Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы. Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.|  
  
> [!NOTE]
> Если вы передаете **XmlReader** **на ReadXml,** который расположен часть пути в документ XML, **ReadXml** будет читать следующий узел элемента и будет рассматривать его как корневой элемент, читая до конца элемента узла только. Это не применяется, если вы **укажете XmlReadMode.Фрагмент**.  
  
## <a name="dtd-entities"></a>Сущности DTD  
 Если XML содержит сущности, определенные в схеме определения типа документа (DTD), будет <xref:System.Data.DataSet> брошено исключение, если вы попытаетесь загрузить имя файла, поток или невалифицирующее **XmlReader** на **ReadXml.** Вместо этого, вы должны создать **XmlValidatingReader**, с **EntityHandling** набор **EntityHandling.ExpandEntities**, и передать **XmlValidatingReader** **ReadXml**. **XmlValidatingReader** расширит сущности до того, как будет прочитан <xref:System.Data.DataSet>.  
  
 В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML-потока. Первый пример показывает, что имя файла передается методу **ReadXml.** Во втором примере показана загрузка строки, содержащей XML-код, с помощью объекта <xref:System.IO.StringReader>.  
  
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
> Если вы называете **ReadXml** для загрузки очень большого файла, вы можете столкнуться с медленной производительностью. Чтобы обеспечить наилучшую производительность для **ReadXml**, на большом файле, позвоните метод <xref:System.Data.DataTable.BeginLoadData%2A> для каждой таблицы в <xref:System.Data.DataSet>, а затем вызов **ReadXml**. Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.  
  
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
> Если схема XSD для <xref:System.Data.DataSet> вашего включает в себя **targetNamespace,** данные могут не быть прочитаны, <xref:System.Data.DataSet> и вы можете столкнуться с исключениями, при вызове **ReadXml** для загрузки с XML, который содержит элементы без квалификационного пространства имен. Чтобы прочитать неквалифицированные элементы в этом случае, установите **элементFormDefault,** равный «квалифицированной» в вашей схеме XSD. Пример:  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>Слияние данных из XML  
 Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>. **ReadXml** не сливается с <xref:System.Data.DataSet> XML в любую информацию о строке с соответствующими первичными ключами. Чтобы перезаписать существующую информацию о строках с новой <xref:System.Data.DataSet>информацией <xref:System.Data.DataSet.Merge%2A> от <xref:System.Data.DataSet> XML, <xref:System.Data.DataSet>используйте **ReadXml** для создания нового, а затем нового в существующую. Обратите внимание, что загрузка DiffGram с помощью **ReadXML** с **XmlReadMode** **DiffGram** объединит строки, которые имеют тот же уникальный идентификатор.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [Наследование реляционной структуры набора данных от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка сведений о схеме набора данных из XML](loading-dataset-schema-information-from-xml.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
