---
title: '>>Оператор = — справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278984"
---
# <a name="-operator-c-reference"></a>Оператор >>= (справочник по C#)

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