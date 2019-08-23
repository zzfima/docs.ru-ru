---
title: Загрузка набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 24b962edc15c04cf1f68b73a7da960857658309c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928444"
---
# <a name="loading-a-dataset-from-xml"></a>Загрузка набора данных из XML
Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML-потока или XML-документа. Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.  
  
 Для заполнения <xref:System.Data.DataSet> данными из XML используйте метод <xref:System.Data.DataSet> **ReadXml** объекта. Метод **ReadXml** считывает данные из файла, потока или **XmlReader**и принимает в качестве аргументов источник XML и необязательный аргумент **XmlReadMode** . Дополнительные сведения о **XmlReader**см. в разделе [чтение XML-данных с помощью XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)). Метод **ReadXml** считывает содержимое XML-потока или документа и загружает <xref:System.Data.DataSet> с данными. Также будет создана реляционная схема в <xref:System.Data.DataSet> зависимости от указанного параметра **XmlReadMode** и наличия уже существующей реляционной схемы.  
  
 В следующей таблице описаны параметры для аргумента **XmlReadMode** .  
  
|Параметр|Описание|  
|------------|-----------------|  
|**Auto**|Это значение по умолчанию. Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.<br /><br /> — Если XML является DiffGram, используется **DiffGram** .<br />— Если <xref:System.Data.DataSet> содержит схему или XML содержит встроенную схему, используется **реадсчема** .<br />— Если объект <xref:System.Data.DataSet> не содержит схему и XML не содержит встроенную схему, используется **инферсчема** .<br /><br /> Если вы знакомы с форматом считываемых данных XML, рекомендуется установить явное значение **XmlReadMode**, а не принимать значение по умолчанию.|  
|**ReadSchema**|Считывает любую встроенную схему и загружает данные и схему.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>. Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение. Вы не сможете изменить схему существующей таблицы с помощью параметра **XmlReadMode. реадсчема**.<br /><br /> Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.<br /><br /> Встроенная схема может быть определена с помощью схемы на языке XSD. Дополнительные сведения о создании встроенной схемы в виде схемы XML см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>. Любые данные, не совпадающие с существующей схемой, удаляются. Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.<br /><br /> Если данные являются DiffGram, **игноресчема** имеет те же функциональные возможности, что и **DiffGram** *.*|  
|**InferSchema**|Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML-данных, а затем загружает данные.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы. Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы. Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.<br /><br /> Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, см. в разделе вывод [реляционной структуры набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Считывает данные DiffGram и добавляет их в текущую схему. **DiffGram** объединяет новые строки с существующими строками, в которых уникальные значения идентификаторов совпадают. См. подраздел «Слияние данных из XML» в конце данного раздела. Дополнительные сведения о дельтами см. в разделе [дельтами](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Экстент**|Продолжает считывание нескольких XML-фрагментов до достижения конца потока. Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы. Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.|  
  
> [!NOTE]
> Если вы передали **XmlReader** в метод **ReadXml** , который располагает частью пути в XML-документ, то метод **ReadXml** прочитает его в следующий узел Element и будет считать его корневым элементом, считывая его только до конца узла Element. Это не применяется при указании **XmlReadMode. Fragment**.  
  
## <a name="dtd-entities"></a>Сущности DTD  
 Если XML содержит сущности, определенные в схеме определения типа документа (DTD), при попытке загрузить объект <xref:System.Data.DataSet> путем передачи имени файла, потока или непроверяющего **XmlReader** в метод **ReadXml**будет создано исключение. Вместо этого необходимо создать **XmlValidatingReader**, указав для **EntityHandling** значение **EntityHandling. ExpandEntities**и передав **XmlValidatingReader** в **ReadXml**. **XmlValidatingReader** развернет сущности перед считыванием <xref:System.Data.DataSet>.  
  
 В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML-потока. В первом примере показано имя файла, передаваемое методу **ReadXml** . Во втором примере показана загрузка строки, содержащей XML-код, с помощью объекта <xref:System.IO.StringReader>.  
  
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
> При вызове метода **ReadXml** для загрузки очень большого файла может возникнуть снижение производительности. Чтобы обеспечить наилучшую производительность для метода **ReadXml**, в большом файле вызовите <xref:System.Data.DataTable.BeginLoadData%2A> метод для <xref:System.Data.DataSet>каждой таблицы в, а затем вызовите метода **ReadXml**. Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.  
  
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
> Если схема <xref:System.Data.DataSet> XSD для включает в себя **targetNamespace**, данные могут быть не считаны, и при вызове метода **ReadXml** могут возникнуть исключения, если для загрузки <xref:System.Data.DataSet> с XML, содержащим элементы с неквалифицированным пространством имен, возникает исключение. Для чтения неквалифицированных элементов в этом случае задайте **elementFormDefault** равным "квалифицированный" в схеме XSD. Например:  
  
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
 Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>. **ReadXml** не выполняет слияние из XML-кода <xref:System.Data.DataSet> с любыми строками с совпадающими первичными ключами. Чтобы перезаписать существующие сведения о строке новыми данными из XML, используйте **ReadXml** , чтобы создать новый <xref:System.Data.DataSet>объект, а <xref:System.Data.DataSet.Merge%2A> затем новый <xref:System.Data.DataSet> в существующем <xref:System.Data.DataSet>. Обратите внимание, что при загрузке DiffGram с помощью метода **ReadXml** с параметром **XmlReadMode** для **DiffGram** будут объединены строки с одинаковым уникальным идентификатором.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
