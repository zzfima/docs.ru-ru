---
title: "Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eeb1bea8c82eaff904ec1076e92609cd16024d28
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="7e34c-102">Практическое руководство. Поиск атрибута родительского элемента (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7e34c-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="7e34c-103">Данный раздел показывает способ перехода к родительскому элементу и нахождения его атрибута.</span><span class="sxs-lookup"><span data-stu-id="7e34c-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="7e34c-104">Выражение XPath:</span><span class="sxs-lookup"><span data-stu-id="7e34c-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="7e34c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="7e34c-105">Example</span></span>  
 <span data-ttu-id="7e34c-106">Сначала в данном примере осуществляется поиск элемента `Author`.</span><span class="sxs-lookup"><span data-stu-id="7e34c-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="7e34c-107">Затем в нем осуществляется поиск атрибута `id` родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="7e34c-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="7e34c-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7e34c-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="7e34c-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="7e34c-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e34c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7e34c-110">See Also</span></span>  
 [<span data-ttu-id="7e34c-111">LINQ to XML для пользователей XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="7e34c-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
