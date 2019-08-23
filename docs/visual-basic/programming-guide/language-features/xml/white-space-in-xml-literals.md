---
title: Пробелы в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: f72dcc25b158d793850069e5cc32c3a3c02fad17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939215"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="2d081-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d081-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="2d081-103">Компилятор Visual Basic включает только значащие символы пробела из XML-литерала при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.</span><span class="sxs-lookup"><span data-stu-id="2d081-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="2d081-104">Незначащие символы пробела не включаются.</span><span class="sxs-lookup"><span data-stu-id="2d081-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="2d081-105">Значительные и незначащие пробелы</span><span class="sxs-lookup"><span data-stu-id="2d081-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="2d081-106">Символы пробелов в XML-литералах являются значимыми только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="2d081-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="2d081-107">Если они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="2d081-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="2d081-108">Если они являются частью текстового содержимого элемента, а текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="2d081-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="2d081-109">Если они находятся в внедренном выражении для текстового содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="2d081-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="2d081-110">В противном случае компилятор рассматривает символы пробела как незначащие и не включает в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объект для литерала.</span><span class="sxs-lookup"><span data-stu-id="2d081-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="2d081-111">Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержащее строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="2d081-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d081-112">Если атрибут отображается в литерале XML-элемента, Visual Basic компилятор включает атрибут <xref:System.Xml.Linq.XElement> в объект, но добавление этого атрибута не влияет на то, как компилятор обрабатывает пробелы. `xml:space`</span><span class="sxs-lookup"><span data-stu-id="2d081-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2d081-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="2d081-113">Examples</span></span>  
 <span data-ttu-id="2d081-114">В следующем примере содержатся два XML-элемента: OUTER и Inner.</span><span class="sxs-lookup"><span data-stu-id="2d081-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="2d081-115">Оба элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="2d081-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="2d081-116">Пробелы во внешнем элементе являются незначащими, так как содержат только пробелы и XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="2d081-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="2d081-117">Пробел во внутреннем элементе важен, так как он содержит пробелы и текст.</span><span class="sxs-lookup"><span data-stu-id="2d081-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="2d081-118">При запуске этот код отображает следующий текст.</span><span class="sxs-lookup"><span data-stu-id="2d081-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d081-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2d081-119">See also</span></span>

- [<span data-ttu-id="2d081-120">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d081-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
