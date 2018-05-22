---
title: Оператор &amp; (справочник по C#)
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 59813b4bc5781776c9f9741c3e49e660c684bff9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-c-reference"></a>Оператор &amp; (справочник по C#)
Оператор `&` может функционировать как унарный или как бинарный оператор.  
  
## <a name="remarks"></a>Примечания  
 Унарный оператор `&` возвращает адрес своего операнда (в этом случае требуется контекст [unsafe](../../../csharp/language-reference/keywords/unsafe.md)).  
  
 Бинарные операторы `&` предварительно определены для целочисленных типов и типа `bool`. Для целочисленных типов оператор & выполняет побитовую логическую операцию И для всех своих операндов. Для операндов типа `bool` оператор & выполняет логическую операцию И для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда оба операнда имеют значение `true`.  
  
 Бинарный оператор `&` вычисляет оба оператора независимо от значения первого из них, в отличие от [условного оператора AND](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`. Пример:  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `&` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Операции с целыми типами обычно разрешены и для перечислений. При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
