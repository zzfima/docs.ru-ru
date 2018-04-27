---
title: Пробелы в XML-литералах (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6d23aa54b150748aac9aa955f4bd86ee88358ea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="dca37-102">Пробелы в XML-литералах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dca37-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="dca37-103">Компилятор Visual Basic включает только значимые пробелы символы из XML-литерала при создании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта.</span><span class="sxs-lookup"><span data-stu-id="dca37-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="dca37-104">Незначащие пробелы не включены.</span><span class="sxs-lookup"><span data-stu-id="dca37-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="dca37-105">Значащие и незначащие пробелы</span><span class="sxs-lookup"><span data-stu-id="dca37-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="dca37-106">Пробелы в XML-литералах значимыми являются только в трех областях:</span><span class="sxs-lookup"><span data-stu-id="dca37-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="dca37-107">Когда они находятся в значении атрибута.</span><span class="sxs-lookup"><span data-stu-id="dca37-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="dca37-108">Если они являются частью текстового содержимого элемента и текст также содержит другие символы.</span><span class="sxs-lookup"><span data-stu-id="dca37-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="dca37-109">Когда они находятся во внедренном выражении для текстового содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="dca37-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="dca37-110">В противном случае компилятор считает незначащие пробельные символы и не включает его в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объекта для литерала.</span><span class="sxs-lookup"><span data-stu-id="dca37-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="dca37-111">Чтобы включить незначащие пробелы в XML-литерал, используйте внедренное выражение, содержит строковый литерал с пробелом.</span><span class="sxs-lookup"><span data-stu-id="dca37-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dca37-112">Если `xml:space` атрибут отображается в литерале XML-элемента, компилятор Visual Basic включает атрибут в <xref:System.Xml.Linq.XElement> объект, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.</span><span class="sxs-lookup"><span data-stu-id="dca37-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="dca37-113">Примеры</span><span class="sxs-lookup"><span data-stu-id="dca37-113">Examples</span></span>  
 <span data-ttu-id="dca37-114">Следующий пример содержит два элемента XML, внешнее и внутреннее.</span><span class="sxs-lookup"><span data-stu-id="dca37-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="dca37-115">Оба этих элемента содержат пробелы в текстовом содержимом.</span><span class="sxs-lookup"><span data-stu-id="dca37-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="dca37-116">Свободное пространство на внешний элемент не важна, так как он содержит только пробелы и XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="dca37-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="dca37-117">Пробелы в внутреннего элемента имеет значение, поскольку он содержит пробелы и текст.</span><span class="sxs-lookup"><span data-stu-id="dca37-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="dca37-118">При выполнении этот код выводит следующий текст.</span><span class="sxs-lookup"><span data-stu-id="dca37-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dca37-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dca37-119">See Also</span></span>  
 [<span data-ttu-id="dca37-120">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dca37-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
