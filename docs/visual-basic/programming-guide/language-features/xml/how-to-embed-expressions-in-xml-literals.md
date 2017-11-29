---
title: "Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Практическое руководство. Внедрение выражений в XML-литералы (Visual Basic)
XML-литералов можно объединить с внедренными выражениями для создания XML документ, фрагмент или элемент, который содержит содержимое, созданное во время выполнения. Следующие примеры демонстрируют, как использовать внедренные выражения для заполнения содержимого элемента, атрибутов и имен элементов во время выполнения.  
  
 Для внедренного выражения используется синтаксис `<%=` `exp` `%>`, который имеет тот же синтаксис, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] использует. Дополнительные сведения см. в разделе [встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Можно также использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API для создания [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] объектов. Для получения дополнительной информации см. <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-insert-text-as-element-content"></a>Вставка текста в качестве содержимого элемента  
  
-   В следующем примере показано, как вставить текст, содержащийся в `contactName` между открывающим и закрывающим элементами имя переменной.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Вставка текста в качестве значения атрибута  
  
-   В следующем примере показано, как вставить текст, содержащийся в `phoneType` в качестве значения переменной `type` атрибута.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Вставка текста для имени элемента  
  
-   В следующем примере показано, как вставить текст, содержащийся в `elementName` переменной в качестве имени элемента.  
  
     При создании элементов с помощью данного метода, необходимо закрыть их с \</ > тег.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     В этом примере выводятся следующие данные:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание XML-литералов](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [Встроенные выражения в XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Создание XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
