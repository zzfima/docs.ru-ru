---
title: "Практическое руководство. Получение адреса переменной (Руководство по программированию на C#) | Microsoft Docs"
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
  - "выражения указателей [C#], address-of - оператор"
  - "указатели [C#], & - оператор"
  - "переменные [C#], адрес"
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Чтобы получить адрес унарного выражения \(которое оценивается как фиксированная переменная\), используйте оператор address\-of:  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Оператор address\-of можно применять только к переменной.  Если переменная является перемещаемой, можно использовать [фиксированное предложение](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.  
  
 Разработчик отвечает за инициализацию переменной.  Если переменная не будет инициализирована, на компиляторе не будет отображено сообщение об ошибке.  
  
 Невозможно получить адрес константы или переменной.  
  
## Пример  
 В данном примере указатель на `int`, `p` объявляется и ему присваивается адрес целочисленной переменной `number`.  Переменная `number` инициализируется в результате присвоения \*p.  Если в тексте кода закомментировать присвоение, то инициализация переменной `number` будет удалена, однако при компиляции не возникнет сообщений об ошибках.  Обратите внимание на применение оператора [доступа члена](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) `->` для получения и отображения адреса, хранящегося в указателе.  
  
 [!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)