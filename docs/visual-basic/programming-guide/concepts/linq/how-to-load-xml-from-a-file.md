---
title: "Практическое руководство: загрузка XML из файла (Visual Basic) | Документы Microsoft"
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
ms.assetid: e2d337ad-8ac8-4671-b694-30e5ca1413b7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0b336816a7a557a4cd820b31f64ee42a791f3649
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-xml-from-a-file-visual-basic"></a><span data-ttu-id="18947-102">Практическое руководство: загрузка XML из файла (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18947-102">How to: Load XML from a File (Visual Basic)</span></span>
<span data-ttu-id="18947-103">В этом разделе показано, как загрузить XML из URI с помощью <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>метод.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="18947-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18947-104">Пример</span><span class="sxs-lookup"><span data-stu-id="18947-104">Example</span></span>  
 <span data-ttu-id="18947-105">В следующем примере показана загрузка XML-документа из файла.</span><span class="sxs-lookup"><span data-stu-id="18947-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="18947-106">В следующем примере загружается файл books.xml и происходит вывод XML-дерева на консоль.</span><span class="sxs-lookup"><span data-stu-id="18947-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="18947-107">В этом примере используется следующий XML-документ: [пример XML-файла: книги (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18947-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim booksFromFile As XElement = XElement.Load("books.xml")  
Console.WriteLine(booksFromFile)  
```  
  
 <span data-ttu-id="18947-108">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="18947-108">This code produces the following output:</span></span>  
  
```xml  
<Catalog>  
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
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18947-109">См. также</span><span class="sxs-lookup"><span data-stu-id="18947-109">See Also</span></span>  
 [<span data-ttu-id="18947-110">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18947-110">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
