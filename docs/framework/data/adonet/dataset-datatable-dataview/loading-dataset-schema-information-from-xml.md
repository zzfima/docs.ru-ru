---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 4b212a7233e6eec93cdce3e521b58e08745e35e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a>Загрузка сведений о схеме набора данных из XML
Схема <xref:System.Data.DataSet> (его таблиц, столбцов, связей и ограничений) можно определить программно, созданные **заполнения** или **FillSchema** методы <xref:System.Data.Common.DataAdapter>, или загрузке из XML-документ. Для загрузки **DataSet** данные схемы из XML-документа, можно использовать **ReadXmlSchema** или **InferXmlSchema** метод **набораданных**. **ReadXmlSchema** позволяет загружать или выводить **DataSet** сведений о схеме из документа, содержащего схемы языка определения схемы XML или XML-документа со встроенной схемой XML. **InferXmlSchema** дает возможность выводить схему из XML-документ, учитывая некоторые указанные пространства имен XML.  
  
> [!NOTE]
>  Упорядочение таблицы в **DataSet** могут не сохраняться при использовании веб-службы или XML-сериализации для передачи **DataSet** в памяти, который был создан с помощью конструкций XSD (таких как вложенные связи). Таким образом, что получатель **набора данных** не должны зависеть от упорядочение таблицы в этом случае. Однако упорядочение таблицы всегда сохраняется, если схема **набора данных** , передаваемый было считано из XSD-файлов, а создана в памяти.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Для загрузки схемы **DataSet** из XML-документа без загрузки других данных, можно использовать **ReadXmlSchema** метод **набора данных**. **ReadXmlSchema** создает **DataSet** схемой, определенной с помощью схемы языка определения схемы XML.  
  
 **ReadXmlSchema** метод принимает один аргумент имени файла, потока или **XmlReader** содержащий документ XML для загрузки. XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные. Дополнительные сведения о записи встроенной схемы в виде схемы XML см. в разделе [наследование реляционной структуры набора данных из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Если XML-документ, передаваемые **ReadXmlSchema** не содержит встроенной схемы сведений, **ReadXmlSchema** выведет схему из элементов в XML-документ. Если **набора данных** уже содержит схему, текущая схема будет расширена путем добавления новых таблиц, если они еще не существует. Новые столбцы не будут добавляться к существующим таблицам. Если добавленный столбец уже существует в **набора данных** , но имеет несовместимый тип со столбцом, содержащимся в XML, создается исключение. Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, в разделе [вывод реляционной структуры набора данных из XML-кода](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Несмотря на то что **ReadXmlSchema** загружает или выводит только схема **DataSet**, **ReadXml** метод **набора данных** загружает или выводит оба Схема и данные, содержащиеся в XML-документе. Дополнительные сведения см. в разделе [загрузка DataSet из XML-кода](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 В следующем примере кода показано, как загрузить **DataSet** схемы из XML-документа или потока. В первом примере имя файла схемы XML, передаваемые **ReadXmlSchema** метод. Во втором примере показывается **System.IO.StreamReader**.  
  
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
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 Можно также указать **DataSet** вывести свою схему из XML-документа с помощью **InferXmlSchema** метод **набора данных**. **InferXmlSchema** работает так же, как **ReadXml** с **XmlReadMode** из **InferSchema** (загружает данные а также формирует схему) и **ReadXmlSchema** если считанный документ не содержит встроенной схемы. Тем не менее **InferXmlSchema** предоставляет дополнительные возможности, позволяя для указания пространства имен XML игнорироваться при формировании схемы. **InferXmlSchema** принимает два обязательных аргумента: местоположение XML-документа, указанные по имени файла, потока или **XmlReader**; и строковый массив пространств имен XML, чтобы использоваться в этой операции.  
  
 Например, рассмотрим следующий XML-код:  
  
```xml  
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
  
 Из-за атрибуты, указанные для элементов в этом документе XML как **ReadXmlSchema** метод и **ReadXml** метод с **XmlReadMode** из **InferSchema** создающих таблицы для каждого элемента в документ: **категории**, **CategoryID**, **CategoryName**, **Описание**, **продуктов**, **ProductID**, **ReorderLevel**, и **неподдерживаемые**. (Дополнительные сведения см. в разделе [вывод реляционной структуры набора данных из XML-кода](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Тем не менее, более подходящие структуры будет создавать только **категории** и **продуктов** таблиц и создание **CategoryID**, **«категория»** , и **описание** столбцы в **категории** таблицы, и **ProductID**, **ReorderLevel**, и **Discontinued** столбцы в **продуктов** таблицы. Чтобы убедиться, что выводимой схеме пропускает атрибуты, указанные в XML-элементы, используйте **InferXmlSchema** метод и укажите пространство имен XML для **officedata** следует игнорировать, как показано в Ниже приведен пример.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>См. также  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
