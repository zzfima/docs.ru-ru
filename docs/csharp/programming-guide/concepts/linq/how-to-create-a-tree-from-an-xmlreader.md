---
title: Практическое руководство. Создание дерева из XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: a0cff596e0a6d50aefab3645a99beec3277d05ec
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418314"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="b24bf-102">Практическое руководство. Создание дерева из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="b24bf-102">How to: Create a Tree from an XmlReader (C#)</span></span>
<span data-ttu-id="b24bf-103">В этом разделе рассказывается, как создать XML-дерево непосредственно из <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b24bf-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="b24bf-104">Чтобы создать <xref:System.Xml.Linq.XElement> на основе <xref:System.Xml.XmlReader>, необходимо указать для модуля <xref:System.Xml.XmlReader> узел элемента.</span><span class="sxs-lookup"><span data-stu-id="b24bf-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="b24bf-105">Модуль <xref:System.Xml.XmlReader> пропускает комментарии и инструкции по обработке, но если для <xref:System.Xml.XmlReader> будет указан текстовый узел, то выдается ошибка.</span><span class="sxs-lookup"><span data-stu-id="b24bf-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="b24bf-106">Чтобы избежать подобных ошибок, всегда задавайте для <xref:System.Xml.XmlReader> элемент, прежде чем приступать к созданию XML-дерева на основе <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b24bf-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b24bf-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b24bf-107">Example</span></span>  
 <span data-ttu-id="b24bf-108">В этом примере используется следующий XML-документ: [Пример XML-файла. Книги (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b24bf-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b24bf-109">Следующий код создает объект `T:System.Xml.XmlReader`, а затем читает узлы, пока не найдет узел первого элемента.</span><span class="sxs-lookup"><span data-stu-id="b24bf-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="b24bf-110">Затем он загружает объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b24bf-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="b24bf-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b24bf-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b24bf-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b24bf-112">See also</span></span>

- [<span data-ttu-id="b24bf-113">Анализ XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b24bf-113">Parsing XML (C#)</span></span>](how-to-parse-a-string.md)
