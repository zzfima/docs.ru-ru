---
title: Доступ к XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 1fa1d94fc710272ac0ba9ea7167989da42a51fcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351751"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="96396-102">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96396-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="96396-103">Visual Basic предоставляет свойства осей XML для доступа и навигации по структурам [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96396-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="96396-104">Эти свойства используют специальный синтаксис, позволяющий получить доступ к элементам и атрибутам, указав имена XML.</span><span class="sxs-lookup"><span data-stu-id="96396-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="96396-105">В следующей таблице перечислены функции языка, позволяющие получать доступ к XML-элементам и атрибутам в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96396-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="96396-106">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="96396-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="96396-107">Описание свойства</span><span class="sxs-lookup"><span data-stu-id="96396-107">Property description</span></span>|<span data-ttu-id="96396-108">Пример</span><span class="sxs-lookup"><span data-stu-id="96396-108">Example</span></span>|<span data-ttu-id="96396-109">Описание</span><span class="sxs-lookup"><span data-stu-id="96396-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="96396-110">*дочерняя ось*</span><span class="sxs-lookup"><span data-stu-id="96396-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="96396-111">Возвращает все элементы `phone`, являющиеся дочерними элементами элемента `contact`.</span><span class="sxs-lookup"><span data-stu-id="96396-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="96396-112">*ось атрибутов*</span><span class="sxs-lookup"><span data-stu-id="96396-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="96396-113">Возвращает все атрибуты `type` элемента `phone`.</span><span class="sxs-lookup"><span data-stu-id="96396-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="96396-114">*ось потомков*</span><span class="sxs-lookup"><span data-stu-id="96396-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="96396-115">Возвращает все элементы `name` элемента `contacts`, независимо от того, насколько глубоко они находятся в иерархии.</span><span class="sxs-lookup"><span data-stu-id="96396-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="96396-116">*индексатор расширения*</span><span class="sxs-lookup"><span data-stu-id="96396-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="96396-117">Возвращает первый элемент `name` из последовательности.</span><span class="sxs-lookup"><span data-stu-id="96396-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="96396-118">*значение*</span><span class="sxs-lookup"><span data-stu-id="96396-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="96396-119">Возвращает строковое представление первого объекта в последовательности или `Nothing`, если последовательность пуста.</span><span class="sxs-lookup"><span data-stu-id="96396-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="96396-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="96396-120">In This Section</span></span>  
 [<span data-ttu-id="96396-121">Практическое руководство. Доступ к элементам-потомкам XML</span><span class="sxs-lookup"><span data-stu-id="96396-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="96396-122">Показывает, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в указанном XML-элементе.</span><span class="sxs-lookup"><span data-stu-id="96396-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="96396-123">Практическое руководство. Доступ к дочерним XML-элементам</span><span class="sxs-lookup"><span data-stu-id="96396-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="96396-124">Показывает, как использовать свойство дочерней оси для доступа ко всем дочерним элементам XML с указанным именем в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="96396-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="96396-125">Практическое руководство. Доступ к XML-атрибутам</span><span class="sxs-lookup"><span data-stu-id="96396-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="96396-126">Показывает, как использовать свойство оси атрибута для доступа ко всем XML-атрибутам, имеющим указанное имя в элементе XML.</span><span class="sxs-lookup"><span data-stu-id="96396-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="96396-127">Практическое руководство. Объявление и использование префиксов пространств имен XML</span><span class="sxs-lookup"><span data-stu-id="96396-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="96396-128">Показывает, как объявить префикс пространства имен XML и использовать его для создания и доступа к XML-элементам.</span><span class="sxs-lookup"><span data-stu-id="96396-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96396-129">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="96396-129">Related Sections</span></span>  
 [<span data-ttu-id="96396-130">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="96396-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="96396-131">Содержит ссылки на разделы, описывающие различные свойства доступа к XML.</span><span class="sxs-lookup"><span data-stu-id="96396-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="96396-132">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96396-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="96396-133">Общие сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96396-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="96396-134">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96396-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="96396-135">Общие сведения об использовании литералов XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96396-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="96396-136">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96396-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="96396-137">Содержит ссылки на разделы, посвященные загрузке и изменению XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96396-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="96396-138">XML</span><span class="sxs-lookup"><span data-stu-id="96396-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="96396-139">Содержит ссылки на разделы, описывающие использование [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96396-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
