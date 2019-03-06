---
title: Руководство по программированию на C#. Увеличение и уменьшение указателей
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 358decb73666d5a5ef7c0fa828168d90d2c22c1e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973708"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Практическое руководство. Увеличение и уменьшение указателей (руководство по программированию на C#)

С помощью операторов инкремента и декремента (`++` и `--`) можно изменить расположение указателя типа `pointer-type*` на `sizeof(pointer-type)`. Выражения инкремента или декремента имеют следующий вид:  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 Операторы инкремента и декремента можно применять к указателям любого типа, за исключением типа `void*`.  
  
 В результате применения оператора инкремента к указателю типа `pointer-type*` к адресу, который содержится в переменной указателя, добавляется `sizeof(pointer-type)`.  
  
 В результате применения оператора декремента к указателю типа `pointer-type*` из адреса, который содержится в переменной указателя, вычитается `sizeof(pointer-type)`.  
  
 Исключения не создаются, если операция переполняет домен указателя, а результат зависит от реализации.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется пошаговая обработка массива путем увеличения указателя на размер `int`. После выполнения каждого шага отображаются адрес и содержимое элемента массива.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#13)]  
  
**Значение:0 @ Адрес:12860272**
**Значение:1 @ Адрес:12860276**
**Значение:2 @ Адрес:12860280**
**Значение:3 @ Адрес:12860284**
**Значение:4 @ Адрес:12860288**

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
- [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
- [sizeof](../../../csharp/language-reference/keywords/sizeof.md)
