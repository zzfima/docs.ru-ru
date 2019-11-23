---
title: Практическое руководство. Поиск одноуровневых узлов (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
ms.openlocfilehash: 52151c939bbf67df37a9535b1081ff902d357123
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344630"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="9e868-102">How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e868-102">How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="9e868-103">Допустим, что требуется найти все одноуровневые элементы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="9e868-103">You might want to find all siblings of a node that have a specific name.</span></span> <span data-ttu-id="9e868-104">Полученная в результате коллекция может содержать контекстный узел, если этот контекстный узел также имеет указанное имя.</span><span class="sxs-lookup"><span data-stu-id="9e868-104">The resulting collection might include the context node if the context node also has the specific name.</span></span>

<span data-ttu-id="9e868-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="9e868-105">The XPath expression is:</span></span>

`../Book`

## <a name="example"></a><span data-ttu-id="9e868-106">Пример</span><span class="sxs-lookup"><span data-stu-id="9e868-106">Example</span></span>

<span data-ttu-id="9e868-107">В этом примере вначале осуществляется поиск элемента `Book`, а затем всех одноуровневых элементов с именем `Book`.</span><span class="sxs-lookup"><span data-stu-id="9e868-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`.</span></span> <span data-ttu-id="9e868-108">Полученная в результате коллекция содержит контекстный узел.</span><span class="sxs-lookup"><span data-stu-id="9e868-108">The resulting collection includes the context node.</span></span>

<span data-ttu-id="9e868-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9e868-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>

```vb
Dim books As XDocument = XDocument.Load("Books.xml")
Dim book As XElement = books.Root.<Book>.Skip(1).First()

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = book.Parent.<Book>

' XPath expression
Dim list2 As IEnumerable(Of XElement) = book.XPathSelectElements("../Book")

If list1.Count() = list2.Count() And _
        list1.Intersect(list2).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="9e868-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="9e868-110">This example produces the following output:</span></span>

```console
Results are identical
<Book id="bk101">
  <Author>Garghentini, Davide</Author>
  <Title>XML Developer's Guide</Title>
  <Genre>Computer</Genre>
  <Price>44.95</Price>
  <PublishDate>2000-10-01</PublishDate>
  <Description>An in-depth look at creating applications
      with XML.</Description>
</Book>
<Book id="bk102">
  <Author>Garcia, Debra</Author>
  <Title>Midnight Rain</Title>
  <Genre>Fantasy</Genre>
  <Price>5.95</Price>
  <PublishDate>2000-12-16</PublishDate>
  <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>
</Book>
```

## <a name="see-also"></a><span data-ttu-id="9e868-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9e868-111">See also</span></span>

- [<span data-ttu-id="9e868-112">LINQ to XML for XPath Users (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e868-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
