---
title: Удаление атрибутов из узла элемента в DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65fd6d2baae29c72241350e4568faf09b9c71f39
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594101"
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a><span data-ttu-id="505d8-102">Удаление атрибутов из узла элемента в DOM</span><span class="sxs-lookup"><span data-stu-id="505d8-102">Removing Attributes from an Element Node in the DOM</span></span>
<span data-ttu-id="505d8-103">Существует много способов удаления атрибутов.</span><span class="sxs-lookup"><span data-stu-id="505d8-103">There are many ways to remove attributes.</span></span> <span data-ttu-id="505d8-104">Один из них заключается в их удалении из коллекции атрибутов.</span><span class="sxs-lookup"><span data-stu-id="505d8-104">One technique is to remove them from the attribute collection.</span></span> <span data-ttu-id="505d8-105">Для этого выполняются следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="505d8-105">To do this, the following steps are performed:</span></span>  
  
1.  <span data-ttu-id="505d8-106">Возвратите коллекцию атрибутов из элемента с помощью кода `XmlAttributeCollection attrs = elem.Attributes;`.</span><span class="sxs-lookup"><span data-stu-id="505d8-106">Get the attribute collection from the element using `XmlAttributeCollection attrs = elem.Attributes;`.</span></span>  
  
2.  <span data-ttu-id="505d8-107">Удалите атрибут из коллекции атрибутов, используя один из трех методов.</span><span class="sxs-lookup"><span data-stu-id="505d8-107">Remove the attribute from the attribute collection using one of three methods:</span></span>  
  
    -   <span data-ttu-id="505d8-108">Метод <xref:System.Xml.XmlAttributeCollection.Remove%2A> удаляет указанный атрибут.</span><span class="sxs-lookup"><span data-stu-id="505d8-108">Use <xref:System.Xml.XmlAttributeCollection.Remove%2A> to remove a specific attribute.</span></span>  
  
    -   <span data-ttu-id="505d8-109">Метод <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> удаляет все атрибуты из коллекции, оставляя элемент без атрибутов.</span><span class="sxs-lookup"><span data-stu-id="505d8-109">Use <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> to remove all attributes from the collection and leave the element with no attributes.</span></span>  
  
    -   <span data-ttu-id="505d8-110">Метод <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> удаляет атрибут из коллекции, используя его индексный номер.</span><span class="sxs-lookup"><span data-stu-id="505d8-110">Use <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> to remove an attribute from the attribute collection by using its index number.</span></span>  
  
 <span data-ttu-id="505d8-111">Следующие методы удаляют атрибуты из узла элемента.</span><span class="sxs-lookup"><span data-stu-id="505d8-111">The following methods remove attributes from the element node.</span></span>  
  
-   <span data-ttu-id="505d8-112">Метод <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> удаляет коллекцию атрибутов.</span><span class="sxs-lookup"><span data-stu-id="505d8-112">Use <xref:System.Xml.XmlElement.RemoveAllAttributes%2A> to remove the attribute collection.</span></span>  
  
-   <span data-ttu-id="505d8-113">Метод <xref:System.Xml.XmlElement.RemoveAttribute%2A> удаляет из коллекции один атрибут по заданному имени.</span><span class="sxs-lookup"><span data-stu-id="505d8-113">Use <xref:System.Xml.XmlElement.RemoveAttribute%2A> to remove a single attribute by name from the collection.</span></span>  
  
-   <span data-ttu-id="505d8-114">Метод <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> удаляет из коллекции один атрибут по индексному номеру.</span><span class="sxs-lookup"><span data-stu-id="505d8-114">Use <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> to remove a single attribute by index number from the collection.</span></span>  
  
 <span data-ttu-id="505d8-115">Чтобы удалить атрибут, можно также вернуть элемент, вернуть атрибут из коллекции атрибутов и напрямую удалить узел атрибута.</span><span class="sxs-lookup"><span data-stu-id="505d8-115">One more alternative is to get the element, get the attribute from the attribute collection, and remove the attribute node directly.</span></span> <span data-ttu-id="505d8-116">Чтобы вернуть атрибут из коллекции атрибутов, можно использовать имя `XmlAttribute attr = attrs["attr_name"];`, индекс `XmlAttribute attr = attrs[0];` или полное имя, включая пространство имен `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span><span class="sxs-lookup"><span data-stu-id="505d8-116">To get the attribute from the attribute collection, you can use a name, `XmlAttribute attr = attrs["attr_name"];`, an index `XmlAttribute attr = attrs[0];`, or by fully qualifying the name with the namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]`.</span></span>  
  
 <span data-ttu-id="505d8-117">Независимо от способа удаления атрибута, существуют специальные ограничения на удаление атрибутов, определенные в определении DTD как атрибуты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="505d8-117">Regardless of the method used to remove attributes, there are special limitations on removing attributes that are defined as default attributes in the document type definition (DTD).</span></span> <span data-ttu-id="505d8-118">Атрибуты по умолчанию нельзя удалять, если не удален элемент, которому они принадлежат.</span><span class="sxs-lookup"><span data-stu-id="505d8-118">Default attributes cannot be removed unless the element they belong to is removed.</span></span> <span data-ttu-id="505d8-119">Атрибуты по умолчанию всегда присутствуют в элементах, для которых декларированы атрибуты по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="505d8-119">Default attributes are always present for elements that have default attributes declared.</span></span> <span data-ttu-id="505d8-120">Удаление атрибута по умолчанию из коллекции <xref:System.Xml.XmlAttributeCollection> или <xref:System.Xml.XmlElement> приводит к вставке замещающего атрибута в коллекцию <xref:System.Xml.XmlAttributeCollection> элемента и инициализации декларированного значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="505d8-120">Removing a default attribute from an <xref:System.Xml.XmlAttributeCollection> or from the <xref:System.Xml.XmlElement> results in a replacement attribute inserted into the <xref:System.Xml.XmlAttributeCollection> of the element, initialized to the default value that was declared.</span></span> <span data-ttu-id="505d8-121">Если существует элемент, определенный как `<book att1="1" att2="2" att3="3"></book>`, то существует элемент `book` с тремя атрибутами, объявленными по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="505d8-121">If you have an element defined as `<book att1="1" att2="2" att3="3"></book>`, then you have a `book` element with three default attributes declared.</span></span> <span data-ttu-id="505d8-122">Реализация модели XML DOM гарантирует, что, пока существует элемент `book`, он имеет три атрибута по умолчанию: `att1`, `att2` и `att3`.</span><span class="sxs-lookup"><span data-stu-id="505d8-122">The XML Document Object Model (DOM) implementation guarantees that as long as this `book` element exists, it has these three default attributes of `att1`, `att2`, and `att3`.</span></span>  
  
 <span data-ttu-id="505d8-123">Если метод <xref:System.Xml.XmlAttribute> вызывается с атрибутом <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A>, он присваивает атрибуту значение String.Empty, поскольку атрибут не может существовать без значения.</span><span class="sxs-lookup"><span data-stu-id="505d8-123">When called with an <xref:System.Xml.XmlAttribute>, the <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> method sets the value of the attribute to String.Empty, as an attribute cannot exist without a value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505d8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="505d8-124">See also</span></span>

- [<span data-ttu-id="505d8-125">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="505d8-125">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
