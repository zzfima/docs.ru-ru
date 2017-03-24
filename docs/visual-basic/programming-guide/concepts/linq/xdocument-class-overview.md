---
title: "Общие сведения о классах XDocument (Visual Basic) | Документы Microsoft"
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
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31111b23adb019aad3ad55787c073dc02446291d
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-visual-basic"></a>Общие сведения о классах XDocument (Visual Basic)
В этом разделе описываются <xref:System.Xml.Linq.XDocument>класса.</xref:System.Xml.Linq.XDocument>  
  
## <a name="overview-of-the-xdocument-class"></a>Общие сведения о классе XDocument  
 <xref:System.Xml.Linq.XDocument>Класс содержит сведения, необходимые для допустимого XML-документа.</xref:System.Xml.Linq.XDocument> К ним относятся XML-декларация, инструкции по обработке и комментарии.  
  
 Обратите внимание, что только для создания <xref:System.Xml.Linq.XDocument>объектов, если требуются определенные функциональные возможности, предоставляемые <xref:System.Xml.Linq.XDocument>класса.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument> Во многих случаях может работать непосредственно с <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> Работа непосредственно с <xref:System.Xml.Linq.XElement>реализует простую модель программирования.</xref:System.Xml.Linq.XElement>  
  
 <xref:System.Xml.Linq.XDocument>является производным от <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XDocument> Поэтому он может содержать дочерние узлы. Тем не менее <xref:System.Xml.Linq.XDocument>объекты могут иметь только один дочерний <xref:System.Xml.Linq.XElement>узла.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.  
  
## <a name="components-of-xdocument"></a>Компоненты XDocument  
 <xref:System.Xml.Linq.XDocument>Может содержать следующие элементы:</xref:System.Xml.Linq.XDocument>  
  
-   Один <xref:System.Xml.Linq.XDeclaration>объекта.</xref:System.Xml.Linq.XDeclaration> <xref:System.Xml.Linq.XDeclaration>позволяет указать соответствующие части XML-декларации: версию XML, кодировку документа, а ли XML-документ изолированным.</xref:System.Xml.Linq.XDeclaration>  
  
-   Один <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> Это корневой узел XML-документа.  
  
-   Любое количество <xref:System.Xml.Linq.XProcessingInstruction>объектов.</xref:System.Xml.Linq.XProcessingInstruction> Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.  
  
-   Любое количество <xref:System.Xml.Linq.XComment>объектов.</xref:System.Xml.Linq.XComment> Комментарии и корневой элемент находятся на одном уровне. <xref:System.Xml.Linq.XComment>Объект не может быть первый аргумент в списке, так как оно является недопустимым для документа XML, начинаться с комментария.</xref:System.Xml.Linq.XComment>  
  
-   Один <xref:System.Xml.Linq.XDocumentType>для DTD.</xref:System.Xml.Linq.XDocumentType>  
  
 При сериализации <xref:System.Xml.Linq.XDocument>, даже если `XDocument.Declaration` — `null`, выходные данные будут иметь XML-декларацию, если модуль записи имеет `Writer.Settings.OmitXmlDeclaration` значение `false` (по умолчанию).</xref:System.Xml.Linq.XDocument>  
  
 По умолчанию [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».  
  
## <a name="using-xelement-without-xdocument"></a>Использование XElement без XDocument  
 Как упоминалось ранее, <xref:System.Xml.Linq.XElement>– это основной класс в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] интерфейс программирования.</xref:System.Xml.Linq.XElement> Во многих случаях приложение не требует создания документа. С помощью <xref:System.Xml.Linq.XElement>класс, создание XML-дерева, добавьте к нему другие XML-деревья, изменять XML-дерево и сохранить его</xref:System.Xml.Linq.XElement>  
  
## <a name="using-xdocument"></a>Использование XDocument  
 Для создания <xref:System.Xml.Linq.XDocument>, используется функциональное построение, так же, как и для создания <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 Следующий код создает <xref:System.Xml.Linq.XDocument>и связанный с ним вложенные объекты.</xref:System.Xml.Linq.XDocument>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
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
  
## <a name="see-also"></a>См. также  
 [LINQ to XML обзор программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
