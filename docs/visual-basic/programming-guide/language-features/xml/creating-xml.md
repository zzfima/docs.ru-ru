---
title: Создание XML в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
ms.openlocfilehash: 46f9174e78cc67c1e352d02ac6b5038f5da01086
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651104"
---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="a0322-102">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0322-102">Creating XML in Visual Basic</span></span>
<span data-ttu-id="a0322-103">Visual Basic позволяет использовать *XML-литералы* непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="a0322-103">Visual Basic enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="a0322-104">Синтаксис XML представляет [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов, который напоминает синтаксис XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="a0322-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="a0322-105">Это упрощает программное создание элементов, документы и фрагменты XML, так как код имеет такую же структуру, как последний XML.</span><span class="sxs-lookup"><span data-stu-id="a0322-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0322-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a0322-106">In This Section</span></span>  
  
|<span data-ttu-id="a0322-107">Термин</span><span class="sxs-lookup"><span data-stu-id="a0322-107">Term</span></span>|<span data-ttu-id="a0322-108">Определение</span><span class="sxs-lookup"><span data-stu-id="a0322-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="a0322-109">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="a0322-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="a0322-110">Общие сведения о XML-литералы и как они связаны с [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0322-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>|  
|[<span data-ttu-id="a0322-111">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="a0322-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="a0322-112">Описание способов использования внедренных выражений в XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="a0322-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="a0322-113">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="a0322-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="a0322-114">Описывает, как создать элемент XML в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="a0322-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="a0322-115">Пробелы в XML-литералах</span><span class="sxs-lookup"><span data-stu-id="a0322-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="a0322-116">Описывает, как Visual Basic обрабатывает пробелы в XML-литералах.</span><span class="sxs-lookup"><span data-stu-id="a0322-116">Describes how Visual Basic treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="a0322-117">XML-литералы и спецификация XML 1.0</span><span class="sxs-lookup"><span data-stu-id="a0322-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="a0322-118">Описывает, как синтаксис XML-литерала в Visual Basic относится к спецификации XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="a0322-118">Describes how the XML literal syntax in Visual Basic relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="a0322-119">Практическое руководство. Внедрение выражений в XML-литералы</span><span class="sxs-lookup"><span data-stu-id="a0322-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="a0322-120">Описание способов использования внедренных выражений в XML-литералах для создания содержимого во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0322-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="a0322-121">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="a0322-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="a0322-122">Описывает правила именования элементов и атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="a0322-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0322-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a0322-123">See Also</span></span>  
 [<span data-ttu-id="a0322-124">XML</span><span class="sxs-lookup"><span data-stu-id="a0322-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
