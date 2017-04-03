---
title: "Общие сведения о классах LINQ to XML (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bf666100-5392-4968-97f4-f6b9d3287d7b
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f75a7a2aa3f9fca867562807595c6387b0be23d4
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-classes-overview-c"></a>Общие сведения о классах LINQ to XML (C#)
В этом разделе приведен список классов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в пространстве имен <xref:System.Xml.Linq> с кратким описанием каждого из них.  
  
## <a name="linq-to-xml-classes"></a>Классы LINQ to XML  
  
### <a name="xattribute-class"></a>Класс XAttribute  
 Класс <xref:System.Xml.Linq.XAttribute> представляет XML-атрибут. Подробные сведения и примеры см. в разделе [Общие сведения о классе XAttribute (C#)](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md).  
  
### <a name="xcdata-class"></a>Класс XCData  
 Класс <xref:System.Xml.Linq.XCData> представляет текстовый узел CDATA.  
  
### <a name="xcomment-class"></a>Класс XComment  
 Класс <xref:System.Xml.Linq.XComment> представляет XML-комментарий.  
  
### <a name="xcontainer-class"></a>Класс XContainer  
 Класс <xref:System.Xml.Linq.XContainer> является абстрактным базовым классом для всех узлов, которые могут иметь дочерние узлы. Следующие классы являются производными от класса <xref:System.Xml.Linq.XContainer>:  
  
-   <xref:System.Xml.Linq.XElement>  
  
-   <xref:System.Xml.Linq.XDocument>  
  
### <a name="xdeclaration-class"></a>Класс XDeclaration  
 Класс <xref:System.Xml.Linq.XDeclaration> представляет XML-декларацию. XML-декларация используется для объявления версии XML и кодировки документа. Кроме того, в XML-декларации указывается, является ли данный XML-документ изолированным. Если документ является изолированным, то внешние декларации разметки не используются ни во внешних DTD, ни во внешних сущностях параметров, ссылки на которые имеются во встроенном DTD.  
  
### <a name="xdocument-class"></a>Класс XDocument  
 Класс <xref:System.Xml.Linq.XDocument> представляет XML-документ. Дополнительные сведения и примеры см. в разделе [Общие сведения о классе XDocument (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
### <a name="xdocumenttype-class"></a>Класс XDocumentType  
 Класс <xref:System.Xml.Linq.XDocumentType> представляет определение типа XML-документа (DTD).  
  
### <a name="xelement-class"></a>Класс XElement  
 Класс <xref:System.Xml.Linq.XElement> представляет XML-элемент. Дополнительные сведения и примеры см. в разделе [Общие сведения о классе XElement (C#)](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md).  
  
### <a name="xname-class"></a>Класс XName  
 Класс <xref:System.Xml.Linq.XName> представляет имена элементов (<xref:System.Xml.Linq.XElement>) и атрибутов (<xref:System.Xml.Linq.XAttribute>). Дополнительные сведения и примеры см. в разделе [Общие сведения о классе XDocument (C#)](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] позволяет сделать XML-имена как можно более понятными. В силу их сложности XML-имена часто считаются затруднительной темой для изучения в XML. Возможно, эта сложность возникает не из-за пространств имен, которые разработчики часто используют при программировании, а из-за префиксов пространств имен. Префиксы пространств имен могут быть полезны для сокращения количества нажатий клавиш при вводе XML или для повышения удобства чтения XML. Но часто префиксы являются просто ярлыком, свидетельствующим об использовании полного пространства имен XML, в большинстве случаев они не нужны. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] упрощает XML-имена путем разрешения всех префиксов в соответствующее им пространство имен XML. Если они нужны, то префиксами можно воспользоваться с помощью метода <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>.  
  
 При необходимости можно управлять префиксами пространства имен. В некоторых ситуациях при работе с другими XML-системами, например XSLT или XAML, необходимо управлять префиксами пространства имен. Например, при наличии выражения XPath, в котором используются префиксы пространства имен и которое внедрено в таблицу стилей XSLT, необходимо сериализовать XML-документ с префиксами пространства имен, которые соответствуют используемым в выражении XPath.  
  
### <a name="xnamespace-class"></a>Класс XNamespace  
 Класс <xref:System.Xml.Linq.XNamespace> представляет пространство имен для объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>. Пространства имен являются компонентом объекта <xref:System.Xml.Linq.XName>.  
  
### <a name="xnode-class"></a>Класс XNode  
 Класс <xref:System.Xml.Linq.XNode> является абстрактным классом, который представляет узлы XML-дерева. Следующие классы являются производными от класса <xref:System.Xml.Linq.XNode>:  
  
-   <xref:System.Xml.Linq.XText>  
  
-   <xref:System.Xml.Linq.XContainer>  
  
-   <xref:System.Xml.Linq.XComment>  
  
-   <xref:System.Xml.Linq.XProcessingInstruction>  
  
-   <xref:System.Xml.Linq.XDocumentType>  
  
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
 [Общие сведения о программировании LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
