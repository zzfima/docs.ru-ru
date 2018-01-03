---
title: "Загрузка набора данных из XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: ebbe1addf47bc76903e362cfb353ade359a1c8ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="loading-a-dataset-from-xml"></a>Загрузка набора данных из XML
Содержимое объекта <xref:System.Data.DataSet> технологии ADO.NET может быть создано на основе XML-потока или XML-документа. Кроме того, использование .NET Framework обеспечивает большую гибкость при выборе сведений, загружаемых из XML, а также способа создания схемы или реляционной структуры <xref:System.Data.DataSet>.  
  
 Для заполнения <xref:System.Data.DataSet> с данными из XML следует использовать **ReadXml** метод <xref:System.Data.DataSet> объекта. **ReadXml** метод выполняет чтение из файла, потока или **XmlReader**, а в качестве аргумента принимает источник XML и еще один дополнительный **XmlReadMode** аргумент. (Дополнительные сведения о **XmlReader**, в разделе [NIB: чтение данных XML с помощью XmlTextReader](http://msdn.microsoft.com/en-us/762c069b-b50c-41b8-936e-39eacfb0d540).) **ReadXml** метод считывает содержимое XML-потока или документа и загружает <xref:System.Data.DataSet> с данными. Он также создаст реляционную схему <xref:System.Data.DataSet> в зависимости от **XmlReadMode** указан и ли реляционной схемы уже существует.  
  
 В следующей таблице описаны параметры для **XmlReadMode** аргумент.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**Auto**|Это значение по умолчанию. Анализирует XML и выбирает наиболее подходящий параметр в следующем порядке.<br /><br /> -Если допустимость XML-DiffGram, **DiffGram** используется.<br />-Если <xref:System.Data.DataSet> содержит схему или XML-документ содержит встроенную схему, **ReadSchema** используется.<br />-Если <xref:System.Data.DataSet> содержит схемы и XML не содержит встроенную схему, **InferSchema** используется.<br /><br /> Если известен формат считанного XML-кода, для достижения оптимальной производительности рекомендуется установить явно **XmlReadMode**, а не принимать **автоматически** по умолчанию.|  
|**ReadSchema**|Считывает любую встроенную схему и загружает данные и схему.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, новые таблицы добавляются из встроенной схемы в существующую в наборе данных <xref:System.Data.DataSet>. Если любая таблица встроенной схемы уже существует в наборе данных <xref:System.Data.DataSet>, возникает исключение. Вы не сможете изменять схему из существующей таблицы с помощью **XmlReadMode.ReadSchema**.<br /><br /> Если набор данных <xref:System.Data.DataSet> не содержит схему, а также отсутствует встроенная схема, то данные не считываются.<br /><br /> Встроенная схема может быть определена с помощью схемы на языке XSD. Дополнительные сведения о записи встроенной схемы в виде схемы XML см. в разделе [наследование реляционной структуры набора данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).|  
|**IgnoreSchema**|Не учитывает любую встроенную схему и загружает данные в существующую схему <xref:System.Data.DataSet>. Любые данные, не совпадающие с существующей схемой, удаляются. Если схема не существует в наборе данных <xref:System.Data.DataSet>, данные не загружаются.<br /><br /> Если данные являются DiffGram, **IgnoreSchema** имеет ту же функциональность, что **DiffGram** *.*|  
|**InferSchema**|Не учитывает любую встроенную схему и формирует по одной схеме в расчете на каждую структуру XML-данных, а затем загружает данные.<br /><br /> Если набор данных <xref:System.Data.DataSet> уже содержит схему, текущая схема расширяется путем добавления столбцов в существующие таблицы. Дополнительные таблицы не будут добавлены, если отсутствуют существующие таблицы. Если уже существует формируемая таблица с другим пространством имен или любой из формируемых столбцов конфликтует с существующими столбцами, то возникает исключение.<br /><br /> Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, в разделе [вывод реляционной структуры набора данных из XML-кода](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).|  
|**DiffGram**|Считывает данные DiffGram и добавляет их в текущую схему. **DiffGram** производится слияние новых строк с существующими строками, в которых совпадают уникальные идентифицирующие значения. См. подраздел «Слияние данных из XML» в конце данного раздела. Дополнительные сведения о формате см. в разделе [дельты](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).|  
|**Фрагмент**|Продолжает считывание нескольких XML-фрагментов до достижения конца потока. Фрагменты, совпадающие со схемой <xref:System.Data.DataSet>, добавляются в соответствующие таблицы. Фрагменты, не совпадающие со схемой <xref:System.Data.DataSet>, удаляются.|  
  
> [!NOTE]
>  Если передать **XmlReader** для **ReadXml** , является позиционированной частью пути в XML-документ, **ReadXml** производит считывание до следующего узла элемента и рассматривает его в качестве корня элемент, до конца узла элемента только чтение. Это неприменимо при указании **XmlReadMode.Fragment**.  
  
## <a name="dtd-entities"></a>Сущности DTD  
 Если XML содержит сущности, определенных в схеме определения DTD типа документа, будет создано исключение, при попытке загрузить <xref:System.Data.DataSet> , передав файл имя, потока или без проверки **XmlReader** для  **Метод ReadXml**. Вместо этого необходимо создать **XmlValidatingReader**, с **EntityHandling** значение **EntityHandling.ExpandEntities**и передать вашей  **XmlValidatingReader** для **ReadXml**. **XmlValidatingReader** развертывает сущности до его считывания <xref:System.Data.DataSet>.  
  
 В следующих примерах кода показаны способы загрузки набора данных <xref:System.Data.DataSet> из XML-потока. В первом примере имя файла, передаваемые **ReadXml** метод. Во втором примере показана загрузка строки, содержащей XML-код, с помощью объекта <xref:System.IO.StringReader>.  
  
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
>  При вызове метода **ReadXml** для загрузки очень больших файлов, могут возникнуть снижения производительности. Чтобы обеспечить наилучшую производительность для **ReadXml**, больших файлов, вызовите метод <xref:System.Data.DataTable.BeginLoadData%2A> метод для каждой таблицы в <xref:System.Data.DataSet>, а затем вызвать **ReadXml**. Наконец, вызывайте метод <xref:System.Data.DataTable.EndLoadData%2A> для каждой таблицы в наборе данных <xref:System.Data.DataSet>, как показано в следующем примере.  
  
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
>  Если схема XSD для вашей <xref:System.Data.DataSet> включает **targetNamespace**, данные не могут быть считаны и исключения, возникающие при вызове **ReadXml** для загрузки <xref:System.Data.DataSet> с XML, содержащий элементы без указанного пространства имен. Для чтения в этом случае неполных элементов, задайте **elementFormDefault** равным «qualified» в XSD-схемы. Пример:  
  
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
 Если набор данных <xref:System.Data.DataSet> уже содержит данные, новые данные из XML-кода добавляются к данным, находящимся в наборе данных <xref:System.Data.DataSet>. **Метод ReadXml** не переносит слиянием из XML-документ в <xref:System.Data.DataSet> любых данных из строк с совпадающими первичными ключами. Чтобы перезаписать существующие данные строк с новыми данными из XML, используйте **ReadXml** для создания нового <xref:System.Data.DataSet>, а затем <xref:System.Data.DataSet.Merge%2A> новый <xref:System.Data.DataSet> с существующим <xref:System.Data.DataSet>. Обратите внимание, что при загрузке данных DiffGram с использованием **ReadXML** с **XmlReadMode** из **DiffGram** происходит слияние строк, имеющих одинаковый уникальный идентификатор.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Загрузка сведений о схеме DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
