---
title: Практическое руководство. Чтение и запись закодированного документа (C#)
ms.date: 07/20/2015
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
ms.openlocfilehash: 9fc6a7beaa4a7b9de21961e1095dd41fe2e407dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317162"
---
# <a name="how-to-read-and-write-an-encoded-document-c"></a>Практическое руководство. Чтение и запись закодированного документа (C#)
Чтобы создать закодированный XML-документ, следует добавить объект <xref:System.Xml.Linq.XDeclaration> в XML-дерево, задав требуемое имя кодовой страницы для кодировки.  
  
 Любое значение, возвращенное методом <xref:System.Text.Encoding.WebName%2A>, является допустимым.  
  
 При чтении закодированного документа свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> нужно будет задать имя этой кодовой страницы.  
  
 Если свойству <xref:System.Xml.Linq.XDeclaration.Encoding%2A> задать допустимое имя кодовой страницы, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] выполняет сериализацию с указанной кодировкой.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются два документа: один с кодировкой utf-8, а другой с кодировкой utf-16. Документы затем загружаются, а кодировка указывается в консоли.  
  
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
  
 В этом примере выводятся следующие данные:  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>  
 [Расширенные методы программирования LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
