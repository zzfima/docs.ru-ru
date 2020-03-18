---
title: LINQ to XML или модель DOM (C#)
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: 92d0da494829d57517d52fe93a3cbcf1398fdbe4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168393"
---
# <a name="linq-to-xml-vs-dom-c"></a>LINQ to XML или модель DOM (C#)
В этом разделе описываются некоторые основные различия между [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] и текущим преобладающим программным интерфейсом API XML, а именно моделью DOM консорциума W3C.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Новые способы построения XML-деревьев  
 В W3C DOM XML-дерево строится снизу вверх, т. е. создается документ, создаются элементы, а затем элементы добавляются в документ.  
  
 В качестве примера ниже показан типичный способ создания XML-дерева при помощи реализации DOM от Майкрософт, <xref:System.Xml.XmlDocument>:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 Такой стиль программирования не дает визуального представления о деталях структуры XML-дерева. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддерживает такой подход к построению XML-дерева, но также предлагает и альтернативный способ, *функциональное построение*. При функциональном построении для создания XML-дерева используются конструкторы <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute>.  
  
 Вот как можно построить такое же XML-дерево с помощью функционального построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Обратите внимание, что отступы в коде, который строит XML-дерево, показывают структуру базового документа XML.  
  
 Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](./linq-to-xml-overview.md).  
  
## <a name="working-directly-with-xml-elements"></a>Работа непосредственно с XML-элементами  
 При программировании на XML основное внимание обычно уделяется XML-элементам и, возможно, атрибутам. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно работать с XML-элементами и атрибутами напрямую. Например, можно выполнять следующие действия.  
  
- Создавать XML-элементы, совсем не используя объект документа. Это упрощает программирование, когда необходимо работать с фрагментами XML-деревьев.  
  
- Загружать объекты `T:System.Xml.Linq.XElement` непосредственно из XML-файла.  
  
- Сериализовать объекты `T:System.Xml.Linq.XElement` в файл или поток.  
  
 Сравним это с W3C DOM, где XML-документ используется как логический контейнер для XML-дерева. В DOM XML-узлы, в том числе элементы и атрибуты, должны создаваться в контексте XML-документа. Вот фрагмент кода, предназначенного для создания элемента имени в DOM:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 Если элемент требуется использовать в нескольких документах, нужно будет импортировать в эти документы узлы. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет избавиться от этих сложностей.  
  
 При использовании LINQ to XML класс <xref:System.Xml.Linq.XDocument> применяется только, если требуется добавить комментарий или инструкцию по обработке на корневом уровне документа.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Упрощенная обработка имен и пространств имен  
 В общем случае обработка имен, пространств имен и префиксов пространств имен является сложной частью в программировании на XML. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] упрощает работу с ними, исключая необходимость использования полных префиксов пространств имен. Их можно использовать, если требуется управлять префиксами пространств имен. Однако, если принято решение явно не управлять префиксами пространств имен, то при сериализации [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] назначит префиксы пространств имен, если они необходимы, или, в противном случае, произведет сериализацию при помощи пространств имен по умолчанию. Если используются пространства имен по умолчанию, то в итоговом документе префиксов пространств имен не будет. Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 Еще одним недостатком DOM является то, что отсутствует возможность изменять имена узлов. Вместо этого необходимо создать новый узел и скопировать в него все дочерние узлы, но при этом идентификатор первоначального узла будет потерян. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] эта проблема решена за счет возможности установки свойства <xref:System.Xml.Linq.XName> узла.  
  
## <a name="static-method-support-for-loading-xml"></a>Поддержка статических методов для загрузки XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет загружать XML при помощи статических методов, а не методов экземпляра. Это упрощает загрузку и синтаксический анализ. Дополнительные сведения см. в руководстве по [загрузке XML из файла (C#)](./how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Удаление поддержки конструкций DTD  
 За счет удаления поддержки сущностей и ссылок на сущности [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] еще более упрощает программирование на XML. Управление сущностями является весьма сложным процессом и поэтому редко используется. Удаление поддержки сущностей позволяет повысить производительность и упростить интерфейс программирования. При заполнении дерева [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] все сущности DTD раскрываются.  
  
## <a name="support-for-fragments"></a>Поддержка фрагментов  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] не предоставляет эквивалент класса `XmlDocumentFragment`. Однако во многих случаях понятие `XmlDocumentFragment` можно обрабатывать с помощью результата запроса, который типизируется как объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XNode> или объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XElement>.  
  
## <a name="support-for-xpathnavigator"></a>Поддержка XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обеспечивает поддержку <xref:System.Xml.XPath.XPathNavigator> через методы расширения в пространстве имен <xref:System.Xml.XPath?displayProperty=nameWithType>. Для получения дополнительной информации см. <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Поддержка пробелов и отступов  
 Обработка пробелов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] проще, чем в DOM.  
  
 Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами. При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева. Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.  
  
 Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами. Эти отступы ни в коем случае изменять нельзя. В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] этого можно достигнуть, если сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] хранит пробелы как узлы <xref:System.Xml.Linq.XText>, а не имеет сериализованный тип узла <xref:System.Xml.XmlNodeType.Whitespace>, который есть в DOM.  
  
## <a name="support-for-annotations"></a>Поддержка заметок  
 Элементы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддерживают расширяемый набор заметок. Это полезно для отслеживания различной информации об элементе, например сведений о схеме, сведений о привязке элемента к пользовательскому интерфейсу, а также любых других сведений, относящихся к конкретному приложению. Дополнительные сведения см. в разделе [Заметки LINQ to XML](./linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Поддержка сведений схемы  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обеспечивает поддержку проверки правильности по схеме XSD через методы расширения в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>. Можно проверить XML-дерево на соответствие схеме XSD. XML-дерево можно заполнить при помощи модуля проверки после обработки схемы (PSVI). Дополнительные сведения см. в руководстве по [проверке XSD с использованием XSD](./how-to-validate-using-xsd-linq-to-xml.md) и <xref:System.Xml.Schema.Extensions>.
  
## <a name="see-also"></a>См. также

- [Начало работы (LINQ to XML)](./linq-to-xml-overview.md)
