---
title: Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 92eb7a79c0e7522d1474537aeefbfdb083a11dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a>Практическое руководство. Доступ к элементу массива с использованием указателя (Руководство по программированию в C#)
В небезопасном контексте для доступа к элементу в памяти можно использовать доступ к элементу указателя, как показано в следующем примере:  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 Выражение в квадратных скобках должно допускать неявное преобразование в `int`, `uint`, `long` или `ulong`. Операция p[e] эквивалентна *(p+e). Как и в C или C++, при доступе к элементу указателя не выполняется проверка на ошибки выхода за пределы диапазона.  
  
## <a name="example"></a>Пример  
 В этом примере для массива символов `charPointer` выделено 123 расположения в памяти. Этот массив использует два цикла [for](../../../csharp/language-reference/keywords/for.md) для отображения строчных и прописных букв.  
  
 Обратите внимание, что выражение `charPointer[i]` эквивалентно выражению `*(charPointer + i)` и с помощью любого из них можно получить тот же результат.  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 **Прописные буквы:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Строчные буквы:**  
**abcdefghijklmnopqrstuvwxyz**   
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
