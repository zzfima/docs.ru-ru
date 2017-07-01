---
title: "#elif (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#elif"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#elif - директива [C#]"
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# #elif (Справочник по C#)
`#elif` позволяет создать составную условную директиву.  Выражение `#elif` будет вызвано, если ни предшествующие директивы [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), ни (необязательно) предшествующие директивы `#elif` не были вызваны со значением `true`. Если результатом вычисления выражения `#elif` является `true`, компилятор вычисляет весь код между `#elif` и следующей условной директивой.  Например:  
  
```  
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 Для вычисления нескольких символов служат операторы `==` \(равенство\), `!=` \(неравенство\), `&&` \(и\) и `||` \(или\).  Можно группировать символы и операторы при помощи скобок.  
  
## Заметки  
 Директива `#elif` эквивалентна использованию:  
  
```  
#else  
#if  
```  
  
 Использование `#elif` проще, так как каждой директиве `#if` требуется [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), в то время как `#elif` можно использовать без соответствующей `#endif`.  
  
 Пример использования `#elif` см. в разделе [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)
