---
title: unsafe (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 367a080cf58514b3ffcc30c17d8fe7bb07e0e9ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="unsafe-c-reference"></a>unsafe (Справочник по C#)
Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей. Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 В объявлении типа или члена типа можно использовать модификатор `unsafe`. Все текстовое пространство типа или члена типа считается небезопасным контекстом. Например, следующий метод объявлен с модификатором `unsafe`:  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок. Пример:  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 Для компиляции небезопасного кода необходимо задать параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md). Небезопасный код не проверяется средой CLR.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Буферы фиксированного размера](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
