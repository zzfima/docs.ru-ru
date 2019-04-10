---
title: Руководство по программированию на C#. Получение адреса переменной
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
ms.openlocfilehash: b12d3bf99f32a3526bd4a1ec8c49b1fd88afd68a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832350"
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)

Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of `&`:  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Оператор address-of применяется только к переменным. Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса. Дополнительные сведения о перемещаемых переменных см. в разделе [Fixed and moveable variables](/dotnet/csharp/language-reference/language-specification/unsafe-code#fixed-and-moveable-variables) (Фиксированные и перемещаемые переменные). 
  
 Вам необходимо самостоятельно обеспечить проверку инициализации переменной. Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.  
  
 Получить адрес константы или значения нельзя.  
  
## <a name="example"></a>Пример  
 В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`. Переменная `number` инициализируется в результате назначения `*p`. Если закомментировать этот оператор назначения, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.  

> [!NOTE]
> Скомпилируйте этот пример с использованием параметра компилятора [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
