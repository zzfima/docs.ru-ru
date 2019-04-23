---
title: Справочник по C#. Ключевое слово bool
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: d87da29872582e9c0d47a6c999312ce88252a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334176"
---
# <a name="bool-c-reference"></a>bool (Справочник по C#)

Ключевое слово `bool` является псевдонимом для <xref:System.Boolean?displayProperty=nameWithType>. Оно используется для объявления переменных для хранения логических значений [true](true-literal.md) и [false](false-literal.md).

> [!NOTE]
> Используйте тип `bool?`, если вам нужно использовать трехзначную логику, например при работе с базами данных, которые поддерживают трехзначный логический тип. Для операндов `bool?` предопределенные операторы `&` и `|` поддерживают троичную логику. См. подробнее о [логических операторах, поддерживающих значение NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../operators/boolean-logical-operators.md).

## <a name="literals"></a>Литералы

Логическое значение можно назначить переменной `bool`. Переменной `bool` также может назначить выражение, результатом которого является `bool`.

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

Значением переменной `bool` по умолчанию является `false`. Значением переменной `bool?` по умолчанию является `null`.

## <a name="conversions"></a>Преобразования

В C++ значение типа `bool` можно преобразовать в значение типа `int`; другими словами, `false` эквивалентно нулю, а `true` эквивалентно ненулевым значениям. В C# не предусмотрено преобразование между типом `bool` и другими типами. Например, следующий оператор `if` недопустим в C#:

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

Чтобы проверить переменную типа `int`, нужно явно сравнить ее со значением, например с нулем, следующим образом:

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>Пример

В этом примере символ вводится с клавиатуры, и программа проверяет, является ли введенный символ буквой. Если это буква, проверяется ее регистр. Эти проверки выполняются с использованием <xref:System.Char.IsLetter%2A> и <xref:System.Char.IsLower%2A>, которые возвращают значение типа `bool`:

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)
- [Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
