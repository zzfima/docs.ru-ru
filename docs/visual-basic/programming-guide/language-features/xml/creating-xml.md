---
title: "Создание XML в Visual Basic | Документы Microsoft"
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
- XML [Visual Basic], creating
- LINQ to XML [Visual Basic], creating XML
- XML literals [Visual Basic], creating
ms.assetid: 8ae29ec5-e5fb-4137-9df5-60a288df7045
caps.latest.revision: 24
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
ms.openlocfilehash: ec45ab4dc7d4c9282d444c00b0b262b3d8dd4da1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-in-visual-basic"></a><span data-ttu-id="8ca49-102">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ca49-102">Creating XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8ca49-103">позволяет использовать *XML-литералы* непосредственно в коде.</span><span class="sxs-lookup"><span data-stu-id="8ca49-103"> enables you to use *XML literals* directly in your code.</span></span> <span data-ttu-id="8ca49-104">Синтаксис литерала XML представляет [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекты и напоминает синтаксис XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="8ca49-104">The XML literal syntax represents [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects, and it is similar to the XML 1.0 syntax.</span></span> <span data-ttu-id="8ca49-105">Это упрощает программное создание элементов, документов и фрагментов XML, так как ваш код имеет такую же структуру, как окончательный XML.</span><span class="sxs-lookup"><span data-stu-id="8ca49-105">This makes it easier to create XML elements, documents, and fragments programmatically because your code has the same structure as the final XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ca49-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="8ca49-106">In This Section</span></span>  
  
|<span data-ttu-id="8ca49-107">Термин</span><span class="sxs-lookup"><span data-stu-id="8ca49-107">Term</span></span>|<span data-ttu-id="8ca49-108">Определение</span><span class="sxs-lookup"><span data-stu-id="8ca49-108">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="8ca49-109">Общие сведения об XML-литералах</span><span class="sxs-lookup"><span data-stu-id="8ca49-109">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)|<span data-ttu-id="8ca49-110">Введение в XML-литералы и как они связаны с [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ca49-110">Introduction to XML literals and how they relate to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>|  
|[<span data-ttu-id="8ca49-111">Встроенные выражения в XML</span><span class="sxs-lookup"><span data-stu-id="8ca49-111">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)|<span data-ttu-id="8ca49-112">Описание способов использования внедренных выражений в XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="8ca49-112">Describes how to use embedded expressions in XML literals.</span></span>|  
|[<span data-ttu-id="8ca49-113">Практическое руководство. Создание XML-литералов</span><span class="sxs-lookup"><span data-stu-id="8ca49-113">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)|<span data-ttu-id="8ca49-114">Описывает, как создать XML-элемента в коде с помощью XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="8ca49-114">Describes how to create an XML element in code by using an XML literal.</span></span>|  
|[<span data-ttu-id="8ca49-115">Пробелы в XML-литералах</span><span class="sxs-lookup"><span data-stu-id="8ca49-115">White Space in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/white-space-in-xml-literals.md)|<span data-ttu-id="8ca49-116">Описывает способ [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обрабатывает пробелы в XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="8ca49-116">Describes how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] treats white space in XML literals.</span></span>|  
|[<span data-ttu-id="8ca49-117">XML-литералы и спецификация XML 1.0</span><span class="sxs-lookup"><span data-stu-id="8ca49-117">XML Literals and the XML 1.0 Specification</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)|<span data-ttu-id="8ca49-118">Описывает как синтаксис XML-литерала в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] относится к спецификации XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="8ca49-118">Describes how the XML literal syntax in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] relates to the XML 1.0 specification.</span></span>|  
|[<span data-ttu-id="8ca49-119">Практическое руководство. Внедрение выражений в XML-литералы</span><span class="sxs-lookup"><span data-stu-id="8ca49-119">How to: Embed Expressions in XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-embed-expressions-in-xml-literals.md)|<span data-ttu-id="8ca49-120">Описание способов использования внедренных выражений в XML-литералах для создания содержимого во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ca49-120">Describes how to use embedded expressions in XML literals to create content at run time.</span></span>|  
|[<span data-ttu-id="8ca49-121">Имена объявленных элементов и атрибутов XML</span><span class="sxs-lookup"><span data-stu-id="8ca49-121">Names of Declared XML Elements and Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)|<span data-ttu-id="8ca49-122">Описывает правила именования элементов и атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="8ca49-122">Describes guidelines for naming XML elements and attributes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ca49-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8ca49-123">See Also</span></span>  
 [<span data-ttu-id="8ca49-124">XML</span><span class="sxs-lookup"><span data-stu-id="8ca49-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
