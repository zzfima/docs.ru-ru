---
title: "Классы LINQ to XML Обзор (Visual Basic) | Документы Microsoft"
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
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
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
ms.openlocfilehash: 12885f93bb7e56dd66d36090d41700195313e944
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>LINQ to XML обзор классов (Visual Basic)
Этот раздел содержит список [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] классы в <xref:System.Xml.Linq>пространства имен и краткое описание каждого из них.</xref:System.Xml.Linq>  
  
## <a name="linq-to-xml-classes"></a>Классы LINQ to XML  
  
### <a name="xattribute-class"></a>Класс XAttribute  
 <xref:System.Xml.Linq.XAttribute>Представляет атрибут XML.</xref:System.Xml.Linq.XAttribute> Подробные сведения и примеры см. в разделе [Общие сведения о классе XAttribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Класс XCData  
 <xref:System.Xml.Linq.XCData>Представляет узел текста CDATA.</xref:System.Xml.Linq.XCData>  
  
### <a name="xcomment-class"></a>Класс XComment  
 <xref:System.Xml.Linq.XComment>Представляет XML-комментарий.</xref:System.Xml.Linq.XComment>  
  
### <a name="xcontainer-class"></a>Класс XContainer  
 <xref:System.Xml.Linq.XContainer>Представляет абстрактный базовый класс для всех узлов, которые могут иметь дочерние узлы.</xref:System.Xml.Linq.XContainer> Следующие классы являются производными от <xref:System.Xml.Linq.XContainer>класса:</xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Класс XDeclaration  
 <xref:System.Xml.Linq.XDeclaration>Представляет объявление XML.</xref:System.Xml.Linq.XDeclaration> XML-декларация используется для объявления версии XML и кодировки документа. Кроме того, в XML-декларации указывается, является ли данный XML-документ изолированным. Если документ является изолированным, то внешние декларации разметки не используются ни во внешних DTD, ни во внешних сущностях параметров, ссылки на которые имеются во встроенном DTD.  
  
### <a name="xdocument-class"></a>Класс XDocument  
 <xref:System.Xml.Linq.XDocument>Представляет XML-документ.</xref:System.Xml.Linq.XDocument> Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Класс XDocumentType  
 <xref:System.Xml.Linq.XDocumentType>Представляет определение типа XML документа (DTD).</xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xelement-class"></a>Класс XElement  
 <xref:System.Xml.Linq.XElement>Представляет элемент XML.</xref:System.Xml.Linq.XElement> Подробные сведения и примеры см. в разделе [Общие сведения о классе XElement (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>Класс XName  
 <xref:System.Xml.Linq.XName>Представляет имена элементов (<xref:System.Xml.Linq.XElement>) и атрибутов (<xref:System.Xml.Linq.XAttribute>).</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XName> Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] позволяет сделать XML-имена как можно более понятными. В силу их сложности XML-имена часто считаются затруднительной темой для изучения в XML. Возможно, эта сложность возникает не из-за пространств имен, которые разработчики часто используют при программировании, а из-за префиксов пространств имен. Префиксы пространств имен могут быть полезны для сокращения количества нажатий клавиш при вводе XML или для повышения удобства чтения XML. Но часто префиксы являются просто ярлыком, свидетельствующим об использовании полного пространства имен XML, в большинстве случаев они не нужны. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]упрощает XML-имена путем разрешения всех префиксов в соответствующее им пространство имен XML. Префиксы доступны, если они требуются, через <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>метод.</xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>  
  
 При необходимости можно управлять префиксами пространства имен. В некоторых ситуациях при работе с другими XML-системами, например XSLT или XAML, необходимо управлять префиксами пространства имен. Например, при наличии выражения XPath, в котором используются префиксы пространства имен и которое внедрено в таблицу стилей XSLT, необходимо сериализовать XML-документ с префиксами пространства имен, которые соответствуют используемым в выражении XPath.  
  
### <a name="xnamespace-class"></a>Класс XNamespace  
 <xref:System.Xml.Linq.XNamespace>представляет пространство имен <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XNamespace> Пространства имен являются компонентом <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName>  
  
### <a name="xnode-class"></a>Класс XNode  
 <xref:System.Xml.Linq.XNode>Представляет абстрактный класс, который представляет узлы XML-дерева.</xref:System.Xml.Linq.XNode> Следующие классы являются производными от <xref:System.Xml.Linq.XNode>класса:</xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XText></xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType></xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>Класс XNodeDocumentOrderComparer  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer>предоставляет возможность сравнивать узлы по их порядку в документе.</xref:System.Xml.Linq.XNodeDocumentOrderComparer>  
  
### <a name="xnodeequalitycomparer-class"></a>Класс XNodeEqualityComparer  
 <xref:System.Xml.Linq.XNodeEqualityComparer>предоставляет возможность сравнивать узлы по равенству значений.</xref:System.Xml.Linq.XNodeEqualityComparer>  
  
### <a name="xobject-class"></a>Класс XObject  
 <xref:System.Xml.Linq.XObject>Представляет абстрактный базовый класс и <xref:System.Xml.Linq.XNode> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XObject> Он предоставляет функции обработки заметок и событий.  
  
### <a name="xobjectchange-class"></a>Класс XObjectChange  
 <xref:System.Xml.Linq.XObjectChange>Указывает тип события, когда происходит событие <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObjectChange>  
  
### <a name="xobjectchangeeventargs-class"></a>Класс XObjectChangeEventArgs  
 <xref:System.Xml.Linq.XObjectChangeEventArgs>Предоставляет данные для <xref:System.Xml.Linq.XObject.Changing>и <xref:System.Xml.Linq.XObject.Changed>события.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObjectChangeEventArgs>  
  
### <a name="xprocessinginstruction-class"></a>Класс XProcessingInstruction  
 <xref:System.Xml.Linq.XProcessingInstruction>Представляет инструкцию обработки XML.</xref:System.Xml.Linq.XProcessingInstruction> Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.  
  
### <a name="xtext-class"></a>Класс XText  
 <xref:System.Xml.Linq.XText>Представляет текстовый узел.</xref:System.Xml.Linq.XText> В большинстве случаев использование этого класса не требуется. Этот класс главным образом используется для смешанного содержимого.  
  
## <a name="see-also"></a>См. также  
 [LINQ to XML обзор программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
