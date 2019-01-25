---
title: Как выполнить Создание XML-литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 0e74dccac0b3528fe73d091670a3368328baeaab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560598"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="335b8-102">Как выполнить Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="335b8-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="335b8-103">XML документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="335b8-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="335b8-104">В примерах в этом разделе показано, как создать элемент XML, содержит три дочерних элемента и способ создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="335b8-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="335b8-105">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API-интерфейсы для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="335b8-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="335b8-106">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="335b8-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="335b8-107">Чтобы создать XML-элемент</span><span class="sxs-lookup"><span data-stu-id="335b8-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="335b8-108">Создайте встроенный XML, используя синтаксис XML, который является таким же, как фактический синтаксис XML.</span><span class="sxs-lookup"><span data-stu-id="335b8-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="335b8-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="335b8-109">Run the code.</span></span> <span data-ttu-id="335b8-110">Ниже приведен результат выполнения этого кода.</span><span class="sxs-lookup"><span data-stu-id="335b8-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="335b8-111">Для создания XML-документа</span><span class="sxs-lookup"><span data-stu-id="335b8-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="335b8-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="335b8-112">Create the XML document inline.</span></span> <span data-ttu-id="335b8-113">Следующий код создает XML-документ, который имеет синтаксис литерала XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="335b8-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="335b8-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="335b8-114">Run the code.</span></span> <span data-ttu-id="335b8-115">Ниже приведен результат выполнения этого кода.</span><span class="sxs-lookup"><span data-stu-id="335b8-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="335b8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="335b8-116">See also</span></span>
- [<span data-ttu-id="335b8-117">XML</span><span class="sxs-lookup"><span data-stu-id="335b8-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="335b8-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="335b8-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="335b8-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="335b8-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="335b8-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="335b8-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
