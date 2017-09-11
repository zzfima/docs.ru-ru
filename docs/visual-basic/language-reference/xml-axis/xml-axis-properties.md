---
title: "Свойства оси XML (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML axis properties [Visual Basic]
- Visual Basic code, XML
- XML axis [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 7e400e20-5d1e-4d22-a65c-9df79d5c1621
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4dd15670eed316552f2f02e4536122a6a110542d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xml-axis-properties-visual-basic"></a><span data-ttu-id="a15d0-102">Свойства оси XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a15d0-102">XML Axis Properties (Visual Basic)</span></span>
<span data-ttu-id="a15d0-103">В подразделах этого раздела документируется синтаксис свойств оси XML в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a15d0-103">The topics in this section document the syntax of XML axis properties in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="a15d0-104">Свойства оси XML упрощают доступ к XML непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="a15d0-104">The XML axis properties make it easy to access XML directly in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a15d0-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="a15d0-105">In This Section</span></span>  
  
|<span data-ttu-id="a15d0-106">Раздел</span><span class="sxs-lookup"><span data-stu-id="a15d0-106">Topic</span></span>|<span data-ttu-id="a15d0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a15d0-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a15d0-108">Свойство оси атрибута XML</span><span class="sxs-lookup"><span data-stu-id="a15d0-108">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="a15d0-109">Описание способов доступа к атрибуты <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a15d0-109">Describes how to access the attributes of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="a15d0-110">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="a15d0-110">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="a15d0-111">Описание способов доступа к потомков <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a15d0-111">Describes how to access the children of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="a15d0-112">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="a15d0-112">XML Descendant Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="a15d0-113">Описание способов доступа к потомкам из <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a15d0-113">Describes how to access the descendants of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="a15d0-114">Свойство индексатора расширения</span><span class="sxs-lookup"><span data-stu-id="a15d0-114">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="a15d0-115">Описание способов доступа к отдельным элементам в коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a15d0-115">Describes how to access individual elements in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
|[<span data-ttu-id="a15d0-116">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="a15d0-116">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)|<span data-ttu-id="a15d0-117">Описание способов доступа к значению первого элемента из коллекции <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>объектов.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a15d0-117">Describes how to access the value of the first element of a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a15d0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a15d0-118">See Also</span></span>  
 [<span data-ttu-id="a15d0-119">XML</span><span class="sxs-lookup"><span data-stu-id="a15d0-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
