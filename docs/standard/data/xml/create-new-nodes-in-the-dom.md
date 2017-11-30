---
title: "Создание новых узлов в модели DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec624a02f98fda4352b5ba8ff43681fba040c676
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="create-new-nodes-in-the-dom"></a><span data-ttu-id="6673b-102">Создание новых узлов в модели DOM</span><span class="sxs-lookup"><span data-stu-id="6673b-102">Create New Nodes in the DOM</span></span>
<span data-ttu-id="6673b-103">К классе <xref:System.Xml.XmlDocument> доступен метод для создания всех типов узлов.</span><span class="sxs-lookup"><span data-stu-id="6673b-103">The <xref:System.Xml.XmlDocument> has a create method for all of the node types.</span></span> <span data-ttu-id="6673b-104">Для создания узла методу нужно передать имя (если необходимо) и содержимое или другие параметры для узлов, имеющих содержимое (например, текстовый узел).</span><span class="sxs-lookup"><span data-stu-id="6673b-104">Supply the method with a name when required, and content or other parameters for those nodes that have content (for example, a text node), and the node is created.</span></span> <span data-ttu-id="6673b-105">Далее представлены методы, которым необходимо передать имя и некоторые другие параметры для создания нужного узла.</span><span class="sxs-lookup"><span data-stu-id="6673b-105">The following methods are ones that need a name and a few other parameters filled to create an appropriate node.</span></span>  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 <span data-ttu-id="6673b-106">Для других типов узлов недостаточно просто задать данные параметров.</span><span class="sxs-lookup"><span data-stu-id="6673b-106">Other node types have more requirements than just providing data to parameters.</span></span>  
  
 <span data-ttu-id="6673b-107">Сведения об атрибутах см. в разделе [создание новых атрибутов для элементов в модели DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="6673b-107">For information on attributes, see [Creating New Attributes for Elements in the DOM](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md).</span></span> <span data-ttu-id="6673b-108">Сведения о проверке имен элементов и атрибутов см. в разделе [XML-элемента Проверка имен и атрибутов при создании новых узлов](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="6673b-108">For information on element and attribute name validation, see [XML Element and Attribute Name Verification when Creating New Nodes](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md).</span></span> <span data-ttu-id="6673b-109">Для создания ссылки на сущности, в разделе [создание новых ссылок на сущности](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span><span class="sxs-lookup"><span data-stu-id="6673b-109">For creating entity references, see [Creating New Entity References](../../../../docs/standard/data/xml/creating-new-entity-references.md).</span></span> <span data-ttu-id="6673b-110">Сведения о влиянии пространств имен на раскрытие ссылок на сущности см. в разделе [влияние пространства имен на раскрытие ссылок на сущности для новых узлов, содержащих элементы и атрибуты](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span><span class="sxs-lookup"><span data-stu-id="6673b-110">For information on how namespaces affect the expansion of entity references, see [Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md).</span></span>  
  
 <span data-ttu-id="6673b-111">После создания новых узлов становятся доступны несколько методов для вставки узлов в дерево.</span><span class="sxs-lookup"><span data-stu-id="6673b-111">Once new nodes are created, there are several methods available to insert them into the tree.</span></span> <span data-ttu-id="6673b-112">В таблице перечислены методы и описано место появления нового узла в модели XML DOM.</span><span class="sxs-lookup"><span data-stu-id="6673b-112">The table lists the methods with a description of where the new node appears in the XML Document Object Model (DOM).</span></span>  
  
|<span data-ttu-id="6673b-113">Метод</span><span class="sxs-lookup"><span data-stu-id="6673b-113">Method</span></span>|<span data-ttu-id="6673b-114">Размещение узла</span><span class="sxs-lookup"><span data-stu-id="6673b-114">Node placement</span></span>|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|<span data-ttu-id="6673b-115">Вставляется перед узлом ссылки.</span><span class="sxs-lookup"><span data-stu-id="6673b-115">Inserted before the reference node.</span></span> <span data-ttu-id="6673b-116">Например, следующий код вставляет новый узел в позицию 5:</span><span class="sxs-lookup"><span data-stu-id="6673b-116">For example, to insert the new node in position 5:</span></span><br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> <span data-ttu-id="6673b-117">Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.InsertBefore%2A>.</span><span class="sxs-lookup"><span data-stu-id="6673b-117">For more information, see the <xref:System.Xml.XmlNode.InsertBefore%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|<span data-ttu-id="6673b-118">Вставляется после узла ссылки.</span><span class="sxs-lookup"><span data-stu-id="6673b-118">Inserted after the reference node.</span></span> <span data-ttu-id="6673b-119">Например:</span><span class="sxs-lookup"><span data-stu-id="6673b-119">For example:</span></span><br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> <span data-ttu-id="6673b-120">Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.InsertAfter%2A>.</span><span class="sxs-lookup"><span data-stu-id="6673b-120">For more information, see the <xref:System.Xml.XmlNode.InsertAfter%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|<span data-ttu-id="6673b-121">Добавляет узел в конец списка дочерних узлов заданного узла.</span><span class="sxs-lookup"><span data-stu-id="6673b-121">Adds the node to the end of the list of child nodes for the given node.</span></span> <span data-ttu-id="6673b-122">Если добавляемый узел представляет собой <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в дочерний список этого узла.</span><span class="sxs-lookup"><span data-stu-id="6673b-122">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="6673b-123">Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.AppendChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="6673b-123">For more information, see the <xref:System.Xml.XmlNode.AppendChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|<span data-ttu-id="6673b-124">Добавляет узел в начало списка дочерних узлов заданного узла.</span><span class="sxs-lookup"><span data-stu-id="6673b-124">Adds the node to the beginning of the list of child nodes of the given node.</span></span> <span data-ttu-id="6673b-125">Если добавляемый узел представляет собой <xref:System.Xml.XmlDocumentFragment>, все содержимое фрагмента документа перемещается в дочерний список этого узла.</span><span class="sxs-lookup"><span data-stu-id="6673b-125">If the node being added is an <xref:System.Xml.XmlDocumentFragment>, the entire contents of the document fragment are moved into the child list of this node.</span></span> <span data-ttu-id="6673b-126">Дополнительные сведения см. в описании метода <xref:System.Xml.XmlNode.PrependChild%2A>.</span><span class="sxs-lookup"><span data-stu-id="6673b-126">For more information, see the <xref:System.Xml.XmlNode.PrependChild%2A> method.</span></span>|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|<span data-ttu-id="6673b-127">Добавляет узел <xref:System.Xml.XmlAttribute> в конец коллекции атрибутов, связанной с элементом.</span><span class="sxs-lookup"><span data-stu-id="6673b-127">Appends an <xref:System.Xml.XmlAttribute> node to the end of the attribute collection associated with an element.</span></span> <span data-ttu-id="6673b-128">Дополнительные сведения см. в описании метода <xref:System.Xml.XmlAttributeCollection.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="6673b-128">For more information, see the <xref:System.Xml.XmlAttributeCollection.Append%2A> method.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6673b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6673b-129">See Also</span></span>  
 [<span data-ttu-id="6673b-130">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="6673b-130">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
