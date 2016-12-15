---
title: "Практическое руководство. Создание XML-литералов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "XML-литералы [Visual Basic], создание"
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Создание XML-литералов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

XML\-документ, фрагмент или элемент можно создать непосредственно в коде с помощью XML\-литералов.  В этом разделе в примерах демонстрируются способы создания XML\-элемента, который имеет три дочерних элемента, а также рассматривается создание XML\-документа.  
  
 Для создания объектов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно также использовать интерфейс API [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
### Создание XML\-элемента  
  
-   Создайте встроенный XML с помощью синтаксиса XML\-литералов, который совпадает с фактическим синтаксисом XML.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     Запустите код.  Результаты выполнения данного кода следующие.  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### Создание XML\-документа  
  
-   Создайте встроенный XML\-документ.  В следующем коде создается XML\-документ, который имеет синтаксис литералов, содержит XML\-объявление, инструкцию по обработке, комментарий и элемент, содержащий другой элемент.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     Запустите код.  Результаты выполнения данного кода следующие.  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works.  -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## См. также  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML\-литерал документа](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)