---
title: Справочник по C#. Оператор |=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333269"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор |=

Оператор присваивания ИЛИ.

## <a name="remarks"></a>Примечания

Выражение, использующее оператор присваивания `|=`, такое как

```csharp
x |= y
```

эквивалентно

```csharp
x = x | y
```

за исключением того, что `x` вычисляется только один раз. [Оператор &#124;](or-operator.md) выполняет побитовую операцию ИЛИ в отношении целочисленных операндов и логическую операцию ИЛИ в отношении операндов типа bool.

Оператор `|=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор &#124;](or-operator.md) (см. [operator](../keywords/operator.md)).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)