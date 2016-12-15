---
title: "Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#) | Microsoft Docs"
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
  - "выражения указателей [C#], увеличение и уменьшение"
  - "указатели [C#], увеличение и уменьшение"
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Используйте операторы инкремента или декремента, `++` и `--`, для изменения положения указателя на значение [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) применительно к указателю, имеющему тип "тип указателя\*".  Выражения инкремента или декремента принимают следующую форму:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Операторы инкремента или декремента можно применять к указателям любого типа, кроме типа `void*`.  
  
 Результатом применения оператора увеличения к указателю типа `pointer-type` является добавление значения [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) к адресу, содержащемуся в переменной указателя.  
  
 Результатом применения оператора уменьшения к указателю типа `pointer-type` является вычитание значения `sizeof` \(`pointer-type`\) из адреса, содержащегося в переменной указателя.  
  
 При переполнении в результате выполнения этой операции домена указателя исключений не генерируется, а результат зависит от конкретной реализации.  
  
## Пример  
 В этом примере выполняется перемещение по массиву путем увеличения значения переменной указателя на размер типа `int`.  После выполнения каждого шага отображается адрес и содержимое элемента массива.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
  **Значение: 0 @ Адрес: 12860272**  
**Значение: 1 @ Адрес: 12860276**  
**Значение: 2 @ Адрес: 12860280**  
**Значение: 3 @ Адрес: 12860284**  
**Значение: 4 @ Адрес: 12860288**   
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)