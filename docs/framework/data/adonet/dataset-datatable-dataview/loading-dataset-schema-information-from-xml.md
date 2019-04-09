---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 06dcbbedf8c1533b3da52b447c121746ce705083
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083352"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Загрузка сведений о схеме набора данных из XML
Схема <xref:System.Data.DataSet> (его таблиц, столбцов, связей и ограничения) может быть определена программно, созданные **заполнения** или **FillSchema** методы <xref:System.Data.Common.DataAdapter>, или загруженных из XML-документ. Загрузить **набора данных** сведения о схеме из XML-документа, можно использовать либо **ReadXmlSchema** или **InferXmlSchema** метод **набораданных**. **ReadXmlSchema** позволяет загружать или выводить **набора данных** сведений о схеме из документа, содержащего схему языка определения схемы XML или XML-документа со встроенной схемой XML. **InferXmlSchema** дает возможность выводить схему из XML-документа, игнорируя определенные вами пространствах имен XML.  
  
> [!NOTE]
>  Упорядочение таблицы в **набора данных** могут не сохраняться при использовании веб-службы или XML-сериализации для передачи **набора данных** в памяти, который был создан с помощью конструкций XSD (таких как вложенные связи). Таким образом, получатель **набора данных** не должно влиять на упорядочение таблицы в этом случае. Однако упорядочение таблицы всегда сохраняется, если схема **набора данных** передаваемых был считан из XSD-файлов, а создана в памяти.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Для загрузки схемы **набора данных** из XML-документа без загрузки других данных, можно использовать **ReadXmlSchema** метод **набора данных**. **ReadXmlSchema** создает **набора данных** схеме, определенной с помощью схемы языка определения схемы XML.  
  
 **ReadXmlSchema** метод принимает один аргумент имени файла, потока или **XmlReader** содержащий документ XML для загрузки. XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные. Дополнительные сведения о записи встроенной схемы в виде схемы XML, см. в разделе [наследование реляционной структуры DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Если XML-документ, передаваемый **ReadXmlSchema** не содержит встроенной схемы сведений, **ReadXmlSchema** выведет схему из элементов в XML-документа. Если **набора данных** уже содержит схему, текущая схема расширяется путем добавления новых таблиц, если они еще не существует. Новые столбцы не будут добавляться к существующим таблицам. Если добавленный столбец уже существует в **набора данных** , но имеет несовместимый тип со столбцом, содержащимся в XML, создается исключение. Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, см. в разделе [определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Несмотря на то что **ReadXmlSchema** загружает или выводит только схему **набора данных**, **ReadXml** метод **набора данных** загружает или выводит оба Схема и данные, содержащиеся в XML-документе. Дополнительные сведения см. в разделе [загрузка DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 В следующих примерах кода показано, как загрузить **набора данных** схемы из XML-документа или потока. В первом примере имя файла схемы XML, которые, передаваемые **ReadXmlSchema** метод. Второй пример показывает **System.IO.StreamReader**.  
  
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
 Вы можете проинструктировать **набора данных** вывести свою схему из XML-документа с помощью **InferXmlSchema** метод **набора данных**. **InferXmlSchema** работает так же, как использовать оба **ReadXml** с **XmlReadMode** из **InferSchema** (загружает данные как и выводит схему) и **ReadXmlSchema** если считанный документ не содержит встроенной схемы. Тем не менее **InferXmlSchema** предоставляет дополнительную возможность позволяет, чтобы указать определенные пространства имен XML, будет пропущен, если схема будет определена. **InferXmlSchema** принимает два обязательных аргумента: местоположение XML-документа, заданное по имени файла, потока или **XmlReader**; и строковый массив пространств имен XML пропускаются операцией.  
  
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
  
 Атрибуты, заданные для элементов в предыдущем XML-документа как **ReadXmlSchema** метод и **ReadXml** метод с **XmlReadMode** из **InferSchema** создает таблицы для каждого элемента в документе: **Категории**, **CategoryID**, **CategoryName**, **описание**, **продуктов**, **ProductID**, **ReorderLevel**, и **неподдерживаемые**. (Дополнительные сведения см. в разделе [определение реляционной структуры DataSet из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Однако более подходящей структурой является создание только **категории** и **продуктов** таблиц, а также создание **CategoryID**, **CategoryName** , и **описание** столбцов в **категории** таблицы, и **ProductID**, **ReorderLevel**, и **Discontinued** столбцов в **продуктов** таблицы. Чтобы убедиться, что созданная схема игнорирует атрибуты, указанные в XML-элементов, используйте **InferXmlSchema** метод и указать пространство имен XML для **officedata** следует игнорировать, как показано на Ниже приведен пример.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [Наследование реляционной структуры набора данных от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Определение реляционной структуры набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
