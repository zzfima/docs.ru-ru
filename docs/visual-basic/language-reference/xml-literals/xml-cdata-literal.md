---
title: "Литеральное представление XML-раздела CDATA (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlLiteralCdata"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CDATA - литерал [Visual Basic]"
  - "XML CDATA - литерал [Visual Basic]"
  - "XML-литералы [Visual Basic], CDATA"
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Литеральное представление XML-раздела CDATA (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Литеральный символ, представляющий объект <xref:System.Xml.Linq.XCData>.  
  
## Синтаксис  
  
```  
<![CDATA[content]]>  
```  
  
## Части  
 `<![CDATA[`  
 Обязательный.  Обозначает начало раздела CDATA XML.  
  
 `content`  
 Обязательный.  Текст содержимого для отображения в разделе CDATA XML.  
  
 `]]>`  
 Обязательный.  Обозначает конец раздела.  
  
## Возвращаемое значение  
 Объект <xref:System.Xml.Linq.XCData>.  
  
## Заметки  
 Разделы CDATA XML содержат необработанный текст, который должен быть включен, но не проанализирован, с помощью XML, в котором он содержится.  Раздел CDATA XML может содержать любой текст.  Он включает зарезервированные символы XML.  Раздел CDATA XML заканчивается последовательностью "\]\]\>".  Это подразумевает следующее:  
  
-   Нельзя использовать внедренные выражения в литеральном представлении XML CDATA потому, что внедренные разделители выражения являются допустимым содержимым XML CDATA.  
  
-   Разделы CDATA XML не могут быть вложенными, поскольку `content` не может содержать значение "\]\]\>".  
  
 Можно присвоить литеральное представление CDATA XML переменной, или включить его в литеральное представление XML\-элемента.  
  
> [!NOTE]
>  XML\-литерал может занимать несколько строк без использования символа продолжения строки.  Это позволяет скопировать содержимое из XML\-документа и вставить его непосредственно в программу [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] преобразует литеральное представление XML CDATA в вызов конструктора <xref:System.Xml.Linq.XCData.%23ctor%2A>.  
  
## Пример  
 В следующем примере создается раздел CDATA, содержащий текст "может содержать теги \<XML\> литерала".  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## См. также  
 <xref:System.Xml.Linq.XCData>   
 [Литеральное представление XML\-элемента](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Создание XML в Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)