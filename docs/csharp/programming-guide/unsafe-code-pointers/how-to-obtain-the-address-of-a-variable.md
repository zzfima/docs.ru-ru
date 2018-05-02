---
title: Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 63a49490effb8b7d365492e8518b7558ec03a705
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)
Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of `&`:  
  
```csharp  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Оператор address-of применяется только к переменным. Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.  
  
 Вам необходимо самостоятельно обеспечить проверку инициализации переменной. Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.  
  
 Получить адрес константы или значения нельзя.  
  
## <a name="example"></a>Пример  
 В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`. Переменная `number` инициализируется в результате назначения `*p`. Если закомментировать этот оператор назначения, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет.  

> [!NOTE]
> Скомпилируйте этот пример с использованием параметра компилятора [`-unsafe`](../../language-reference/compiler-options/unsafe-compiler-option.md).
  
 [!code-csharp[address-of-a-variable](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#8)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
