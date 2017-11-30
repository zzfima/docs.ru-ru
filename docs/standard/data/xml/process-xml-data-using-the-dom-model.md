---
title: "Обработка XML-данных с использованием модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 06c8b2e130dbecaca4c08684d030c8dcef1cd5a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="69ffb-102">Обработка XML-данных с использованием модели DOM</span><span class="sxs-lookup"><span data-stu-id="69ffb-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="69ffb-103">Модель DOM рассматривает XML-данные как стандартный набор объектов и используется для обработки XML-данных в памяти.</span><span class="sxs-lookup"><span data-stu-id="69ffb-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="69ffb-104">Пространство имен `System.Xml` обеспечивает программное представление XML-документов, фрагментов, узлов и наборов узлов.</span><span class="sxs-lookup"><span data-stu-id="69ffb-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="69ffb-105">Оно основывается на рекомендациях базовой модели DOM уровня 1 и модели DOM уровня 2 консорциума W3C.</span><span class="sxs-lookup"><span data-stu-id="69ffb-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="69ffb-106">Класс <xref:System.Xml.XmlDocument> представляет XML-документ.</span><span class="sxs-lookup"><span data-stu-id="69ffb-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="69ffb-107">Он включает элементы для получения и создания всех других XML-объектов.</span><span class="sxs-lookup"><span data-stu-id="69ffb-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="69ffb-108">С помощью класса <xref:System.Xml.XmlDocument> и связанных с ним классов можно конструировать XML-документы, загружать и обращаться к данным, изменять данные и сохранять изменения.</span><span class="sxs-lookup"><span data-stu-id="69ffb-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69ffb-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="69ffb-109">In This Section</span></span>  
  
-   [<span data-ttu-id="69ffb-110">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="69ffb-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
-   [<span data-ttu-id="69ffb-111">Типы XML-узлов</span><span class="sxs-lookup"><span data-stu-id="69ffb-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
-   [<span data-ttu-id="69ffb-112">Иерархия объектной модели (DOM) XML документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
-   [<span data-ttu-id="69ffb-113">Сопоставление объектной иерархии с XML-данными</span><span class="sxs-lookup"><span data-stu-id="69ffb-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
-   [<span data-ttu-id="69ffb-114">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
-   [<span data-ttu-id="69ffb-115">Считывание XML-документа в DOM</span><span class="sxs-lookup"><span data-stu-id="69ffb-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
-   [<span data-ttu-id="69ffb-116">Вставка узлов в XML-документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
-   [<span data-ttu-id="69ffb-117">Удаление узлов, содержимого и значений из XML-документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
-   [<span data-ttu-id="69ffb-118">Изменение узлов, содержимого и значений в XML-документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
-   [<span data-ttu-id="69ffb-119">Проверка XML-документа в DOM</span><span class="sxs-lookup"><span data-stu-id="69ffb-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
-   [<span data-ttu-id="69ffb-120">Сохранение и запись документа</span><span class="sxs-lookup"><span data-stu-id="69ffb-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
-   [<span data-ttu-id="69ffb-121">Выбор узлов с помощью XPath-навигации</span><span class="sxs-lookup"><span data-stu-id="69ffb-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
-   [<span data-ttu-id="69ffb-122">Разрешение внешних ресурсов</span><span class="sxs-lookup"><span data-stu-id="69ffb-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
-   [<span data-ttu-id="69ffb-123">Сравнение объекта с помощью класса XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="69ffb-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
-   [<span data-ttu-id="69ffb-124">Коллекции узлов в NamedNodeMap и nodelist</span><span class="sxs-lookup"><span data-stu-id="69ffb-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
-   [<span data-ttu-id="69ffb-125">Динамические обновления объектов nodelist и NamedNodeMap</span><span class="sxs-lookup"><span data-stu-id="69ffb-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
-   [<span data-ttu-id="69ffb-126">Поддержка пространств имен в модели DOM</span><span class="sxs-lookup"><span data-stu-id="69ffb-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
-   [<span data-ttu-id="69ffb-127">Обработка событий в XML-документа с помощью XmlNodeChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="69ffb-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
-   [<span data-ttu-id="69ffb-128">Расширение модели DOM</span><span class="sxs-lookup"><span data-stu-id="69ffb-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="69ffb-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="69ffb-129">Related Sections</span></span>  
 [<span data-ttu-id="69ffb-130">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="69ffb-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="69ffb-131">Описывает обработку XML с использованием класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="69ffb-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
