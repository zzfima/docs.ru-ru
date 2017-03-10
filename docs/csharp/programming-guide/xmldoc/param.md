---
title: "&lt;param&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "param"
  - "<param>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<param> - XML-тег C#"
  - "param - XML-тег C#"
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;param&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<param name="name">description</param>  
```  
  
#### Параметры  
 `name`  
 Имя параметра метода.  Заключите имя в двойные кавычки \(" "\).  
  
 `description`  
 Описание для параметра.  
  
## Заметки  
 Тег \<param\> должен использоваться в комментариях объявления метода для описания его параметров.  Чтобы документировать несколько параметров, используйте несколько тегов\<param\>.  
  
 Текст для тега \<param\> будет отображен в IntelliSense, в обозревателе объектов и в веб\-отчете комментариев кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/param_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)