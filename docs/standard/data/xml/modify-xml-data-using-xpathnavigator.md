---
title: Изменение XML-данных с помощью класса XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
ms.openlocfilehash: 906de1ded4961b7c67d48a010555d139df97cded
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710639"
---
# <a name="modify-xml-data-using-xpathnavigator"></a>Изменение XML-данных с помощью класса XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет набор методов для изменения узлов и значений в XML-документе. Для использования этих методов необходимо сделать редактируемым объект <xref:System.Xml.XPath.XPathNavigator>, то есть установить для свойства <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> значение `true`.  
  
 Объекты <xref:System.Xml.XPath.XPathNavigator> для правки XML-документа создаются с помощью метода <xref:System.Xml.XmlDocument.CreateNavigator%2A> класса <xref:System.Xml.XmlDocument>. Объекты <xref:System.Xml.XPath.XPathNavigator>, созданные классом <xref:System.Xml.XPath.XPathDocument>, доступны только для чтения, и любая попытка вызова методов редактирования объекта <xref:System.Xml.XPath.XPathNavigator>, созданного объектом <xref:System.Xml.XPath.XPathDocument>, приводит к возникновению исключения <xref:System.NotSupportedException>.  
  
 Дополнительные сведения о доступных только для чтения и изменяемых объектах <xref:System.Xml.XPath.XPathNavigator> см. в руководстве по [чтению данных XML с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="modifying-nodes"></a>Изменение узлов  
 Удобнее всего изменять значение узла с помощью методов <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> и <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> класса <xref:System.Xml.XPath.XPathNavigator>.  
  
 В следующей таблице описывается действие этих методов на различные типы узлов.  
  
|<xref:System.Xml.XPath.XPathNodeType>|Измененные данные|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|Не поддерживается.|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|Содержимое элемента.|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|Значение атрибута.|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|Текстовое содержимое.|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|Содержимое, за исключением цели.|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|Содержимое комментария.|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|Не поддерживается.|  
  
> [!NOTE]
> Изменение узлов <xref:System.Xml.XPath.XPathNodeType.Namespace> и узла <xref:System.Xml.XPath.XPathNodeType.Root> не поддерживается.  
  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет также набор методов для вставки и удаления узлов. Дополнительные сведения о вставке и удалении узлов в XML-документах вы найдете в статьях [Вставка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md) и [Удаление XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md).  
  
### <a name="modifying-untyped-values"></a>Изменение нетипизированных значений  
 Метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> просто вставляет нетипизированное значение `string`, переданное в качестве параметра, как значение узла, на котором в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>. Значение вставляется без какого-либо типа и без проверки допустимости нового значения в соответствии с типом узла, если доступны сведения о схеме.  
  
 В следующем примере метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> используется для обновления всех элементов `price` в файле `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a>Изменение типизированных значений  
 Когда тип узла является простым типом XML-схемы W3C, новое значение, вставленное методом <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, проверяется по особенностям простого типа, прежде чем будет установлено значение. Если новое значение недопустимо в соответствии с типом узла (например, при установке значения `-1` для элемента с типом `xs:positiveInteger`), возникает исключение.  
  
 В следующем примере предпринимается попытка изменить значение элемента `price` первого элемента `book` в файле `contosoBooks.xml` на <xref:System.DateTime>. Так как в файлах `price` тип элемента `xs:decimal` по XML-схеме определен как `contosoBooks.xsd`, возникает исключение.  
  
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
  
navigator.SetTypedValue(DateTime.Now)  
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
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 В примере также в качестве входных данных используется `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a>Последствия изменения строго типизированных XML-данных  
 Класс <xref:System.Xml.XPath.XPathNavigator> использует схему XML W3C, как основу для описания строго типизированного XML. Элементы и атрибуты могут сопровождаться информацией о типе, создаваемой по результатам проверки на основе документа схемы XML W3C. Элементы, содержащие другие элементы или атрибуты, называются сложными типами, а имеющие только текстовое содержимое - простыми типами.  
  
> [!NOTE]
> Атрибуты могут иметь только простой тип.  
  
 Элемент или атрибут считается соответствующим схеме, если он соответствует всем правилам, специфичным для определения его типа. Элемент, относящийся к простому типу `xs:int`, чтобы соответствовать схеме, должен содержать числовое значение в диапазоне от -2147483648 до 2147483647. Для сложных типов соответствие элемента схеме определяется на основе соответствия схеме его дочерних элементов и атрибутов. Таким образом, если элемент соответствует определению своего сложного типа, все его дочерние элементы и атрибуты соответствуют определениям своих типов. Аналогично, если хотя бы один из дочерних элементов или атрибутов элемента не соответствует определению своего типа или факт его соответствия не установлен, весь элемент также не соответствует или его соответствие не установлено.  
  
 Поскольку соответствие элемента зависит от соответствия его дочерних элементов и атрибутов, их изменения могут повлиять на соответствие элемента, который ранее соответствовал. Конкретнее, если дочерние элементы или атрибуты элемента добавляются, изменяются или удаляются, элемент переходит в состояние неустановленного соответствия. Чтобы отразить этот факт, свойство <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> свойства <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> элемента получает значение <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>. Затем этот эффект рекурсивно распространяется вверх по XML-документу, поскольку соответствие родительского элемента данного элемента (и его родительского элемента и т. п.) также приходит в неустановленное состояние.  
  
 Дополнительные сведения о проверке схемы и классе <xref:System.Xml.XPath.XPathNavigator> см. в статье [Проверка по схеме с помощью XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md).  
  
### <a name="modifying-attributes"></a>Изменение атрибутов  
 Для изменения узлов типизированных и нетипизированных атрибутов, а также других типов узлов, перечисленных в разделе «Изменение узлов», применяются методы <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> и <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>.  
  
 В следующем примере изменяется значение атрибута `genre` первого элемента `book` в файле `books.xml`.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
navigator.MoveToChild("book", String.Empty)  
navigator.MoveToAttribute("genre", String.Empty)  
  
navigator.SetValue("non-fiction")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
navigator.MoveToChild("book", String.Empty);  
navigator.MoveToAttribute("genre", String.Empty);  
  
navigator.SetValue("non-fiction");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 Дополнительные сведения о методах <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> и <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> см. в разделах «Изменение нетипизированных значений» и «Изменение типизированных значений».  
  
## <a name="innerxml-and-outerxml-properties"></a>Свойства InnerXml и OuterXml  
 Свойства <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> и <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> класса <xref:System.Xml.XPath.XPathNavigator> изменяют XML-разметку узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>.  
  
 Свойство <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, разобранный содержимым заданной XML-строки (`string`). Подобным образом свойство <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, так же как и самого текущего узла.  
  
 В следующем примере свойство <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> используется для изменения значения элемента `price` и вставки нового атрибута `discount` в первый элемент `book` в файле `contosoBooks.xml`.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml");  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>"  
  
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
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>";  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a>Изменение узлов пространств имен  
 В модели DOM декларации пространств имен обрабатываются как обычные атрибуты, которые можно вставлять, изменять и удалять. Класс <xref:System.Xml.XPath.XPathNavigator> не допускает подобных операций на узлах пространств имен, поскольку изменение значения узла пространства имен может изменить идентификатор элементов и атрибутов в области действия узла пространства имен, как показано в следующем примере.  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 Если изменить приведенный выше пример следующим образом, это эквивалентно переименованию всех элементов документа, поскольку изменится значение URI-кода пространства имен всех элементов.  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 Класс <xref:System.Xml.XPath.XPathNavigator> разрешает вставлять узлы пространств имен, не конфликтующие с декларациями пространств имен в данной области действия. В данном случае декларации пространств имен не производятся в нижележащих областях действия XML-документа и не вызывают переименования, как показано в следующем примере.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 Если изменить приведенный выше пример следующим образом, декларации пространств имен корректно распространяются по всему XML-документу ниже областей действия других деклараций пространств имен.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/">  
    </parent>  
</root>  
```  
  
 В приведенном выше примере атрибут `a:parent-id` вставляется в элемент `parent` в пространстве имен `http://www.contoso.com/parent-id`. Метод <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> используется для вставки атрибута для текущего элемента `parent`. Декларация пространства имен `http://www.contoso.com` автоматически вставляется классом <xref:System.Xml.XPath.XPathNavigator> для сохранения согласованности всего остального XML-документа.  
  
## <a name="modifying-entity-reference-nodes"></a>Изменение узлов ссылок на сущности  
 Ссылки на сущности в объекте <xref:System.Xml.XmlDocument> служат только для чтения; их нельзя изменять ни с помощью класса <xref:System.Xml.XPath.XPathNavigator>, ни с помощью класса <xref:System.Xml.XmlNode>. Любые попытки изменения узла ссылки на сущность приводят к исключению <xref:System.InvalidOperationException>.  
  
## <a name="modifying-xsinil-nodes"></a>Изменение узлов xsi:nil  
 Рекомендации схемы XML W3C содержат понятие обнуляемого (nillable) элемента. Обнуляемый элемент может не иметь никакого содержимого и все же быть допустимым. Понятие обнуляемого элемента аналогично понятию объекта со значением `null`. Основное различие заключается в том, что объект со значением `null` недоступен ни для каких взаимодействий, в то время как элемент `xsi:nil` все же обладает доступными свойствами (например, атрибутами), но не имеет содержимого (дочерних элементов или текста). Существование атрибута `xsi:nil` со значением `true` у элемента в XML-документе используется для обозначения отсутствия содержимого у данного элемента.  
  
 Если объект <xref:System.Xml.XPath.XPathNavigator> используется для добавления содержимого к допустимому элементу с атрибутом `xsi:nil` со значением `true`, для его атрибута `xsi:nil` будет установлено значение `false`.  
  
> [!NOTE]
> Если содержимое элемента с атрибутом `xsi:nil`, значение которого равно `false`, удалить, значение атрибута не будет изменено на `true`.  
  
## <a name="saving-an-xml-document"></a>Сохранение XML-документа  
 Сохранение изменений, внесенных в объект <xref:System.Xml.XmlDocument> с помощью описанных в данном разделе методов, выполняется с помощью методов класса <xref:System.Xml.XmlDocument>. Дополнительные сведения о сохранении изменений, внесенных в объект <xref:System.Xml.XmlDocument>, см. в руководстве по [созданию и сохранению документов](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Вставка XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [Удаление XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
