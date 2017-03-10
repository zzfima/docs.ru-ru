---
title: "&lt;c&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "c"
  - "<c>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<c> - XML-тег C#"
  - "c - XML-тег C#"
  - "код, пометка текста в качестве [C#]"
  - "текст, пометка в качестве кода [C#]"
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;c&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<c>text</c>  
```  
  
#### Параметры  
 `text`  
 Текст, который нужно было бы представить как код.  
  
## Заметки  
 Тег \<c\> дает возможность указать, что текст в описании должен быть помечен как код.  Используйте [\<c\>](../../../csharp/programming-guide/xmldoc/code.md), чтобы указать несколько строк в качестве кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#2](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/code-inline_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)