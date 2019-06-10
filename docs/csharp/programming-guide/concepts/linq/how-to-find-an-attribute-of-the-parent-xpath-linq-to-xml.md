---
title: Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: f30c810483d8253132b9fe3e0959d04a8b4d26a0
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690062"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="5b717-102">Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5b717-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="5b717-103">Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.</span><span class="sxs-lookup"><span data-stu-id="5b717-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="5b717-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="5b717-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="5b717-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5b717-105">Example</span></span>

<span data-ttu-id="5b717-106">Сначала в данном примере осуществляется поиск элемента `Author`.</span><span class="sxs-lookup"><span data-stu-id="5b717-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="5b717-107">Затем в нем осуществляется поиск атрибута `id` родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="5b717-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="5b717-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5b717-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="5b717-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5b717-109">This example produces the following output:</span></span>

```
Results are identical
id="bk101"
```
