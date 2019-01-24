---
title: Справочник по C#. Оператор &lt;&lt;=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 4513c4b78dea3e8102c72a43249b4a44ffa2421d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333256"
---
# <a name="ltlt-operator-c-reference"></a>Справочник по C#. Оператор &lt;&lt;=

Оператор присваивания сдвига влево.

## <a name="remarks"></a>Примечания

Выражение в формате

```csharp
x <<= y
```

вычисляется как

```csharp
x = x << y
```

за исключением того, что `x` вычисляется только один раз. [Оператор <<](left-shift-operator.md) сдвигает `x` влево на число битов, заданное в `y`.

Оператор `<<=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор <<](left-shift-operator.md) (см. [оператор](../keywords/operator.md)).

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
