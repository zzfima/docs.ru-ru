---
title: "Практическое руководство. Чтение и запись закодированного документа (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fc7c21c1aa6f4035bfaee509c7bc542542635313
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-and-write-an-encoded-document-c"></a><span data-ttu-id="4f1a2-102">Практическое руководство. Чтение и запись закодированного документа (C#)</span><span class="sxs-lookup"><span data-stu-id="4f1a2-102">How to: Read and Write an Encoded Document (C#)</span></span>
<span data-ttu-id="4f1a2-103">Чтобы создать закодированный XML-документ, следует добавить объект <xref:System.Xml.Linq.XDeclaration> в XML-дерево, задав требуемое имя кодовой страницы для кодировки.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="4f1a2-104">Любое значение, возвращенное методом <xref:System.Text.Encoding.WebName%2A>, является допустимым.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="4f1a2-105">При чтении закодированного документа свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> нужно будет задать имя этой кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="4f1a2-106">Если свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> задать допустимое имя кодовой страницы, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] выполняет сериализацию с указанной кодировкой.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f1a2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="4f1a2-107">Example</span></span>  
 <span data-ttu-id="4f1a2-108">В следующем примере создаются два документа: один с кодировкой utf-8, а другой с кодировкой utf-16.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="4f1a2-109">Документы затем загружаются, а кодировка указывается в консоли.</span><span class="sxs-lookup"><span data-stu-id="4f1a2-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 <span data-ttu-id="4f1a2-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="4f1a2-110">This example produces the following output:</span></span>  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f1a2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4f1a2-111">See Also</span></span>  
 <span data-ttu-id="4f1a2-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4f1a2-112"><xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></span></span>   
 [<span data-ttu-id="4f1a2-113">Расширенные методы программирования LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4f1a2-113">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

