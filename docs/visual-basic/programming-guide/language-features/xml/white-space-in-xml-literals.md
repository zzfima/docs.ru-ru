---
title: Пробелы в XML-литералах
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 56ededeb12d07e979bc86b03924e1ae0f0432822
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336006"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="c93a0-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c93a0-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="c93a0-103">Компилятор Visual Basic включает только значащие символы пробела из XML-литерала при создании объекта [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c93a0-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="c93a0-104">Незначащие символы пробела не включаются.</span><span class="sxs-lookup"><span data-stu-id="c93a0-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="c93a0-105">Значительные и незначащие пробелы</span><span class="sxs-lookup"><span data-stu-id="c93a0-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="c93a0-106">Символы пробелов в XML-литералах являются значимыми только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="c93a0-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="c93a0-107">Если они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="c93a0-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="c93a0-108">Если они являются частью текстового содержимого элемента, а текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="c93a0-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="c93a0-109">Если они находятся в внедренном выражении для текстового содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="c93a0-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="c93a0-110">В противном случае компилятор считает символы пробела незначащими и не включает в объект [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] для литерала.</span><span class="sxs-lookup"><span data-stu-id="c93a0-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="c93a0-111">Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержащее строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="c93a0-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c93a0-112">Если атрибут `xml:space` отображается в литерале XML-элемента, компилятор Visual Basic включает атрибут в объект <xref:System.Xml.Linq.XElement>, но добавление этого атрибута не влияет на то, как компилятор обрабатывает пробелы.</span><span class="sxs-lookup"><span data-stu-id="c93a0-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c93a0-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c93a0-113">Examples</span></span>  
 <span data-ttu-id="c93a0-114">В следующем примере содержатся два XML-элемента: OUTER и Inner.</span><span class="sxs-lookup"><span data-stu-id="c93a0-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="c93a0-115">Оба элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="c93a0-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="c93a0-116">Пробелы во внешнем элементе являются незначащими, так как содержат только пробелы и XML-элементы.</span><span class="sxs-lookup"><span data-stu-id="c93a0-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="c93a0-117">Пробел во внутреннем элементе важен, так как он содержит пробелы и текст.</span><span class="sxs-lookup"><span data-stu-id="c93a0-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="c93a0-118">При запуске этот код отображает следующий текст.</span><span class="sxs-lookup"><span data-stu-id="c93a0-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c93a0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="c93a0-119">See also</span></span>

- [<span data-ttu-id="c93a0-120">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c93a0-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
