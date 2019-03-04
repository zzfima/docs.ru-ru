---
title: . Справочник по C#. Оператор -
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836465"
---
# <a name="-operator-c-reference"></a>. operator (Справочник по C#)

Оператор "точка" (`.`) обычно используется для доступа к членам.

Маркер `.` используется для обращения к члену пространства имен или типа, как в следующих примерах.

- Используйте `.` для обращения к пространству имен, вложенному в другое пространство имен, как показано в следующем примере [директивы `using`](../keywords/using-directive.md).

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- Используйте `.` для создания *полного имени* для обращения к типу в пределах пространства имен, как показано в следующем коде:

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  Используйте [директиву `using`](../keywords/using-directive.md), чтобы сделать использование полных имен необязательным.

- Используйте `.` для обращения к [членам типов](../../programming-guide/classes-and-structs/index.md#members) (статическим и нестатическим), как показано в следующем коде:

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

Можно также использовать `.` для вызова [метода расширения](../../programming-guide/classes-and-structs/extension-methods.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор `.` перегрузить нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Доступ к членам](~/_csharplang/spec/expressions.md#member-access) в [спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Операторы ?. и ?[]](null-conditional-operators.md)