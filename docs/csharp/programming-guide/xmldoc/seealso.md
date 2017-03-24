---
title: "&lt;seealso&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cref"
  - "<seealso>"
  - "seealso"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<seealso> - XML-тег C#"
  - "cref [C#]"
  - "cref [C#], см. также"
  - "перекрестные ссылки [C#], теги"
  - "seealso - XML-тег C#"
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;seealso&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<seealso cref="member"/>  
```  
  
#### Параметры  
 cref \= " `member`"  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли данный элемент кода, и передает значение `member` имени элемента в выходных данных XML. Элемент `member` должен быть в двойных кавычках \(" "\).  
  
 Дополнительные сведения о создании cref\-ссылки на универсальный тип см. в разделе [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
## Заметки  
 Тег \<seealso\> позволяет указать текст, который будет отображаться в разделе "См. также".  Используйте элемент [\<see\>](../../../csharp/programming-guide/xmldoc/see.md), чтобы указать ссылку в тексте.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 Пример использования элемента \<seealso\> см. в разделе [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md).  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)