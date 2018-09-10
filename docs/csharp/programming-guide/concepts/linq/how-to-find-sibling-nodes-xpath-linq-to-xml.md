---
title: Практическое руководство. Поиск одноуровневых узлов (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e2c73d10-a8ca-4e11-b5aa-d055de285874
ms.openlocfilehash: e10b23c311e4e7debf228c01c898f3582e2ac8d4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43865362"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-c"></a><span data-ttu-id="415da-102">Практическое руководство. Поиск одноуровневых узлов (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="415da-102">How to: Find Sibling Nodes (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="415da-103">Допустим, что требуется найти все одноуровневые элементы с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="415da-103">You might want to find all siblings of a node that have a specific name.</span></span> <span data-ttu-id="415da-104">Полученная в результате коллекция может содержать контекстный узел, если этот контекстный узел также имеет указанное имя.</span><span class="sxs-lookup"><span data-stu-id="415da-104">The resulting collection might include the context node if the context node also has the specific name.</span></span>  
  
 <span data-ttu-id="415da-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="415da-105">The XPath expression is:</span></span>  
  
 `../Book`  
  
## <a name="example"></a><span data-ttu-id="415da-106">Пример</span><span class="sxs-lookup"><span data-stu-id="415da-106">Example</span></span>  
 <span data-ttu-id="415da-107">В этом примере вначале осуществляется поиск элемента `Book`, а затем всех одноуровневых элементов с именем `Book`.</span><span class="sxs-lookup"><span data-stu-id="415da-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`.</span></span> <span data-ttu-id="415da-108">Полученная в результате коллекция содержит контекстный узел.</span><span class="sxs-lookup"><span data-stu-id="415da-108">The resulting collection includes the context node.</span></span>  
  
 <span data-ttu-id="415da-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="415da-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Elements("Book")  
    .Skip(1)  
    .First();  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    book  
    .Parent  
    .Elements("Book");  
  
// XPath expression  
IEnumerable<XElement> list2 = book.XPathSelectElements("../Book");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="415da-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="415da-110">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="415da-111">См. также</span><span class="sxs-lookup"><span data-stu-id="415da-111">See Also</span></span>

- [<span data-ttu-id="415da-112">LINQ to XML для пользователей XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="415da-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
