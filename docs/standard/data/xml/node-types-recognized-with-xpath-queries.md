---
title: Типы узлов, распознаваемые запросами XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005c5f4981a7ab1889678e391a6df6e0b7b43f71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="c1297-102">Типы узлов, распознаваемые запросами XPath</span><span class="sxs-lookup"><span data-stu-id="c1297-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="c1297-103">Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML-документа.</span><span class="sxs-lookup"><span data-stu-id="c1297-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="c1297-104">Типы узлов W3C XPath</span><span class="sxs-lookup"><span data-stu-id="c1297-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="c1297-105">Типы узлов, распознаваемые в запросе XPath, отличаются от типов узлов в модели DOM XML-документа.</span><span class="sxs-lookup"><span data-stu-id="c1297-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="c1297-106">Ниже приведены типы узлов XPath, представленные перечислением <xref:System.Xml.XPath.XPathNodeType>.</span><span class="sxs-lookup"><span data-stu-id="c1297-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNodeType.All>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Element>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Root>  
  
-   <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Text>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="c1297-107">Эти типы узлов основаны на модели данных XPath, где узлы являются производными от набора данных XML.</span><span class="sxs-lookup"><span data-stu-id="c1297-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="c1297-108">Типы узлов <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> и <xref:System.Xml.XPath.XPathNodeType.Whitespace> - расширения платформы Microsoft .NET Framework для базовых типов узлов, описанных в модели данных XPath.</span><span class="sxs-lookup"><span data-stu-id="c1297-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="c1297-109">Тип узла атрибута используется в модели данных XPath иначе, нежели в DOM.</span><span class="sxs-lookup"><span data-stu-id="c1297-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="c1297-110">В модели данных XPath узел элемента имеет набор связанных с ним узлов атрибута, и узел элемента является родителем каждого узла атрибута.</span><span class="sxs-lookup"><span data-stu-id="c1297-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="c1297-111">Однако в DOM узел элемента является владельцем, но не родителем.</span><span class="sxs-lookup"><span data-stu-id="c1297-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="c1297-112">В обеих моделях узлы атрибута и пространства имен не считаются дочерними узлами узла элемента.</span><span class="sxs-lookup"><span data-stu-id="c1297-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="c1297-113">Тип узла пространства имен - дополнение к модели данных XPath и не является распознаваемым типом узла DOM.</span><span class="sxs-lookup"><span data-stu-id="c1297-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="c1297-114">См. дополнительные сведения о навигации в руководствах по [навигации по наборам улов](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) и [улов атрибутов и пространств имен](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) с помощью XPathNavigator.</span><span class="sxs-lookup"><span data-stu-id="c1297-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1297-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c1297-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="c1297-116">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="c1297-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="c1297-117">Выборка XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c1297-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c1297-118">Вычисление выражения XPath с помощью класса XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c1297-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="c1297-119">Соответствие узлов с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c1297-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="c1297-120">Запросы XPath и пространства имен</span><span class="sxs-lookup"><span data-stu-id="c1297-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="c1297-121">Скомпилированные выражения XPath</span><span class="sxs-lookup"><span data-stu-id="c1297-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
