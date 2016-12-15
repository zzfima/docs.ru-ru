---
title: "&lt;exception&gt; (Руководство по программированию на C#) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<exception> - XML-тег C#"
  - "exception - XML-тег C#"
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;exception&gt; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Синтаксис  
  
```  
<exception cref="member">description</exception>  
```  
  
#### Параметры  
 cref \= " `member`"  
 Ссылка на исключение, которое доступно из текущей среды компиляции.  Компилятор проверяет, существует ли исключение и приводит `member` к каноническому имени элемента в выходных XML\-данных.  `member` необходимо заключать в двойные кавычки \(" "\).  
  
 Дополнительные сведения о создании cref\-ссылки на универсальный тип см. в разделе [\<see\>](../../../csharp/programming-guide/xmldoc/see.md).  
  
 `description`  
 Описание исключения.  
  
## Заметки  
 Тег \<exception\> служит для указания возможных исключений.  Этот тег может применяться к определениям методов, свойств, событий и индексаторов.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
 Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../../../csharp/programming-guide/exceptions/exceptions-and-exception-handling.md).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)