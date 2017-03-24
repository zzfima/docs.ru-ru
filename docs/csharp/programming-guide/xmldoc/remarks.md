---
title: "&lt;remarks&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> - XML-тег C#"
  - "remarks - XML-тег C#"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;remarks&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<remarks>description</remarks>  
```  
  
#### Параметры  
 `Description`  
 Описание члена.  
  
## Заметки  
 Тег \<remarks\> используется для добавления сведений о типе, дополняющих сведения, указанные в [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  Эти сведения отображаются в [Object Browser Window](http://msdn.microsoft.com/ru-ru/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)