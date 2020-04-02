---
title: Выражение nameof. Справочник по C#
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof expression [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 5a68161be7bb03122d2a63ccef4365c5853862b2
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507143"
---
# <a name="nameof-expression-c-reference"></a>Выражение nameof (справочник по C#)

Выражение `nameof` создает имя, тип или элемент переменной в качестве строковой константы:

[!code-csharp-interactive[nameof expression](snippets/NameOfOperator.cs#Examples)]

Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Значение выражения `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.

С помощью выражения `nameof` можно сделать код проверки аргументов более удобным:

[!code-csharp[nameof and argument check](snippets/NameOfOperator.cs#ExceptionMessage)]

Выражение `nameof` доступно в C# версии 6 и выше.

## <a name="c-language-specification"></a>Спецификация языка C#

См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
