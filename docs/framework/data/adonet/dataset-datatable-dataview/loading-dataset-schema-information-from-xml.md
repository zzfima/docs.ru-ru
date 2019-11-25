---
title: Загрузка сведений о схеме набора данных из XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: d834f0c4517f4ff9fe8645257d5a947c03893881
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968395"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Загрузка сведений о схеме набора данных из XML
Схема <xref:System.Data.DataSet> (ее таблиц, столбцов, связей и ограничений) может быть определена программным способом, созданными методами **Fill** или **FillSchema** <xref:System.Data.Common.DataAdapter>или загруженными из XML-документа. Чтобы загрузить сведения о схеме **набора данных** из XML-документа, можно использовать метод **ReadXmlSchema** или **инферксмлсчема** **набора данных**. **ReadXmlSchema** позволяет загружать или выводить сведения о схеме **набора данных** из документа, содержащего схему XSD, или XML-документ со встроенной схемой XML. **Инферксмлсчема** позволяет вывести схему из XML-документа, игнорируя определенные заданное пространство имен XML.  
  
> [!NOTE]
> Упорядочивание таблиц в **наборе данных** может не сохраняться при использовании веб-служб или сериализации XML для перемещения **набора данных** , созданного в памяти, с помощью конструкций XSD (например, вложенных связей). Таким образом, получатель **набора данных** не должен зависеть от упорядочения таблиц в этом случае. Однако порядок таблиц всегда сохраняется, если схема перемещаемого **набора данных** СЧИТЫВАЕТСЯ из XSD-файлов, а не создается в памяти.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Чтобы загрузить схему **набора данных** из XML-документа без загрузки данных, можно использовать метод **ReadXmlSchema** **набора данных**. **ReadXmlSchema** создает схему **набора данных** , определенную с помощью схемы языка определения схемы XML (XSD).  
  
 Метод **ReadXmlSchema** принимает один аргумент имени файла, потока или **XmlReader** , содержащий XML-документ для загрузки. XML-документ может содержать либо только схему, либо схему со встроенными XML-элементами, содержащими данные. Дополнительные сведения о создании встроенной схемы в виде схемы XML см. [в разделе Наследование реляционной структуры набора данных из схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Если XML-документ, переданный в **ReadXmlSchema** , не содержит встроенных сведений о схеме, **ReadXmlSchema** будет выводить схему из элементов XML-документа. Если **набор данных** уже содержит схему, то текущая схема будет расширена путем добавления новых таблиц, если они еще не существуют. Новые столбцы не будут добавляться к существующим таблицам. Если добавляемый столбец уже существует в **наборе данных** , но имеет несовместимый тип со столбцом, найденным в XML, возникает исключение. Дополнительные сведения о том, как **ReadXmlSchema** выводит схему из XML-документа, см. в разделе вывод [реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Хотя **ReadXmlSchema** загружает или выводит только схему **набора данных**, метод **ReadXml** **набора данных** загружает и определяет схему и данные, содержащиеся в XML-документе. Дополнительные сведения см. [в разделе Загрузка набора данных из XML](loading-a-dataset-from-xml.md).  
  
 В следующих примерах кода показано, как загрузить схему **набора данных** из XML-документа или потока. В первом примере показано имя файла схемы XML, передаваемое методу **ReadXmlSchema** . Во втором примере показан объект **System. IO. StreamReader**.  
  
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
 Также можно указать **набору данных** , что его схема будет изменяться из XML-документа с помощью метода **инферксмлсчема** **набора данных**. **Инферксмлсчема** функционирует так же, как и метода **ReadXml** с параметром **XmlReadMode** **инферсчема** (загружает данные и выводит схему), а **ReadXmlSchema** , если считываемый документ не содержит встроенной схемы. Однако **инферксмлсчема** предоставляет дополнительную возможность, позволяющую указывать определенные пространства имен XML, которые будут игнорироваться при выводимой схеме. **Инферксмлсчема** принимает два обязательных аргумента: расположение XML-документа, определяемое именем файла, потоком или **XmlReader**; и строковый массив пространств имен XML, которые будут игнорироваться операцией.  
  
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
  
 В связи с атрибутами, указанными для элементов в предыдущем XML-документе, метод **ReadXmlSchema** и метод **ReadXml** с параметром **XmlReadMode** **инферсчема** будут создавать таблицы для каждого элемента в документе: **категории**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**и больше не **поддерживаются**. (Дополнительные сведения см. [в разделе выведение реляционной структуры набора данных из XML](inferring-dataset-relational-structure-from-xml.md).) Однако более подходящей структурой является создание только таблиц **Categories** и **Products** , а затем создание столбцов **CategoryID**, **CategoryName**и **Description** в таблице **Categories** , а также столбцов **ProductID**, **ReorderLevel**и **неподдерживаемые** столбцы таблицы **Products** . Чтобы убедиться, что выводимая схема не пропускает атрибуты, указанные в XML-элементах, используйте метод **инферксмлсчема** и укажите пространство имен XML для **оффицедата** , которое будет игнорироваться, как показано в следующем примере.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Наследование реляционной структуры DataSet от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Определение реляционной структуры DataSet из XML](inferring-dataset-relational-structure-from-xml.md)
- [Загрузка DataSet из XML](loading-a-dataset-from-xml.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
