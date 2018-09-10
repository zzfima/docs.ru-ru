---
title: Оператор foreach в C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: d84c68eb102d55b31ba20a6b6b5c01b96963924d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524253"
---
# <a name="foreach-in-c-reference"></a>foreach, in (справочник по C#)

Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:

- включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;
- тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.

В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md). Также можно выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

## <a name="examples"></a>Примеры

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`. В следующем примере с помощью переменной итерации `ref` устанавливается значение каждого элемента в массиве stackalloc. В версии `ref readonly` выполняется перебор коллекции для печати всех значений. В объявлении `readonly` используется неявное объявление локальной переменной. Неявные объявления переменных могут использоваться с объявлениями `ref` или `ref readonly`, так же как и явно типизированные объявления переменных.

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Оператор foreach (спецификация языка C#)](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)
- [Использование оператора foreach с массивами](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for](for.md)
- [Операторы итерации](iteration-statements.md)
- [Ключевые слова в C#](index.md)
- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
