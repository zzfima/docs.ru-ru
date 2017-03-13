---
title: "goto (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "goto_CSharpKeyword"
  - "goto"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "goto - ключевое слово [C#]"
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# goto (Справочник по C#)
Оператор `goto` передает управление именованному оператору.  
  
 Чаще всего оператор `goto` используется для передачи управления определенной подписи смены регистра или подписи по умолчанию в операторе `switch`.  
  
 Оператор `goto` также используется для выхода из вложенных циклов со сложной структурой.  
  
## Пример  
 В следующем примере демонстрируется использование оператора `goto` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!code-cs[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## Пример  
 В следующем примере демонстрируется использование оператора `goto` для выхода из вложенных циклов.  
  
 [!code-cs[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор goto](/visual-cpp/cpp/goto-statement-cpp)   
 [Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)