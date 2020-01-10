---
title: Запросы XPath и пространства имен
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: 91503ce0bffa1a9390432a51bff1ef10d80f563a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709781"
---
# <a name="xpath-queries-and-namespaces"></a>Запросы XPath и пространства имен
Запросы XPath учитывают наличие пространств имен в XML-документе и могут использовать префиксы пространств имен для дополнения имен элементов и атрибутов. Добавление префикса пространства имен к именам элементов и атрибутов ограничивает набор узлов, возвращаемых запросом XPath, лишь теми узлами, которые принадлежат к определенному пространству имен.  
  
 Например, если префикс `books` соответствует пространству имен `http://www.contoso.com/books`, то следующий запрос XPath `/books:books/books:book` выберет только элементы `book` в пространстве имен `http://www.contoso.com/books`.  
  
## <a name="the-xmlnamespacemanager"></a>Класс XmlNamespaceManager  
 Чтобы использовать пространства имен в запросе XPath, объект, производный от интерфейса <xref:System.Xml.IXmlNamespaceResolver>, например класс <xref:System.Xml.XmlNamespaceManager>, конструируется с URI-кодом пространства имен и префиксом, включаемым в запрос XPath.  
  
 Объект <xref:System.Xml.XmlNamespaceManager> можно использовать в запросе любым из следующих способов.  
  
- Объект <xref:System.Xml.XmlNamespaceManager> связывается с существующим объектом <xref:System.Xml.XPath.XPathExpression> с помощью метода <xref:System.Xml.XPath.XPathExpression.SetContext%2A> объекта <xref:System.Xml.XPath.XPathExpression>. Также можно скомпилировать новый объект <xref:System.Xml.XPath.XPathExpression> с помощью статического метода <xref:System.Xml.XPath.XPathExpression.Compile%2A>, который принимает в качестве параметров строку, представляющую выражение XPath, и объект <xref:System.Xml.XmlNamespaceManager>, а затем возвращает новый объект <xref:System.Xml.XPath.XPathExpression>.  
  
- Сам объект <xref:System.Xml.XmlNamespaceManager> передается в качестве параметра методу класса <xref:System.Xml.XPath.XPathNavigator> вместе со строкой, представляющей выражение XPath.  
  
 Далее представлены методы класса <xref:System.Xml.XPath.XPathNavigator>, которые принимают в качестве параметра объект, производный от интерфейса <xref:System.Xml.IXmlNamespaceResolver>.  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a>Пространство имен по умолчанию  
 В следующем XML-документе используется пространство имен по умолчанию с пустым префиксом, чтобы объявить пространство имен `http://www.contoso.com/books`.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 XPath обрабатывает пустой префикс как пространство имен `null`. Другими словами, в запросах XPath можно использовать только префиксы, сопоставленные с пространствами имен. Это значит, что если нужно построить запрос к пространству имен в XML-документе, то даже если оно является пространством имен по умолчанию, для него необходимо определить префикс.  
  
 Например, если не определить префикс для представленного выше XML-документа, запрос XPath `/books/book` не вернет никаких результатов.  
  
 Префикс должен быть привязан, чтобы исключить неоднозначность во время запроса документов, часть узлов которых лежит вне пространства имен, а часть - в пространстве имен по умолчанию.  
  
 В следующем коде определяется префикс для пространства имен по умолчанию и выбираются все элементы `book` из пространства имен `http://www.contoso.com/books`.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Выборка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Вычисление выражения XPath с помощью класса XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Соответствие узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [Типы узлов, распознаваемые запросами XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [Скомпилированные выражения XPath](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
