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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8c999860ed04c754855792d814cd3801f5f92c90
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-classes-overview-visual-basic"></a><span data-ttu-id="71c54-102">LINQ to XML обзор классов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71c54-102">LINQ to XML Classes Overview (Visual Basic)</span></span>
<span data-ttu-id="71c54-103">Этот раздел содержит список [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] классы в <xref:System.Xml.Linq>пространства имен и краткое описание каждого из них.</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="71c54-103">This topic provides a list of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes in the <xref:System.Xml.Linq> namespace, and a short description of each.</span></span>  
  
## <a name="linq-to-xml-classes"></a><span data-ttu-id="71c54-104">Классы LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="71c54-104">LINQ to XML Classes</span></span>  
  
### <a name="xattribute-class"></a><span data-ttu-id="71c54-105">Класс XAttribute</span><span class="sxs-lookup"><span data-stu-id="71c54-105">XAttribute Class</span></span>  
 <span data-ttu-id="71c54-106"><xref:System.Xml.Linq.XAttribute>Представляет атрибут XML.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="71c54-106"><xref:System.Xml.Linq.XAttribute> represents an XML attribute.</span></span> <span data-ttu-id="71c54-107">Подробные сведения и примеры см. в разделе [Общие сведения о классе XAttribute (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71c54-107">For detailed information and examples, see [XAttribute Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md).</span></span>  
  
### <a name="xcdata-class"></a><span data-ttu-id="71c54-108">Класс XCData</span><span class="sxs-lookup"><span data-stu-id="71c54-108">XCData Class</span></span>  
 <span data-ttu-id="71c54-109"><xref:System.Xml.Linq.XCData>Представляет узел текста CDATA.</xref:System.Xml.Linq.XCData></span><span class="sxs-lookup"><span data-stu-id="71c54-109"><xref:System.Xml.Linq.XCData> represents a CDATA text node.</span></span>  
  
### <a name="xcomment-class"></a><span data-ttu-id="71c54-110">Класс XComment</span><span class="sxs-lookup"><span data-stu-id="71c54-110">XComment Class</span></span>  
 <span data-ttu-id="71c54-111"><xref:System.Xml.Linq.XComment>Представляет XML-комментарий.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="71c54-111"><xref:System.Xml.Linq.XComment> represents an XML comment.</span></span>  
  
### <a name="xcontainer-class"></a><span data-ttu-id="71c54-112">Класс XContainer</span><span class="sxs-lookup"><span data-stu-id="71c54-112">XContainer Class</span></span>  
 <span data-ttu-id="71c54-113"><xref:System.Xml.Linq.XContainer>Представляет абстрактный базовый класс для всех узлов, которые могут иметь дочерние узлы.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="71c54-113"><xref:System.Xml.Linq.XContainer> is an abstract base class for all nodes that can have child nodes.</span></span> <span data-ttu-id="71c54-114">Следующие классы являются производными от <xref:System.Xml.Linq.XContainer>класса:</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="71c54-114">The following classes derive from the <xref:System.Xml.Linq.XContainer> class:</span></span>  
  
-   <span data-ttu-id="71c54-115"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71c54-115"><xref:System.Xml.Linq.XElement></span></span>  
  
-   <span data-ttu-id="71c54-116"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="71c54-116"><xref:System.Xml.Linq.XDocument></span></span>  
  
### <a name="xdeclaration-class"></a><span data-ttu-id="71c54-117">Класс XDeclaration</span><span class="sxs-lookup"><span data-stu-id="71c54-117">XDeclaration Class</span></span>  
 <span data-ttu-id="71c54-118"><xref:System.Xml.Linq.XDeclaration>Представляет объявление XML.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="71c54-118"><xref:System.Xml.Linq.XDeclaration> represents an XML declaration.</span></span> <span data-ttu-id="71c54-119">XML-декларация используется для объявления версии XML и кодировки документа.</span><span class="sxs-lookup"><span data-stu-id="71c54-119">An XML declaration is used to declare the XML version and the encoding of a document.</span></span> <span data-ttu-id="71c54-120">Кроме того, в XML-декларации указывается, является ли данный XML-документ изолированным.</span><span class="sxs-lookup"><span data-stu-id="71c54-120">In addition, an XML declaration specifies whether the XML document is stand-alone.</span></span> <span data-ttu-id="71c54-121">Если документ является изолированным, то внешние декларации разметки не используются ни во внешних DTD, ни во внешних сущностях параметров, ссылки на которые имеются во встроенном DTD.</span><span class="sxs-lookup"><span data-stu-id="71c54-121">If a document is stand-alone, there are no external markup declarations, either in an external DTD, or in an external parameter entity referenced from the internal subset.</span></span>  
  
### <a name="xdocument-class"></a><span data-ttu-id="71c54-122">Класс XDocument</span><span class="sxs-lookup"><span data-stu-id="71c54-122">XDocument Class</span></span>  
 <span data-ttu-id="71c54-123"><xref:System.Xml.Linq.XDocument>Представляет XML-документ.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="71c54-123"><xref:System.Xml.Linq.XDocument> represents an XML document.</span></span> <span data-ttu-id="71c54-124">Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71c54-124">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
### <a name="xdocumenttype-class"></a><span data-ttu-id="71c54-125">Класс XDocumentType</span><span class="sxs-lookup"><span data-stu-id="71c54-125">XDocumentType Class</span></span>  
 <span data-ttu-id="71c54-126"><xref:System.Xml.Linq.XDocumentType>Представляет определение типа XML документа (DTD).</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="71c54-126"><xref:System.Xml.Linq.XDocumentType> represents an XML Document Type Definition (DTD).</span></span>  
  
### <a name="xelement-class"></a><span data-ttu-id="71c54-127">Класс XElement</span><span class="sxs-lookup"><span data-stu-id="71c54-127">XElement Class</span></span>  
 <span data-ttu-id="71c54-128"><xref:System.Xml.Linq.XElement>Представляет элемент XML.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71c54-128"><xref:System.Xml.Linq.XElement> represents an XML element.</span></span> <span data-ttu-id="71c54-129">Подробные сведения и примеры см. в разделе [Общие сведения о классе XElement (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71c54-129">For detailed information and examples, see [XElement Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md).</span></span>  
  
### <a name="xname-class"></a><span data-ttu-id="71c54-130">Класс XName</span><span class="sxs-lookup"><span data-stu-id="71c54-130">XName Class</span></span>  
 <span data-ttu-id="71c54-131"><xref:System.Xml.Linq.XName>Представляет имена элементов (<xref:System.Xml.Linq.XElement>) и атрибутов (<xref:System.Xml.Linq.XAttribute>).</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="71c54-131"><xref:System.Xml.Linq.XName> represents names of elements (<xref:System.Xml.Linq.XElement>) and attributes (<xref:System.Xml.Linq.XAttribute>).</span></span> <span data-ttu-id="71c54-132">Подробные сведения и примеры см. в разделе [Общие сведения о классе XDocument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span><span class="sxs-lookup"><span data-stu-id="71c54-132">For detailed information and examples, see [XDocument Class Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="71c54-133"> позволяет сделать XML-имена как можно более понятными.</span><span class="sxs-lookup"><span data-stu-id="71c54-133"> is designed to make XML names as straightforward as possible.</span></span> <span data-ttu-id="71c54-134">В силу их сложности XML-имена часто считаются затруднительной темой для изучения в XML.</span><span class="sxs-lookup"><span data-stu-id="71c54-134">Due to their complexity, XML names are often considered to be an advanced topic in XML.</span></span> <span data-ttu-id="71c54-135">Возможно, эта сложность возникает не из-за пространств имен, которые разработчики часто используют при программировании, а из-за префиксов пространств имен.</span><span class="sxs-lookup"><span data-stu-id="71c54-135">Arguably, this complexity comes not from namespaces, which developers use regularly in programming, but from namespace prefixes.</span></span> <span data-ttu-id="71c54-136">Префиксы пространств имен могут быть полезны для сокращения количества нажатий клавиш при вводе XML или для повышения удобства чтения XML.</span><span class="sxs-lookup"><span data-stu-id="71c54-136">Namespace prefixes can be useful to reduce the keystrokes required when you input XML, or to make XML easier to read.</span></span> <span data-ttu-id="71c54-137">Но часто префиксы являются просто ярлыком, свидетельствующим об использовании полного пространства имен XML, в большинстве случаев они не нужны.</span><span class="sxs-lookup"><span data-stu-id="71c54-137">However, prefixes are often just a shortcut for using the full XML namespace, and are not required in most cases.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="71c54-138">упрощает XML-имена путем разрешения всех префиксов в соответствующее им пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="71c54-138"> simplifies XML names by resolving all prefixes to their corresponding XML namespace.</span></span> <span data-ttu-id="71c54-139">Префиксы доступны, если они требуются, через <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A>метод.</xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="71c54-139">Prefixes are available, if they are required, through the <xref:System.Xml.Linq.XElement.GetPrefixOfNamespace%2A> method.</span></span>  
  
 <span data-ttu-id="71c54-140">При необходимости можно управлять префиксами пространства имен.</span><span class="sxs-lookup"><span data-stu-id="71c54-140">It is possible, if necessary, to control namespace prefixes.</span></span> <span data-ttu-id="71c54-141">В некоторых ситуациях при работе с другими XML-системами, например XSLT или XAML, необходимо управлять префиксами пространства имен.</span><span class="sxs-lookup"><span data-stu-id="71c54-141">In some circumstances, if you are working with other XML systems, such as XSLT or XAML, you need to control namespace prefixes.</span></span> <span data-ttu-id="71c54-142">Например, при наличии выражения XPath, в котором используются префиксы пространства имен и которое внедрено в таблицу стилей XSLT, необходимо сериализовать XML-документ с префиксами пространства имен, которые соответствуют используемым в выражении XPath.</span><span class="sxs-lookup"><span data-stu-id="71c54-142">For example, if you have an XPath expression that uses namespace prefixes and is embedded in an XSLT stylesheet, you must make sure that your XML document is serialized with namespace prefixes that match those used in the XPath expression.</span></span>  
  
### <a name="xnamespace-class"></a><span data-ttu-id="71c54-143">Класс XNamespace</span><span class="sxs-lookup"><span data-stu-id="71c54-143">XNamespace Class</span></span>  
 <span data-ttu-id="71c54-144"><xref:System.Xml.Linq.XNamespace>представляет пространство имен <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="71c54-144"><xref:System.Xml.Linq.XNamespace> represents a namespace for an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="71c54-145">Пространства имен являются компонентом <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="71c54-145">Namespaces are a component of an <xref:System.Xml.Linq.XName>.</span></span>  
  
### <a name="xnode-class"></a><span data-ttu-id="71c54-146">Класс XNode</span><span class="sxs-lookup"><span data-stu-id="71c54-146">XNode Class</span></span>  
 <span data-ttu-id="71c54-147"><xref:System.Xml.Linq.XNode>Представляет абстрактный класс, который представляет узлы XML-дерева.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="71c54-147"><xref:System.Xml.Linq.XNode> is an abstract class that represents the nodes of an XML tree.</span></span> <span data-ttu-id="71c54-148">Следующие классы являются производными от <xref:System.Xml.Linq.XNode>класса:</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="71c54-148">The following classes derive from the <xref:System.Xml.Linq.XNode> class:</span></span>  
  
-   <span data-ttu-id="71c54-149"><xref:System.Xml.Linq.XText></xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="71c54-149"><xref:System.Xml.Linq.XText></span></span>  
  
-   <span data-ttu-id="71c54-150"><xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="71c54-150"><xref:System.Xml.Linq.XContainer></span></span>  
  
-   <span data-ttu-id="71c54-151"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="71c54-151"><xref:System.Xml.Linq.XComment></span></span>  
  
-   <span data-ttu-id="71c54-152"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="71c54-152"><xref:System.Xml.Linq.XProcessingInstruction></span></span>  
  
-   <span data-ttu-id="71c54-153"><xref:System.Xml.Linq.XDocumentType></xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="71c54-153"><xref:System.Xml.Linq.XDocumentType></span></span>  
  
### <a name="xnodedocumentordercomparer-class"></a><span data-ttu-id="71c54-154">Класс XNodeDocumentOrderComparer</span><span class="sxs-lookup"><span data-stu-id="71c54-154">XNodeDocumentOrderComparer Class</span></span>  
 <span data-ttu-id="71c54-155"><xref:System.Xml.Linq.XNodeDocumentOrderComparer>предоставляет возможность сравнивать узлы по их порядку в документе.</xref:System.Xml.Linq.XNodeDocumentOrderComparer></span><span class="sxs-lookup"><span data-stu-id="71c54-155"><xref:System.Xml.Linq.XNodeDocumentOrderComparer> provides functionality to compare nodes for their document order.</span></span>  
  
### <a name="xnodeequalitycomparer-class"></a><span data-ttu-id="71c54-156">Класс XNodeEqualityComparer</span><span class="sxs-lookup"><span data-stu-id="71c54-156">XNodeEqualityComparer Class</span></span>  
 <span data-ttu-id="71c54-157"><xref:System.Xml.Linq.XNodeEqualityComparer>предоставляет возможность сравнивать узлы по равенству значений.</xref:System.Xml.Linq.XNodeEqualityComparer></span><span class="sxs-lookup"><span data-stu-id="71c54-157"><xref:System.Xml.Linq.XNodeEqualityComparer> provides functionality to compare nodes for value equality.</span></span>  
  
### <a name="xobject-class"></a><span data-ttu-id="71c54-158">Класс XObject</span><span class="sxs-lookup"><span data-stu-id="71c54-158">XObject Class</span></span>  
 <span data-ttu-id="71c54-159"><xref:System.Xml.Linq.XObject>Представляет абстрактный базовый класс и <xref:System.Xml.Linq.XNode> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="71c54-159"><xref:System.Xml.Linq.XObject> is an abstract base class of <xref:System.Xml.Linq.XNode> and <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="71c54-160">Он предоставляет функции обработки заметок и событий.</span><span class="sxs-lookup"><span data-stu-id="71c54-160">It provides annotation and event functionality.</span></span>  
  
### <a name="xobjectchange-class"></a><span data-ttu-id="71c54-161">Класс XObjectChange</span><span class="sxs-lookup"><span data-stu-id="71c54-161">XObjectChange Class</span></span>  
 <span data-ttu-id="71c54-162"><xref:System.Xml.Linq.XObjectChange>Указывает тип события, когда происходит событие <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="71c54-162"><xref:System.Xml.Linq.XObjectChange> specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>  
  
### <a name="xobjectchangeeventargs-class"></a><span data-ttu-id="71c54-163">Класс XObjectChangeEventArgs</span><span class="sxs-lookup"><span data-stu-id="71c54-163">XObjectChangeEventArgs Class</span></span>  
 <span data-ttu-id="71c54-164"><xref:System.Xml.Linq.XObjectChangeEventArgs>Предоставляет данные для <xref:System.Xml.Linq.XObject.Changing>и <xref:System.Xml.Linq.XObject.Changed>события.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="71c54-164"><xref:System.Xml.Linq.XObjectChangeEventArgs> provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>  
  
### <a name="xprocessinginstruction-class"></a><span data-ttu-id="71c54-165">Класс XProcessingInstruction</span><span class="sxs-lookup"><span data-stu-id="71c54-165">XProcessingInstruction Class</span></span>  
 <span data-ttu-id="71c54-166"><xref:System.Xml.Linq.XProcessingInstruction>Представляет инструкцию обработки XML.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="71c54-166"><xref:System.Xml.Linq.XProcessingInstruction> represents an XML processing instruction.</span></span> <span data-ttu-id="71c54-167">Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.</span><span class="sxs-lookup"><span data-stu-id="71c54-167">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
### <a name="xtext-class"></a><span data-ttu-id="71c54-168">Класс XText</span><span class="sxs-lookup"><span data-stu-id="71c54-168">XText Class</span></span>  
 <span data-ttu-id="71c54-169"><xref:System.Xml.Linq.XText>Представляет текстовый узел.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="71c54-169"><xref:System.Xml.Linq.XText> represents a text node.</span></span> <span data-ttu-id="71c54-170">В большинстве случаев использование этого класса не требуется.</span><span class="sxs-lookup"><span data-stu-id="71c54-170">In most cases, you do not have to use this class.</span></span> <span data-ttu-id="71c54-171">Этот класс главным образом используется для смешанного содержимого.</span><span class="sxs-lookup"><span data-stu-id="71c54-171">This class is primarily used for mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c54-172">См. также</span><span class="sxs-lookup"><span data-stu-id="71c54-172">See Also</span></span>  
 [<span data-ttu-id="71c54-173">LINQ to XML обзор программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71c54-173">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
