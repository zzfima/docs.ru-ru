---
title: "Практическое руководство. Создание XML-литералов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce1bf763529b436158c2d74811c4938182166f92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="3587c-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3587c-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="3587c-103">Можно создать документ, фрагмент или элемент XML непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="3587c-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="3587c-104">Примеры в этом разделе демонстрируют способ создания XML-элемента, который имеет три дочерних элемента и способ создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="3587c-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="3587c-105">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="3587c-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="3587c-106">Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="3587c-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="3587c-107">Чтобы создать XML-элемент</span><span class="sxs-lookup"><span data-stu-id="3587c-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="3587c-108">Создайте встроенный XML, используя синтаксис XML-литерала, который совпадает с фактическим синтаксисом XML.</span><span class="sxs-lookup"><span data-stu-id="3587c-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="3587c-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="3587c-109">Run the code.</span></span> <span data-ttu-id="3587c-110">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="3587c-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="3587c-111">Для создания XML-документа</span><span class="sxs-lookup"><span data-stu-id="3587c-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="3587c-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="3587c-112">Create the XML document inline.</span></span> <span data-ttu-id="3587c-113">Следующий код создает XML-документ, который имеет синтаксис литералов, XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="3587c-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="3587c-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="3587c-114">Run the code.</span></span> <span data-ttu-id="3587c-115">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="3587c-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="3587c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3587c-116">See Also</span></span>  
 [<span data-ttu-id="3587c-117">XML</span><span class="sxs-lookup"><span data-stu-id="3587c-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="3587c-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3587c-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="3587c-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="3587c-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="3587c-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="3587c-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
