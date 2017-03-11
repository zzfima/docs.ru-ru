---
title: "Оператор % (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "%_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "% - оператор [C#]"
  - "модуль - оператор [C#]"
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Оператор % (Справочник по C#)
Оператор `%` вычисляет остаток после деления первого операнда на второй.  Все числовые типы имеют предопределенные операторы остатка.  
  
## Заметки  
 Типы, определенные пользователем, могут вызвать перегрузку оператора `%` \(см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)\).  Если бинарный оператор перегружен, соответствующий оператор присваивания \(если таковой имеется\), также будет явно перегружен.  
  
## Пример  
 [!code-cs[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#9)]  
  
## Комментарии  
 Обратите внимание на ошибки округления, связанные с двойным типом.  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)