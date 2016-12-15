---
title: "XML-литералы и спецификация XML 1.0 (Visual Basic) | Microsoft Docs"
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
  - "XML-литералы [Visual Basic], XML 1.0 спецификация"
ms.assetid: 46f046e5-293c-41a3-b893-4e5f6e32e78a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML-литералы и спецификация XML 1.0 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Синтаксис XML\-литералов в [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] поддерживает большую часть спецификации XML 1.0.  Сведения о спецификации XML 1.0 содержатся на веб\-сайте W3C [Extensible Markup Language \(XML\) 1.0](http://go.microsoft.com/fwlink/?LinkId=73927).  
  
## Что не поддерживает Visual Basic  
  
-   XML\-литералы не могут содержать определение типа документа \(DTD\).  
  
-   Литерал XML\-документа должен начинаться с объявления XML\-документа.  
  
-   XML\-литералы не могут содержать более 65535 знаков в одной строке.  
  
-   Префиксы пространства имен XML, имена элементов и атрибутов не могут содержать более 1 024 символов.  
  
## Дополнительные возможности, поддерживаемые Visual Basic  
  
-   Синтаксис внедренных выражений допустим в документе, литералы элементов не являются допустимыми в XML.  
  
## См. также  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)