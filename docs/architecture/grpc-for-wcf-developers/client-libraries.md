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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="446cc-103">Создание клиентских библиотек gRPC</span><span class="sxs-lookup"><span data-stu-id="446cc-103">Create gRPC client libraries</span></span>

<span data-ttu-id="446cc-104">Нет необходимости распространять клиентские библиотеки для приложения gRPC.</span><span class="sxs-lookup"><span data-stu-id="446cc-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="446cc-105">В Организации можно создать общую библиотеку `.proto` файлов, и другие команды смогут использовать эти файлы для создания клиентского кода в своих проектах.</span><span class="sxs-lookup"><span data-stu-id="446cc-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="446cc-106">Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET Core, вы можете создавать и публиковать клиентские пакеты NuGet в рамках проекта службы.</span><span class="sxs-lookup"><span data-stu-id="446cc-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="446cc-107">Это может быть хорошим способом совместного использования и повышения уровня службы.</span><span class="sxs-lookup"><span data-stu-id="446cc-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="446cc-108">Одним из преимуществ распространения клиентской библиотеки является то, что вы можете усовершенствовать созданные классы gRPC и protobuf с помощью полезных "удобных" методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="446cc-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="446cc-109">В клиентском коде, как и на сервере, все классы объявляются как `partial`, поэтому их можно расширить, не редактируя созданный код.</span><span class="sxs-lookup"><span data-stu-id="446cc-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="446cc-110">Это означает, что можно легко добавить в базовые типы конструкторы, методы и вычисляемые свойства.</span><span class="sxs-lookup"><span data-stu-id="446cc-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="446cc-111">Не следует использовать пользовательский код для предоставления необходимых функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="446cc-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="446cc-112">Вы не хотите ограничивать эту функциональность командам .NET, которые используют общую библиотеку, и не предоставлять ее группам, использующим другие языки или платформы, такие как Python или Java.</span><span class="sxs-lookup"><span data-stu-id="446cc-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="446cc-113">Убедитесь, что максимально возможное количество команд может получить доступ к службе gRPC.</span><span class="sxs-lookup"><span data-stu-id="446cc-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="446cc-114">Лучший способ сделать это — предоставить общий доступ к файлам `.proto`, чтобы разработчики могли создавать собственные клиенты.</span><span class="sxs-lookup"><span data-stu-id="446cc-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="446cc-115">Это особенно справедливо в многоплатформенной среде, где разные группы часто используют разные языки программирования и платформы, или если ваш API доступен извне.</span><span class="sxs-lookup"><span data-stu-id="446cc-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="446cc-116">Полезные расширения</span><span class="sxs-lookup"><span data-stu-id="446cc-116">Useful extensions</span></span>

<span data-ttu-id="446cc-117">Существует два часто используемых интерфейса .NET для работы с потоками объектов: <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="446cc-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="446cc-118">Начиная с .NET Core 3,0 и C# 8,0, существует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601> для асинхронной обработки потоков и `await foreach`ный синтаксис для использования интерфейса.</span><span class="sxs-lookup"><span data-stu-id="446cc-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="446cc-119">В этом разделе представлен многократно используемый код для применения этих интерфейсов к gRPC потокам.</span><span class="sxs-lookup"><span data-stu-id="446cc-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="446cc-120">В клиентских библиотеках .NET Core gRPC существует метод расширения `ReadAllAsync` для `IAsyncStreamReader<T>`, который создает интерфейс `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="446cc-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="446cc-121">Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания интерфейса `IObservable<T>` может выглядеть как пример в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="446cc-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="446cc-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="446cc-122">IObservable</span></span>

<span data-ttu-id="446cc-123">`IObservable<T>` интерфейс является обратным инверсией `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="446cc-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="446cc-124">Вместо того чтобы извлекать элементы из потока, реактивный подход позволяет потоку отправлять элементы подписчику.</span><span class="sxs-lookup"><span data-stu-id="446cc-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="446cc-125">Это очень похоже на потоки gRPC, и можно легко обернуть интерфейс `IObservable<T>` вокруг интерфейса `IAsyncStreamReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="446cc-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="446cc-126">Этот код длиннее, чем код `IAsyncEnumerable<T>`, поскольку C# не имеет встроенной поддержки для работы с observable.</span><span class="sxs-lookup"><span data-stu-id="446cc-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="446cc-127">Класс реализации необходимо создать вручную.</span><span class="sxs-lookup"><span data-stu-id="446cc-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="446cc-128">Однако это универсальный класс, поэтому одна реализация работает для всех типов.</span><span class="sxs-lookup"><span data-stu-id="446cc-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="446cc-129">Эта наблюдаемая реализация позволяет вызывать метод `Subscribe` только один раз, так как наличие нескольких подписчиков, пытающихся выполнить чтение из потока, приведет к Chaos.</span><span class="sxs-lookup"><span data-stu-id="446cc-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="446cc-130">Существуют операторы, такие как `Replay` в [System. Reactive. LINQ](https://www.nuget.org/packages/System.Reactive.Linq), позволяющие выполнять буферизацию и повторяемый общий доступ к observable, который можно использовать с этой реализацией.</span><span class="sxs-lookup"><span data-stu-id="446cc-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="446cc-131">Класс `GrpcStreamSubscription` обрабатывает перечисление `IAsyncStreamReader`.</span><span class="sxs-lookup"><span data-stu-id="446cc-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="446cc-132">Все, что нужно сделать, это простой метод расширения для создания наблюдаемого элемента из модуля чтения потока.</span><span class="sxs-lookup"><span data-stu-id="446cc-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="446cc-133">Сводка</span><span class="sxs-lookup"><span data-stu-id="446cc-133">Summary</span></span>

<span data-ttu-id="446cc-134">Модели `IAsyncEnumerable` и `IObservable` являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET.</span><span class="sxs-lookup"><span data-stu-id="446cc-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="446cc-135">gRPC потоки хорошо сопоставляются с обеими парадигмами, предлагают близкую интеграцию с .NET Core, а также реактивный и асинхронный стиль программирования.</span><span class="sxs-lookup"><span data-stu-id="446cc-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="446cc-136">[Назад](streaming-versus-repeated.md)
>[Вперед](security.md)</span><span class="sxs-lookup"><span data-stu-id="446cc-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
