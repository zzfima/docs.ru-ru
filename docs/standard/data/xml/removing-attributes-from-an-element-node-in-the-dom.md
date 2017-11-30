---
title: "Удаление атрибутов из узла элемента в DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b4ca08d8080c2116ce05634a544c91780869b165
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a><span data-ttu-id="0d287-102">Удаление атрибутов из узла элемента в DOM</span><span class="sxs-lookup"><span data-stu-id="0d287-102">Removing Attributes from an Element Node in the DOM</span></span>
<span data-ttu-id="0d287-103">Существует много способов удаления атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0d287-103">There are many ways to remove attributes.</span></span> <span data-ttu-id="0d287-104">Один из них заключается в их удалении из коллекции атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0d287-104">One technique is to remove them from the attribute collection.</span></span> <span data-ttu-id="0d287-105">Для этого выполняются следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="0d287-105">To do this, the following steps are performed:</span></span>  
  
1.  <span data-ttu-id="0d287-106">Возвратите коллекцию атрибутов из элемента с помощью кода `XmlAttributeCollection attrs = elem.Attributes;`.</span><span class="sxs-lookup"><span data-stu-id="0d287-106">Get the attribute collection from the element using `XmlAttributeCollection attrs = elem.Attributes;`.</span></span>  
  
2.  <span data-ttu-id="0d287-107">Удалите атрибут из коллекции атрибутов, используя один из трех методов.</span><span class="sxs-lookup"><span data-stu-id="0d287-107">Remove the attribute from the attribute collection using one of three methods:</span></span>  
  
    -   <span data-ttu-id="0d287-108">Метод <xref:System.Xml.XmlAttributeCollection.Remove%2A> удаляет указанный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0d287-108">Use <xref:System.Xml.XmlAttributeCollection.Remove%2A> to remove a specific attribute.</span></span>  
  
    -   <span data-ttu-id="0d287-109">Метод <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> удаляет все атрибуты из коллекции, оставляя элемент без атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0d287-109">Use <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> to remove all attributes from the collection and leave the element with no attributes.</span></span>  
  
    -   <span data-ttu-id="0d287-110">Метод <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> удаляет атрибут из коллекции, используя его индексный номер.</span><span class="sxs-lookup"><span data-stu-id="0d287-110">Use <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> to remove an attribute from the attribute collection by using its index number.</span></span>  
  
 <span data-ttu-id="0d287-111">Следующие методы удаляют атрибуты из узла элемента.</span><span class="sxs-lookup"><span data-stu-id="0d287-111">The following methods remove attributes from the element node.</span></span>  
  
-   <span data-ttu-id="0d287-112">Метод <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> удаляет коллекцию атрибутов.</span><span class="sxs-lookup"><span data-stu-id="0d287-112">Use <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> to remove the attribute collection.</span></span>  
  
-   <span data-ttu-id="0d287-113">Метод <xref:System.Xml.XmlElement.RemoveAttribute%2A> удаляет из коллекции один атрибут по заданному имени.</span><span class="sxs-lookup"><span data-stu-id="0d287-113">Use <xref:System.Xml.XmlElement.RemoveAttribute%2A> to remove a single attribute by name from the collection.</span></span>  
  
-   <span data-ttu-id="0d287-114">Метод <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> удаляет из коллекции один атрибут по индексному номеру.</span><span class="sxs-lookup"><span data-stu-id="0d287-114">Use <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> to remove a single attribute by index number from the collection.</span></span>  
  
 <span data-ttu-id="0d287-115">Чтобы удалить атрибут, можно также вернуть элемент, вернуть атрибут из коллекции атрибутов и напрямую удалить узел атрибута.</span><span class="sxs-lookup"><span data-stu-id="0d287-115">One more alternative is to get the element, get the attribute from the attribute collection, and remove the attribute node directly.</span></span> <span data-ttu-id="0d287-116">Чтобы вернуть атрибут из коллекции атрибутов, можно использовать имя `XmlAttribute attr = attrs["attr_name"];`, индекс `XmlAttribute attr = attrs[0];` или полное имя, включая пространство имен `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span><span class="sxs-lookup"><span data-stu-id="0d287-116">To get the attribute from the attribute collection, you can use a name, `XmlAttribute attr = attrs["attr_name"];`, an index `XmlAttribute attr = attrs[0];`, or by fully qualifying the name with the namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span></span>  
  
 <span data-ttu-id="0d287-117">Независимо от способа удаления атрибута, существуют специальные ограничения на удаление атрибутов, определенные в определении DTD как атрибуты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d287-117">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the document type definition (DTD).</span></span> <span data-ttu-id="0d287-118">Атрибуты по умолчанию нельзя удалять, если не удален элемент, которому они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="0d287-118">Default attributes cannot be removed unless the element they belong to is removed.</span></span> <span data-ttu-id="0d287-119">Атрибуты по умолчанию всегда присутствуют в элементах, для которых декларированы атрибуты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d287-119">Default attributes are always present for elements that have default attributes declared.</span></span> <span data-ttu-id="0d287-120">Удаление атрибута по умолчанию из коллекции <xref:System.Xml.XmlAttributeCollection> или <xref:System.Xml.XmlElement> приводит к вставке замещающего атрибута в коллекцию <xref:System.Xml.XmlAttributeCollection> элемента и инициализации декларированного значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d287-120">Removing a default attribute from an <xref:System.Xml.XmlAttributeCollection> or from the <xref:System.Xml.XmlElement> results in a replacement attribute inserted into the <xref:System.Xml.XmlAttributeCollection> of the element, initialized to the default value that was declared.</span></span> <span data-ttu-id="0d287-121">Если существует элемент, определенный как `<book att1="1" att2="2" att3="3"></book>`, то существует элемент `book` с тремя атрибутами, объявленными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d287-121">If you have an element defined as `<book att1="1" att2="2" att3="3"></book>`, then you have a `book` element with three default attributes declared.</span></span> <span data-ttu-id="0d287-122">Реализация модели объекта документа XML (DOM) гарантирует, что, пока это `book` элемент существует, он имеет эти три атрибута по умолчанию `att1`, `att2`, и `att3`.</span><span class="sxs-lookup"><span data-stu-id="0d287-122">The XML Document Object Model (DOM) implementation guarantees that as long as this `book` element exists, it has these three default attributes of `att1`, `att2`, and `att3`.</span></span>  
  
 <span data-ttu-id="0d287-123">Если метод <xref:System.Xml.XmlAttribute> вызывается с атрибутом <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A>, он присваивает атрибуту значение String.Empty, поскольку атрибут не может существовать без значения.</span><span class="sxs-lookup"><span data-stu-id="0d287-123">When called with an <xref:System.Xml.XmlAttribute>, the <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> method sets the value of the attribute to String.Empty, as an attribute cannot exist without a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d287-124">См. также</span><span class="sxs-lookup"><span data-stu-id="0d287-124">See Also</span></span>  
 [<span data-ttu-id="0d287-125">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="0d287-125">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
