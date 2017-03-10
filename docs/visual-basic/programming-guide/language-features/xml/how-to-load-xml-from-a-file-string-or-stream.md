---
title: "Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], загрузка XML из файлов"
  - "XML [Visual Basic], загрузка"
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Можно создать [XML\-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым внешнего источника, например файла, строки или потока, с помощью нескольких методов.  Эти методы представлены в следующих примерах.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Загрузка XML\-кода из файла  
  
-   Чтобы заполнить XML\-литерал, например объект <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> из файла, используйте метод `Load`.  Этот метод может принимать в качестве входных данных путь к файлу, текстовый поток или XML\-поток.  
  
     В следующем примере показано использование метода <xref:System.Xml.Linq.XDocument.Load%28System.String%29> для заполнения объекта <xref:System.Xml.Linq.XDocument> XML\-кодом из текстового файла.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_1.vb)]  
  
### Загрузка XML\-кода из строки  
  
-   Чтобы заполнить из строки XML\-литерал, например объект <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>, можно использовать метод `Parse`.  
  
     В следующем примере показано использование метода <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName> для заполнения объекта <xref:System.Xml.Linq.XDocument> XML\-кодом из строки.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_2.vb)]  
  
### Загрузка XML\-кода из потока  
  
-   Чтобы заполнить из потока XML\-литерал, например объект <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument>, можно использовать метод `Load` или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>.  
  
 В следующем примере показано использование метода <xref:System.Xml.Linq.XNode.ReadFrom%2A> для заполнения объекта <xref:System.Xml.Linq.XDocument> XML\-кодом из потока.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_3.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML\-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)