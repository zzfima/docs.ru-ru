---
title: Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ded20c173063492d260aee5ba55f3c4c585bd961
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828658"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="e82c1-102">Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e82c1-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="e82c1-103">Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.</span><span class="sxs-lookup"><span data-stu-id="e82c1-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="e82c1-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="e82c1-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="e82c1-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e82c1-105">Example</span></span>  
 <span data-ttu-id="e82c1-106">Сначала в данном примере осуществляется поиск элемента `Author`.</span><span class="sxs-lookup"><span data-stu-id="e82c1-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="e82c1-107">Затем в нем осуществляется поиск атрибута `id` родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="e82c1-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="e82c1-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e82c1-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="e82c1-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e82c1-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="e82c1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e82c1-110">See also</span></span>

- [<span data-ttu-id="e82c1-111">LINQ to XML для пользователей XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e82c1-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
