---
title: "XML-литерал комментариев (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "литералы комментариев [Visual Basic]"
  - "XML-литералы комментариев [Visual Basic]"
  - "XML-комментарии, добавление [Visual Basic]"
  - "XML-литералы [Visual Basic], комментарий"
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML-литерал комментариев (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Литеральный символ, представляющий объект <xref:System.Xml.Linq.XComment>.  
  
## Синтаксис  
  
```  
<!-- content -->  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`<!--`|Обязательный.  Обозначает начало комментария XML.|  
|`content`|Обязательный.  Текст, который отображается в комментарии XML.  Не может содержать ряд двух дефисов \(\-\-\) или заканчиваться дефисом рядом с закрывающим тегом.|  
|`-->`|Обязательный.  Обозначает конец комментария XML.|  
  
## Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XComment>.  
  
## Заметки  
 XML\-литералы комментариев не включают в себя содержимое документа; а содержат сведения о документе.  Раздел комментария XML заканчивается последовательностью "\-\-\>".  Это подразумевает следующее:  
  
-   Нельзя использовать внедренное выражение в литерале комментария XML, поскольку разделители внедренного выражения являются допустимым содержимым комментария XML.  
  
-   Разделы комментария XML не могут быть вложенными, поскольку `content` не может содержать значение "\-\-\>".  
  
 Можно присвоить XML\-литерал комментария переменной и включить его в XML\-литерал элемента.  
  
> [!NOTE]
>  XML\-литерал может занимать несколько строк без использования символа продолжения строки.  Эта особенность позволяет копировать содержимое из XML\-документа и вставлять его непосредственно в программу [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует XML\-литерал комментария в вызов конструктора <xref:System.Xml.Linq.XComment.%23ctor%2A>.  
  
## Пример  
 В следующем примере создается XML\-комментарий, содержащий текст "This is a comment".  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XComment>   
 [Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)