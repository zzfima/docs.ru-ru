---
title: Создание клиентских библиотек gRPC — gRPC для разработчиков WCF
description: Обсуждение общих клиентских библиотек или пакетов для служб gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: 2135fe8b24a2311a31cb2bed191d290b1112bc66
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967874"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="b5162-103">Создание клиентских библиотек gRPC</span><span class="sxs-lookup"><span data-stu-id="b5162-103">Create gRPC client libraries</span></span>

<span data-ttu-id="b5162-104">Нет необходимости распространять клиентские библиотеки для приложения gRPC.</span><span class="sxs-lookup"><span data-stu-id="b5162-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="b5162-105">В Организации можно создать общую библиотеку `.proto` файлов, и другие команды смогут использовать эти файлы для создания клиентского кода в своих проектах.</span><span class="sxs-lookup"><span data-stu-id="b5162-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="b5162-106">Но если у вас есть частный репозиторий NuGet и многие другие команды используют .NET Core, создание и публикация пакетов NuGet клиента в рамках проекта службы может быть хорошим способом совместного использования и повышения уровня службы.</span><span class="sxs-lookup"><span data-stu-id="b5162-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="b5162-107">Одним из преимуществ распространения клиентской библиотеки является то, что вы можете усовершенствовать созданные классы gRPC и protobuf с помощью полезных "удобных" методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="b5162-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="b5162-108">В клиентском коде, как и на сервере, все классы объявляются как `partial`, поэтому их можно расширять без изменения созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b5162-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="b5162-109">Это означает, что можно легко добавлять в базовые типы конструкторы, методы, вычисляемые свойства и многое другое.</span><span class="sxs-lookup"><span data-stu-id="b5162-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="b5162-110">**Не** следует использовать пользовательский код для предоставления необходимых функциональных возможностей, так как это означает, что функциональность будет ограничена командами .NET, использующими общую библиотеку, а не командами, использующими другие языки или платформы, такие как Python или Java.</span><span class="sxs-lookup"><span data-stu-id="b5162-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="b5162-111">В среде с несколькими платформами, в которой разные группы часто используют разные языки программирования и платформы, или если ваш API доступен извне, просто делитесь `.proto` файлами, чтобы разработчики могли создавать собственные клиенты, чтобы обеспечить максимально возможное количество команд для доступа к службе gRPC.</span><span class="sxs-lookup"><span data-stu-id="b5162-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="b5162-112">Полезные расширения</span><span class="sxs-lookup"><span data-stu-id="b5162-112">Useful extensions</span></span>

<span data-ttu-id="b5162-113">Существует два часто используемых интерфейса .NET для работы с потоками объектов: <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="b5162-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="b5162-114">Начиная с .NET Core 3,0 и C# 8,0, существует интерфейс <xref:System.Collections.Generic.IAsyncEnumerable%601> для асинхронной обработки потоков и `await foreach`ный синтаксис для использования интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b5162-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="b5162-115">В этом разделе представлен многократно используемый код для применения этих интерфейсов к gRPC потокам.</span><span class="sxs-lookup"><span data-stu-id="b5162-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="b5162-116">В клиентских библиотеках .NET Core gRPC существует метод расширения `ReadAllAsync` для `IAsyncStreamReader<T>`, который создает `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="b5162-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="b5162-117">Для разработчиков, использующих реактивное программирование, эквивалентный метод расширения для создания `IObservable<T>` может выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b5162-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="b5162-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="b5162-118">IObservable</span></span>

<span data-ttu-id="b5162-119">`IObservable<T>` интерфейс является обратным инверсией `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="b5162-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="b5162-120">Вместо того чтобы извлекать элементы из потока, реактивный подход позволяет потоку отправлять элементы подписчику.</span><span class="sxs-lookup"><span data-stu-id="b5162-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="b5162-121">Это очень похоже на потоки gRPC, и можно легко обернуть `IObservable<T>` вокруг `IAsyncStreamReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="b5162-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="b5162-122">Этот код длиннее `IAsyncEnumerable<T>` кода, поскольку C# не имеет встроенной поддержки работы с observable, поэтому класс реализации необходимо создать вручную.</span><span class="sxs-lookup"><span data-stu-id="b5162-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="b5162-123">Однако это универсальный класс, поэтому одна реализация будет работать для всех типов.</span><span class="sxs-lookup"><span data-stu-id="b5162-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

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
> <span data-ttu-id="b5162-124">Эта наблюдаемая реализация позволяет только вызывать метод `Subscribe`, так как наличие нескольких подписчиков, пытающихся выполнить чтение из потока, приведет к Chaos.</span><span class="sxs-lookup"><span data-stu-id="b5162-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="b5162-125">В системе есть такие операторы, как `Replay` в [System. Reactive. LINQ](https://www.nuget.org/packages/System.Reactive.Linq) , позволяющие выполнять буферизацию и повторяемый общий доступ к observable, который можно использовать с этой реализацией.</span><span class="sxs-lookup"><span data-stu-id="b5162-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="b5162-126">Класс `GrpcStreamSubscription` обрабатывает перечисление `IAsyncStreamReader`.</span><span class="sxs-lookup"><span data-stu-id="b5162-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

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

<span data-ttu-id="b5162-127">Все, что нужно сделать, это простой метод расширения для создания наблюдаемого элемента из модуля чтения потока.</span><span class="sxs-lookup"><span data-stu-id="b5162-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="b5162-128">Сводка</span><span class="sxs-lookup"><span data-stu-id="b5162-128">Summary</span></span>

<span data-ttu-id="b5162-129">Модели `IAsyncEnumerable` и `IObservable` являются хорошо поддерживаемыми и хорошо документированными способами работы с асинхронными потоками данных в .NET.</span><span class="sxs-lookup"><span data-stu-id="b5162-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="b5162-130">gRPC потоки хорошо сопоставляются с обеими парадигмами, предлагая возможность тесной интеграции с современной платформой .NET Core, а также с помощью неактивных и асинхронных стилей программирования.</span><span class="sxs-lookup"><span data-stu-id="b5162-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b5162-131">[Назад](streaming-versus-repeated.md)
>[Вперед](security.md)</span><span class="sxs-lookup"><span data-stu-id="b5162-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
