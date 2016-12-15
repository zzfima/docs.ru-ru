---
title: "stackalloc (Справочник по C#) | Microsoft Docs"
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
  - "stackalloc_CSharpKeyword"
  - "stackalloc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "stackalloc - ключевое слово [C#]"
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# stackalloc (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `stackalloc` используется в небезопасном контексте кода для выделения блока памяти в стеке.  
  
```  
int* block = stackalloc int[100];  
```  
  
## Заметки  
 Ключевое слово является допустимой только в инициализаторах локальных переменных.  Следующий код вызывает ошибки компилятора.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Поскольку затрагиваются типы указателей, для `stackalloc` требуется контекст [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 `stackalloc` аналогично [\_alloca](/visual-cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения языка C.  
  
 В следующем примере вычисляет и отображает первые 20 числа в последовательности Фибоначчи.  Каждое число является суммой предыдущих двух чисел.  В коде показан блок памяти, имеющий достаточный размер для хранения 20 элементов типа `int` и выделенный в стеке, а не в куче.  Адрес блока хранится в указателе `fib`.  Сборка мусора не затрагивает память и поэтому память не должна быть закреплена \(с помощью [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)\).  Время существования блока памяти ограничено жизненным циклом определяющего его метода.  Перед возвращением метода освободить память нельзя.  
  
## Пример  
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## Безопасность  
 Небезопасный код менее надежен, чем его защищенные альтернативы.  Однако при использовании `stackalloc` в CLR автоматически активируются функции обнаружения переполнения буфера.  В случае обнаружения переполнения происходит максимально быстрое завершение процесса, которое сокращает вероятность выполнения вредоносного кода.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)