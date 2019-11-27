---
title: LINQ to XML и DOM
ms.date: 07/20/2015
ms.assetid: 18c36130-d598-40b7-9007-828232252978
ms.openlocfilehash: b25993fba4d878beb881dfdc46effe5a8ab3485b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331706"
---
# <a name="linq-to-xml-vs-dom-visual-basic"></a>LINQ to XML и DOM (Visual Basic)
В этом разделе описываются некоторые основные различия между [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] и текущим преобладающим программным интерфейсом API XML, а именно моделью DOM консорциума W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Новые способы построения XML-деревьев  
 В W3C DOM XML-дерево строится снизу вверх, т. е. создается документ, создаются элементы, а затем элементы добавляются в документ.  
  
 В качестве примера ниже показан типичный способ создания XML-дерева при помощи реализации DOM от Майкрософт, <xref:System.Xml.XmlDocument>:  
  
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
  
 Такой стиль программирования не дает визуального представления о деталях структуры XML-дерева. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддерживает такой подход к построению XML-дерева, но также предлагает и альтернативный способ, *функциональное построение*. В Visual Basic функциональное построение использует XML-литералы для построения XML-дерева.  
  
 Вот как можно построить такое же XML-дерево с помощью функционального построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
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
  
 Дополнительные сведения см. в разделе [Создание деревьев XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="working-directly-with-xml-elements"></a>Работа непосредственно с XML-элементами  
 При программировании на XML основное внимание обычно уделяется XML-элементам и, возможно, атрибутам. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно работать с XML-элементами и атрибутами напрямую. Например, можно выполнять следующие действия.  
  
- Создавать XML-элементы, совсем не используя объект документа. Это упрощает программирование, когда необходимо работать с фрагментами XML-деревьев.  
  
- Загружать объекты `T:System.Xml.Linq.XElement` непосредственно из XML-файла.  
  
- Сериализовать объекты `T:System.Xml.Linq.XElement` в файл или поток.  
  
 Сравним это с W3C DOM, где XML-документ используется как логический контейнер для XML-дерева. В DOM XML-узлы, в том числе элементы и атрибуты, должны создаваться в контексте XML-документа. Вот фрагмент кода, предназначенного для создания элемента имени в DOM:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 Если элемент требуется использовать в нескольких документах, нужно будет импортировать в эти документы узлы. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет избавиться от этих сложностей.  
  
 При использовании LINQ to XML класс <xref:System.Xml.Linq.XDocument> применяется только, если требуется добавить комментарий или инструкцию по обработке на корневом уровне документа.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Упрощенная обработка имен и пространств имен  
 В общем случае обработка имен, пространств имен и префиксов пространств имен является сложной частью в программировании на XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] упрощает работу с ними, исключая необходимость использования полных префиксов пространств имен. Их можно использовать, если требуется управлять префиксами пространств имен. Однако, если принято решение явно не управлять префиксами пространств имен, то при сериализации [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] назначит префиксы пространств имен, если они необходимы, или, в противном случае, произведет сериализацию при помощи пространств имен по умолчанию. Если используются пространства имен по умолчанию, то в итоговом документе префиксов пространств имен не будет. Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 Еще одним недостатком DOM является то, что отсутствует возможность изменять имена узлов. Вместо этого необходимо создать новый узел и скопировать в него все дочерние узлы, но при этом идентификатор первоначального узла будет потерян. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] эта проблема решена за счет возможности установки свойства <xref:System.Xml.Linq.XName> узла.  
  
## <a name="static-method-support-for-loading-xml"></a>Поддержка статических методов для загрузки XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет загружать XML при помощи статических методов, а не методов экземпляра. Это упрощает загрузку и синтаксический анализ. Дополнительные сведения см. [в разделе инструкции. Загрузка XML из файла (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Удаление поддержки конструкций DTD  
 За счет удаления поддержки сущностей и ссылок на сущности [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] еще более упрощает программирование на XML. Управление сущностями является весьма сложным процессом и поэтому редко используется. Удаление поддержки сущностей позволяет повысить производительность и упростить интерфейс программирования. При заполнении дерева [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] все сущности DTD раскрываются.  
  
## <a name="support-for-fragments"></a>Поддержка фрагментов  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] не предоставляет эквивалент класса `XmlDocumentFragment`. Однако во многих случаях понятие `XmlDocumentFragment` можно обрабатывать с помощью результата запроса, который типизируется как объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XNode> или объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XElement>.  
  
## <a name="support-for-xpathnavigator"></a>Поддержка XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обеспечивает поддержку <xref:System.Xml.XPath.XPathNavigator> через методы расширения в пространстве имен <xref:System.Xml.XPath?displayProperty=nameWithType>. Дополнительные сведения см. в разделе <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Поддержка пробелов и отступов  
 Обработка пробелов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] проще, чем в DOM.  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] этого можно достигнуть, если сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] хранит пробелы как узлы <xref:System.Xml.Linq.XText>, а не имеет сериализованный тип узла <xref:System.Xml.XmlNodeType.Whitespace>, который есть в DOM.  
  
## <a name="support-for-annotations"></a>Поддержка заметок  
 Элементы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддерживают расширяемый набор заметок. Это полезно для отслеживания различной информации об элементе, например сведений о схеме, сведений о привязке элемента к пользовательскому интерфейсу, а также любых других сведений, относящихся к конкретному приложению. Дополнительные сведения см. в разделе [Заметки LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Поддержка сведений схемы  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обеспечивает поддержку проверки правильности по схеме XSD через методы расширения в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>. Можно проверить XML-дерево на соответствие схеме XSD. XML-дерево можно заполнить при помощи модуля проверки после обработки схемы (PSVI). Дополнительные сведения см. в разделах [Практическое руководство. Проверка XSD с использованием XSD](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) и <xref:System.Xml.Schema.Extensions>.  
  
## <a name="see-also"></a>См. также

- [Начало работы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
