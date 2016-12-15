---
title: "Оператор () (Справочник по C#) | Microsoft Docs"
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
  - "()_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "() - оператор [C#]"
  - "cast - оператор [C#]"
  - "преобразование типов [С#], () - оператор"
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор () (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Круглые скобки используются для указания порядка выполнения операций в выражении, а также для выполнения следующих задач:  
  
1.  Определение операций приведения или преобразования типов.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Вызов методов или делегатов.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## Заметки  
 Операция приведения явно вызывает оператор преобразования одного типа в другой. Если такой оператор преобразования не определен, операция приведения возвращает ошибку.  Информацию об определении оператора преобразования см. в разделах, посвященных [явным](../../../csharp/language-reference/keywords/explicit.md) и [неявным](../../../csharp/language-reference/keywords/implicit.md) операциям.  
  
 Оператор `()` перегрузить нельзя.  
  
 Дополнительные сведения см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Выражение приведения может иметь неоднозначное толкование.  Например, выражение `(x)–y` можно интерпретировать как выражение приведения \(приведение –y к типу x\) или как выражение добавления в сочетании с выражением в скобках, которое вычисляет значение x – y.  
  
 Дополнительные сведения о вызове метода см. в разделе [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)