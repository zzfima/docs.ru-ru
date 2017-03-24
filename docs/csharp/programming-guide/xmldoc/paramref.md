---
title: "&lt;paramref&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "paramref"
  - "<paramref>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<paramref> - XML-тег C#"
  - "paramref - XML-тег C#"
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;paramref&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<paramref name="name"/>  
```  
  
#### Параметры  
 `name`  
 Имя параметра, на который нужна ссылка.  Заключите имя в двойные кавычки \(" "\).  
  
## Заметки  
 Тег \<paramref\> позволяет указать, что слово в комментариях кода, например в блоке \<summary\> или \<remarks\>, ссылается на параметр.  Чтобы форматировать это слово некоторым конкретным образом, например выделить курсивом или жирным, может быть обработан XML\-файл.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)