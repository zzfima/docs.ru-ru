---
title: Шаблоны асинхронного программирования
ms.date: 10/16/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36798fabcd42cf7e04b0a6f288736503eecad88b
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169129"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="612c0-102">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="612c0-102">Asynchronous programming patterns</span></span>

<span data-ttu-id="612c0-103">В .NET есть три шаблона для выполнения асинхронных операций:</span><span class="sxs-lookup"><span data-stu-id="612c0-103">.NET provides three patterns for performing asynchronous operations:</span></span>  

- <span data-ttu-id="612c0-104">**Асинхронный шаблон на основе задач (TAP)** , который использует один метод для запуска и завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="612c0-104">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="612c0-105">Шаблон TAP был реализован в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="612c0-105">TAP was introduced in the .NET Framework 4.</span></span> <span data-ttu-id="612c0-106">**Именно его рекомендуется использовать для асинхронного программирования в .NET**.</span><span class="sxs-lookup"><span data-stu-id="612c0-106">**It's the recommended approach to asynchronous programming in .NET.**</span></span> <span data-ttu-id="612c0-107">Ключевые слова [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) в C#, а также операторы [Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic добавляют для TAP поддержку языка.</span><span class="sxs-lookup"><span data-stu-id="612c0-107">The [async](../../csharp/language-reference/keywords/async.md) and [await](../../csharp/language-reference/operators/await.md) keywords in C# and the [Async](../../visual-basic/language-reference/modifiers/async.md) and [Await](../../visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic add language support for TAP.</span></span> <span data-ttu-id="612c0-108">Дополнительные сведения см. в разделе [Асинхронный шаблон, основанный на задачах (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="612c0-108">For more information, see [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>  

- <span data-ttu-id="612c0-109">**Асинхронная модель на основе событий (EAP)** . Это устаревшая модель на основе событий, обеспечивающая работу в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="612c0-109">**Event-based Asynchronous Pattern (EAP)**, which is the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="612c0-110">Для нее требуется метод с суффиксом `Async`, одно или несколько событий, типы делегатов обработчика событий и производные типы `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="612c0-110">It requires a method that has the `Async` suffix and one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="612c0-111">Протокол EAP был введен в платформа.NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="612c0-111">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="612c0-112">Ее не рекомендуется использовать для новых разработок.</span><span class="sxs-lookup"><span data-stu-id="612c0-112">It's no longer recommended for new development.</span></span> <span data-ttu-id="612c0-113">Дополнительные сведения см. в разделе [Асинхронная модель на основе событий (EAP)](event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="612c0-113">For more information, see [Event-based Asynchronous Pattern (EAP)](event-based-asynchronous-pattern-eap.md).</span></span>  

- <span data-ttu-id="612c0-114">**Модель асинхронного программирования (APM)** (также называется шаблоном <xref:System.IAsyncResult>). Это устаревшая модель, в которой для реализации асинхронного поведения используется интерфейс <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="612c0-114">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), which is the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="612c0-115">В этом шаблоне для синхронных операций требуются методы `Begin` и `End` (например, `BeginWrite` и `EndWrite` позволяют реализовать асинхронную операцию записи).</span><span class="sxs-lookup"><span data-stu-id="612c0-115">In this pattern, synchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` to implement an asynchronous write operation).</span></span> <span data-ttu-id="612c0-116">Этот шаблон не рекомендуется использовать для разработки новых приложений.</span><span class="sxs-lookup"><span data-stu-id="612c0-116">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="612c0-117">Дополнительные сведения см. в статье [Асинхронная модель программирования (APM)](asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="612c0-117">For more information, see [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md).</span></span>  
  
## <a name="comparison-of-patterns"></a><span data-ttu-id="612c0-118">Сравнение шаблонов</span><span class="sxs-lookup"><span data-stu-id="612c0-118">Comparison of patterns</span></span>

<span data-ttu-id="612c0-119">Для быстрого сравнения, как с помощью трех шаблонов моделировать асинхронные операции, рассмотрим метод `Read`, который считывает указанный объем данных в предоставленный буфер, начиная с заданного смещения:</span><span class="sxs-lookup"><span data-stu-id="612c0-119">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  

<span data-ttu-id="612c0-120">Этот же метод с использованием TAP предоставит такой метод `ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="612c0-120">The TAP counterpart of this method would expose the following single `ReadAsync` method:</span></span>  
  
```csharp
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```

<span data-ttu-id="612c0-121">Аналог EAP будут предоставлять следующий набор типов и членов:</span><span class="sxs-lookup"><span data-stu-id="612c0-121">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="612c0-122">Этот же метод с APM предоставит методы `BeginRead` и `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="612c0-122">The APM counterpart would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  

## <a name="see-also"></a><span data-ttu-id="612c0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="612c0-123">See also</span></span>

- [<span data-ttu-id="612c0-124">Подробный обзор асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="612c0-124">Async in depth</span></span>](../async-in-depth.md)
- [<span data-ttu-id="612c0-125">Асинхронное программирование на C#</span><span class="sxs-lookup"><span data-stu-id="612c0-125">Asynchronous programming in C#</span></span>](../../csharp/async.md)
- [<span data-ttu-id="612c0-126">Асинхронное программирование на F#</span><span class="sxs-lookup"><span data-stu-id="612c0-126">Async Programming in F#</span></span>](../../fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)
- [<span data-ttu-id="612c0-127">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="612c0-127">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/async/index.md)
