---
title: "unsafe (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "unsafe_CSharpKeyword"
  - "unsafe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "unsafe - ключевое слово [C#]"
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# unsafe (Справочник по C#)
Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для работы с указателями.  Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 Модификатор `unsafe` можно использовать в объявлении типа или члена.  Таким образом, вся текстовая область типа или члена считается небезопасным контекстом.  Например, в следующем примере показан метод, объявленный с модификатором `unsafe`:  
  
```  
  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Область небезопасного контекста начинается от списка параметров и заканчивается концом метода, поэтому указатели можно также использовать в списке параметров:  
  
```  
  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 Кроме того, можно использовать небезопасный блок, чтобы внутри него использовать небезопасный код.  Примеры.  
  
```  
  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Для компиляции небезопасного кода необходимо указать параметр компилятора [\/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Небезопасный код не проверяется средой CLR.  
  
## Пример  
 [!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsModifiers/csrefKeywordsModifiers.cs#22)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)