---
title: Оператор await — справочник по C#
ms.date: 11/08/2019
f1_keywords:
- await_CSharpKeyword
helpviewer_keywords:
- await keyword [C#]
- await [C#]
ms.assetid: 50725c24-ac76-4ca7-bca1-dd57642ffedb
ms.openlocfilehash: 9f541ae9c26eb12acdcf9a8c59bab98c4772c3b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173449"
---
# <a name="await-operator-c-reference"></a>Оператор await (справочник по C#)

Оператор `await` приостанавливает вычисление включающего [асинхронного](../keywords/async.md) метода до завершения асинхронной операции, представленной его операндом. После завершения асинхронной операции оператор `await` возвращает результат операции, если таковой имеется. Когда оператор `await` применяется к операнду, который представляет уже завершенную операцию, он возвращает результат операции немедленно без приостановки включающего метода. Оператор `await` не блокирует поток, который вычисляет асинхронный метод. Когда оператор `await` приостанавливает включающий метод async, элемент управления возвращается вызывающему объекту метода.

В следующем примере метод <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A?displayProperty=nameWithType> возвращает экземпляр `Task<byte[]>`, который представляет асинхронную операцию, создающую массив байтов после завершения. До завершения операции оператор `await` приостанавливает метод `DownloadDocsMainPageAsync`. Когда `DownloadDocsMainPageAsync` приостанавливается, управление возвращается методу `Main`, который является вызывающим объектом `DownloadDocsMainPageAsync`. Метод `Main` выполняется до тех пор, пока ему не потребуется результат асинхронной операции, выполняемой методом `DownloadDocsMainPageAsync`. Когда <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> получает все байты, вычисляется остальная часть метода `DownloadDocsMainPageAsync`. После этого вычисляется остальная часть метода `Main`.

[!code-csharp[await example](snippets/AwaitOperator.cs)]

В предыдущем примере используется [асинхронный метод `Main`](../../programming-guide/main-and-command-args/index.md), который доступен, начиная с версии C# 7.1. Дополнительные сведения см. в описании [оператора await в методе Main](#await-operator-in-the-main-method).

> [!NOTE]
> Общие сведения об асинхронном программировании см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../programming-guide/concepts/async/index.md). Асинхронное программирование `async` и `await` следует [асинхронной модели, основанной на задачах](../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).

Оператор `await` можно использовать только в методе, [лямбда-выражении](../../programming-guide/statements-expressions-operators/lambda-expressions.md) или в [анонимном методе](delegate-operator.md), изменяемом ключевым словом [async](../keywords/async.md). В асинхронном методе нельзя использовать оператор `await` в теле синхронной функции, внутри блока [инструкции lock](../keywords/lock-statement.md) и в [ненадежном](../keywords/unsafe.md) контексте.

Операнд оператора `await` обычно имеет один из следующих типов .NET: <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask> или <xref:System.Threading.Tasks.ValueTask%601>. Однако любое ожидаемое выражение может быть операндом оператора `await`. Дополнительные сведения см. в разделе об [ожидаемых выражениях](~/_csharplang/spec/expressions.md#awaitable-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

Начиная с версии C# 8.0, вы можете использовать инструкцию `await foreach` для работы с асинхронным потоком данных. Дополнительные сведения см. в статье [Инструкция `foreach`](../keywords/foreach-in.md) и в разделе [Асинхронные потоки](../../whats-new/csharp-8.md#asynchronous-streams) статьи [Новые возможности в C# 8.0](../../whats-new/csharp-8.md).

Тип выражения `await t` является `TResult`, если тип выражения `t` является <xref:System.Threading.Tasks.Task%601> или <xref:System.Threading.Tasks.ValueTask%601>. Если тип `t` является <xref:System.Threading.Tasks.Task> или <xref:System.Threading.Tasks.ValueTask>, тип `await t` является `void`. В обоих случаях, если `t` вызывает исключение, `await t` воспроизводит это исключение. Дополнительные сведения об обработке исключений см. в разделе [Исключения в асинхронных методах](../keywords/try-catch.md#exceptions-in-async-methods) в статье о [try-catch](../keywords/try-catch.md).

Ключевые слова `async` и `await` доступны, начиная с версии C# 5.

## <a name="await-operator-in-the-main-method"></a>Оператор await в методе Main

Начиная с версии C# 7.1 [метод `Main`](../../programming-guide/main-and-command-args/index.md), который является точкой входа приложения, может возвращать `Task` или `Task<int>`, позволяя использовать оператор `await` в теле. В более ранних версиях C#, чтобы убедиться, что метод `Main` ожидает завершения асинхронной операции, можно получить значение свойства <xref:System.Threading.Tasks.Task%601.Result?displayProperty=nameWithType> экземпляра <xref:System.Threading.Tasks.Task%601>, возвращаемого соответствующим асинхронным методом. Для асинхронных операций, которые не создают значение, можно вызвать метод <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>. См. сведения о том, как выбрать версию языка в описании [версий C#](../configure-language-version.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе об [ожидаемых выражениях](~/_csharplang/spec/expressions.md#await-expressions) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Операторы в C#](index.md)
- [async](../keywords/async.md)
- [Асинхронная модель программирования](../../programming-guide/concepts/async/task-asynchronous-programming-model.md)
- [Асинхронное программирование](../../async.md)
- [Подробный обзор асинхронного программирования](../../../standard/async-in-depth.md)
- [Пошаговое руководство. Получение доступа к Интернету с помощью async и await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Учебник. Создание и использование асинхронных потоков с использованием C# 8.0 и .NET Core 3.0](../../tutorials/generate-consume-asynchronous-stream.md)
