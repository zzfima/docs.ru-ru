---
title: Справочник по C#. Оператор *=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333438"
---
# <a name="-operator-c-reference"></a>Оператор \*= (справочник по C#)

Бинарный оператор присваивания умножения.

## <a name="remarks"></a>Примечания

Выражение, использующее оператор присваивания `*=`, такое как

```csharp
x *= y
```

эквивалентно

```csharp
x = x * y
```

за исключением того, что `x` вычисляется только один раз. В числовых типах [оператор \*](multiplication-operator.md) используется для выполнения операций умножения.

Оператор `*=` нельзя перегружать напрямую, но пользовательские типы могут перегружать [оператор \*](multiplication-operator.md) (см. [operator](../keywords/operator.md)).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
