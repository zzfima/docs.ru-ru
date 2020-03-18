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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="79afa-103">Создание клиентских библиотек gRPC</span><span class="sxs-lookup"><span data-stu-id="79afa-103">Create gRPC client libraries</span></span>

<span data-ttu-id="79afa-104">Нет необходимости распространять клиентские библиотеки для приложения gRPC.</span><span class="sxs-lookup"><span data-stu-id="79afa-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="79afa-105">Можно создать общую `.proto` библиотеку файлов в организации, и другие группы могут использовать эти файлы для генерации клиентского кода в своих собственных проектах.</span><span class="sxs-lookup"><span data-stu-id="79afa-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="79afa-106">Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET Core, вы можете создавать и публиковать пакеты клиентов NuGet в рамках вашего проекта обслуживания.</span><span class="sxs-lookup"><span data-stu-id="79afa-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="79afa-107">Это может быть хорошим способом обмена и продвижения вашего сервиса.</span><span class="sxs-lookup"><span data-stu-id="79afa-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="79afa-108">Одним из преимуществ распространения клиентской библиотеки является то, что вы можете улучшить генерируемые классы gRPC и Protobuf с полезными "удобными" методами и свойствами.</span><span class="sxs-lookup"><span data-stu-id="79afa-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="79afa-109">В клиентском коде, как и на сервере, все классы объявляются как, `partial`так что вы можете расширить их без редактирования генерируемого кода.</span><span class="sxs-lookup"><span data-stu-id="79afa-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="79afa-110">Это означает, что легко добавить конструкторы, методы и рассчитанные свойства к основным типам.</span><span class="sxs-lookup"><span data-stu-id="79afa-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="79afa-111">Вы не должны использовать пользовательский код для обеспечения существенной функциональности.</span><span class="sxs-lookup"><span data-stu-id="79afa-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="79afa-112">Вы не хотите ограничивать эту важную функциональность группами .NET, которые используют общую библиотеку, и не предоставлять ее группам, которые используют другие языки или платформы, такие как Python или Java.</span><span class="sxs-lookup"><span data-stu-id="79afa-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="79afa-113">Убедитесь, что как можно больше команд смогут получить доступ к службе gRPC.</span><span class="sxs-lookup"><span data-stu-id="79afa-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="79afa-114">Лучший способ сделать это `.proto` — обмениваться файлами, чтобы разработчики могли создавать своих собственных клиентов.</span><span class="sxs-lookup"><span data-stu-id="79afa-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="79afa-115">Это особенно верно в многоплатформенных средах, где разные команды часто используют различные языки программирования и платформы, или где ваш API является внешним доступным.</span><span class="sxs-lookup"><span data-stu-id="79afa-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="79afa-116">Полезные расширения</span><span class="sxs-lookup"><span data-stu-id="79afa-116">Useful extensions</span></span>

<span data-ttu-id="79afa-117">Есть два часто используемых интерфейсов в .NET для <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>работы с потоками объектов: и .</span><span class="sxs-lookup"><span data-stu-id="79afa-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="79afa-118">Начиная с .NET Core 3.0 и C'8.0, есть <xref:System.Collections.Generic.IAsyncEnumerable%601> интерфейс для обработки потоков `await foreach` асинхронно, и синтаксис для использования интерфейса.</span><span class="sxs-lookup"><span data-stu-id="79afa-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="79afa-119">В этом разделе представлен многоразовый код для применения этих интерфейсов к потокам gRPC.</span><span class="sxs-lookup"><span data-stu-id="79afa-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="79afa-120">С библиотеками клиентов .NET Core gRPC существует метод `ReadAllAsync` расширения, который `IAsyncStreamReader<T>` создает `IAsyncEnumerable<T>` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="79afa-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="79afa-121">Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания интерфейса `IObservable<T>` может выглядеть как пример в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="79afa-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="79afa-122">Инобытый</span><span class="sxs-lookup"><span data-stu-id="79afa-122">IObservable</span></span>

<span data-ttu-id="79afa-123">Интерфейс `IObservable<T>` является "реактивным" обратным `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="79afa-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="79afa-124">Вместо того, чтобы вытаскивать элементы из потока, реактивный подход позволяет потоку толкать элементы абоненту.</span><span class="sxs-lookup"><span data-stu-id="79afa-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="79afa-125">Это очень похоже на потоки gRPC, и это `IObservable<T>` легко `IAsyncStreamReader<T>` обернуть интерфейс вокруг интерфейса.</span><span class="sxs-lookup"><span data-stu-id="79afa-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="79afa-126">Этот код длиннее `IAsyncEnumerable<T>` кода, так как у C-е нет встроенной поддержки для работы с наблюдаемыми.</span><span class="sxs-lookup"><span data-stu-id="79afa-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="79afa-127">Вы должны создать класс реализации вручную.</span><span class="sxs-lookup"><span data-stu-id="79afa-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="79afa-128">Это общий класс, так что одна реализация работает во всех типах.</span><span class="sxs-lookup"><span data-stu-id="79afa-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="79afa-129">Эта наблюдаемая реализация `Subscribe` позволяет называть метод только один раз, потому что наличие нескольких подписчиков, пытающихся читать из потока, приведет к хаосу.</span><span class="sxs-lookup"><span data-stu-id="79afa-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="79afa-130">Есть операторы, `Replay` например, в [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), которые позволяют буферизации и повторяемый обмен наблюдаемых, которые могут быть использованы с этой реализацией.</span><span class="sxs-lookup"><span data-stu-id="79afa-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="79afa-131">Класс `GrpcStreamSubscription` обрабатывает перечисление: `IAsyncStreamReader`</span><span class="sxs-lookup"><span data-stu-id="79afa-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="79afa-132">Все, что требуется сейчас, это простой метод расширения для создания наблюдаемого из чтения потока.</span><span class="sxs-lookup"><span data-stu-id="79afa-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="79afa-133">Сводка</span><span class="sxs-lookup"><span data-stu-id="79afa-133">Summary</span></span>

<span data-ttu-id="79afa-134">Модели `IAsyncEnumerable` `IObservable` и модели являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET.</span><span class="sxs-lookup"><span data-stu-id="79afa-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="79afa-135">gRPC потоки хорошо отображаются в обеих парадигмах, предлагая тесную интеграцию с .NET Core, а также реактивные и асинхронные стили программирования.</span><span class="sxs-lookup"><span data-stu-id="79afa-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="79afa-136">[Предыдущий](streaming-versus-repeated.md)
>[Следующий](security.md)</span><span class="sxs-lookup"><span data-stu-id="79afa-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
