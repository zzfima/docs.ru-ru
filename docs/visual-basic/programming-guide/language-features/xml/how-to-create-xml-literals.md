---
title: Практическое руководство. Создание XML-литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775912"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="2f1ac-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f1ac-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="2f1ac-103">XML документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="2f1ac-104">В примерах в этом разделе показано, как создать элемент XML, содержит три дочерних элемента и способ создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="2f1ac-105">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-интерфейсы для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="2f1ac-106">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="2f1ac-107">Чтобы создать XML-элемент</span><span class="sxs-lookup"><span data-stu-id="2f1ac-107">To create an XML element</span></span>  
  
- <span data-ttu-id="2f1ac-108">Создайте встроенный XML, используя синтаксис XML, который является таким же, как фактический синтаксис XML.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="2f1ac-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-109">Run the code.</span></span> <span data-ttu-id="2f1ac-110">Ниже приведен результат выполнения этого кода.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="2f1ac-111">Для создания XML-документа</span><span class="sxs-lookup"><span data-stu-id="2f1ac-111">To create an XML document</span></span>  
  
- <span data-ttu-id="2f1ac-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-112">Create the XML document inline.</span></span> <span data-ttu-id="2f1ac-113">Следующий код создает XML-документ, который имеет синтаксис литерала XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="2f1ac-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-114">Run the code.</span></span> <span data-ttu-id="2f1ac-115">Ниже приведен результат выполнения этого кода.</span><span class="sxs-lookup"><span data-stu-id="2f1ac-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="2f1ac-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2f1ac-116">See also</span></span>

- [<span data-ttu-id="2f1ac-117">XML</span><span class="sxs-lookup"><span data-stu-id="2f1ac-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="2f1ac-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f1ac-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="2f1ac-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="2f1ac-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="2f1ac-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="2f1ac-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
