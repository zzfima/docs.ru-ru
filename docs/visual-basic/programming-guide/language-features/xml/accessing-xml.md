---
title: "Доступ к XML в Visual Basic | Документы Microsoft"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
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
ms.openlocfilehash: fe096d3686adc2386235944b59b51fb7442dd096
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="48145-102">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48145-102">Accessing XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="48145-103">предоставляет свойства осей XML для доступа и перемещения по [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] структуры.</span><span class="sxs-lookup"><span data-stu-id="48145-103"> provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] structures.</span></span> <span data-ttu-id="48145-104">Эти свойства используют специальный синтаксис для доступа к элементам и атрибутам, указав имена XML.</span><span class="sxs-lookup"><span data-stu-id="48145-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="48145-105">В следующей таблице перечислены средства языка, которые позволяют получить доступ к XML-элементов и атрибутов в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="48145-105">The following table lists the language features that enable you to access XML elements and attributes in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="48145-106">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="48145-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="48145-107">Описание свойства</span><span class="sxs-lookup"><span data-stu-id="48145-107">Property description</span></span>|<span data-ttu-id="48145-108">Пример</span><span class="sxs-lookup"><span data-stu-id="48145-108">Example</span></span>|<span data-ttu-id="48145-109">Описание</span><span class="sxs-lookup"><span data-stu-id="48145-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="48145-110">*дочерняя ось*</span><span class="sxs-lookup"><span data-stu-id="48145-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="48145-111">Возвращает все `phone` элементы, которые являются дочерними элементами элемента `contact` элемент.</span><span class="sxs-lookup"><span data-stu-id="48145-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="48145-112">*ось атрибутов*</span><span class="sxs-lookup"><span data-stu-id="48145-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="48145-113">Возвращает все `type` атрибуты `phone` элемента.</span><span class="sxs-lookup"><span data-stu-id="48145-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="48145-114">*оси-потомка*</span><span class="sxs-lookup"><span data-stu-id="48145-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="48145-115">Возвращает все `name` элементы `contacts` элемент, независимо от того, насколько глубоко в иерархии.</span><span class="sxs-lookup"><span data-stu-id="48145-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="48145-116">*индексатор расширения*</span><span class="sxs-lookup"><span data-stu-id="48145-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="48145-117">Возвращает первый `name` элемент из последовательности.</span><span class="sxs-lookup"><span data-stu-id="48145-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="48145-118">*value*</span><span class="sxs-lookup"><span data-stu-id="48145-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="48145-119">Возвращает строковое представление первого объекта в последовательности, или `Nothing` , если последовательность пуста.</span><span class="sxs-lookup"><span data-stu-id="48145-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="48145-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="48145-120">In This Section</span></span>  
 [<span data-ttu-id="48145-121">Практическое руководство. Доступ к элементам-потомкам XML</span><span class="sxs-lookup"><span data-stu-id="48145-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="48145-122">Показано, как использовать свойство дочерней оси для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.</span><span class="sxs-lookup"><span data-stu-id="48145-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="48145-123">Практическое руководство. Доступ к дочерним XML-элементам</span><span class="sxs-lookup"><span data-stu-id="48145-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="48145-124">Демонстрируется использование дочернего свойства ось для доступа к все дочерние элементы XML, которые имеют указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="48145-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="48145-125">Практическое руководство. Доступ к XML-атрибутам</span><span class="sxs-lookup"><span data-stu-id="48145-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="48145-126">Показано, как использовать свойство оси атрибута для доступа ко всем атрибутам XML, которые имеют указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="48145-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="48145-127">Практическое руководство. Объявление и использование префиксов пространств имен XML</span><span class="sxs-lookup"><span data-stu-id="48145-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="48145-128">Показано, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="48145-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="48145-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="48145-129">Related Sections</span></span>  
 [<span data-ttu-id="48145-130">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="48145-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="48145-131">Ссылки на разделы, описывающие различные свойства XML доступа.</span><span class="sxs-lookup"><span data-stu-id="48145-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="48145-132">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48145-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="48145-133">Введение в использование [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48145-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="48145-134">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48145-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="48145-135">Введение в использование литералов XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48145-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="48145-136">Обработка XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48145-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="48145-137">Содержит ссылки на разделы о загрузке и изменении XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48145-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="48145-138">XML</span><span class="sxs-lookup"><span data-stu-id="48145-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="48145-139">Содержит ссылки на разделы, описывающие, как использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48145-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>
