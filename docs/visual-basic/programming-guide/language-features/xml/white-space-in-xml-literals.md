---
title: Пробелы в XML-литералах (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: ef371a984d03485ccaf1ee5d61aa3cf39d80ef32
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979064"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="79272-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79272-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="79272-103">Компилятор Visual Basic включает только символы значащих пробелов из XML-литерала, при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.</span><span class="sxs-lookup"><span data-stu-id="79272-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="79272-104">Незначащие пробелы не включены.</span><span class="sxs-lookup"><span data-stu-id="79272-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="79272-105">Значащий и незначащий пробел</span><span class="sxs-lookup"><span data-stu-id="79272-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="79272-106">Пробелы в XML-литералах значимы только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="79272-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="79272-107">Когда они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="79272-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="79272-108">Когда они являются частью содержимого текстового элемента и текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="79272-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="79272-109">Когда они находятся во внедренном выражении для текстового содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="79272-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="79272-110">В противном случае компилятор считает незначащие пробелы и не включает его в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта для литерала.</span><span class="sxs-lookup"><span data-stu-id="79272-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="79272-111">Чтобы включить незначащие пробелы в XML-литерал, используйте встроенное выражение, которое содержит строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="79272-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79272-112">Если `xml:space` атрибут содержится в литерале XML-элемента, компилятор Visual Basic включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.</span><span class="sxs-lookup"><span data-stu-id="79272-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="79272-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="79272-113">Examples</span></span>  
 <span data-ttu-id="79272-114">Следующий пример содержит два элемента XML, внешними и внутренними.</span><span class="sxs-lookup"><span data-stu-id="79272-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="79272-115">Оба этих элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="79272-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="79272-116">Пустое пространство во внешнем элементе не играет роли, так как он содержит только пробелы и XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="79272-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="79272-117">Пустое пространство во внутреннем элементе важен, так как он содержит пробел и текст.</span><span class="sxs-lookup"><span data-stu-id="79272-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="79272-118">При запуске этот код отображает следующий текст.</span><span class="sxs-lookup"><span data-stu-id="79272-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79272-119">См. также</span><span class="sxs-lookup"><span data-stu-id="79272-119">See also</span></span>
- [<span data-ttu-id="79272-120">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79272-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
