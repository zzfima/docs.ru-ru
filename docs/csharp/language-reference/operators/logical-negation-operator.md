---
title: '! Справочник по C#. Оператор -'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 6b6d1796032f536aac0be49d4f101c1380b4e98f
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333230"
---
# <a name="-operator-c-reference"></a>! operator (Справочник по C#)

Оператор логического отрицания (`!`) представляет собой унарный оператор, который инвертирует свой операнд. Он определяется для значения типа `bool` и возвращает `true` только в том случае, если операнд имеет значение `false`.

## <a name="remarks"></a>Примечания

Определяемые пользователем типы могут вызвать перегрузку оператора `!` (см. раздел [operator](../keywords/operator.md)) .

## <a name="example"></a>Пример

[!code-csharp[csRefOperators#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#7)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)