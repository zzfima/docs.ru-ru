---
title: Оператор <<= — справочник по C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258738"
---
# <a name="-operator-c-reference"></a>Справочник по C#. Оператор \<\<=

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
