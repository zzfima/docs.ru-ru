---
title: "Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- variables [C#], address of
- pointers [C#], & operator
- pointer expressions [C#], address-of operator
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d0969f7e62864c682660f08cd4198aa4032e0e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-the-address-of-a-variable-c-programming-guide"></a>Практическое руководство. Получение адреса переменной (Руководство по программированию на C#)
Чтобы получить адрес унарного выражения, при вычислении которого получается фиксированная переменная, используйте оператор address-of:  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Оператор address-of применяется только к переменным. Если переменная может перемещаться, используйте [оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md), чтобы временно зафиксировать переменную перед получением ее адреса.  
  
 Вам необходимо самостоятельно обеспечить проверку того, что переменная инициализирована. Если переменная не инициализирована, компилятор не выдает сообщение об ошибке.  
  
 Получить адрес константы или значения нельзя.  
  
## <a name="example"></a>Пример  
 В этом примере объявляется указатель на `int`, `p`, которому присваивается адрес целочисленной переменной `number`. Переменная `number` инициализируется в результате присваивания *p. Если закомментировать этот оператор присваивания, инициализация `number` будет удалена, однако во время компиляции ошибка не возникнет. Обратите внимание на использование оператора [доступа к члену](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) (`->`) для получения и отображения адреса, хранящегося в указателе.  
  
 [!code-csharp[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-address-of-a-variable_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Типы](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
