---
title: Арифметические операции над указателями (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 3694699466f7a200eecd5eef85f60fa19f9584a8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862307"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Арифметические операции над указателями (Руководство по программированию в C#)
В этом разделе рассматривается использование арифметических операторов `+` и **-** для управления указателями.  
  
> [!NOTE]
>  Выполнение арифметических операций с указателями void невозможно.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Добавление числовых значений в указатели и вычитание из них  
 Можно добавить значение `n` типа [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) или [ulong](../../../csharp/language-reference/keywords/ulong.md) в указатель, `p`, любого типа, за исключением `void*`. Результат `p+n` — это указатель, полученный при добавлении `n * sizeof(p) to the address of p`. Аналогичным образом, `p-n` является указателем, полученным в результате вычитания `n * sizeof(p)` из адреса `p`.  
  
## <a name="subtracting-pointers"></a>Вычитание указателей  
 Также можно вычитать указатели одного типа. Результат всегда имеет тип `long`. Например, если `p1` и `p2` являются указателями типа `pointer-type*`, то результатом выражения `p1-p2` будет:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 Исключения не создаются, если арифметическая операция переполняет домен указателя, а результат зависит от реализации.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
- [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Типы](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
