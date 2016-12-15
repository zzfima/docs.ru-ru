---
title: "Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic) | Microsoft Docs"
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
  - "встроенные выражения [Visual Basic]"
  - "XML-литералы [Visual Basic], встроенные выражения"
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Можно объединять XML\-литералы с внедренными выражениями для создания XML\-документа, фрагмента или элемента, содержащего содержимое созданное во время выполнения.  Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имен элементов во время выполнения.  
  
 Синтаксис внедренного выражения — `<%=` `exp` `%>`. Он совпадает с синтаксисом, используемым [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]. Дополнительные сведения см. в разделе [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Для создания объектов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно также использовать интерфейс API [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XElement>.  
  
## Процедуры  
  
#### Вставка текста в качестве содержимого элемента  
  
-   Ниже приведен пример того, как вставить текст, содержащийся в переменной `contactName` между открывающими и закрывающими элементами имени.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     В этом примере получается следующий результат:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### Вставка текста в качестве значения атрибута  
  
-   Ниже приведен пример того, как вставить текст, содержащийся в переменной `phoneType` в качестве значения атрибута `type`.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     В этом примере получается следующий результат:  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### Вставка текста для имени элемента  
  
-   Ниже приведен пример того, как вставить текст, содержащийся в переменной `elementName` в качестве имени элемента.  
  
     При создании элементов с помощью этого приема, необходимо завершить их с помощью тега \<\/\>.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     В этом примере получается следующий результат:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## См. также  
 [Практическое руководство. Создание XML\-литералов](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)