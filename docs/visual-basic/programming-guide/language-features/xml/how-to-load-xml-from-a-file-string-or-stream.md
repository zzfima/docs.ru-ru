---
title: "Практическое руководство: загрузка XML из файла, строки или потока (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 242c8b79cbe1329b6f53e9fd4e5495d4a157e08c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Практическое руководство. Загрузка XML-кода из файла, строки или потока (Visual Basic)
Можно создать [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md) и заполнить их содержимым из внешнего источника, например файла, строки или потока с помощью нескольких методов. Эти методы представлены в следующих примерах.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Загрузка XML из файла  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из файла, используйте `Load` метод.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Этот метод можно использовать в качестве входа путь к файлу, текстовый поток или XML-потока.  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Load%28System.String%29>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из текстового файла.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%28System.String%29>  
  
     [!code-vb[VbXMLSamples&#43;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>Загрузка XML из строки  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из строки, можно использовать `Parse` метода.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
     В следующем примере кода показано использование <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из строки.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName>  
  
     [!code-vb[VbXMLSamples&#47;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>Загрузка XML-кода из потока  
  
-   Для заполнения XML-литерал, например <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта из потока, можно использовать `Load` метода или <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>метод.</xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement>  
  
 В следующем примере кода показано использование <xref:System.Xml.Linq.XNode.ReadFrom%2A>способ заполнения <xref:System.Xml.Linq.XDocument>объектов с XML из XML-потока.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 [!code-vb[VbXMLSamples&#46;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML-литералы](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)

