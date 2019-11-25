---
title: Общие сведения о классах LINQ to XML
ms.date: 07/20/2015
ms.assetid: f11b62b5-d522-4c23-92ae-23186dc16447
ms.openlocfilehash: 8b7c1e13d462bbee38f4e958bb3ef90a8c7d32f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352013"
---
# <a name="linq-to-xml-classes-overview-visual-basic"></a>LINQ to XML Classes Overview (Visual Basic)
В этом разделе приведен список классов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в пространстве имен <xref:System.Xml.Linq> с кратким описанием каждого из них.  
  
## <a name="linq-to-xml-classes"></a>Классы LINQ to XML  
  
### <a name="xattribute-class"></a>Класс XAttribute  
 Класс <xref:System.Xml.Linq.XAttribute> представляет XML-атрибут. For detailed information and examples, see [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Класс XCData  
 Класс <xref:System.Xml.Linq.XCData> представляет узел текста CDATA.  
  
### <a name="xcomment-class"></a>Класс XComment  
 Класс <xref:System.Xml.Linq.XComment> представляет XML-комментарий.  
  
### <a name="xcontainer-class"></a>Класс XContainer  
 Класс <xref:System.Xml.Linq.XContainer> является абстрактным базовым классом для всех узлов, которые могут иметь дочерние узлы. Следующие классы происходят от класса <xref:System.Xml.Linq.XContainer>:  
  
- <xref:System.Xml.Linq.XElement>  
  
- <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Класс XDeclaration  
 Класс <xref:System.Xml.Linq.XDeclaration> представляет XML-декларацию. XML-декларация используется для объявления версии XML и кодировки документа. Кроме того, в XML-декларации указывается, является ли данный XML-документ изолированным. Если документ является изолированным, то внешние декларации разметки не используются ни во внешних DTD, ни во внешних сущностях параметров, ссылки на которые имеются во встроенном DTD.  
  
### <a name="xdocument-class"></a>Класс XDocument  
 Класс <xref:System.Xml.Linq.XDocument> представляет XML-документ. For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Класс XDocumentType  
 Класс <xref:System.Xml.Linq.XDocumentType> представляет определения типа XML-документа (DTD).  
  
### <a name="xelement-class"></a>Класс XElement  
 Класс <xref:System.Xml.Linq.XElement> представляет XML-элемент. For detailed information and examples, see [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>Класс XName  
 Класс <xref:System.Xml.Linq.XName> представляет имена элементов (<xref:System.Xml.Linq.XElement>) и атрибутов (<xref:System.Xml.Linq.XAttribute>). For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет сделать XML-имена как можно более понятными. В силу их сложности XML-имена часто считаются затруднительной темой для изучения в XML. Возможно, эта сложность возникает не из-за пространств имен, которые разработчики часто используют при программировании, а из-за префиксов пространств имен. Префиксы пространств имен могут быть полезны для сокращения количества нажатий клавиш при вводе XML или для повышения удобства чтения XML. Но часто префиксы являются просто ярлыком, свидетельствующим об использовании полного пространства имен XML, в большинстве случаев они не нужны. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] упрощает XML-имена путем разрешения всех префиксов в соответствующее им пространство имен XML. Если они нужны, то префиксами можно воспользоваться при помощи метода <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.  
  
 При необходимости можно управлять префиксами пространства имен. В некоторых ситуациях при работе с другими XML-системами, например XSLT или XAML, необходимо управлять префиксами пространства имен. Например, при наличии выражения XPath, в котором используются префиксы пространства имен и которое внедрено в таблицу стилей XSLT, необходимо сериализовать XML-документ с префиксами пространства имен, которые соответствуют используемым в выражении XPath.  
  
### <a name="xnamespace-class"></a>Класс XNamespace  
 Класс <xref:System.Xml.Linq.XNamespace> представляет пространство имен для объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>. Пространства имен являются компонентом объекта <xref:System.Xml.Linq.XName>.  
  
### <a name="xnode-class"></a>Класс XNode  
 Класс <xref:System.Xml.Linq.XNode> является абстрактным классом, который представляет узлы XML-дерева. Следующие классы происходят от класса <xref:System.Xml.Linq.XNode>:  
  
- <xref:System.Xml.Linq.XText>  
  
- <xref:System.Xml.Linq.XContainer>  
  
- <xref:System.Xml.Linq.XComment>  
  
- <xref:System.Xml.Linq.XProcessingInstruction>  
  
- <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>Класс XNodeDocumentOrderComparer  
 Класс <xref:System.Xml.Linq.XNodeDocumentOrderComparer> предоставляет возможность сравнивать узлы по их порядку в документе.  
  
### <a name="xnodeequalitycomparer-class"></a>Класс XNodeEqualityComparer  
 Класс <xref:System.Xml.Linq.XNodeEqualityComparer> предоставляет возможность сравнивать узлы по равенству значений.  
  
### <a name="xobject-class"></a>Класс XObject  
 Класс <xref:System.Xml.Linq.XObject> является абстрактным базовым классом объектов <xref:System.Xml.Linq.XNode> и <xref:System.Xml.Linq.XAttribute>. Он предоставляет функции обработки заметок и событий.  
  
### <a name="xobjectchange-class"></a>Класс XObjectChange  
 Класс <xref:System.Xml.Linq.XObjectChange> указывает тип события, когда событие возникает для объекта <xref:System.Xml.Linq.XObject>.  
  
### <a name="xobjectchangeeventargs-class"></a>Класс XObjectChangeEventArgs  
 Класс <xref:System.Xml.Linq.XObjectChangeEventArgs> предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.  
  
### <a name="xprocessinginstruction-class"></a>Класс XProcessingInstruction  
 Класс <xref:System.Xml.Linq.XProcessingInstruction> представляет инструкцию обработки XML-кода. Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.  
  
### <a name="xtext-class"></a>Класс XText  
 Класс <xref:System.Xml.Linq.XText> представляет текстовый узел. В большинстве случаев использование этого класса не требуется. Этот класс главным образом используется для смешанного содержимого.  
  
## <a name="see-also"></a>См. также

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
