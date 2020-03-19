---
title: Создание и использование асинхронных потоков
description: Это расширенное руководство иллюстрирует сценарии, в которых создание и использование асинхронных потоков обеспечивает более естественный способ работы с последовательностями данных, которые могут создаваться асинхронно.
ms.date: 02/10/2019
ms.technology: csharp-async
ms.custom: mvc
ms.openlocfilehash: de090eb9cc1e8b511956313ab5169ee4d07a492f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156744"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a>Учебник. Создание и использование асинхронных потоков с использованием C# 8.0 и .NET Core 3.0

C# 8.0 представляет **асинхронные потоки**, которые моделируют источник потоковых данных, когда можно получить элементы в потоке данных или создать их асинхронно. Асинхронные потоки опираются на новые интерфейсы, представленные в .NET Standard 2.1 и реализованные в .NET Core 3.0, чтобы обеспечить естественную модель программирования для асинхронных источников потоковых данных.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> - Создать источник данных, который формирует последовательность элементов данных асинхронно.
> - Использовать этот источник данных асинхронно.
> - Распознавать, когда новый интерфейс и источник данных предпочтительнее для более ранних синхронных последовательностей данных.

## <a name="prerequisites"></a>Предварительные требования

Вам нужно настроить свой компьютер для выполнения .NET Core, включая компилятор C# 8.0. Компилятор C# 8 доступен, начиная с [версии 16.3 Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) или [в пакете SDK .NET Core 3.0](https://dotnet.microsoft.com/download).

Чтобы вы могли получить доступ к конечной точке GraphQL GitHub, необходимо создать [маркер доступа GitHub](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token). Выберите следующие разрешения для маркеров доступа GitHub.

- repo:status
- public_repo

Храните маркер доступа в надежном месте, чтобы вы могли использовать его для получения доступа к конечной точке API GitHub.

> [!WARNING]
> Храните свой личный маркер доступа в безопасном месте. Любое программное обеспечение с вашим личным маркером доступа может выполнять вызовы API GitHub с помощью ваших прав доступа.

В этом руководстве предполагается, что вы знакомы с C# и .NET, включая Visual Studio или .NET Core CLI.

## <a name="run-the-starter-application"></a>Запуск начального приложения

Вы можете получить код для начального приложения, используемый в этом руководстве в репозитории [dotnet/samples](https://github.com/dotnet/samples) в папке [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start).

Начальное приложение представляет собой консольное приложение, которое использует интерфейс [GraphQL GitHub](https://developer.github.com/v4/) для получения последних проблем, написанных в репозитории [dotnet/docs](https://github.com/dotnet/docs). Начнем с просмотра следующего кода для метода `Main` начального приложения.

[!code-csharp[StarterAppMain](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

Вы можете задать переменную среды `GitHubKey` личному маркеру доступа или заменить последний аргумент в вызове на `GenEnvVariable` с помощью личного маркера доступа. Не помещайте свой код доступа в исходный код, если вы будете сохранять исходный код вместе с другими или помещать его в общий репозиторий с исходным кодом.

После создания клиента GitHub код в `Main` создает объект отчета о ходе выполнения и маркер отмены. После создания этих объектов `Main` вызывает `runPagedQueryAsync`, чтобы получить более 250 недавно созданных проблем. Результаты отобразятся после выполнения этой задачи.

При запуске начального приложения вы можете обнаружить некоторые важные замечания о том, как будет выполняться приложение.  Вы увидите ход выполнения, передаваемый каждой странице, возвращенной с GitHub. Прежде чем GitHub вернет каждую новую страницу проблем, возникает заметная пауза. Наконец, проблемы отображаются только после того, как получены все 10 страниц с GitHub.

## <a name="examine-the-implementation"></a>Изучение реализации

Реализация показывает, почему возникло поведение, обсуждавшееся в предыдущем разделе. Изучите код для `runPagedQueryAsync`.

[!code-csharp[RunPagedQueryStarter](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

Давайте сконцентрируемся на алгоритме разбивки по страницам и асинхронной структуре предыдущего кода. (Дополнительные сведения об API GraphQL GitHub см. в [этой документации](https://developer.github.com/v4/guides/).) Метод `runPagedQueryAsync` перечисляет проблемы от самых последних до самых старых. Чтобы продолжить с предыдущей страницы, он запрашивает по 25 выпусков на страницу и проверяет структуру ответа `pageInfo`. Это следует за стандартной поддержкой страниц GraphQL для многостраничных ответов. Ответ включает в себя объект `pageInfo`, который содержит значение `hasPreviousPages` и `startCursor`, используемые для запроса предыдущей страницы. Проблемы в массиве `nodes`. Метод `runPagedQueryAsync` добавляет эти узлы в массив, который содержит результаты со всех страниц.

После получения и восстановления страницы результатов `runPagedQueryAsync` сообщает о ходе выполнения и проверяет наличие отмены. Если есть запрос на отмену, `runPagedQueryAsync` выдает <xref:System.OperationCanceledException>.

Существует несколько элементов в этом коде, которые можно улучшить. Самое главное, `runPagedQueryAsync` должен выделить хранилище для всех возвращенных проблем. Этот пример останавливается после нахождения 250 проблем, так как для извлечения всех открытых проблем потребуется гораздо больше памяти на их хранение. Кроме того, протоколы для поддержки хода выполнения и отмены делают алгоритм более сложным для понимания при первом чтении. Необходимо определить класс, где предоставляется ход выполнения. Вы также должны отслеживать передачу данных с помощью <xref:System.Threading.CancellationTokenSource> и связанный с ним <xref:System.Threading.CancellationToken>, чтобы понять, где запрашивается отмена и где она предоставляется.

## <a name="async-streams-provide-a-better-way"></a>Предоставление лучшего способа асинхронных потоков

Асинхронные потоки и связанная языковая поддержка обращаются ко всем этим вопросам. Код, который формирует последовательность, теперь может использовать `yield return` для возврата элементов в методе, который был объявлен с помощью модификатора `async`. Вы можете применить асинхронный поток, используя цикл `await foreach`, аналогично любой последовательности с помощью цикла `foreach`.

Эти новые языковые функции зависят от трех новых интерфейсов, добавленных в .NET Standard 2.1 и реализованных в .NET Core 3.0.

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

Большинство разработчиков C# должны знать об этих трех интерфейсах. Они ведут себя подобно своим синхронным аналогам.

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

Один тип, который может быть незнаком, — <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>. Структура `ValueTask` предоставляет API, аналогичный классу <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>. `ValueTask` используется в этих интерфейсах по причинам производительности.

## <a name="convert-to-async-streams"></a>Преобразование в асинхронные потоки

Затем для создания асинхронного потока преобразуйте метод `runPagedQueryAsync`. Сначала измените подпись `runPagedQueryAsync`, чтобы вернуть `IAsyncEnumerable<JToken>`, затем удалите маркер отмены и объекты хода выполнения из списка параметров, как показано в следующем коде.

[!code-csharp[FinishedSignature](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

В следующем коде показано, как начальный код обрабатывает каждую страницу для извлечения.

[!code-csharp[StarterPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

Замените эти три строки следующим кодом.

[!code-csharp[FinishedPaging](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

Вы также можете удалить объявление `finalResults` ранее в этом методе и оператор `return`, следующий за измененным циклом.

Вы завершили изменения для создания асинхронного потока. Готовый метод должен напоминать код, указанный ниже.

[!code-csharp[FinishedGenerate](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

Затем измените код, который использует коллекцию, для асинхронного потока. Найдите следующий код в `Main`, который обрабатывает коллекцию проблем.

[!code-csharp[EnumerateOldStyle](~/samples/snippets/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

Замените код следующим циклом `await foreach`.

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/snippets/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

Элементы потока по умолчанию обрабатываются в захваченном контексте. Чтобы отключить захват контекста, используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Дополнительные сведения о контекстах синхронизации и захвате текущего контекста см. в [статье](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md), посвященной использованию асинхронной модели на основе задач.

Вы можете получить код для 	готового руководства, используемый в репозитории [dotnet/samples](https://github.com/dotnet/samples) в папке [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished).

## <a name="run-the-finished-application"></a>Запуск готового приложения

Снова запустите приложение. Сравните его поведение с поведением начального приложения. Первая страница результатов перечисляется, как только она становится доступной. Поскольку каждую новую страницу запрашивают и извлекают, результаты следующей страницы быстро перечисляются, возникает пауза. Блок `try` / `catch` не требует обработки отмены. Вызывающий может прекратить перечисление коллекции. Отчет о ходе выполнения четко сформирован, так как асинхронный поток формирует результаты скачивания каждой страницы. Состояние каждой возвращенной проблемы включается в цикл `await foreach`. Для отслеживания хода выполнения объект обратного вызова не требуется.

Изучив код, вы увидите улучшения в использовании памяти. Вам больше не нужно выделять коллекцию для хранения всех результатов до их перечисления. Вызывающий может определить, как использовать результаты и нужен ли набор хранилищ.

Запустите начальное и готовое приложение, и вы увидите различия между реализациями самостоятельно. Вы можете удалить маркер доступа GitHub, созданный при начале работы с этим руководством, после завершения изучения. Если злоумышленник получил доступ к этому маркеру, ему удастся получить доступ к API GitHub с помощью ваших учетных данных.
