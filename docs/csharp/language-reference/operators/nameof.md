---
title: Справочник по C#. Оператор nameof
ms.date: 07/12/2019
f1_keywords:
- nameof_CSharpKeyword
- nameof
helpviewer_keywords:
- nameof operator [C#]
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: c1d71d52a9222379adc36479715113b181da7133
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712693"
---
# <a name="nameof-operator-c-reference"></a>Справочник по C#. Оператор nameof

Оператор `nameof` получает имя, тип или член переменной в качестве строковой константы:

[!code-csharp-interactive[nameof operator](~/samples/csharp/language-reference/operators/NameOfOperator.cs#Examples)]

Как показано в предыдущем примере, при использовании типа и пространства имен созданное имя обычно не является [полным](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

Оператор `nameof` вычисляется во время компиляции, и это не влияет на время выполнения.

С помощью оператора `nameof` можно сделать код проверки аргументов более удобным:

[!code-csharp[nameof and argument check](~/samples/csharp/language-reference/operators/NameOfOperator.cs#ExceptionMessage)]

Оператор `nameof` доступен в C# версии 6 и выше.

## <a name="c-language-specification"></a>Спецификация языка C#

См. подробнее о [выражениях nameof](~/_csharplang/spec/expressions.md#nameof-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
