---
title: Изменение элементов, атрибутов и узлов в XML-Tree1
ms.date: 07/20/2015
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
ms.openlocfilehash: 91a7cca2e39e5ddc62d6010fbe4efad9bd7ff3c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645217"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="987f6-102">Изменение элементов, атрибутов и узлов в дереве XML</span><span class="sxs-lookup"><span data-stu-id="987f6-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="987f6-103">В следующей таблице приведена сводка методов и свойств, используемых для изменения элемента, его дочерних элементов или его атрибутов.</span><span class="sxs-lookup"><span data-stu-id="987f6-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="987f6-104">Следующие методы используются для изменения <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="987f6-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="987f6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="987f6-105">Method</span></span>|<span data-ttu-id="987f6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="987f6-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-107">Заменяет элемент проанализированным XML.</span><span class="sxs-lookup"><span data-stu-id="987f6-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-108">Удаляет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-109">Удаляет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-110">Заменяет все содержимое (дочерние узлы и атрибуты) элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-111">Заменяет атрибуты элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-112">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="987f6-112">Sets the value of an attribute.</span></span> <span data-ttu-id="987f6-113">Создает атрибут, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="987f6-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="987f6-114">Если значение устанавливается в `null`, удаляет атрибут.</span><span class="sxs-lookup"><span data-stu-id="987f6-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-115">Задает значение дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-115">Sets the value of a child element.</span></span> <span data-ttu-id="987f6-116">Создает элемент, если он не существует.</span><span class="sxs-lookup"><span data-stu-id="987f6-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="987f6-117">Если значение устанавливается в `null`, удаляет элемент.</span><span class="sxs-lookup"><span data-stu-id="987f6-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-118">Заменяет содержимое (дочерние узлы) элемента заданным текстом.</span><span class="sxs-lookup"><span data-stu-id="987f6-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-119">Задает значение элемента.</span><span class="sxs-lookup"><span data-stu-id="987f6-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="987f6-120">Следующие методы используются для изменения <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="987f6-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="987f6-121">Метод</span><span class="sxs-lookup"><span data-stu-id="987f6-121">Method</span></span>|<span data-ttu-id="987f6-122">Описание</span><span class="sxs-lookup"><span data-stu-id="987f6-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-123">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="987f6-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-124">Устанавливает значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="987f6-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="987f6-125">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XNode> (включая <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="987f6-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="987f6-126">Метод</span><span class="sxs-lookup"><span data-stu-id="987f6-126">Method</span></span>|<span data-ttu-id="987f6-127">Описание</span><span class="sxs-lookup"><span data-stu-id="987f6-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-128">Заменяет узел новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="987f6-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="987f6-129">Следующие методы предназначены для изменения <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>).</span><span class="sxs-lookup"><span data-stu-id="987f6-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="987f6-130">Метод</span><span class="sxs-lookup"><span data-stu-id="987f6-130">Method</span></span>|<span data-ttu-id="987f6-131">Описание</span><span class="sxs-lookup"><span data-stu-id="987f6-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="987f6-132">Заменяет дочерние узлы новым содержимым.</span><span class="sxs-lookup"><span data-stu-id="987f6-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="987f6-133">См. также</span><span class="sxs-lookup"><span data-stu-id="987f6-133">See Also</span></span>  
 [<span data-ttu-id="987f6-134">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="987f6-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
