---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151056"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Загрузка сведений о схеме набора данных из XML
Схема <xref:System.Data.DataSet> a (ее таблицы, столбцы, связи и ограничения) может быть определена программно, создана методами <xref:System.Data.Common.DataAdapter> **заполнения** или **заполнения,** или загружена из документа XML. Для загрузки информации о схеме **DataSet** из документа XML можно использовать либо **ReadXmlSchema,** либо метод **InferXmlSchema** **DataSet.** **ReadXmlSchema** позволяет загружать или выгонить информацию о схеме **DataSet** из документа, содержащего схему определения XML Schema (XSD) или документ XML с inline XML Schema. **InferXmlSchema** позволяет вывести схему из документа XML, игнорируя некоторые указанные пространства имен XML.  
  
> [!NOTE]
> Заказ таблицы в **DataSet** может быть не сохранен при использовании Web-сервисов или сериализации XML для передачи **DataSet,** созданного в памяти с помощью конструкций XSD (например, вложенных связей). Таким образом, получатель **DataSet** не должен зависеть от заказа таблицы в этом случае. Однако заказ таблицвсегдасохраняется, если схема передачи **DataSet** была прочитана из файлов XSD, а не создавалась в памяти.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Для загрузки схемы **DataSet** из документа XML без загрузки данных можно использовать метод **ReadXmlSchema** **DataSet.** **ReadXmlSchema** создает схему **DataSet,** определяемую с помощью схемы определения XML Schema (XSD).  
  
 Метод **ReadXmlSchema** требует загрузки одного аргумента имени файла, потока или **XmlReader,** содержащего xML-документ. XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные. Подробнее о написании встроенной схемы xML Schema можно узнать из [XML Schema (XSD).](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
  
 Если документ XML, переданный **ReadXmlSchema,** не содержит информации о вливной схеме, **ReadXmlSchema** выдвинет схему из элементов в документе XML. Если **DataSet** уже содержит схему, текущая схема будет расширена путем добавления новых таблиц, если они еще не существуют. Новые столбцы не будут добавляться к существующим таблицам. Если добавленная колонка уже существует в **DataSet,** но имеет несовместимый тип с столбцом, найденным в XML, выбрасывается исключение. Подробную информацию о том, как **ReadXmlSchema** выносит схему из документа XML, [см. Вывод о соотношении DataSet от XML.](inferring-dataset-relational-structure-from-xml.md)  
  
 Хотя **ReadXmlSchema** загружает или выносит только схему **DataSet,** метод **ReadXml** **DataSet** загружает или выносит как схему, так и данные, содержащиеся в документе XML. Для получения дополнительной информации [см. Загрузка Набора данных из XML](loading-a-dataset-from-xml.md).  
  
 Следующие примеры кода показывают, как загрузить схему **DataSet** из документа или потока XML. На первом примере показано, что имя файла XML Schema передается методу **ReadXmlSchema.** Второй пример показывает **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
 Можно также поручить **DataSet** сделать вывод о своей схеме из документа XML с помощью метода **InferXmlSchema** **DataSet.** **InferXmlSchema** функционирует так же, как и **ReadXml** с **XmlReadMode** **InferSchema** (загружает данные, а также выводы схемы), и **ReadXmlSchema,** если считывается документ не содержит водной схемы. Тем не менее, **InferXmlSchema** предоставляет дополнительную возможность, позволяющую указывать определенные пространства имен XML, которые будут проигнорированы при выводе схемы. **InferXmlSchema** принимает два необходимых аргумента: расположение документа XML, указанного именем файла, потоком или **XmlReader;** и строки массива XML пространства имен, которые будут проигнорированы операцией.  
  
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
  
 Из-за атрибутов, указанных для элементов в предыдущем документе XML, как метод **ReadXmlSchema,** так и метод **ReadXml** с **XmlReadMode** **of InferSchema** создадут таблицы для каждого элемента в документе: **Категории** **, CategoryID**, **CategoryName**, **Описание**, **Продукты,** **ProductID,** **ReorderLevel**, и **Прекращение**. (Для получения дополнительной [информации см. Вывод на соотношения DataSet от XML.)](inferring-dataset-relational-structure-from-xml.md) Однако более подходящей структурой было бы создание только таблиц **категорий** и **продуктов,** а затем создание **categoryID,** **CategoryName**и столбцов **описания** в таблице **Категорий** и **ProductID,** **ReorderLevel**и **Discontinued** столбцы в таблице **Продуктов.** Для обеспечения того, чтобы выведенная схема игнорировала атрибуты, указанные в элементах XML, используйте метод **InferXmlSchema** и укажите пространство имен XML для того, чтобы **данные officedata** были проигнорированы, как показано в следующем примере.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наследование реляционной структуры набора данных от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Определение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
