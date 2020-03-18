---
title: Создание клиентских библиотек gRPC - gRPC для разработчиков WCF
description: Обсуждение общих клиентских библиотек/пакетов для услуг gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401775"
---
# <a name="create-grpc-client-libraries"></a>Создание клиентских библиотек gRPC

Нет необходимости распространять клиентские библиотеки для приложения gRPC. Можно создать общую `.proto` библиотеку файлов в организации, и другие группы могут использовать эти файлы для генерации клиентского кода в своих собственных проектах. Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET Core, вы можете создавать и публиковать пакеты клиентов NuGet в рамках вашего проекта обслуживания. Это может быть хорошим способом обмена и продвижения вашего сервиса.

Одним из преимуществ распространения клиентской библиотеки является то, что вы можете улучшить генерируемые классы gRPC и Protobuf с полезными "удобными" методами и свойствами. В клиентском коде, как и на сервере, все классы объявляются как, `partial`так что вы можете расширить их без редактирования генерируемого кода. Это означает, что легко добавить конструкторы, методы и рассчитанные свойства к основным типам.

> [!CAUTION]
> Вы не должны использовать пользовательский код для обеспечения существенной функциональности. Вы не хотите ограничивать эту важную функциональность группами .NET, которые используют общую библиотеку, и не предоставлять ее группам, которые используют другие языки или платформы, такие как Python или Java.

Убедитесь, что как можно больше команд смогут получить доступ к службе gRPC. Лучший способ сделать это `.proto` — обмениваться файлами, чтобы разработчики могли создавать своих собственных клиентов. Это особенно верно в многоплатформенных средах, где разные команды часто используют различные языки программирования и платформы, или где ваш API является внешним доступным.

## <a name="useful-extensions"></a>Полезные расширения

Есть два часто используемых интерфейсов в .NET для <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>работы с потоками объектов: и . Начиная с .NET Core 3.0 и C'8.0, есть <xref:System.Collections.Generic.IAsyncEnumerable%601> интерфейс для обработки потоков `await foreach` асинхронно, и синтаксис для использования интерфейса. В этом разделе представлен многоразовый код для применения этих интерфейсов к потокам gRPC.

С библиотеками клиентов .NET Core gRPC существует метод `ReadAllAsync` расширения, который `IAsyncStreamReader<T>` создает `IAsyncEnumerable<T>` интерфейс. Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания интерфейса `IObservable<T>` может выглядеть как пример в следующем разделе.

### <a name="iobservable"></a>Инобытый

Интерфейс `IObservable<T>` является "реактивным" обратным `IEnumerable<T>`. Вместо того, чтобы вытаскивать элементы из потока, реактивный подход позволяет потоку толкать элементы абоненту. Это очень похоже на потоки gRPC, и это `IObservable<T>` легко `IAsyncStreamReader<T>` обернуть интерфейс вокруг интерфейса.

Этот код длиннее `IAsyncEnumerable<T>` кода, так как у C-е нет встроенной поддержки для работы с наблюдаемыми. Вы должны создать класс реализации вручную. Это общий класс, так что одна реализация работает во всех типах.

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
> Эта наблюдаемая реализация `Subscribe` позволяет называть метод только один раз, потому что наличие нескольких подписчиков, пытающихся читать из потока, приведет к хаосу. Есть операторы, `Replay` например, в [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), которые позволяют буферизации и повторяемый обмен наблюдаемых, которые могут быть использованы с этой реализацией.

Класс `GrpcStreamSubscription` обрабатывает перечисление: `IAsyncStreamReader`

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

Все, что требуется сейчас, это простой метод расширения для создания наблюдаемого из чтения потока.

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

Модели `IAsyncEnumerable` `IObservable` и модели являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET. gRPC потоки хорошо отображаются в обеих парадигмах, предлагая тесную интеграцию с .NET Core, а также реактивные и асинхронные стили программирования.

>[!div class="step-by-step"]
>[Предыдущий](streaming-versus-repeated.md)
>[Следующий](security.md)
