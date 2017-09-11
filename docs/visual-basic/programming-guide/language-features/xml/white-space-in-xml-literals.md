---
title: "Пробелы в XML-литералах (Visual Basic) | Документы Microsoft"
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: 4fc3d30a9c71cbd732597c5e3f32bd01eb489a80
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="c368e-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c368e-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="c368e-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор включает только значащие символы пробелов из XML-литерала при создании [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта.</span><span class="sxs-lookup"><span data-stu-id="c368e-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object.</span></span> <span data-ttu-id="c368e-104">Незначащие пробелы не включены.</span><span class="sxs-lookup"><span data-stu-id="c368e-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="c368e-105">Значащие и незначащие пробелы</span><span class="sxs-lookup"><span data-stu-id="c368e-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="c368e-106">Пробелы в XML-литералах учитываются только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="c368e-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="c368e-107">Когда они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="c368e-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="c368e-108">Когда они являются частью текста содержимого элемента и текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="c368e-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="c368e-109">Когда они находятся во встроенном выражении текстовое содержимое элемента.</span><span class="sxs-lookup"><span data-stu-id="c368e-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="c368e-110">В противном случае, компилятор считает незначащие пробельные символы и не включает его в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] объекта для литерала.</span><span class="sxs-lookup"><span data-stu-id="c368e-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="c368e-111">Чтобы включить незначащие пробелы в XML-литерал, используйте встроенное выражение, которое содержит строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="c368e-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c368e-112">Если `xml:space` атрибут отображается в XML-литерал, элемент [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор включает атрибут в <xref:System.Xml.Linq.XElement>объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c368e-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c368e-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="c368e-113">Examples</span></span>  
 <span data-ttu-id="c368e-114">Следующий пример содержит два элемента XML, внешний и внутренний.</span><span class="sxs-lookup"><span data-stu-id="c368e-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="c368e-115">Оба этих элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="c368e-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="c368e-116">Пробелы во внешнем элементе незначительна, так как он содержит только пробелы и XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="c368e-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="c368e-117">Пробелы в внутреннего элемента имеет значение, поскольку он содержит пробелы и текст.</span><span class="sxs-lookup"><span data-stu-id="c368e-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 <span data-ttu-id="c368e-118">[!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c368e-118">[!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span></span>  
  
 <span data-ttu-id="c368e-119">При выполнении этот код выводит следующий текст.</span><span class="sxs-lookup"><span data-stu-id="c368e-119">When run, this code displays the following text.</span></span>  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c368e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c368e-120">See Also</span></span>  
 [<span data-ttu-id="c368e-121">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c368e-121">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
