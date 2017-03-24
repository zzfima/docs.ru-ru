---
title: "Оператор ++ (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "++_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "++ - оператор [C#]"
  - "оператор увеличения (++) [C#]"
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Оператор ++ (справочник по C#)
Оператор инкремента \(`++`\) увеличивает операнд на 1. Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.  
  
## Заметки  
 Первый случай — это операция префиксного инкремента. Результатом операции является значение операнда после его увеличения.  
  
 Второй случай — это операция постфиксного инкремента. Результатом операции является значение операнда до его увеличения.  
  
 Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента. Определяемые пользователем типы могут перегружать оператор `++`. Операции с целыми типами обычно разрешены и для перечислений.  
  
## Пример  
 [!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)