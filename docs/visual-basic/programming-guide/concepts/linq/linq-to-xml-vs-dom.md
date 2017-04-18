---
title: "LINQ to XML или Модель DOM (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 18c36130-d598-40b7-9007-828232252978
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 88b6bddcdeec2859844f5d5f94777146d488b5fb
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-vs-dom-visual-basic"></a>LINQ to XML или Модель DOM (Visual Basic)
В этом разделе описываются некоторые основные различия между [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] и текущий XML преобладающим программным интерфейсом API, модель объектов документов (DOM) W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Новые способы построения XML-деревьев  
 В W3C DOM XML-дерево строится снизу вверх, т. е. создается документ, создаются элементы, а затем элементы добавляются в документ.  
  
 Например следующий синтаксис будет типичный способ создания XML-дерева с помощью Microsoft реализации DOM, <xref:System.Xml.XmlDocument>:</xref:System.Xml.XmlDocument>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 Такой стиль программирования не дает визуального представления о деталях структуры XML-дерева. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]поддерживает такой подход к построению XML-дерева, но также предлагает и альтернативный способ, *функциональное построение*. В Visual Basic функциональное построение использует XML-литералы для построения XML-дерева.  
  
 Вот как можно построить же XML-дерево с помощью [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] функциональное построение:  
  
```vb  
Dim contacts = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="Home">206-555-0144</Phone>  
            <Phone Type="Work">425-555-0145</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Обратите внимание, что отступы в коде, который строит XML-дерево, показывают структуру базового документа XML.  
  
 Дополнительные сведения см. в разделе [Создание XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="working-directly-with-xml-elements"></a>Работа непосредственно с XML-элементами  
 При программировании на XML основное внимание обычно уделяется XML-элементам и, возможно, атрибутам. В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно работать с XML-элементами и атрибутами напрямую. Например, можно выполнять следующие действия.  
  
-   Создавать XML-элементы, совсем не используя объект документа. Это упрощает программирование, когда необходимо работать с фрагментами XML-деревьев.  
  
-   Загружать объекты `T:System.Xml.Linq.XElement` непосредственно из XML-файла.  
  
-   Сериализовать объекты `T:System.Xml.Linq.XElement` в файл или поток.  
  
 Сравним это с W3C DOM, где XML-документ используется как логический контейнер для XML-дерева. В DOM XML-узлы, в том числе элементы и атрибуты, должны создаваться в контексте XML-документа. Вот фрагмент кода, предназначенного для создания элемента имени в DOM:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 Если элемент требуется использовать в нескольких документах, нужно будет импортировать в эти документы узлы. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]позволяет избежать этих сложностей.  
  
 При использовании LINQ to XML, <xref:System.Xml.Linq.XDocument>только в том случае, если требуется добавить комментарий или инструкцию по обработке на корневом уровне документа.</xref:System.Xml.Linq.XDocument>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Упрощенная обработка имен и пространств имен  
 В общем случае обработка имен, пространств имен и префиксов пространств имен является сложной частью в программировании на XML. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]упрощает имена и пространства имен путем устранения требования использовать полные префиксы пространств имен. Их можно использовать, если требуется управлять префиксами пространств имен. Но если принято решение явно не управлять префиксами пространств имен, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] назначит префиксы пространств имен при сериализации, если они необходимы, или произведет сериализацию при помощи пространств имен по умолчанию, если они не являются. Если используются пространства имен по умолчанию, то в итоговом документе префиксов пространств имен не будет. Дополнительные сведения см. в разделе [работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Еще одним недостатком DOM является то, что отсутствует возможность изменять имена узлов. Вместо этого необходимо создать новый узел и скопировать в него все дочерние узлы, но при этом идентификатор первоначального узла будет потерян. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Эта проблема решена за счет возможности установки <xref:System.Xml.Linq.XName>свойство на узле.</xref:System.Xml.Linq.XName>  
  
## <a name="static-method-support-for-loading-xml"></a>Поддержка статических методов для загрузки XML  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]позволяет загружать XML при помощи статических методов, а не методов экземпляра. Это упрощает загрузку и синтаксический анализ. Дополнительные сведения см. в разделе [Практическое руководство: загрузка XML из файла (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Удаление поддержки конструкций DTD  
 За счет удаления поддержки сущностей и ссылок на сущности [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] еще более упрощает программирование на XML. Управление сущностями является весьма сложным процессом и поэтому редко используется. Удаление поддержки сущностей позволяет повысить производительность и упростить интерфейс программирования. Когда [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] дерево заполняется, все сущности DTD раскрываются.  
  
## <a name="support-for-fragments"></a>Поддержка фрагментов  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]не предоставляет эквивалент `XmlDocumentFragment` класса. Во многих случаях, однако `XmlDocumentFragment` концепции может обрабатываться с помощью результата запроса, который типизируется как <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XNode>, или <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XNode> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="support-for-xpathnavigator"></a>Поддержка XPathNavigator  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]обеспечивает поддержку для <xref:System.Xml.XPath.XPathNavigator>через методы расширения в <xref:System.Xml.XPath?displayProperty=fullName>имен.</xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.XPath.XPathNavigator> Дополнительные сведения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName>  
  
## <a name="support-for-white-space-and-indentation"></a>Поддержка пробелов и отступов  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]обрабатывает пробелы просто более чем в DOM.  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] этого можно достигнуть, если сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]хранит пробелы как <xref:System.Xml.Linq.XText>узел, а не имеет сериализованный <xref:System.Xml.XmlNodeType>Тип узла в модели DOM выполняет.</xref:System.Xml.XmlNodeType> </xref:System.Xml.Linq.XText>  
  
## <a name="support-for-annotations"></a>Поддержка заметок  
 Элементы [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] поддерживают расширяемый набор заметок. Это полезно для отслеживания различной информации об элементе, например сведений о схеме, сведений о привязке элемента к пользовательскому интерфейсу, а также любых других сведений, относящихся к конкретному приложению. Дополнительные сведения см. в разделе [примечания LINQ to XML](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).  
  
## <a name="support-for-schema-information"></a>Поддержка сведений схемы  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]обеспечивает поддержку проверки XSD через методы расширения в <xref:System.Xml.Schema?displayProperty=fullName>имен.</xref:System.Xml.Schema?displayProperty=fullName> Можно проверить XML-дерево на соответствие схеме XSD. XML-дерево можно заполнить при помощи модуля проверки после обработки схемы (PSVI). Дополнительные сведения см. в разделе [Практическое руководство: проверка XSD с помощью](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) и <xref:System.Xml.Schema.Extensions>.</xref:System.Xml.Schema.Extensions>  
  
## <a name="see-also"></a>См. также  
 [Начало работы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
