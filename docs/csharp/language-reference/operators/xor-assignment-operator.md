---
title: Справочник по C#. Оператор ^=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: 12189d6469a9716d3b7ebcffef23423a75692d1a
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333555"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор ^=

Оператор присваивания исключающего ИЛИ.

## <a name="remarks"></a>Примечания

Выражение в формате

```csharp
x ^= y
```

вычисляется как

```csharp
x = x ^ y
```

за исключением того, что `x` вычисляется только один раз. [Оператор ^](xor-operator.md) выполняет побитовую операцию исключающего ИЛИ в отношении целочисленных операндов и логическую операцию исключающего ИЛИ в отношении операндов типа [bool](../keywords/bool.md).

Оператор ^= нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор ^](xor-operator.md) (см. [operator](../keywords/operator.md)).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#23)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)