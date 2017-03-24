---
title: "&lt;value&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<value>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<value> - XML-тег C#"
  - "value - XML-тег C#"
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;value&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<value>property-description</value>  
```  
  
#### Параметры  
 `property-description`  
 Описание свойства.  
  
## Заметки  
 Тэг \<value\> позволяет описывать представляемое свойством значение.  Обратите внимание, что при добавлении свойства посредством мастера создания кода в среде разработки Visual Studio .NET для нового свойства добавляется тег [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  Затем следует вручную добавить тег \<value\>, предназначенный для описания представляемого этим свойством значения.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)