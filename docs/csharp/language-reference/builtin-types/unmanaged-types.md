---
title: Справочник по C#. Неуправляемые типы
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512077"
---
# <a name="unmanaged-types-c-reference"></a>Справочник по C#. Неуправляемые типы

**Неуправляемый тип** — это любой тип, который не является ссылочным или сконструированным типом (включающим как минимум один аргумент типа) и не содержит поля ссылочного или сконструированного типа на любом уровне вложенности. Другими словами, неуправляемым является один из следующих типов:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` или `bool`;
- любой тип [перечисления](../keywords/enum.md);
- любой тип [указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md).
- Любой пользовательский тип [структуры](../keywords/struct.md), который не является сконструированным и содержит поля только неуправляемых типов.

Начиная с C# 7.3 можно использовать [ограничение `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), чтобы указать, что параметр типа является отличным от указателя неуправляемым типом.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы, связанные с памятью и диапазонами](../../../standard/memory-and-spans/index.md)
- [Оператор sizeof](../operators/sizeof.md)
- [Оператор stackalloc](../operators/stackalloc.md)
