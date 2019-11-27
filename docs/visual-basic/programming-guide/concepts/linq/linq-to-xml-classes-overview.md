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
# <a name="linq-to-xml-classes-overview-visual-basic"></a>Общие сведения о LINQ to XML классах (Visual Basic)
В этом разделе приведен список классов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в пространстве имен <xref:System.Xml.Linq> с кратким описанием каждого из них.  
  
## <a name="linq-to-xml-classes"></a>Классы LINQ to XML  
  
### <a name="xattribute-class"></a>Класс XAttribute  
 <xref:System.Xml.Linq.XAttribute> представляет XML-атрибут. Подробные сведения и примеры см. в разделе [Общие сведения о классе XAttribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Класс XCData  
 <xref:System.Xml.Linq.XCData> представляет текстовый узел CDATA.  
  
### <a name="xcomment-class"></a>Класс XComment  
 <xref:System.Xml.Linq.XComment> представляет комментарий XML.  
  
### <a name="xcontainer-class"></a>Класс XContainer  
 <xref:System.Xml.Linq.XContainer> является абстрактным базовым классом для всех узлов, которые могут иметь дочерние узлы. Следующие классы происходят от класса <xref:System.Xml.Linq.XContainer>:  
  
- <xref:System.Xml.Linq.XElement>  
  
- <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Класс XDeclaration  
 <xref:System.Xml.Linq.XDeclaration> представляет XML-декларацию. XML-декларация используется для объявления версии XML и кодировки документа. Кроме того, в XML-декларации указывается, является ли данный XML-документ изолированным. Если документ является изолированным, то внешние декларации разметки не используются ни во внешних DTD, ни во внешних сущностях параметров, ссылки на которые имеются во встроенном DTD.  
  
### <a name="xdocument-class"></a>Класс XDocument  
 <xref:System.Xml.Linq.XDocument> представляет XML-документ. Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Класс XDocumentType  
 <xref:System.Xml.Linq.XDocumentType> представляет определение типа XML-документа (DTD).  
  
### <a name="xelement-class"></a>Класс XElement  
 <xref:System.Xml.Linq.XElement> представляет XML-элемент. Подробные сведения и примеры см. в разделе [Общие сведения о классе XElement (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>Класс XName  
 <xref:System.Xml.Linq.XName> представляет имена элементов (<xref:System.Xml.Linq.XElement>) и атрибуты (<xref:System.Xml.Linq.XAttribute>). Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяет сделать XML-имена как можно более понятными. В силу их сложности XML-имена часто считаются затруднительной темой для изучения в XML. Возможно, эта сложность возникает не из-за пространств имен, которые разработчики часто используют при программировании, а из-за префиксов пространств имен. Префиксы пространств имен могут быть полезны для сокращения количества нажатий клавиш при вводе XML или для повышения удобства чтения XML. Но часто префиксы являются просто ярлыком, свидетельствующим об использовании полного пространства имен XML, в большинстве случаев они не нужны. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] упрощает XML-имена путем разрешения всех префиксов в соответствующее им пространство имен XML. Если они нужны, то префиксами можно воспользоваться при помощи метода <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.  
  
 При необходимости можно управлять префиксами пространства имен. В некоторых ситуациях при работе с другими XML-системами, например XSLT или XAML, необходимо управлять префиксами пространства имен. Например, при наличии выражения XPath, в котором используются префиксы пространства имен и которое внедрено в таблицу стилей XSLT, необходимо сериализовать XML-документ с префиксами пространства имен, которые соответствуют используемым в выражении XPath.  
  
### <a name="xnamespace-class"></a>Класс XNamespace  
 <xref:System.Xml.Linq.XNamespace> представляет пространство имен для <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>. Пространства имен являются компонентом объекта <xref:System.Xml.Linq.XName>.  
  
### <a name="xnode-class"></a>Класс XNode  
 <xref:System.Xml.Linq.XNode> является абстрактным классом, представляющим узлы XML-дерева. Следующие классы происходят от класса <xref:System.Xml.Linq.XNode>:  
  
- <xref:System.Xml.Linq.XText>  
  
- <xref:System.Xml.Linq.XContainer>  
  
- <xref:System.Xml.Linq.XComment>  
  
- <xref:System.Xml.Linq.XProcessingInstruction>  
  
- <xref:System.Xml.Linq.XDocumentType>  
  
### <a name="xnodedocumentordercomparer-class"></a>Класс XNodeDocumentOrderComparer  
 <xref:System.Xml.Linq.XNodeDocumentOrderComparer> предоставляет функции для сравнения узлов в порядке их расположения в документах.  
  
### <a name="xnodeequalitycomparer-class"></a>Класс XNodeEqualityComparer  
 <xref:System.Xml.Linq.XNodeEqualityComparer> предоставляет функциональные возможности для сравнения узлов на равенство значений.  
  
### <a name="xobject-class"></a>Класс XObject  
 <xref:System.Xml.Linq.XObject> является абстрактным базовым классом <xref:System.Xml.Linq.XNode> и <xref:System.Xml.Linq.XAttribute>. Он предоставляет функции обработки заметок и событий.  
  
### <a name="xobjectchange-class"></a>Класс XObjectChange  
 <xref:System.Xml.Linq.XObjectChange> указывает тип события при возникновении события для <xref:System.Xml.Linq.XObject>.  
  
### <a name="xobjectchangeeventargs-class"></a>Класс XObjectChangeEventArgs  
 Класс <xref:System.Xml.Linq.XObjectChangeEventArgs> предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.  
  
### <a name="xprocessinginstruction-class"></a>Класс XProcessingInstruction  
 <xref:System.Xml.Linq.XProcessingInstruction> представляет инструкцию по обработке XML. Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.  
  
### <a name="xtext-class"></a>Класс XText  
 <xref:System.Xml.Linq.XText> представляет текстовый узел. В большинстве случаев использование этого класса не требуется. Этот класс главным образом используется для смешанного содержимого.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о программировании LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
