---
title: Иерархия модели объектов (DOM) XML-документа
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 1193d7631816fe9fbf7aa1984d79ef8e61d5da80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709976"
---
# <a name="xml-document-object-model-dom-hierarchy"></a><span data-ttu-id="5f115-102">Иерархия модели объектов (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="5f115-102">XML Document Object Model (DOM) Hierarchy</span></span>
<span data-ttu-id="5f115-103">Следующая иллюстрация показывает иерархию классов для модели XML DOM с именем W3C в скобках наряду с именем класса, где это уместно.</span><span class="sxs-lookup"><span data-stu-id="5f115-103">The following illustration shows the class hierarchy for the XML Document Object Model (DOM), with the World Wide Web Consortium (W3C) name in parenthesis along with the class name where it is relevant.</span></span>  
  
 <span data-ttu-id="5f115-104">![Иерархия &#40;XML&#41; модель DOM DOM](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span><span class="sxs-lookup"><span data-stu-id="5f115-104">![XML Document Object Model &#40;DOM&#41; hierarchy](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")</span></span>  
<span data-ttu-id="5f115-105">Иерархия объектной модели (DOM) XML-документа</span><span class="sxs-lookup"><span data-stu-id="5f115-105">XML Document Object Model (DOM) hierarchy</span></span>  
  
 <span data-ttu-id="5f115-106">Следующие классы не наследуют от класса **XmlNode**:</span><span class="sxs-lookup"><span data-stu-id="5f115-106">The following classes do not inherit from the **XmlNode**:</span></span>  
  
- <span data-ttu-id="5f115-107">**XmlImplementation**</span><span class="sxs-lookup"><span data-stu-id="5f115-107">**XmlImplementation**</span></span>  
  
- <span data-ttu-id="5f115-108">**XmlNamedNodeMap**</span><span class="sxs-lookup"><span data-stu-id="5f115-108">**XmlNamedNodeMap**</span></span>  
  
- <span data-ttu-id="5f115-109">**XmlNodeList**</span><span class="sxs-lookup"><span data-stu-id="5f115-109">**XmlNodeList**</span></span>  
  
- <span data-ttu-id="5f115-110">**XmlNodeChangedEventArgs**</span><span class="sxs-lookup"><span data-stu-id="5f115-110">**XmlNodeChangedEventArgs**</span></span>  
  
 <span data-ttu-id="5f115-111">Класс **XmlImplementation** используется для создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="5f115-111">The **XmlImplementation** class is used to create an XML document.</span></span> <span data-ttu-id="5f115-112">Дополнительные сведения см. в статье [Создание XML-документа](../../../../docs/standard/data/xml/xml-document-creation.md).</span><span class="sxs-lookup"><span data-stu-id="5f115-112">For more information, see [XML Document Creation](../../../../docs/standard/data/xml/xml-document-creation.md).</span></span>  
  
 <span data-ttu-id="5f115-113">Класс **XmlNamedNodeMap** обрабатывает неупорядоченный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="5f115-113">The **XmlNamedNodeMap** class handles an unordered set of nodes.</span></span> <span data-ttu-id="5f115-114">Дополнительные сведения см. в статье [Неупорядоченное извлечение узлов по имени или индексу](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span><span class="sxs-lookup"><span data-stu-id="5f115-114">For more information, see [Unordered Node Retrieval by Name or Index](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).</span></span>  
  
 <span data-ttu-id="5f115-115">Класс **XmlNamedNodeMap** обрабатывает упорядоченный набор узлов.</span><span class="sxs-lookup"><span data-stu-id="5f115-115">The **XmlNodeList** class handles an ordered list of nodes.</span></span> <span data-ttu-id="5f115-116">Дополнительные сведения см. в статье [Упорядоченное извлечение узлов по индексу](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span><span class="sxs-lookup"><span data-stu-id="5f115-116">For more information, see [Ordered Node Retrieval by Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).</span></span>  
  
 <span data-ttu-id="5f115-117">Класс **XmlNodeChangedEventArgs** управляет обработчиками событий, которые зарегистрированы в объекте **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="5f115-117">The **XmlNodeChangedEventArgs** class handles event handlers registered on the **XmlDocument**.</span></span> <span data-ttu-id="5f115-118">Дополнительные сведения см. в статье [Обработка событий в XML-документе с помощью XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span><span class="sxs-lookup"><span data-stu-id="5f115-118">For more information, see [Event Handling in an XML Document using the XmlNodeChangedEventArgs](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).</span></span>  
  
 <span data-ttu-id="5f115-119">Класс **XmlLinkedNode** наследует от класса **XmlNode**.</span><span class="sxs-lookup"><span data-stu-id="5f115-119">The **XmlLinkedNode** class inherits from **XmlNode**.</span></span> <span data-ttu-id="5f115-120">Он предназначен для того, чтобы переопределять два метода **XmlNode**, а именно: **PreviousSibling** и **NextSibling**.</span><span class="sxs-lookup"><span data-stu-id="5f115-120">Its purpose is to override two methods from **XmlNode**: the **PreviousSibling** and **NextSibling** methods.</span></span> <span data-ttu-id="5f115-121">Эти переопределенные методы затем наследуются и используются классами **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** и **XmlProcessingInstruction**, для которых существуют предыдущие и следующие одноуровневые элементы.</span><span class="sxs-lookup"><span data-stu-id="5f115-121">These overridden methods are then inherited and used by **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, and **XmlProcessingInstruction**, which are classes that have previous and next siblings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f115-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="5f115-122">See also</span></span>

- [<span data-ttu-id="5f115-123">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="5f115-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
