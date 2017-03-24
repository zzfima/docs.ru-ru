---
title: "break (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "break"
  - "break_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "break - ключевое слово [C#]"
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# break (Справочник по C#)
Оператор `break` завершает ближайший внешний цикл или оператор [switch](../../../csharp/language-reference/keywords/switch.md), в котором он появляется.  Управление передается оператору, следующему за завершенным оператором \(если таковой имеется\).  
  
## Пример  
 В этом примере условный оператор содержит счетчик, который должен считать от 1 до 100; однако оператор `break` завершает цикл после четырех.  
  
 [!code-cs[csrefKeywordsJump#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_1.cs)]  
  
## Пример  
 В этом примере для разрыва внутреннего вложенного цикла и возвращения управления во внешний цикл используется оператор `break`.  
  
 [!code-cs[csrefKeywordsJump#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_2.cs)]  
  
## Пример  
 В этом примере показано использование `break` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!code-cs[csrefKeywordsJump#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/break_3.cs)]  
  
 При вводе `4` будет следующий результат.  
  
```  
Enter your selection (1, 2, or 3): 4  
Sorry, invalid selection.  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [switch](../../../csharp/language-reference/keywords/switch.md)   
 [Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)