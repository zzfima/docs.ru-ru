---
title: Чтение и запись закодированного документа (C#)
ms.date: 07/20/2015
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
ms.openlocfilehash: fa28c26845a0c6019943e0532ea0692a6dffd5a9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347667"
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a><span data-ttu-id="0d190-102">Чтение и запись закодированного документа (C#)</span><span class="sxs-lookup"><span data-stu-id="0d190-102">How to read and write an encoded document (C#)</span></span>
<span data-ttu-id="0d190-103">Чтобы создать закодированный XML-документ, следует добавить объект <xref:System.Xml.Linq.XDeclaration> в XML-дерево, задав требуемое имя кодовой страницы для кодировки.</span><span class="sxs-lookup"><span data-stu-id="0d190-103">To create an encoded XML document, you add an <xref:System.Xml.Linq.XDeclaration> to the XML tree, setting the encoding to the desired code page name.</span></span>  
  
 <span data-ttu-id="0d190-104">Любое значение, возвращенное методом <xref:System.Text.Encoding.WebName%2A>, является допустимым.</span><span class="sxs-lookup"><span data-stu-id="0d190-104">Any value returned by <xref:System.Text.Encoding.WebName%2A> is a valid value.</span></span>  
  
 <span data-ttu-id="0d190-105">При чтении закодированного документа свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> нужно будет задать имя этой кодовой страницы.</span><span class="sxs-lookup"><span data-stu-id="0d190-105">If you read an encoded document, the <xref:System.Xml.Linq.XDeclaration.Encoding%2A> property will be set to the code page name.</span></span>  
  
 <span data-ttu-id="0d190-106">Если свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> задать допустимое имя кодовой страницы, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] выполняет сериализацию с указанной кодировкой.</span><span class="sxs-lookup"><span data-stu-id="0d190-106">If you set <xref:System.Xml.Linq.XDeclaration.Encoding%2A> to a valid code page name, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will serialize with the specified encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d190-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0d190-107">Example</span></span>  
 <span data-ttu-id="0d190-108">В следующем примере создаются два документа: один с кодировкой utf-8, а другой с кодировкой utf-16.</span><span class="sxs-lookup"><span data-stu-id="0d190-108">The following example creates two documents, one with utf-8 encoding, and one with utf-16 encoding.</span></span> <span data-ttu-id="0d190-109">Документы затем загружаются, а кодировка указывается в консоли.</span><span class="sxs-lookup"><span data-stu-id="0d190-109">It then loads the documents and prints the encoding to the console.</span></span>  
  
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
  
 <span data-ttu-id="0d190-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="0d190-110">This example produces the following output:</span></span>  
  
```output  
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
  
## <a name="see-also"></a><span data-ttu-id="0d190-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0d190-111">See also</span></span>

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
