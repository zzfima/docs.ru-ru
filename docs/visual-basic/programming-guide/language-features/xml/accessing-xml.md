---
title: Доступ к XML в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
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
ms.openlocfilehash: 064e4b224d37172b8f79e57c73164b90186ef922
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="a32f5-102">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a32f5-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="a32f5-103">Visual Basic предоставляет свойства оси XML для доступа и перемещения по [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] структуры.</span><span class="sxs-lookup"><span data-stu-id="a32f5-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="a32f5-104">Эти свойства используют специальный синтаксис для доступа к элементам и атрибутам, указав имена XML.</span><span class="sxs-lookup"><span data-stu-id="a32f5-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="a32f5-105">В следующей таблице перечислены возможности языка, которые позволяют получить доступ к XML-элементы и атрибуты в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a32f5-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="a32f5-106">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="a32f5-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="a32f5-107">Описание свойства</span><span class="sxs-lookup"><span data-stu-id="a32f5-107">Property description</span></span>|<span data-ttu-id="a32f5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a32f5-108">Example</span></span>|<span data-ttu-id="a32f5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a32f5-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="a32f5-110">*дочерняя ось*</span><span class="sxs-lookup"><span data-stu-id="a32f5-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="a32f5-111">Возвращает все `phone` элементы, которые являются дочерними элементами `contact` элемента.</span><span class="sxs-lookup"><span data-stu-id="a32f5-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="a32f5-112">*ось атрибутов*</span><span class="sxs-lookup"><span data-stu-id="a32f5-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="a32f5-113">Возвращает все `type` атрибуты `phone` элемента.</span><span class="sxs-lookup"><span data-stu-id="a32f5-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="a32f5-114">*оси-потомка*</span><span class="sxs-lookup"><span data-stu-id="a32f5-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="a32f5-115">Возвращает все `name` элементы `contacts` элемент, независимо от того, насколько глубоко в иерархии.</span><span class="sxs-lookup"><span data-stu-id="a32f5-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="a32f5-116">*индексатор расширения*</span><span class="sxs-lookup"><span data-stu-id="a32f5-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="a32f5-117">Возвращает первый `name` элемента последовательности.</span><span class="sxs-lookup"><span data-stu-id="a32f5-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="a32f5-118">*значение*</span><span class="sxs-lookup"><span data-stu-id="a32f5-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="a32f5-119">Возвращает строковое представление первого объекта в последовательности, или `Nothing` Если последовательность пуста.</span><span class="sxs-lookup"><span data-stu-id="a32f5-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a32f5-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a32f5-120">In This Section</span></span>  
 [<span data-ttu-id="a32f5-121">Практическое руководство. Доступ к элементам-потомкам XML</span><span class="sxs-lookup"><span data-stu-id="a32f5-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="a32f5-122">Показано, как использовать свойство дочерней оси для доступа ко всем элементам XML, которые имеют указанное имя и расположены под указанным элементом XML.</span><span class="sxs-lookup"><span data-stu-id="a32f5-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="a32f5-123">Практическое руководство. Доступ к дочерним XML-элементам</span><span class="sxs-lookup"><span data-stu-id="a32f5-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="a32f5-124">Демонстрируется использование дочернего свойства оси для доступа к все дочерние элементы XML, которые имеют указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="a32f5-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="a32f5-125">Практическое руководство. Доступ к XML-атрибутам</span><span class="sxs-lookup"><span data-stu-id="a32f5-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="a32f5-126">Показано, как использовать свойство оси атрибута для доступа ко всем атрибутам XML, которые имеют указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="a32f5-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="a32f5-127">Практическое руководство. Объявление и использование префиксов пространств имен XML</span><span class="sxs-lookup"><span data-stu-id="a32f5-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="a32f5-128">Показано, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементов.</span><span class="sxs-lookup"><span data-stu-id="a32f5-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a32f5-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a32f5-129">Related Sections</span></span>  
 [<span data-ttu-id="a32f5-130">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="a32f5-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="a32f5-131">Ссылки на разделы, описывающие различные свойства XML доступа.</span><span class="sxs-lookup"><span data-stu-id="a32f5-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="a32f5-132">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a32f5-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="a32f5-133">Предоставляет сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a32f5-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a32f5-134">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a32f5-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="a32f5-135">Предоставляет сведения об использовании XML-литералов в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a32f5-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a32f5-136">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a32f5-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="a32f5-137">Ссылки на разделы о загрузке и изменении XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a32f5-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a32f5-138">XML</span><span class="sxs-lookup"><span data-stu-id="a32f5-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="a32f5-139">Содержит ссылки на разделы, в которых описываются способы использования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a32f5-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
