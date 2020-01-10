---
title: Удаление XML-данных с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: 062a98a9cc10e6be00f165cf617de2d92d65acbf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710366"
---
# <a name="remove-xml-data-using-xpathnavigator"></a>Удаление XML-данных с помощью XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> располагает набором методов, используемых для удаления узлов и значений из XML-документа. Для использования этих методов необходимо сделать редактируемым объект <xref:System.Xml.XPath.XPathNavigator>, то есть установить для свойства <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> значение `true`.  
  
 Объекты <xref:System.Xml.XPath.XPathNavigator> для правки XML-документа создаются с помощью метода <xref:System.Xml.XmlDocument.CreateNavigator%2A> класса <xref:System.Xml.XmlDocument>. Объекты <xref:System.Xml.XPath.XPathNavigator>, созданные классом <xref:System.Xml.XPath.XPathDocument>, доступны только для чтения, и любая попытка вызова методов редактирования объекта <xref:System.Xml.XPath.XPathNavigator>, созданного объектом <xref:System.Xml.XPath.XPathDocument>, приводит к возникновению исключения <xref:System.NotSupportedException>.  
  
 Дополнительные сведения о доступных только для чтения и изменяемых объектах <xref:System.Xml.XPath.XPathNavigator> см. в руководстве по [чтению данных XML с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="removing-nodes"></a>Удаление узлов  
 Класс <xref:System.Xml.XPath.XPathNavigator> представляет метод <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> для удаления узлов из XML-документа.  
  
### <a name="removing-a-node"></a>Удаление узла  
 Класс <xref:System.Xml.XPath.XPathNavigator> представляет метод <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> для удаления узлов текущего узла, на котором в данное время позиционирован объект <xref:System.Xml.XPath.XPathNavigator>, из XML-документа.  
  
 Узел, удаленный с помощью метода <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, более недоступен из корня объекта <xref:System.Xml.XmlDocument>. После удаления узла объект <xref:System.Xml.XPath.XPathNavigator> позиционируется на родительском узле удаленного узла.  
  
 Операция удаления не влияет на позицию любого объекта <xref:System.Xml.XPath.XPathNavigator>, позиционированного на удаленном узле. Эти объекты <xref:System.Xml.XPath.XPathNavigator> допустимы в том отношении, что могут перемещаться внутри удаленного поддерева, но не могут быть перенесены в главный узел дерева с помощью обычных методов перемещения по набору узлов класса <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> Метод <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> класса <xref:System.Xml.XPath.XPathNavigator> может быть использован для перемещения этих объектов <xref:System.Xml.XPath.XPathNavigator> назад в главный узел дерева или из главного узла дерева в удаленное поддерево.  
  
 В следующем примере элемент `price` первого элемента `book` файла `contosoBooks.xml` удаляется с помощью метода <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>. Позиция объекта <xref:System.Xml.XPath.XPathNavigator> после удаления элемента `price` - на родительском элементе `book`.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a>Удаление узла атрибута  
 Узлы атрибута удаляются из XML-документа с помощью метода <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.  
  
 Удаленный узел атрибута более недоступен из корневого узла объекта <xref:System.Xml.XmlDocument>, и объект <xref:System.Xml.XPath.XPathNavigator> позиционируется на родительском элементе.  
  
#### <a name="default-attributes"></a>Атрибуты по умолчанию  
 Независимо от метода удаления атрибутов, существуют специальные ограничения на удаление атрибутов, определенных как атрибуты по умолчанию в определении DTD или схеме XML для XML-документа. Атрибуты по умолчанию нельзя удалить, если не удален элемент, к которому они принадлежат. Атрибуты по умолчанию всегда присутствуют для элементов с объявленными атрибутами по умолчанию, и в результате удаление атрибута по умолчанию приводит к вставке в элемент атрибута замены, инициируемого с декларированным значением по умолчанию.  
  
## <a name="removing-values"></a>Удаление значений  
 Класс <xref:System.Xml.XPath.XPathNavigator> представляет методы <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> и <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> для удаления узлов нетипизированных и типизированных значений из XML-документа.  
  
### <a name="removing-untyped-values"></a>Удаление нетипизированных значений  
 Метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> просто вставляет нетипизированное значение `string`, переданное в качестве параметра, как значение узла, на котором в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>. Передача пустой строки в метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> удаляет значение текущего узла.  
  
 В следующем примере значение элемента `price` первого элемента `book` в файле `contosoBooks.xml` удаляется с помощью метода <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a>Удаление типизированных значений  
 Когда тип узла является простым типом XML-схемы W3C, новое значение, вставленное методом <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, проверяется по особенностям простого типа, прежде чем будет установлено значение. Если новое значение недопустимо в соответствии с типом узла (например, при установке значения `-1` для элемента с типом `xs:positiveInteger`), возникает исключение. Методу <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> также невозможно передать значение `null` в качестве параметра. В результате удаления значение типизированного узла должно соответствовать типу схемы узла.  
  
 В следующем примере значение элемента `price` первого элемента `book` в файле `contosoBooks.xml` удаляется с помощью метода <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> путем присвоения значения `0`. Значение узла не удаляется, но цена книги удалена в соответствии с ее типом данных `xs:decimal`.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a>Узлы пространства имен  
 Узлы пространства имен нельзя удалить из объекта <xref:System.Xml.XmlDocument>. Попытки удалить узлы пространства имен с помощью метода <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> приводят к исключению.  
  
## <a name="the-innerxml-and-outerxml-properties"></a>Свойства InnerXml и OuterXml  
 Свойства <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> и <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> класса <xref:System.Xml.XPath.XPathNavigator> изменяют XML-разметку узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>.  
  
 Свойство <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, разобранный содержимым заданной XML-строки (`string`). Подобным образом свойство <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, так же как и самого текущего узла.  
  
 В дополнение к методам, описанным в этом разделе, свойства <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> и <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> могут использоваться, чтобы удалить узлы и значения из XML-документа. Дополнительные сведения об использовании свойств <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> и [ для изменения узлов см. в <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>руководстве по изменению данных XML с помощью XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
## <a name="saving-an-xml-document"></a>Сохранение XML-документа  
 Сохранение изменений, внесенных в объект <xref:System.Xml.XmlDocument> в результате выполнения описанных в данном разделе методов, выполняется с помощью методов класса <xref:System.Xml.XmlDocument>. Дополнительные сведения о сохранении изменений, внесенных в объект <xref:System.Xml.XmlDocument>, см. в руководстве по [созданию и сохранению документов](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Вставка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [Изменение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
