---
title: Справочник по C#. Оператор &gt;&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 80e38d8e75b9ad573b635d544d6381950f107583
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333694"
---
# <a name="gtgt-operator-c-reference"></a>Справочник по C#. Оператор &gt;&gt;

Оператор сдвига вправо (`>>`) сдвигает первый операнд вправо на число битов, задаваемое вторым операндом.

## <a name="remarks"></a>Примечания

Если первый операнд имеет тип [int](../keywords/int.md) или [uint](../keywords/uint.md) (32-разрядное число), величина сдвига определяется пятью младшими разрядами второго операнда (второй операнд и 0x1f).

Если первый операнд имеет тип [long](../keywords/long.md) или [ulong](../keywords/ulong.md) (64-разрядное число), величина сдвига определяется шестью младшими разрядами второго операнда (второй операнд и 0x3f).

Если первый операнд имеет тип [int](../keywords/int.md) или [long](../keywords/long.md), величина сдвига вправо определяется арифметическим сдвигом (пустые старшие разряды используются для бита знака). Если первый операнд имеет тип [uint](../keywords/uint.md) или [ulong](../keywords/ulong.md), величина сдвига вправо определяется логическим сдвигом (старшие разряды заполняются нулями).

Определяемые пользователем типы могут перегружать оператор `>>`. В этом случае первый операнд должен иметь определяемый пользователем тип, а второй операнд — тип [int](../keywords/int.md). Дополнительные сведения см. в статье [operator](../keywords/operator.md). При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#26)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)