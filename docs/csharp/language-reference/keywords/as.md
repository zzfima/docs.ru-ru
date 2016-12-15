---
title: "as (Справочник по C#) | Microsoft Docs"
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
  - "as_CSharpKeyword"
  - "as"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "as - ключевое слово [C#]"
  - "преобразование типов [С#], as - ключевое слово"
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# as (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно выполнить с помощью оператора `as` в некоторых случаях совместимость между ссылочными типами или [тип, допускающий значение NULL](../../../csharp/programming-guide/nullable-types/index.md).  В следующем коде приведен пример.  
  
 [!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]  
  
## Заметки  
 Оператор `as` подобен оператору приведения.  Однако если преобразование невозможно, то `as` возвращает `null` вместо вызова исключения.  Рассмотрим следующий пример:  
  
```  
expression as type  
```  
  
 Код эквивалентен следующему выражению, за исключением того, что переменная `expression` вычисляется только один раз.  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 Обратите внимание, что оператор `as` выполняет только преобразования ссылок, подобные преобразования и преобразования упаковка\-преобразования.  Оператор `as` не может выполнять другие преобразования, например определенное пользователем преобразование, вместо этого следует выполнять с помощью результатов выражения.  
  
## Пример  
 [!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [?Оператор :](../../../csharp/language-reference/operators/conditional-operator.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)