---
title: Практическое руководство. Поиск атрибутов элементов того же уровня с определенным именем (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 788945232874ed5c1ba9a8a43c10eaf012320cbb
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141139"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="59b6c-102">Практическое руководство. Поиск атрибутов элементов того же уровня с определенным именем (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="59b6c-102">How to find attributes of siblings with a specific name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="59b6c-103">В этом разделе показано, как найти все атрибуты одноуровневых элементов контекстного узла.</span><span class="sxs-lookup"><span data-stu-id="59b6c-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="59b6c-104">В коллекции возвращаются только атрибуты с заданным именем.</span><span class="sxs-lookup"><span data-stu-id="59b6c-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="59b6c-105">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="59b6c-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="59b6c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="59b6c-106">Example</span></span>  
 <span data-ttu-id="59b6c-107">В этом примере вначале происходит поиск элемента `Book`, затем всех одноуровневых элементов с именем `Book`, а после этого всех атрибутов с именем `id`.</span><span class="sxs-lookup"><span data-stu-id="59b6c-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="59b6c-108">Результатом становится коллекция атрибутов.</span><span class="sxs-lookup"><span data-stu-id="59b6c-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="59b6c-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="59b6c-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="59b6c-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="59b6c-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  