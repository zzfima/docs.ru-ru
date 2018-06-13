---
title: Практическое руководство. Увеличение и уменьшение указателей (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: e1c3ac12a126450781d0ce78e788f39c740b5279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324289"
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
  
 **Значение:0 по адресу:12860272**  
**Значение:1 по адресу:12860276**  
**Значение:2 по адресу:12860280**  
**Значение:3 по адресу:12860284**  
**Значение:4 по адресу:12860288**   
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
