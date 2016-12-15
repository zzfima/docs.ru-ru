---
title: "while (Справочник по C#) | Microsoft Docs"
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
  - "while_CSharpKeyword"
  - "while"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "while - ключевое слово [C#]"
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# while (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `while` выполняет оператор или блок операторов, пока определенное выражение не примет значение `false`.  
  
## Пример  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## Пример  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## Пример  
 Поскольку перед каждым выполнением цикла выражение `while` тестируется, цикл `while` выполняется от нуля до нескольких раз.  Это отличает его от цикла [do](../../../csharp/language-reference/keywords/do.md), который выполняется от одного до нескольких раз.  
  
 Цикл `while` может быть завершен, если оператор [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md) передает управление за пределы цикла.  Чтобы передать управление на следующую итерацию без выхода из цикла, используйте оператор [continue](../../../csharp/language-reference/keywords/continue.md).  Обратите внимание на разницу в результатах трех предыдущих примеров, которые зависят от места увеличения `int n`.  В следующем примере результат отсутствует.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор while \(C\+\+\)](/visual-cpp/cpp/while-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)