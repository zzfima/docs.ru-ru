---
title: "&lt;code&gt; (Visual Basic) | Microsoft Docs"
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
  - "<code> - XML-тег"
  - "code - XML-тег"
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;code&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указывает, что текст представляет собой несколько строк кода.  
  
## Синтаксис  
  
```  
<code>content</code>  
```  
  
#### Параметры  
 `content`  
 Текст, который необходимо пометить как код.  
  
## Заметки  
 Используйте тег `<code>` для указания нескольких строк в качестве кода.  Используйте [\<c\>](../../../visual-basic/language-reference/xmldoc/c.md), чтобы указать, что текст вместе с описанием должен быть помечен как код.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере используется тег \<code\>, чтобы включить пример кода для использования поля `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)