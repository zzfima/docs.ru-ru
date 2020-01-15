---
title: Вставка XML-данных с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 68c003467d837fe79d5e275968e47fa5dc3490cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710730"
---
# <a name="insert-xml-data-using-xpathnavigator"></a>Вставка XML-данных с помощью XPathNavigator
Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет набор методов для вставки в XML-документ одноуровневых узлов, дочерних узлов и узлов атрибутов. Для использования этих методов необходимо сделать редактируемым объект <xref:System.Xml.XPath.XPathNavigator>, то есть установить для свойства <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> значение `true`.  
  
 Объекты <xref:System.Xml.XPath.XPathNavigator> для правки XML-документа создаются с помощью метода <xref:System.Xml.XmlDocument.CreateNavigator%2A> класса <xref:System.Xml.XmlDocument>. Объекты <xref:System.Xml.XPath.XPathNavigator>, созданные классом <xref:System.Xml.XPath.XPathDocument>, доступны только для чтения, и любая попытка вызова методов редактирования объекта <xref:System.Xml.XPath.XPathNavigator>, созданного объектом <xref:System.Xml.XPath.XPathDocument>, приводит к возникновению исключения <xref:System.NotSupportedException>.  
  
 Дополнительные сведения о доступных только для чтения и изменяемых объектах <xref:System.Xml.XPath.XPathNavigator> см. в руководстве по [чтению данных XML с помощью XPathDocument и XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="inserting-nodes"></a>Вставка узлов  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет методы для вставки в XML-документ одноуровневых узлов, дочерних узлов и узлов атрибутов. Эти методы позволяют вставить узлы и атрибуты в разные места относительно текущего положения объекта <xref:System.Xml.XPath.XPathNavigator> и описываются в следующих разделах.  
  
### <a name="inserting-sibling-nodes"></a>Вставка одноуровневых узлов  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет следующие методы для вставки одноуровневых узлов.  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 Эти методы вставляют одноуровневые узлы до и после узла, на котором располагается объект <xref:System.Xml.XPath.XPathNavigator>.  
  
 Методы <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> и <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> перегружаются и принимают в качестве параметров объект `string`, <xref:System.Xml.XmlReader> или объект <xref:System.Xml.XPath.XPathNavigator>, содержащий одноуровневый узел. Оба метода также возвращают объект <xref:System.Xml.XmlWriter>, используемый для вставки одноуровневых узлов.  
  
 Методы <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> и <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> вставляют один одноуровневый узел до и после узла, на котором располагается объект <xref:System.Xml.XPath.XPathNavigator>, используя префикс пространства имен, локальное имя, URI-код пространства имен и значение, указанное в параметрах.  
  
 В следующем примере новый элемент `pages` вставляется перед дочерним элементом `price` первого элемента `book` в файле `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Дополнительные сведения о методах <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> и <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> см. в справочной документации по классу <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="inserting-child-nodes"></a>Вставка дочерних узлов  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет следующие методы для вставки дочерних узлов.  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 Эти методы вставляют дочерние узлы в конец и в начало списка дочерних узлов того узла, на котором в текущий момент располагается объект <xref:System.Xml.XPath.XPathNavigator>.  
  
 Подобно методам из раздела «Вставка одноуровневых узлов», методы <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> и <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> принимают в качестве параметров объект `string`, <xref:System.Xml.XmlReader> или объект <xref:System.Xml.XPath.XPathNavigator>, содержащий дочерний узел. Оба метода также возвращают объект <xref:System.Xml.XmlWriter>, используемый для вставки дочерних узлов.  
  
 Также, подобно методам из раздела «Вставка одноуровневых узлов», методы <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> и <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> вставляют один дочерний узел в начало и конец списка дочерних узлов узла, на котором в текущий момент располагается объект <xref:System.Xml.XPath.XPathNavigator>, используя в качестве параметров префикс пространства имен, локальное имя, URI-код пространства имен и значение, указанное в параметрах.  
  
 В следующем примере новый элемент `pages` добавляется в список дочерних элементов первого элемента `book` в файле `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Дополнительные сведения о методах <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> и <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> см. в справочной документации по классу <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="inserting-attribute-nodes"></a>Вставка узлов атрибутов  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет следующие методы для вставки узлов атрибутов.  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 Эти методы вставляют узлы атрибутов в узел элемента, на котором в текущий момент находится объект <xref:System.Xml.XPath.XPathNavigator>. Метод <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> создает узел атрибута для элемента узла, на котором в текущий момент располагается объект <xref:System.Xml.XPath.XPathNavigator>, используя в качестве параметров префикс пространства имен, локальное имя, URI-код пространства имен и указанное значение. Метод <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> возвращает объект <xref:System.Xml.XmlWriter>, используемый для вставки узлов атрибутов.  
  
 В следующем примере создаются новые атрибуты `discount` и `currency` для дочернего элемента `price` первого элемента `book` в файле `contosoBooks.xml` с использованием объекта <xref:System.Xml.XmlWriter>, возвращаемого методом <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>.  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Дополнительные сведения о методах <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> и <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> см. в справочной документации по классу <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="copying-nodes"></a>Копирование узлов  
 В некоторых случаях необходимо заполнить XML-документ содержимым другого XML-документа. Оба класса, <xref:System.Xml.XPath.XPathNavigator> и <xref:System.Xml.XmlWriter>, могут копировать узлы в объект <xref:System.Xml.XmlDocument> из существующего объекта <xref:System.Xml.XmlReader> или объекта <xref:System.Xml.XPath.XPathNavigator>.  
  
 Методы <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> и <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> класса <xref:System.Xml.XPath.XPathNavigator> имеют перегруженные варианты, которые могут принимать в качестве параметра объект <xref:System.Xml.XPath.XPathNavigator> или объект <xref:System.Xml.XmlReader>.  
  
 Метод <xref:System.Xml.XmlWriter.WriteNode%2A> класса <xref:System.Xml.XmlWriter> имеет перегруженные варианты, которые могут принимать объекты <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader> или <xref:System.Xml.XPath.XPathNavigator>.  
  
 В следующем примере выполняется копирование всех элементов `book` из одного документа в другой.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a>Вставка значений  
 Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет методы <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> и <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, чтобы вставить значения для узла в объект <xref:System.Xml.XmlDocument>.  
  
### <a name="inserting-untyped-values"></a>Вставка нетипизированных значений  
 Метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> просто вставляет нетипизированное значение `string`, переданное в качестве параметра, как значение узла, на котором в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>. Значение вставляется без какого-либо типа и без проверки допустимости нового значения в соответствии с типом узла, если доступны сведения о схеме.  
  
 В следующем примере метод <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> используется для обновления всех элементов `price` в файле `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 В примере в качестве входных данных используется файл `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a>Вставка типизированных значений  
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
  
## <a name="the-innerxml-and-outerxml-properties"></a>Свойства InnerXml и OuterXml  
 Свойства <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> и <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> класса <xref:System.Xml.XPath.XPathNavigator> изменяют XML-разметку узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>.  
  
 Свойство <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, разобранный содержимым заданной XML-строки (`string`). Подобным образом свойство <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> изменяет XML-разметку дочерних узлов, на которых в данный момент позиционируется объект <xref:System.Xml.XPath.XPathNavigator>, так же как и самого текущего узла.  
  
 Помимо методов, описанных в этом разделе, для вставки узлов и значений в XML-документ можно использовать свойства <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> и <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>. Дополнительные сведения об использовании свойств <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> и [ для добавления узлов и значений см. в <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>руководстве по изменению данных XML с помощью XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
## <a name="namespace-and-xmllang-conflicts"></a>Конфликты пространства имен и деклараций xml:lang  
 При вставке XML-данных с помощью методов `xml:lang`, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> и <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> класса <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, принимающих в качестве параметров объекты <xref:System.Xml.XPath.XPathNavigator>, могут возникнуть определенные конфликты, связанные с областью пространства имен и деклараций <xref:System.Xml.XmlReader>.  
  
 Ниже перечислены возможные конфликты пространства имен.  
  
- Если существует пространство имен в контексте объекта <xref:System.Xml.XmlReader>, где префикс сопоставления URI-кода пространства имен не содержится в контексте объекта <xref:System.Xml.XPath.XPathNavigator>, то к вновь добавленному узлу добавляется новая декларация пространства имен.  
  
- Если один и тот же URI-код пространства имен находится как в контексте объекта <xref:System.Xml.XmlReader>, так и в контексте объекта <xref:System.Xml.XPath.XPathNavigator>, но префиксы в различных контекстах различаются, то к вновь добавленному узлу добавляется декларация нового пространства имен, а префикс и URI-код пространства имен берутся из объекта <xref:System.Xml.XmlReader>.  
  
- Если один и тот же префикс пространства имен находится как в контексте объекта <xref:System.Xml.XmlReader>, так и в контексте объекта <xref:System.Xml.XPath.XPathNavigator>, но в контекстах ему сопоставлены различные URI-коды пространств имен, то к вновь добавленному узлу добавляется декларация нового пространства имен, а префикс и URI-код пространства имен берутся из объекта <xref:System.Xml.XmlReader>.  
  
- Если и префикс, и URI-код пространства имен в обоих контекстах объекта <xref:System.Xml.XmlReader> и объекта <xref:System.Xml.XPath.XPathNavigator> одинаковы, то к вновь добавленному узлу декларация нового пространства имен не добавляется.  
  
> [!NOTE]
> Приведенное выше описание применимо также к декларациям пространства имен с пустой строкой `string` в качестве префикса (например, декларация пространства имен по умолчанию).  
  
 Ниже перечислены возможные конфликты деклараций `xml:lang`.  
  
- Если атрибут `xml:lang` существует в контексте объекта <xref:System.Xml.XmlReader>, но отсутствует в контексте объекта <xref:System.Xml.XPath.XPathNavigator>, то к вновь добавленному узлу добавляется атрибут `xml:lang`, значение которого берется из объекта<xref:System.Xml.XmlReader>.  
  
- Если атрибут `xml:lang` существует в контексте обоих объектов, <xref:System.Xml.XmlReader> и <xref:System.Xml.XPath.XPathNavigator>, но его значения там различаются, то к вновь добавленному узлу добавляется атрибут `xml:lang`, значение которого берется из объекта <xref:System.Xml.XmlReader>.  
  
- Если атрибут `xml:lang` существует в контексте обоих объектов, <xref:System.Xml.XmlReader> и <xref:System.Xml.XPath.XPathNavigator>, с одинаковыми значениями, то к вновь добавленному узлу новый атрибут `xml:lang` не добавляется.  
  
- Если атрибут `xml:lang` существует в контексте объекта <xref:System.Xml.XPath.XPathNavigator>, но не существует в контексте объекта <xref:System.Xml.XmlReader>, то к вновь добавленному узлу вообще не добавляется атрибут `xml:lang`.  
  
## <a name="inserting-nodes-with-xmlwriter"></a>Вставка узлов с помощью класса XmlWriter  
 Методы, используемые для вставки одноуровневых узлов, дочерних узлов и узлов атрибутов, которые описаны в разделе «Вставка узлов и атрибутов», перегружены. Методы <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> и <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> класса <xref:System.Xml.XPath.XPathNavigator> возвращают объект <xref:System.Xml.XmlWriter>, используемый для вставки узлов.  
  
### <a name="unsupported-xmlwriter-methods"></a>Неподдерживаемые методы класса XmlWriter  
 Не все методы, используемые для записи данных в XML-документ с помощью класса <xref:System.Xml.XmlWriter>, поддерживаются классом <xref:System.Xml.XPath.XPathNavigator>, что связано с различиями между моделями данных XPath и DOM.  
  
 В следующей таблице описаны методы класса <xref:System.Xml.XmlWriter>, которые не поддерживаются в классе <xref:System.Xml.XPath.XPathNavigator>.  
  
|Метод|Описание|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|Формирует исключение <xref:System.NotSupportedException>.|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|Не обрабатывается на корневом уровне и формирует исключение <xref:System.NotSupportedException> при вызове на любом другом уровне XML-документа.|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|Интерпретируется как вызов метода <xref:System.Xml.XmlWriter.WriteString%2A> для эквивалентного символа или символов.|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|Интерпретируется как вызов метода <xref:System.Xml.XmlWriter.WriteString%2A> для эквивалентного символа или символов.|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|Интерпретируется как вызов метода <xref:System.Xml.XmlWriter.WriteString%2A> для эквивалентного символа или символов.|  
  
 Дополнительные сведения о классе <xref:System.Xml.XmlWriter> см. в справочной документации по классу <xref:System.Xml.XmlWriter>.  
  
### <a name="multiple-xmlwriter-objects"></a>Несколько объектов XmlWriter  
 Можно иметь несколько объектов <xref:System.Xml.XPath.XPathNavigator>, указывающих на различные части XML-документа с одним или более открытыми объектами <xref:System.Xml.XmlWriter>. Использование нескольких объектов <xref:System.Xml.XmlWriter> разрешено и поддерживается в однопоточных сценариях.  
  
 При использовании нескольких объектов <xref:System.Xml.XmlWriter> важно учесть следующие замечания.  
  
- XML-фрагменты, созданные с помощью объекта <xref:System.Xml.XmlWriter>, добавляются в XML-документ при вызове метода <xref:System.Xml.XmlWriter.Close%2A> для каждого объекта <xref:System.Xml.XmlWriter>. До этого момента объект <xref:System.Xml.XmlWriter> записывает данные в отсоединенный фрагмент. Если операция выполняется на открытом XML-документе, то все фрагменты, записываемые объектом <xref:System.Xml.XmlWriter>, не затрагиваются до вызова метода <xref:System.Xml.XmlWriter.Close%2A>.  
  
- Если на определенном поддереве XML существует открытый объект <xref:System.Xml.XmlWriter>, и поддерево удаляется, то объект <xref:System.Xml.XmlWriter> все равно может добавляться к поддереву. Просто это поддерево становится удаленным фрагментом.  
  
- Если в одном XML-документе одновременно открыто несколько объектов <xref:System.Xml.XmlWriter>, то они добавляются в XML-документ в порядке закрытия объектов <xref:System.Xml.XmlWriter>, а не в порядке их открытия.  
  
 В следующем примере создается объект <xref:System.Xml.XmlDocument>, создается объект <xref:System.Xml.XPath.XPathNavigator>, а потом используется объект <xref:System.Xml.XmlWriter>, возвращаемый методом <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, чтобы создать структуру первой книги в файле `books.xml`. Затем файл `book.xml` сохраняется.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a>Сохранение XML-документа  
 Сохранение изменений, внесенных в объект <xref:System.Xml.XmlDocument> в результате выполнения описанных в данном разделе методов, выполняется с помощью методов класса <xref:System.Xml.XmlDocument>. Дополнительные сведения о сохранении изменений, внесенных в объект <xref:System.Xml.XmlDocument>, см. в руководстве по [созданию и сохранению документов](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Обработка XML-данных с использованием модели данных XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Изменение XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
- [Удаление XML-данных с помощью XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
