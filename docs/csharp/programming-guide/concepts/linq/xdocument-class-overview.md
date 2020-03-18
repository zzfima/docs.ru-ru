---
title: Общие сведения о классе XDocument (C#)
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: de49dc071d22dd77dddea29ca114663261e3edda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69590846"
---
# <a name="xdocument-class-overview-c"></a>Общие сведения о классе XDocument (C#)
В этом разделе представлен класс <xref:System.Xml.Linq.XDocument>.  
  
## <a name="overview-of-the-xdocument-class"></a>Общие сведения о классе XDocument  
 Класс <xref:System.Xml.Linq.XDocument> содержит сведения, необходимые для допустимого XML-документа. К ним относятся XML-декларация, инструкции по обработке и комментарии.  
  
 Отметим, что, если требуются только конкретные функции, обеспечиваемые классом <xref:System.Xml.Linq.XDocument>, необходимо создавать только объекты <xref:System.Xml.Linq.XDocument>. Во многих случаях пользователь может работать непосредственно с <xref:System.Xml.Linq.XElement>. Непосредственная работа с <xref:System.Xml.Linq.XElement> реализует более простую модель программирования.  
  
 <xref:System.Xml.Linq.XDocument> является производным от <xref:System.Xml.Linq.XContainer>. Поэтому он может содержать дочерние узлы. Однако объекты <xref:System.Xml.Linq.XDocument> могут иметь только по одному дочернему узлу <xref:System.Xml.Linq.XElement>. Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.  
  
## <a name="components-of-xdocument"></a>Компоненты XDocument  
 Документ <xref:System.Xml.Linq.XDocument> может включать в себя следующие элементы:  
  
- Один объект <xref:System.Xml.Linq.XDeclaration>. <xref:System.Xml.Linq.XDeclaration> позволяет указать соответствующие части XML-объявления: версию XML, кодировку документа, а также то, является ли этот XML-документ изолированным.  
  
- Один объект <xref:System.Xml.Linq.XElement>. Это корневой узел XML-документа.  
  
- Любое количество объектов <xref:System.Xml.Linq.XProcessingInstruction>. Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.  
  
- Любое количество объектов <xref:System.Xml.Linq.XComment>. Комментарии и корневой элемент находятся на одном уровне. Объект <xref:System.Xml.Linq.XComment> не может быть первым аргументом в списке, так как XML-документ не может начинаться с комментария.  
  
- Один тип документа <xref:System.Xml.Linq.XDocumentType> для DTD.  
  
 При сериализации документа <xref:System.Xml.Linq.XDocument>, даже если значением декларации `XDocument.Declaration` является `null`, выходные данные будут иметь XML-декларацию, если для свойства `Writer.Settings.OmitXmlDeclaration` автор указал значение `false` (применяется по умолчанию).  
  
 По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».  
  
## <a name="using-xelement-without-xdocument"></a>Использование XElement без XDocument  
 Как уже отмечалось, класс <xref:System.Xml.Linq.XElement> является основным классом интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Во многих случаях приложение не требует создания документа. Класс <xref:System.Xml.Linq.XElement> позволяет создавать XML-дерево, добавлять к нему другие XML-деревья, изменять XML-дерево и сохранять его.  
  
## <a name="using-xdocument"></a>Использование XDocument  
 При создании объектов <xref:System.Xml.Linq.XDocument> используется функциональное построение, так же как и при создании объектов <xref:System.Xml.Linq.XElement>.  
  
 Следующий фрагмент кода создает объект <xref:System.Xml.Linq.XDocument> и ассоциированные с ним вложенные объекты.  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 В результате анализа файла test.xml получается следующий выход:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о программировании LINQ to XML (C#)](./linq-to-xml-overview.md)
