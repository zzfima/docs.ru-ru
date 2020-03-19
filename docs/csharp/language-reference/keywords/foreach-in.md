---
title: Оператор foreach в C#
ms.date: 05/17/2019
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: dbe4f4e95c2b99f1be47885e39d51db81ba3a97d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173709"
---
# <a name="foreach-in-c-reference"></a>foreach, in (справочник по C#)

Оператор `foreach` выполняет оператор или блок операторов для каждого элемента в экземпляре типа, который реализует интерфейс <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Оператор `foreach` не ограничивается этими типами. Он может применяться к экземпляру любого типа, который удовлетворяет следующим условиям:

- включает открытый метод `GetEnumerator` без параметров со следующим типом возвращаемого значения: класс, структура или тип интерфейса;
- тип возвращаемого значения метода `GetEnumerator` должен содержать открытое свойство `Current` и открытый метод `MoveNext` без параметров с типом возвращаемого значения <xref:System.Boolean>.

Начиная с версии C# 7.3, если свойство перечислителя `Current` возвращает [ссылочное возвращаемое значение](ref.md#reference-return-values) (`ref T`, где `T` — это тип элемента коллекции), вы можете объявить переменную итерации с модификатором `ref` или `ref readonly`.

Начиная с версии C# 8.0, можно применять оператор `await` к инструкции `foreach`, если тип коллекции реализует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601>. Каждую итерацию цикла можно приостановить, пока будет осуществляться асинхронное извлечение следующего элемента. Элементы потока по умолчанию обрабатываются в захваченном контексте. Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в [статье](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md), посвященной использованию асинхронной модели на основе задач.

В любой момент в блоке операторов `foreach` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md). Также можно выйти из цикла `foreach` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).

Если оператор `foreach` применяется к `null`, возникает исключение <xref:System.NullReferenceException>. Если исходная коллекция инструкции `foreach` пустая, тело цикла `foreach` не выполняется и пропускается.

## <a name="examples"></a>Примеры

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Collections.Generic.List%601>, который реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>:

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

В следующем примере показано использование оператора `foreach` с экземпляром типа <xref:System.Span%601?displayProperty=nameWithType>, который не реализует интерфейс:

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

В следующем примере с помощью переменной итерации `ref` устанавливается значение каждого элемента в массиве stackalloc. В версии `ref readonly` выполняется перебор коллекции для печати всех значений. В объявлении `readonly` используется неявное объявление локальной переменной. Неявные объявления переменных могут использоваться с объявлениями `ref` или `ref readonly`, так же как и явно типизированные объявления переменных.

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

В следующем примере используется `await foreach` для выполнения итерации коллекции с асинхронным созданием каждого элемента:

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#AwaitForeach)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Оператор foreach](~/_csharplang/spec/statements.md#the-foreach-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Использование оператора foreach с массивами](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [Оператор for](for.md)
