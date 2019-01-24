---
title: Справочник по C#. Оператор &gt;&gt;=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333697"
---
# <a name="gtgt-operator-c-reference"></a>Справочник по C#. Оператор &gt;&gt;=

Оператор присваивания сдвига вправо.

## <a name="remarks"></a>Примечания

Выражение в формате

```csharp
x >>= y
```

вычисляется как

```csharp
x = x >> y
```

за исключением того, что `x` вычисляется только один раз. [Оператор >>](right-shift-operator.md) сдвигает `x` вправо на величину, указанную в `y`.

Оператор >>= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор >>](right-shift-operator.md) (см. [оператор](../keywords/operator.md)).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)