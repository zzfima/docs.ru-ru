---
title: "Иерархия модели объектов (DOM) XML-документа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="a9238-102">Иерархия модели объектов (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="a9238-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="a9238-103">Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.</span><span class="sxs-lookup"><span data-stu-id="a9238-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="a9238-104">![Модель объектов XML-документов &#40; DOM &#41; Иерархия](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="a9238-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="a9238-105">Иерархия объектной модели (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="a9238-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="a9238-106">Следующие классы не наследуют от **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="a9238-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
-   <span data-ttu-id="a9238-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="a9238-107">**XmlImplementation**</span></span>  
  
-   <span data-ttu-id="a9238-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="a9238-108">**XmlNamedNodeMap**</span></span>  
  
-   <span data-ttu-id="a9238-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="a9238-109">**XmlNodeList**</span></span>  
  
-   <span data-ttu-id="a9238-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="a9238-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="a9238-111">**XmlImplementation** класс используется для создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a9238-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="a9238-112">Дополнительные сведения см. в разделе [Создание XML-документа](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="a9238-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="a9238-113">**XmlNamedNodeMap** класс обрабатывает неупорядоченный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="a9238-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="a9238-114">Дополнительные сведения см. в разделе [получение неупорядоченных узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="a9238-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="a9238-115">**XmlNodeList** класс обрабатывает неупорядоченный список узлов.</span><span class="sxs-lookup"><span data-stu-id="a9238-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="a9238-116">Дополнительные сведения см. в разделе [получение упорядоченных узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="a9238-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="a9238-117">**XmlNodeChangedEventArgs** класс обрабатывает обработчики событий, зарегистрированных на **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="a9238-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="a9238-118">Дополнительные сведения см. в разделе [обработка событий в XML-документа с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="a9238-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="a9238-119">**XmlLinkedNode** класс наследует от **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="a9238-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="a9238-120">Он предназначен для переопределения двух методов **XmlNode**: **PreviousSibling** и **NextSibling** методы.</span><span class="sxs-lookup"><span data-stu-id="a9238-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="a9238-121">Эти переопределенные методы затем наследуются и используемые **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, и **XmlProcessingInstruction**, которые являются классы, которые имеют предыдущие и следующие одноуровневые элементы.</span><span class="sxs-lookup"><span data-stu-id="a9238-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9238-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a9238-122">See Also</span></span>  
 [<span data-ttu-id="a9238-123">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="a9238-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
