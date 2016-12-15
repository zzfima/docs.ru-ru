---
title: "&lt;exception&gt; (Visual Basic) | Microsoft Docs"
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
  - "<exception> - XML-тег"
  - "exception - XML-тег"
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;exception&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает, какие исключения могут возникнуть.  
  
## Синтаксис  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Параметры  
 `member`  
 Ссылка на исключение, которое доступно из текущей среды компиляции.  Компилятор проверяет, существует ли исключение и приводит `member` к каноническому имени элемента в выходных XML\-данных.  `member` необходимо заключать в двойные кавычки \(" "\).  
  
 `description`  
 Описание  
  
## Заметки  
 Тег `<exception>` служит для указания возможных исключений.  Этот тег применяется к определению метода.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере используется тег `<exception>` для описания исключения, которое может создавать функция `IntDivide`.  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)