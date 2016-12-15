---
title: "&lt;example&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<example>"
  - "example"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<example> - XML-тег C#"
  - "example - XML-тег C#"
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;example&gt; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Синтаксис  
  
```  
<example>description</example>  
```  
  
#### Параметры  
 `description`  
 Описание примера кода.  
  
## Заметки  
 Тег \<example\> позволяет указывать пример того, как использовать метод или другой элемент библиотеки.  Это обычно включает в себя использование тега [\<code\>](../../../csharp/programming-guide/xmldoc/code.md).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/example_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)