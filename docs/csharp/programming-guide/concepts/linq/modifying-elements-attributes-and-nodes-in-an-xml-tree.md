---
title: Изменение элементов, атрибутов и узлов в дереве XML3
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 68195133a944f14f83bf6a33903152393205bfce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606246"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="2e754-102">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="2e754-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="2e754-103">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2e754-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="2e754-104">Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2e754-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="2e754-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2e754-105">Method</span></span>|<span data-ttu-id="2e754-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2e754-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-107">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="2e754-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-108">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-109">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-110">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-111">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-112">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="2e754-112">Sets the value of an attribute.</span></span> <span data-ttu-id="2e754-113">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="2e754-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="2e754-114">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="2e754-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-115">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-115">Sets the value of a child element.</span></span> <span data-ttu-id="2e754-116">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="2e754-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="2e754-117">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="2e754-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-118">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="2e754-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-119">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="2e754-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="2e754-120">Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2e754-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="2e754-121">Метод</span><span class="sxs-lookup"><span data-stu-id="2e754-121">Method</span></span>|<span data-ttu-id="2e754-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2e754-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-123">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="2e754-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-124">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="2e754-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="2e754-125">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="2e754-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="2e754-126">Метод</span><span class="sxs-lookup"><span data-stu-id="2e754-126">Method</span></span>|<span data-ttu-id="2e754-127">Описание</span><span class="sxs-lookup"><span data-stu-id="2e754-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-128">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="2e754-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="2e754-129">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="2e754-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="2e754-130">Метод</span><span class="sxs-lookup"><span data-stu-id="2e754-130">Method</span></span>|<span data-ttu-id="2e754-131">Описание</span><span class="sxs-lookup"><span data-stu-id="2e754-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="2e754-132">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="2e754-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e754-133">См. также</span><span class="sxs-lookup"><span data-stu-id="2e754-133">See also</span></span>

- [<span data-ttu-id="2e754-134">Изменение деревьев XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2e754-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
