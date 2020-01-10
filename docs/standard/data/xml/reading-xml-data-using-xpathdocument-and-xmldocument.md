---
title: Чтение XML-данных с помощью XPathDocument и XmlDocument
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
ms.openlocfilehash: 87ae96944f9a9f2bbcefb54c343f429c75c3022d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710392"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a>Чтение XML-данных с помощью XPathDocument и XmlDocument
Существует два способа чтения XML-документа в пространстве имен <xref:System.Xml.XPath?displayProperty=nameWithType>. Один - считывание XML-документа с использованием доступного только для чтения класса <xref:System.Xml.XPath.XPathDocument>, а другой - считывание XML-документа с использованием редактируемого класса <xref:System.Xml.XmlDocument> в пространстве имен <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a>Чтение XML-документов с использованием класса XPathDocument  
 Класс <xref:System.Xml.XPath.XPathDocument> обеспечивает быстрое и доступное только для чтения представление XML-документа в памяти с использованием модели данных XPath. Экземпляры класса <xref:System.Xml.XPath.XPathDocument> создаются с использованием одного из шести конструкторов. Эти конструкторы позволяют прочитать XML-документ с использованием как объектов <xref:System.IO.Stream>, <xref:System.IO.TextReader> или <xref:System.Xml.XmlReader>, так и строкового `string` пути к XML-файлу.  
  
 В следующем примере продемонстрировано использование конструктора <xref:System.Xml.XPath.XPathDocument> класса `string` для чтения XML-документа.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a>Чтение XML-документов с помощью класса XmlDocument  
 Класс <xref:System.Xml.XmlDocument> представляет собой изменяемое в памяти представление XML-документа, реализующего модель W3C DOM базового уровня 1 и базового уровня 2. Экземпляры класса <xref:System.Xml.XmlDocument> создаются с использованием одного из трех конструкторов. Можно создать новый, пустой объект <xref:System.Xml.XmlDocument> путем вызова конструктора класса <xref:System.Xml.XmlDocument> без параметров. После вызова конструктора используйте метод <xref:System.Xml.XmlDocument.Load%2A>, чтобы загрузить XML-данные в новый объект <xref:System.Xml.XmlDocument> из объекта <xref:System.IO.Stream>, <xref:System.IO.TextReader> или <xref:System.Xml.XmlReader>, либо из строкового `string` пути к XML-файлу.  
  
 В следующем примере продемонстрировано использование конструктора класса <xref:System.Xml.XmlDocument> без параметров и метода <xref:System.Xml.XmlDocument.Load%2A> для чтения XML-документа.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a>Определение кодировки XML-документа  
 Объект <xref:System.Xml.XmlReader> можно использовать для чтения XML-документа и создания объектов <xref:System.Xml.XPath.XPathDocument> и <xref:System.Xml.XmlDocument>, как показано в предыдущих разделах. Однако объект <xref:System.Xml.XmlReader> может считывать данные, которые не закодированы и не содержат никаких сведений о кодировке.  
  
 Класс <xref:System.Xml.XmlTextReader> наследуется от класса <xref:System.Xml.XmlReader> и предоставляет сведения о кодировке с помощью свойства <xref:System.Xml.XmlTextReader.Encoding%2A>. Его можно использовать для создания объекта <xref:System.Xml.XPath.XPathDocument> или объекта <xref:System.Xml.XmlDocument>.  
  
 Дополнительные сведения о кодировке, предоставляемых классом <xref:System.Xml.XmlTextReader> см. в справочной документации по свойству <xref:System.Xml.XmlTextReader.Encoding%2A> класса <xref:System.Xml.XmlTextReader>.  
  
## <a name="creating-xpathnavigator-objects"></a>Создание объектов XPathNavigator  
 После считывания XML-документа в объект <xref:System.Xml.XPath.XPathDocument> или <xref:System.Xml.XmlDocument>, можно создать объект <xref:System.Xml.XPath.XPathNavigator> для выбора, оценки, навигации и, в некоторых случаях, изменения базовых XML-данных.  
  
 Как класс <xref:System.Xml.XPath.XPathDocument>, так и <xref:System.Xml.XmlDocument>, наряду с классом <xref:System.Xml.XmlNode>, реализуют интерфейс <xref:System.Xml.XPath.IXPathNavigable> пространства имен <xref:System.Xml.XPath?displayProperty=nameWithType>. В результате все три класса предоставляют метод <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A>, который возвращает объект <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a>Изменение XML-документов с помощью класса XPathNavigator  
 Кроме выборки, оценки и навигации по XML-данным, класс <xref:System.Xml.XPath.XPathNavigator> в некоторых случаях можно использовать для изменения XML-документа, в зависимости от создавшего его объекта.  
  
 Класс <xref:System.Xml.XPath.XPathDocument> предназначен только для чтения, а класс <xref:System.Xml.XmlDocument> доступен для редактирования и, в результате, объекты <xref:System.Xml.XPath.XPathNavigator>, созданные из объекта <xref:System.Xml.XPath.XPathDocument>, не могут быть использованы для изменения XML-документа, а созданные из объекта <xref:System.Xml.XmlDocument> - могут. Класс <xref:System.Xml.XPath.XPathDocument> должен использоваться только для чтения XML-документа. В случаях, когда нужно изменить XML-документ или требуется доступ к дополнительной функциональности, предоставленной классом <xref:System.Xml.XmlDocument>, например, при обработке событий, нужно использовать класс <xref:System.Xml.XmlDocument>.  
  
 Свойство <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> класса <xref:System.Xml.XPath.XPathNavigator> указывает, может ли объект <xref:System.Xml.XPath.XPathNavigator> изменить XML-данные.  
  
 В следующей таблице описаны значения свойства <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> для каждого класса.  
  
|Реализация интерфейса <xref:System.Xml.XPath.IXPathNavigable>|Значение <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Доступ к XML-данным с помощью класса XPathNavigator](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [Изменение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)
- [Проверка по схеме с помощью XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
