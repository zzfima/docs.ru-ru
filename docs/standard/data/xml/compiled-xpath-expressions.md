---
title: Скомпилированные выражения XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: b4675765849299050eb6cddeaaa497bc6cdc620a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711107"
---
# <a name="compiled-xpath-expressions"></a>Скомпилированные выражения XPath
Объект <xref:System.Xml.XPath.XPathExpression> представляет скомпилированный запрос XPath, возвращаемый либо статическим методом <xref:System.Xml.XPath.XPathExpression.Compile%2A> класса <xref:System.Xml.XPath.XPathExpression>, либо методом <xref:System.Xml.XPath.XPathNavigator.Compile%2A> класса <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="the-xpathexpression-class"></a>Класс XPathExpression  
 Скомпилированный запрос XPath, представляемый объектом <xref:System.Xml.XPath.XPathExpression> полезен в случаях, когда один запрос XPath используется несколько раз.  
  
 Например, если метод <xref:System.Xml.XPath.XPathNavigator.Select%2A> вызывается несколько раз, то вместо многократного использования строки, представляющей запрос XPath, используйте метод <xref:System.Xml.XPath.XPathExpression.Compile%2A> класса <xref:System.Xml.XPath.XPathExpression> или метод <xref:System.Xml.XPath.XPathNavigator.Compile%2A> класса <xref:System.Xml.XPath.XPathNavigator>, чтобы скомпилировать запрос XPath и поместить его в кэш в объекте <xref:System.Xml.XPath.XPathExpression> для повторного использования и повышения производительности.  
  
 Скомпилированный объект <xref:System.Xml.XPath.XPathExpression> можно использовать как входной аргумент для следующих методов класса <xref:System.Xml.XPath.XPathNavigator> в зависимости от типа, возвращаемого запросом XPath.  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 В следующей таблице описаны возвращаемые типы W3C XPath и их эквиваленты в платформе Microsoft .NET Framework, а также методы, с которыми можно использовать объект <xref:System.Xml.XPath.XPathExpression> в зависимости от возвращаемого им типа.  
  
|Тип возвращаемого значения W3C XPath|Эквивалентный тип в .NET Framework|Описание|Методы|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|Неупорядоченная коллекция узлов без повторяющихся узлов, созданная в порядке документа.|<xref:System.Xml.XPath.XPathNavigator.Select%2A> или <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`Boolean`|<xref:System.Boolean>|Значение `true` или `false`.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> или<br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|Число с плавающей запятой.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|Последовательность символов UCS.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> Метод <xref:System.Xml.XPath.XPathNavigator.Matches%2A> принимает в качестве параметра выражение XPath. Метод <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> возвращает объект <xref:System.Xml.XPath.XPathNavigator>, а не один из возвращаемых типов W3C XPath.  
  
### <a name="the-returntype-property"></a>Свойство ReturnType  
 После компиляции запроса XPath в объект <xref:System.Xml.XPath.XPathExpression> можно использовать свойство <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> объекта <xref:System.Xml.XPath.XPathExpression>, чтобы определить возвращаемый тип запроса XPath.  
  
 Свойство <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> возвращает одно из следующих значений перечисления <xref:System.Xml.XPath.XPathResultType>, представляющего возвращаемые типы W3C XPath.  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 В следующем примере используется объект <xref:System.Xml.XPath.XPathExpression>, чтобы вернуть число и набор узлов из файла `books.xml`. Свойство <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> каждого объекта <xref:System.Xml.XPath.XPathExpression>, а также результаты методов <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> и <xref:System.Xml.XPath.XPathNavigator.Select%2A> записываются в консоль.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 В примере в качестве входных данных используется файл `books.xml`.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a>Выражения XPath повышенной производительности  
 Для повышения производительности используйте в запросах по возможности наиболее точно заданные выражения XPath. Например, если узел `book` является дочерним для узла `bookstore`, а узел `bookstore` является элементом верхнего уровня в XML-документе, то использование выражения XPath `/bookstore/book` обеспечит скорость большую, чем использование выражения `//book`. Выражение XPath `//book` будет просматривать каждый узел в XML-дереве для определения совпадающих узлов.  
  
 Кроме того, использование методов перемещения по набору узлов, предоставляемых классом <xref:System.Xml.XPath.XPathNavigator>, может повысить производительность по сравнению с методами выбора, предоставляемыми классом <xref:System.Xml.XPath.XPathNavigator>, в случаях с простыми критериями выбора. Например, если нужно выбрать первый дочерний узел текущего узла, быстрее использовать метод <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>, чем выражение XPath `child::*[1]` и метод <xref:System.Xml.XPath.XPathNavigator.Select%2A>.  
  
 Дополнительные сведения о методах перемещения по набору узлов в классе <xref:System.Xml.XPath.XPathNavigator> см. в руководстве по [перемещению по узлам с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Выборка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Вычисление выражения XPath с помощью класса XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Соответствие узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [Типы узлов, распознаваемые запросами XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [Запросы XPath и пространства имен](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
