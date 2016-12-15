---
title: "Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#) | Microsoft Docs"
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
  - "указатели [C#], доступ к массивам"
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В небезопасной среде можно получить доступ к элементу в памяти посредством доступа к элементу указателя \(см. пример ниже\).  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 Выражение в квадратных скобках должно быть явным образом преобразуемым в `int`, `uint`, `long` или `ulong`.  Операция p\[e\] эквивалентна \*\(p\+e\).  Как в C и C\+\+, доступ к элементу указателя не проверяет ошибки, выходящие за пределы.  
  
## Пример  
 В этом примере области памяти 123 назначаются массиву символов `charPointer`.  Массив используется для отображения букв нижнего регистра и букв верхнего регистра в двух циклах [for](../../../csharp/language-reference/keywords/for.md).  
  
 Обратите внимание, что выражение `charPointer[i]` эквивалентно выражению `*(charPointer + i)` и можно получить одинаковый результат с помощью любого из этих двух выражений.  
  
 [!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
  **Буквы верхнего регистра:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Буквы нижнего регистра:**  
**abcdefghijklmnopqrstuvwxyz**   
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)