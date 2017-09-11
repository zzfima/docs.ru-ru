---
title: "Практическое руководство: Создание XML-литералов (Visual Basic) | Документы Microsoft"
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
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 3a7b5dc692317067290b48222ba056d765a449f3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="cbc17-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc17-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="cbc17-103">XML документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="cbc17-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="cbc17-104">Примеры в этом разделе показано, как создать XML-элемент, который имеет три дочерних элементов и создание XML-документа.</span><span class="sxs-lookup"><span data-stu-id="cbc17-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="cbc17-105">Можно также использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API для создания [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="cbc17-105">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="cbc17-106">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="cbc17-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="cbc17-107">Чтобы создать XML-элемент</span><span class="sxs-lookup"><span data-stu-id="cbc17-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="cbc17-108">Создайте встроенный XML, используя синтаксис XML, который совпадает с фактическим синтаксисом XML.</span><span class="sxs-lookup"><span data-stu-id="cbc17-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     <span data-ttu-id="cbc17-109">[!code-vb[VbXMLSamples&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cbc17-109">[!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="cbc17-110">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="cbc17-110">Run the code.</span></span> <span data-ttu-id="cbc17-111">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="cbc17-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="cbc17-112">Для создания XML-документа</span><span class="sxs-lookup"><span data-stu-id="cbc17-112">To create an XML document</span></span>  
  
-   <span data-ttu-id="cbc17-113">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="cbc17-113">Create the XML document inline.</span></span> <span data-ttu-id="cbc17-114">Следующий код создает XML-документ, который имеет синтаксис литералов, XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="cbc17-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     <span data-ttu-id="cbc17-115">[!code-vb[VbXMLSamples&#30;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cbc17-115">[!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="cbc17-116">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="cbc17-116">Run the code.</span></span> <span data-ttu-id="cbc17-117">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="cbc17-117">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="cbc17-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc17-118">See Also</span></span>  
 <span data-ttu-id="cbc17-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="cbc17-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="cbc17-120"> [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="cbc17-120"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="cbc17-121"> [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="cbc17-121"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="cbc17-122"> [XML-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span><span class="sxs-lookup"><span data-stu-id="cbc17-122"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span></span>
