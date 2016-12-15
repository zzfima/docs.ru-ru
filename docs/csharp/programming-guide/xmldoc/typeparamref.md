---
title: "&lt;typeparamref&gt; (Руководство по программированию на C#) | Microsoft Docs"
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
  - "typeparamref"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparamref> - XML-тег C#"
  - "typeparamref - XML-тег C#"
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;typeparamref&gt; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Синтаксис  
  
```  
<typeparamref name="name"/>  
```  
  
#### Параметры  
 `name`  
 Имя параметра типа.  Заключите имя в двойные кавычки \(" "\).  
  
## Заметки  
 Дополнительные сведения параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).  
  
 Использование этого тега позволит пользователям файла документации придать слову определенный формат, например выделить его курсивом.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)