---
title: Создание XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 1c720bc2aca4cec3dd10656d924cf2413fc18a2d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351739"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="f830d-102">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f830d-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="f830d-103">Visual Basic позволяет использовать *XML-литералы* непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="f830d-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="f830d-104">Синтаксис XML-литерала представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекты и аналогичен синтаксису XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="f830d-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="f830d-105">Это упрощает создание XML-элементов, документов и фрагментов программным способом, так как код имеет ту же структуру, что и окончательный XML.</span><span class="sxs-lookup"><span data-stu-id="f830d-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f830d-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f830d-106">In This Section</span></span>  
  
|<span data-ttu-id="f830d-107">Термин</span><span class="sxs-lookup"><span data-stu-id="f830d-107">Term</span></span>|<span data-ttu-id="f830d-108">Определение</span><span class="sxs-lookup"><span data-stu-id="f830d-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="f830d-109">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="f830d-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="f830d-110">Знакомство с XML-литералами и их связь с [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f830d-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="f830d-111">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="f830d-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="f830d-112">Описывает использование внедренных выражений в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="f830d-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="f830d-113">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="f830d-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="f830d-114">Описывает создание XML-элемента в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="f830d-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="f830d-115">Пробелы в XML-литералах</span><span class="sxs-lookup"><span data-stu-id="f830d-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="f830d-116">Описывает, как Visual Basic обрабатывает пробелы в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="f830d-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="f830d-117">XML-литералы и спецификация XML 1.0</span><span class="sxs-lookup"><span data-stu-id="f830d-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="f830d-118">Описывает, как синтаксис XML-литерала в Visual Basic относится к спецификации XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="f830d-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="f830d-119">Практическое руководство. Внедрение выражений в XML-литералы</span><span class="sxs-lookup"><span data-stu-id="f830d-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="f830d-120">Описывает использование внедренных выражений в XML-литералах для создания содержимого во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f830d-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="f830d-121">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="f830d-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="f830d-122">Описывает правила именования XML-элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f830d-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f830d-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="f830d-123">See also</span></span>

- [<span data-ttu-id="f830d-124">XML</span><span class="sxs-lookup"><span data-stu-id="f830d-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
