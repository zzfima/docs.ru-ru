---
title: "&lt;permission&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "permission"
  - "<permission>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<permission> - XML-тег C#"
  - "permission - XML-тег C#"
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;permission&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Параметры  
 cref \= " `member`"  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли данный элемент кода, и переводит `member` к каноническому имени элемента в выходных данных XML. *member* должен находиться в двойных кавычках \(""\).  
  
 Дополнительные сведения о создании cref\-ссылки на универсальный тип см. в разделе [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Описание доступа к члену.  
  
## Заметки  
 Тег \<permission\> позволяет документу получил доступ к члену.  Класс <xref:System.Security.PermissionSet> позволяет задать доступ к члену.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#8](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/permission_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)