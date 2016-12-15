---
title: "&lt;para&gt; (Руководство по программированию на C#) | Microsoft Docs"
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
  - "<para>"
  - "para"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<para> - XML-тег C#"
  - "para - XML-тег C#"
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;para&gt; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Синтаксис  
  
```  
<para>content</para>  
```  
  
#### Параметры  
 `content`  
 Текст абзаца.  
  
## Заметки  
 Тег \<para\> используется внутри таких тегов, как [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md), [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md) или [\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md), и позволяет структурировать текст.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 Пример использования элемента \<para\> см. в разделе [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)