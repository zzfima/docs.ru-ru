---
title: Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 39cefc5dcebf1331a5e0ac0fadb8284e9041eb27
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44206475"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)
С помощью операторов инкремента и декремента (`++` и `--`) можно изменить расположение указателя на тип на величину [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`)*. Выражения инкремента или декремента имеют следующий вид:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Операторы инкремента и декремента можно применять к указателям любого типа, за исключением типа `void*`.  
  
 В результате применения оператора инкремента к указателю типа `pointer-type` добавляется [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) к адресу, который содержится в переменной указателя.  
  
 В результате применения оператора декремента к указателю типа `pointer-type` вычитается `sizeof` (`pointer-type`) из адреса, который содержится в переменной указателя.  
  
 Исключения не создаются, если операция переполняет домен указателя, а результат зависит от реализации.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется пошаговая обработка массива путем увеличения указателя на размер `int`. После выполнения каждого шага отображаются адрес и содержимое элемента массива.  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
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
