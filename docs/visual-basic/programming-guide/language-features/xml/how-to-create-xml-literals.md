---
title: Практическое руководство. Создание XML-литералов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652874"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="67599-102">Практическое руководство. Создание XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67599-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="67599-103">Можно создать документ, фрагмент или элемент XML непосредственно в коде с помощью XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="67599-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="67599-104">Примеры в этом разделе демонстрируют способ создания XML-элемента, который имеет три дочерних элемента и способ создания XML-документа.</span><span class="sxs-lookup"><span data-stu-id="67599-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="67599-105">Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="67599-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="67599-106">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="67599-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="67599-107">Чтобы создать XML-элемент</span><span class="sxs-lookup"><span data-stu-id="67599-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="67599-108">Создайте встроенный XML, используя синтаксис XML-литерала, который совпадает с фактическим синтаксисом XML.</span><span class="sxs-lookup"><span data-stu-id="67599-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="67599-109">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="67599-109">Run the code.</span></span> <span data-ttu-id="67599-110">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="67599-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="67599-111">Для создания XML-документа</span><span class="sxs-lookup"><span data-stu-id="67599-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="67599-112">Создайте встроенный XML-документ.</span><span class="sxs-lookup"><span data-stu-id="67599-112">Create the XML document inline.</span></span> <span data-ttu-id="67599-113">Следующий код создает XML-документ, который имеет синтаксис литералов, XML-декларация, инструкции по обработке, комментарий и элемент, содержащий другой элемент.</span><span class="sxs-lookup"><span data-stu-id="67599-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="67599-114">Выполните код.</span><span class="sxs-lookup"><span data-stu-id="67599-114">Run the code.</span></span> <span data-ttu-id="67599-115">Результат выполнения этого кода является:</span><span class="sxs-lookup"><span data-stu-id="67599-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="67599-116">См. также</span><span class="sxs-lookup"><span data-stu-id="67599-116">See Also</span></span>  
 [<span data-ttu-id="67599-117">XML</span><span class="sxs-lookup"><span data-stu-id="67599-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="67599-118">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="67599-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="67599-119">XML-литерал элемента</span><span class="sxs-lookup"><span data-stu-id="67599-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="67599-120">XML-литерал документа</span><span class="sxs-lookup"><span data-stu-id="67599-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
