---
title: "Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "выражения указателей [C#], косвенное обращение"
  - "указатели [C#], * - оператор"
  - "указатели [C#], косвенное обращение"
  - "переменные [C#], указатели"
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#)
Косвенный оператор указателя служит для получения переменной в расположении, на которое указывает указатель.  Выражение имеет следующий вид \(где  `p` — тип указателя\):  
  
```  
*p;  
```  
  
 Невозможно использовать унарный косвенный оператор с выражениями какого\-либо типа, за исключением типа указателя.  Кроме того, его невозможно применить к [пустому](../../../csharp/language-reference/keywords/void.md) указателю.  
  
 При применении косвенного оператора к указателю с [нулевым](../../../csharp/language-reference/keywords/null.md) значением результат зависит от конкретной реализации.  
  
## Пример  
 В следующем примере к переменной типа `char` получают доступы указатели различных типов.  Обратите внимание, что адрес `theChar` будет изменяться в каждом случае, поскольку физический адрес переменной может изменяться.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#5)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#6)]  
  
  **Значение theChar \= Z**   
**Адрес theChar \= 12F718**  
**Значение pChar \= Z**   
**Значение pInt \= 90**    
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)