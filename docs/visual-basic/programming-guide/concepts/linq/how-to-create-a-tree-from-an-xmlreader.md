---
title: "Практическое руководство: Создание дерева из XmlReader (Visual Basic) | Документы Microsoft"
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
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
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
ms.openlocfilehash: a60b5cb3557016bba7bae9be6e0b9c9a448c1284
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="0182d-102">Практическое руководство: Создание дерева из XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0182d-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="0182d-103">В этом разделе показано, как создать XML-дерево непосредственно из <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0182d-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="0182d-104">Для создания <xref:System.Xml.Linq.XElement>из <xref:System.Xml.XmlReader>, необходимо разместить <xref:System.Xml.XmlReader>на узле элемента.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0182d-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="0182d-105"><xref:System.Xml.XmlReader>Пропускает комментарии и инструкции по обработке, но если <xref:System.Xml.XmlReader>располагается на текстовый узел, возникнет ошибка.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0182d-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="0182d-106">Чтобы избежать подобных ошибок, всегда задавайте <xref:System.Xml.XmlReader>элемент, прежде чем создавать XML-дерева из <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="0182d-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0182d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0182d-107">Example</span></span>  
 <span data-ttu-id="0182d-108">В этом примере используется следующий XML-документ: [пример XML-файла: книги (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0182d-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="0182d-109">Следующий код создает объект `T:System.Xml.XmlReader`, а затем читает узлы, пока не найдет узел первого элемента.</span><span class="sxs-lookup"><span data-stu-id="0182d-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="0182d-110">Затем он загружает <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0182d-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="0182d-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="0182d-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0182d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0182d-112">See Also</span></span>  
 [<span data-ttu-id="0182d-113">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0182d-113">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
