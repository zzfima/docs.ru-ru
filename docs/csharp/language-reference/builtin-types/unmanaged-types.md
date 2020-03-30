---
title: Справочник по C#. Неуправляемые типы
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 9dd2ab4e044b8a86bfe72a6fcf2481b8e1e80bf4
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507234"
---
# <a name="unmanaged-types-c-reference"></a>Справочник по C#. Неуправляемые типы

Тип является **неуправляемым типом**, если он принадлежит к одному из следующих типов:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` или `bool`;
- любой тип [перечисления](enum.md);
- любой тип [указателя](../../programming-guide/unsafe-code-pointers/pointer-types.md).
- Любой определенный пользователем тип [структуры](struct.md), который содержит поля только неуправляемых типов в C# 7.3 и более ранних версиях, не является сконструированным типом (тип, который включает по крайней мере один аргумент типа)

Начиная с C# 7.3 можно использовать [ограничение `unmanaged`](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint), чтобы указать, что параметр типа является отличным от указателя неуправляемым типом, не допускающим значения NULL.

Начиная с C# 8.0, *сконструированный* тип структуры, содержащий поля только неуправляемых типов, также является неуправляемым, как показано в следующем примере:

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

Универсальная структура может быть источником как для неуправляемых сконструированных типов, так и для сконструированных типов, отличных от неуправляемых. В предыдущем примере определяется универсальная структура `Coords<T>`, а также представлены примеры неуправляемых сконструированных типов. Примером типа, отличного от неуправляемого, является `Coords<object>`. Он не является неуправляемым, так как содержит поля типа `object`, которые являются отличными от неуправляемых. Если необходимо, чтобы *все* сконструированные типы были неуправляемыми, используйте ограничение `unmanaged` в определении универсальной структуры:

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Типы указателей](~/_csharplang/spec/unsafe-code.md#pointer-types) в статье [Спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы, связанные с памятью и диапазонами](../../../standard/memory-and-spans/index.md)
- [Оператор sizeof](../operators/sizeof.md)
- [stackalloc](../operators/stackalloc.md)
