---
title: "Изменение элементов, атрибутов и узлов в XML Tree1 | Документы Microsoft"
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
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88531f2af88074f4406c4859354860829efda69f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="fa741-102">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="fa741-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="fa741-103">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="fa741-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="fa741-104">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="fa741-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="fa741-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fa741-105">Method</span></span>|<span data-ttu-id="fa741-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fa741-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fa741-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-108">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="fa741-108">Replaces an element with parsed XML.</span></span>|  
|<span data-ttu-id="fa741-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-110">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-110">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="fa741-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-112">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-112">Removes the attributes of an element.</span></span>|  
|<span data-ttu-id="fa741-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-114">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-114">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="fa741-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-116">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-116">Replaces the attributes of an element.</span></span>|  
|<span data-ttu-id="fa741-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-118">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="fa741-118">Sets the value of an attribute.</span></span> <span data-ttu-id="fa741-119">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="fa741-119">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="fa741-120">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="fa741-120">If the value is set to `null`, removes the attribute.</span></span>|  
|<span data-ttu-id="fa741-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-122">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-122">Sets the value of a child element.</span></span> <span data-ttu-id="fa741-123">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="fa741-123">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="fa741-124">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="fa741-124">If the value is set to `null`, removes the element.</span></span>|  
|<span data-ttu-id="fa741-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-126">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="fa741-126">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<span data-ttu-id="fa741-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-128">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="fa741-128">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="fa741-129">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="fa741-129">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="fa741-130">Метод</span><span class="sxs-lookup"><span data-stu-id="fa741-130">Method</span></span>|<span data-ttu-id="fa741-131">Описание</span><span class="sxs-lookup"><span data-stu-id="fa741-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fa741-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-133">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="fa741-133">Sets the value of an attribute.</span></span>|  
|<span data-ttu-id="fa741-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-135">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="fa741-135">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="fa741-136">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode>(включая <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="fa741-136">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="fa741-137">Метод</span><span class="sxs-lookup"><span data-stu-id="fa741-137">Method</span></span>|<span data-ttu-id="fa741-138">Описание</span><span class="sxs-lookup"><span data-stu-id="fa741-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fa741-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-140">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="fa741-140">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="fa741-141">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer>( <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>).</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="fa741-141">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="fa741-142">Метод</span><span class="sxs-lookup"><span data-stu-id="fa741-142">Method</span></span>|<span data-ttu-id="fa741-143">Описание</span><span class="sxs-lookup"><span data-stu-id="fa741-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fa741-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fa741-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="fa741-145">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="fa741-145">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa741-146">См. также</span><span class="sxs-lookup"><span data-stu-id="fa741-146">See Also</span></span>  
 [<span data-ttu-id="fa741-147">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa741-147">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
