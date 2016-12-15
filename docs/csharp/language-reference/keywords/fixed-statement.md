---
title: "Оператор fixed (Справочник по C#) | Microsoft Docs"
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
  - "fixed_CSharpKeyword"
  - "fixed"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "fixed - ключевое слово [C#]"
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Оператор fixed (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.  Оператор `fixed` допускается только в [небезопасном](../../../csharp/language-reference/keywords/unsafe.md) контексте.  `Fixed` также можно использовать для создания [буферов фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.  Без `fixed`, указатели на перемещаемые управляемые переменные были бы мало полезны, так как при сборке мусора переменные переносились бы непредсказуемым образом.  Компилятор C\# позволяет назначить указатель только управляемой переменной в операторе `fixed`.  
  
 [!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 Можно инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.  В следующем примере демонстрируется использование переменных адресов, массивов и строк.  Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).  
  
 [!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 Можно инициализировать несколько указателей одного типа.  
  
```  
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```  
  
 Чтобы инициализировать указатели разных типов, просто разместите операторы `fixed`, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 После выполнения кода в операторе закрепление любых закрепленных переменных снимается и они могут пройти сборку мусора.  Таким образом, не следует указывать на эти переменные за пределами оператора `fixed`.  
  
> [!NOTE]
>  Переменные, инициализированные в фиксированных операторах изменять не допускается.  
  
 В небезопасном режиме память выделяется стеку, где сборка мусора не производится и, соответственно, закрепление не требуется.  Дополнительные сведения см. в разделе [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).  
  
## Пример  
 [!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)