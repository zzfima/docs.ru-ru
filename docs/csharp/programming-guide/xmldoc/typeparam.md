---
title: "&lt;typeparam&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeparam"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparam> - XML-тег C#"
  - "typeparam - XML-тег C#"
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &lt;typeparam&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### Параметры  
 `name`  
 Имя параметра типа.  Заключите имя в двойные кавычки \(" "\).  
  
 `description`  
 Описание параметра типа.  
  
## Заметки  
 Тег `<typeparam>` должен использоваться в комментарии объявления универсального типа или метода для описания параметра типа.  Добавьте тег для каждого параметра типа для универсального типа или метода.  
  
 Дополнительные сведения см. в разделе [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md).  
  
 Текст для тега `<typeparam>` будет отображен в IntelliSense, веб\-отчете комментариев кода [Object Browser Window](http://msdn.microsoft.com/ru-ru/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/typeparam_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)