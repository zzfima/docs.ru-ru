---
title: "Оператор false (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "false - оператор, ключевое слово [C#]"
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор false (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возвращает [логическое](../../../csharp/language-reference/keywords/bool.md) значение `true`, чтобы указать на то, что операнд имеет значение `false`, а в противном случае возвращает `false`.  
  
 В версиях до версии C\# 2.0 операторы `true` и `false` использовались для создания пользовательских нулевых типов значений, которые были совместимыми с такими типами, как `SqlBool`.  Однако теперь язык предоставляет встроенную поддержку для нулевых типов значений и по возможности следует использовать их вместо перегрузки операторов `true` и `false`.  Дополнительные сведения см. в разделе [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 С нулевыми логическими значениями выражение `a != b` не обязательно равно `!(a == b)`, поскольку одно или оба значения могут быть нулевыми.  Необходимо отдельно перегрузить операторы `true` и `false`, чтобы правильно обработать нулевые значения в выражении.  В следующем примере показана перегрузка и применение операторов `true` и `false`.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 Тип, перегружающий операторы `true` и `false`, может использоваться для выражения управления в операторах [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) и [for](../../../csharp/language-reference/keywords/for.md) и в [условных выражениях](../../../csharp/language-reference/operators/conditional-operator.md).  
  
 Если тип определяет оператор `false`, он должен определить и оператор [true](../../../csharp/language-reference/keywords/true.md).  
  
 Тип не может непосредственно выполнить перегрузку условных логических операторов [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) и [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), однако такой же результат может быть достигнут путем перегрузки регулярных логических операторов и операторов `true` и `false`.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [true](../../../csharp/language-reference/keywords/true.md)