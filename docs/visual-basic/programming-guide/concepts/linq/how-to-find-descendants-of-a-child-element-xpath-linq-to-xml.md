---
title: Практическое руководство. Поиск потомков дочернего элемента (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: a958af40-f754-4409-85f9-7746978d4cb3
ms.openlocfilehash: beb949be521bfde70fbcdbcf18cebf49d7cc5a58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344674"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="3de45-102">Руководство. Поиск потомков дочернего элемента (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3de45-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="3de45-103">В этом разделе рассказывается, как возвращать элементы-потомки дочерних элементов с определенным именем.</span><span class="sxs-lookup"><span data-stu-id="3de45-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="3de45-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="3de45-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="3de45-105">Пример</span><span class="sxs-lookup"><span data-stu-id="3de45-105">Example</span></span>  
 <span data-ttu-id="3de45-106">В этом примере имитируются проблемы извлечения текста из XML-представления документа текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="3de45-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="3de45-107">В нем сначала выделяются все элементы `Paragraph`, а затем в нем выделяются все элементы-потомки `Text` каждого элемента `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="3de45-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="3de45-108">В этом примере элементы-потомки `Text` элемента `Comment` не выделяются.</span><span class="sxs-lookup"><span data-stu-id="3de45-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Paragraph>  
            <Text>This is the start of</Text>  
        </Paragraph>  
        <Comment>  
            <Text>This comment is not part of the paragraph text.</Text>  
        </Comment>  
        <Paragraph>  
            <Annotation Emphasis='true'>  
                <Text> a sentence.</Text>  
            </Annotation>  
        </Paragraph>  
        <Paragraph>  
            <Text>This is a second sentence.</Text>  
        </Paragraph>  
    </Root>  
  
' LINQ to XML query  
Dim str1 As String = _  
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _  
    Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
' XPath expression  
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _  
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _  
    .Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
If str1 = str2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(str2)  
```  
  
 <span data-ttu-id="3de45-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3de45-109">This example produces the following output:</span></span>  
  
```console  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="3de45-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3de45-110">See also</span></span>

- [<span data-ttu-id="3de45-111">LINQ to XML для пользователей XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3de45-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
