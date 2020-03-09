---
title: Создание клиентских библиотек gRPC — gRPC для разработчиков WCF
description: Обсуждение общих клиентских библиотек или пакетов для служб gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675174"
---
# <a name="create-grpc-client-libraries"></a>Создание клиентских библиотек gRPC

Нет необходимости распространять клиентские библиотеки для приложения gRPC. В Организации можно создать общую библиотеку `.proto` файлов, и другие команды смогут использовать эти файлы для создания клиентского кода в своих проектах. Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET Core, вы можете создавать и публиковать клиентские пакеты NuGet в рамках проекта службы. Это может быть хорошим способом совместного использования и повышения уровня службы.

Одним из преимуществ распространения клиентской библиотеки является то, что вы можете усовершенствовать созданные классы gRPC и protobuf с помощью полезных "удобных" методов и свойств. В клиентском коде, как и на сервере, все классы объявляются как `partial`, поэтому их можно расширить, не редактируя созданный код. Это означает, что можно легко добавить в базовые типы конструкторы, методы и вычисляемые свойства.

> [!CAUTION]
> Не следует использовать пользовательский код для предоставления необходимых функциональных возможностей. Вы не хотите ограничивать эту функциональность командам .NET, которые используют общую библиотеку, и не предоставлять ее группам, использующим другие языки или платформы, такие как Python или Java.

Убедитесь, что максимально возможное количество команд может получить доступ к службе gRPC. Лучший способ сделать это — предоставить общий доступ к файлам `.proto`, чтобы разработчики могли создавать собственные клиенты. Это особенно справедливо в многоплатформенной среде, где разные группы часто используют разные языки программирования и платформы, или если ваш API доступен извне.

## <a name="useful-extensions"></a>Полезные расширения

Существует два часто используемых интерфейса .NET для работы с потоками объектов: <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IObservable%601>. Начиная с .NET Core 3,0 и C# 8,0, существует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601> для асинхронной обработки потоков и `await foreach`ный синтаксис для использования интерфейса. В этом разделе представлен многократно используемый код для применения этих интерфейсов к gRPC потокам.

В клиентских библиотеках .NET Core gRPC существует метод расширения `ReadAllAsync` для `IAsyncStreamReader<T>`, который создает интерфейс `IAsyncEnumerable<T>`. Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания интерфейса `IObservable<T>` может выглядеть как пример в следующем разделе.

### <a name="iobservable"></a>IObservable

`IObservable<T>` интерфейс является обратным инверсией `IEnumerable<T>`. Вместо того чтобы извлекать элементы из потока, реактивный подход позволяет потоку отправлять элементы подписчику. Это очень похоже на потоки gRPC, и можно легко обернуть интерфейс `IObservable<T>` вокруг интерфейса `IAsyncStreamReader<T>`.

Этот код длиннее, чем код `IAsyncEnumerable<T>`, поскольку C# не имеет встроенной поддержки для работы с observable. Класс реализации необходимо создать вручную. Однако это универсальный класс, поэтому одна реализация работает для всех типов.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> Эта наблюдаемая реализация позволяет вызывать метод `Subscribe` только один раз, так как наличие нескольких подписчиков, пытающихся выполнить чтение из потока, приведет к Chaos. Существуют операторы, такие как `Replay` в [System. Reactive. LINQ](https://www.nuget.org/packages/System.Reactive.Linq), позволяющие выполнять буферизацию и повторяемый общий доступ к observable, который можно использовать с этой реализацией.

Класс `GrpcStreamSubscription` обрабатывает перечисление `IAsyncStreamReader`.

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

Все, что нужно сделать, это простой метод расширения для создания наблюдаемого элемента из модуля чтения потока.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>Сводка

Модели `IAsyncEnumerable` и `IObservable` являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET. gRPC потоки хорошо сопоставляются с обеими парадигмами, предлагают близкую интеграцию с .NET Core, а также реактивный и асинхронный стиль программирования.

>[!div class="step-by-step"]
>[Назад](streaming-versus-repeated.md)
>[Вперед](security.md)
