---
title: "Встроенные в язык оси в Visual Basic (LINQ to XML) | Документы Microsoft"
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
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7ca88aed0772f4fb93ab561af4bd9a1129cbf3c5
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="c03c4-102">Загрузка встроенных в язык осей в Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c03c4-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="c03c4-103">В этом разделе описываются встроенные возможности [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] языка для упрощения доступа к XML.</span><span class="sxs-lookup"><span data-stu-id="c03c4-103">This section describes features built directly into the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="c03c4-104">Во многих примерах в документации LINQ to XML используются интегрированные оси [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c03c4-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c03c4-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="c03c4-105">In This Section</span></span>  
  
|<span data-ttu-id="c03c4-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="c03c4-106">Topic</span></span>|<span data-ttu-id="c03c4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c03c4-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c03c4-108">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="c03c4-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="c03c4-109">Предоставляет доступ к дочерним элементам одного из следующих действий: <xref:System.Xml.Linq.XElement>объекта <xref:System.Xml.Linq.XDocument>объекта, набор <xref:System.Xml.Linq.XElement>объекты или коллекции <xref:System.Xml.Linq.XDocument>объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c03c4-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="c03c4-110">Эта ось эквивалентна <xref:System.Xml.Linq.XContainer.Elements%2A>оси.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="c03c4-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="c03c4-111">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="c03c4-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="c03c4-112">Предоставляет доступ к потомкам из следующих: <xref:System.Xml.Linq.XElement>объект, <xref:System.Xml.Linq.XDocument>объект или коллекцию <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c03c4-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="c03c4-113">Эта ось эквивалентна <xref:System.Xml.Linq.XContainer.Descendants%2A>оси.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="c03c4-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="c03c4-114">Свойство оси атрибута XML</span><span class="sxs-lookup"><span data-stu-id="c03c4-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="c03c4-115">Предоставляет доступ к атрибуту объекта <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c03c4-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="c03c4-116">Эта ось примерно эквивалентна <xref:System.Xml.Linq.XElement.Attribute%2A>оси.</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="c03c4-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="c03c4-117">Эта ось отличается от <xref:System.Xml.Linq.XElement.Attribute%2A>оси не возвращается значение атрибута <xref:System.Xml.Linq.XAttribute>объекта.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="c03c4-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="c03c4-118">Свойство индексатора расширения</span><span class="sxs-lookup"><span data-stu-id="c03c4-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="c03c4-119">Обеспечивает доступ к отдельным элементам коллекции.</span><span class="sxs-lookup"><span data-stu-id="c03c4-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c03c4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c03c4-120">See Also</span></span>  
 [<span data-ttu-id="c03c4-121">Оси LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c03c4-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
