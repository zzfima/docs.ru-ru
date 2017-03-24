---
title: "Практическое руководство: чтение и запись закодированного документа (Visual Basic) | Документы Microsoft"
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
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3247af177066e9b50d5028766f99e7bf6589050f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a>Практическое руководство: чтение и запись закодированного документа (Visual Basic)
Чтобы создать закодированный XML-документа, добавьте <xref:System.Xml.Linq.XDeclaration>XML-дерево, задав для требуемое имя кодовой страницы кодировки.</xref:System.Xml.Linq.XDeclaration>  
  
 Любое значение, возвращаемое <xref:System.Text.Encoding.WebName%2A>является допустимым значением.</xref:System.Text.Encoding.WebName%2A>  
  
 Если вы читаете кодированный документ, <xref:System.Xml.Linq.XDeclaration.Encoding%2A>свойству будет присвоено имя кодовой страницы.</xref:System.Xml.Linq.XDeclaration.Encoding%2A>  
  
 Если задать <xref:System.Xml.Linq.XDeclaration.Encoding%2A>для имени страницы кода, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] будет сериализовать с заданной кодировкой.</xref:System.Xml.Linq.XDeclaration.Encoding%2A>  
  
## <a name="example"></a>Пример  
 В следующем примере создаются два документа: один с кодировкой utf-8, а другой с кодировкой utf-16. Документы затем загружаются, а кодировка указывается в консоли.  
  
```vb  
Console.WriteLine("Creating a document with utf-8 encoding")  
Dim encodedDoc8 As XDocument = _  
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>  
        <Root>Content</Root>   
  
encodedDoc8.Save("EncodedUtf8.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Console.WriteLine("Creating a document with utf-16 encoding")  
Dim encodedDoc16 As XDocument = _  
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>  
        <Root>Content</Root>  
  
encodedDoc16.Save("EncodedUtf16.xml")  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)  
Console.WriteLine()  
  
Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")  
Console.WriteLine("Encoded document:")  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))  
Console.WriteLine()  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)  
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
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName></xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName>   
 [Дополнительно программированию LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
