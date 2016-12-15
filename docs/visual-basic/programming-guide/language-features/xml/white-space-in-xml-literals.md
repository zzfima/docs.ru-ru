---
title: "Пробелы в XML-литералах (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "пробел [XML в Visual Basic]"
  - "XML-литералы [Visual Basic], пробел"
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пробелы в XML-литералах (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] включает только значащие символы пробелов из исходного XML\-литерала при создании объекта [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Незначащие пробелы не включены.  
  
## Значащие и незначащие пробелы  
 Символы пробела в XML\-литерале являются значащими только в трех областях:  
  
-   Когда они находятся в значении атрибута.  
  
-   Когда они являются частью текста содержимого элемента, и текст также содержит другие символы.  
  
-   Когда они находятся во встроенном выражении для содержания текстового элемента.  
  
 В противном случае компилятор рассматривает символ пробела как незначащий и не включает его в объект [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] для литерала.  
  
 Чтобы включить незначащий пробельный символ в литерал XML, используйте встроенное выражение, которое содержит строковый литерал с пробелом.  
  
> [!NOTE]
>  Если в литерале XML\-элемента используется атрибут `xml:space`, то компилятор [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] включает атрибут в объект <xref:System.Xml.Linq.XElement>, но добавление этого атрибута не изменяет способ обработки пробелов компилятором.  
  
## Примеры  
 В следующем примере содержатся два элемента XML, внешний и внутренний.  Оба этих элемента содержат пробелы в текстовом содержимом.  Пробелы во внешнем элементе незначащие, поскольку он содержит только пробелы и XML\-элемент.  Пробелы во внутреннем элементе являются значащими, поскольку в нем содержатся и пробелы, и текст.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 При запуске этот код отображает следующий текст.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)