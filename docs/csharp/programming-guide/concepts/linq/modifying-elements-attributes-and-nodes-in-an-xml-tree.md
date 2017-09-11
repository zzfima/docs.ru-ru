---
title: "Изменение элементов, атрибутов и узлов в дереве XML3"
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
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 432587324fbd3560da924c7516a743e623a38b1e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="69b12-102">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="69b12-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="69b12-103">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="69b12-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="69b12-104">Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="69b12-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="69b12-105">Метод</span><span class="sxs-lookup"><span data-stu-id="69b12-105">Method</span></span>|<span data-ttu-id="69b12-106">Описание</span><span class="sxs-lookup"><span data-stu-id="69b12-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>|<span data-ttu-id="69b12-107">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="69b12-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|<span data-ttu-id="69b12-108">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|<span data-ttu-id="69b12-109">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName>|<span data-ttu-id="69b12-110">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName>|<span data-ttu-id="69b12-111">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|<span data-ttu-id="69b12-112">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="69b12-112">Sets the value of an attribute.</span></span> <span data-ttu-id="69b12-113">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="69b12-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="69b12-114">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="69b12-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|<span data-ttu-id="69b12-115">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-115">Sets the value of a child element.</span></span> <span data-ttu-id="69b12-116">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="69b12-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="69b12-117">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="69b12-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>|<span data-ttu-id="69b12-118">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="69b12-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName>|<span data-ttu-id="69b12-119">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="69b12-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="69b12-120">Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="69b12-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="69b12-121">Метод</span><span class="sxs-lookup"><span data-stu-id="69b12-121">Method</span></span>|<span data-ttu-id="69b12-122">Описание</span><span class="sxs-lookup"><span data-stu-id="69b12-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>|<span data-ttu-id="69b12-123">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="69b12-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName>|<span data-ttu-id="69b12-124">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="69b12-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="69b12-125">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="69b12-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="69b12-126">Метод</span><span class="sxs-lookup"><span data-stu-id="69b12-126">Method</span></span>|<span data-ttu-id="69b12-127">Описание</span><span class="sxs-lookup"><span data-stu-id="69b12-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName>|<span data-ttu-id="69b12-128">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="69b12-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="69b12-129">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="69b12-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="69b12-130">Метод</span><span class="sxs-lookup"><span data-stu-id="69b12-130">Method</span></span>|<span data-ttu-id="69b12-131">Описание</span><span class="sxs-lookup"><span data-stu-id="69b12-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName>|<span data-ttu-id="69b12-132">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="69b12-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69b12-133">См. также</span><span class="sxs-lookup"><span data-stu-id="69b12-133">See Also</span></span>  
 [<span data-ttu-id="69b12-134">Изменение деревьев XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="69b12-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

