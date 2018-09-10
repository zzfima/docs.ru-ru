---
title: Шаблоны асинхронного программирования
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous design patterns, .NET Framework
- .NET Framework, asynchronous design patterns
ms.assetid: 4ece5c0b-f8fe-4114-9862-ac02cfe5a5d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e399a512d2bee636aec35e008c0632ce9c5fa781
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249040"
---
# <a name="asynchronous-programming-patterns"></a><span data-ttu-id="8828e-102">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="8828e-102">Asynchronous Programming Patterns</span></span>

<span data-ttu-id="8828e-103">Платформа .NET Framework предоставляет три шаблона для выполнения асинхронных операций:</span><span class="sxs-lookup"><span data-stu-id="8828e-103">The .NET Framework provides three patterns for performing asynchronous operations:</span></span>  
  
- <span data-ttu-id="8828e-104">Шаблон **асинхронной модели программирования (АРМ)** (также называемый шаблоном <xref:System.IAsyncResult>), где асинхронные операции требуют методов `Begin` и `End` (например, асинхронные операции записи `BeginWrite` и `EndWrite`).</span><span class="sxs-lookup"><span data-stu-id="8828e-104">**Asynchronous Programming Model (APM)** pattern (also called the <xref:System.IAsyncResult> pattern), where asynchronous operations require `Begin` and `End` methods (for example, `BeginWrite` and `EndWrite` for asynchronous write operations).</span></span> <span data-ttu-id="8828e-105">Этот шаблон не рекомендуется использовать для разработки новых приложений.</span><span class="sxs-lookup"><span data-stu-id="8828e-105">This pattern is no longer recommended for new development.</span></span> <span data-ttu-id="8828e-106">Дополнительные сведения см. в статье [Асинхронная модель программирования (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span><span class="sxs-lookup"><span data-stu-id="8828e-106">For more information, see [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md).</span></span>  
  
- <span data-ttu-id="8828e-107">**Асинхронный шаблон на основе событий (EAP)**, который требует метод с суффиксом `Async`, а также одно или несколько событий, типов делегата обработчика событий и производных типов `EventArg`.</span><span class="sxs-lookup"><span data-stu-id="8828e-107">**Event-based Asynchronous Pattern (EAP)**, which requires a method that has the `Async` suffix, and also requires one or more events, event handler delegate types, and `EventArg`-derived types.</span></span> <span data-ttu-id="8828e-108">Протокол EAP был введен в платформа.NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="8828e-108">EAP was introduced in the .NET Framework 2.0.</span></span> <span data-ttu-id="8828e-109">Не рекомендуется для новых разработок.</span><span class="sxs-lookup"><span data-stu-id="8828e-109">It is no longer recommended for new development.</span></span> <span data-ttu-id="8828e-110">Дополнительные сведения см. в разделе [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="8828e-110">For more information, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
- <span data-ttu-id="8828e-111">**Асинхронный шаблон на основе задач (TAP)**, который использует один метод для запуска и завершения асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="8828e-111">**Task-based Asynchronous Pattern (TAP)**, which uses a single method to represent the initiation and completion of an asynchronous operation.</span></span> <span data-ttu-id="8828e-112">Шаблон ТАР был введен в платформа.NET Framework 4 и рекомендуется для асинхронного программирования в платформа.NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8828e-112">TAP was introduced in the .NET Framework 4 and is the recommended approach to asynchronous programming in the .NET Framework.</span></span> <span data-ttu-id="8828e-113">Ключевые слова [async](~/docs/csharp/language-reference/keywords/async.md) и [await](~/docs/csharp/language-reference/keywords/await.md) в C#, а также операторы [Async](~/docs/visual-basic/language-reference/modifiers/async.md) и [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) в языке Visual Basic добавляют поддержку языка для ТАР.</span><span class="sxs-lookup"><span data-stu-id="8828e-113">The [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) keywords in C# and the [Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) operators in Visual Basic Language add language support for TAP.</span></span> <span data-ttu-id="8828e-114">Дополнительные сведения см. в разделе [Асинхронный шаблон, основанный на задачах (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="8828e-114">For more information, see [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md).</span></span>  
  
## <a name="comparing-patterns"></a><span data-ttu-id="8828e-115">Сравнение шаблонов</span><span class="sxs-lookup"><span data-stu-id="8828e-115">Comparing Patterns</span></span>  

<span data-ttu-id="8828e-116">Для быстрого сравнения, как с помощью трех шаблонов моделировать асинхронные операции, рассмотрим метод `Read`, который считывает указанный объем данных в предоставленный буфер, начиная с заданного смещения:</span><span class="sxs-lookup"><span data-stu-id="8828e-116">For a quick comparison of how the three patterns model asynchronous operations, consider a `Read` method that reads a specified amount of data into a provided buffer starting at a specified offset:</span></span>  
  
```csharp  
public class MyClass  
{  
    public int Read(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="8828e-117">Аналог APM этого метода приведет к методам `BeginRead` и `EndRead`:</span><span class="sxs-lookup"><span data-stu-id="8828e-117">The APM counterpart of this method would expose the `BeginRead` and `EndRead` methods:</span></span>  
  
```csharp  
public class MyClass  
{  
    public IAsyncResult BeginRead(  
        byte [] buffer, int offset, int count,   
        AsyncCallback callback, object state);  
    public int EndRead(IAsyncResult asyncResult);  
}  
```  
  
<span data-ttu-id="8828e-118">Аналог EAP будут предоставлять следующий набор типов и членов:</span><span class="sxs-lookup"><span data-stu-id="8828e-118">The EAP counterpart would expose the following set of types and members:</span></span>  
  
```csharp  
public class MyClass  
{  
    public void ReadAsync(byte [] buffer, int offset, int count);  
    public event ReadCompletedEventHandler ReadCompleted;  
}  
```  
  
<span data-ttu-id="8828e-119">Аналог TAP приведет к следующему одному методу `ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="8828e-119">The TAP counterpart would expose the following single `ReadAsync` method:</span></span>  
  
```csharp  
public class MyClass  
{  
    public Task<int> ReadAsync(byte [] buffer, int offset, int count);  
}  
```  
  
<span data-ttu-id="8828e-120">Для подробного обсуждения TAP, APM и EAP перейдите по ссылкам в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="8828e-120">For a comprehensive discussion of TAP, APM, and EAP, see the links provided in the next section.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="8828e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8828e-121">Related topics</span></span>

| <span data-ttu-id="8828e-122">Заголовок</span><span class="sxs-lookup"><span data-stu-id="8828e-122">Title</span></span> | <span data-ttu-id="8828e-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="8828e-123">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="8828e-124">Асинхронная модель программирования (APM)</span><span class="sxs-lookup"><span data-stu-id="8828e-124">Asynchronous Programming Model (APM)</span></span>](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) | <span data-ttu-id="8828e-125">Описание устаревшей модели, использующей интерфейс <xref:System.IAsyncResult> для предоставления асинхронного поведения.</span><span class="sxs-lookup"><span data-stu-id="8828e-125">Describes the legacy model that uses the <xref:System.IAsyncResult> interface to provide asynchronous behavior.</span></span> <span data-ttu-id="8828e-126">Этот шаблон не рекомендуется использовать для новых разработок.</span><span class="sxs-lookup"><span data-stu-id="8828e-126">This model is no longer recommended for new development.</span></span> |
| [<span data-ttu-id="8828e-127">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="8828e-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) | <span data-ttu-id="8828e-128">Описание события устаревшие модели для предоставления асинхронного поведения.</span><span class="sxs-lookup"><span data-stu-id="8828e-128">Describes the event-based legacy model for providing asynchronous behavior.</span></span> <span data-ttu-id="8828e-129">Этот шаблон не рекомендуется использовать для новых разработок.</span><span class="sxs-lookup"><span data-stu-id="8828e-129">This model is no longer recommended for new development.</span></span> |
| <span data-ttu-id="8828e-130">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) (Асинхронный шаблон, основанный на задачах (TAP))</span><span class="sxs-lookup"><span data-stu-id="8828e-130">[Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)</span></span> | <span data-ttu-id="8828e-131">Описание новой асинхронной модели на основе пространства имен <xref:System.Threading.Tasks>.</span><span class="sxs-lookup"><span data-stu-id="8828e-131">Describes the new asynchronous pattern based on the <xref:System.Threading.Tasks> namespace.</span></span> <span data-ttu-id="8828e-132">Эта модель является рекомендуемым подходом для асинхронного программирования в NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="8828e-132">This model is the recommended approach to asynchronous programming in the .NET Framework 4 and later versions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8828e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="8828e-133">See also</span></span>

- [<span data-ttu-id="8828e-134">Асинхронное программирование на C#</span><span class="sxs-lookup"><span data-stu-id="8828e-134">Asynchronous programming in C#</span></span>](~/docs/csharp/async.md)   
- [<span data-ttu-id="8828e-135">Асинхронное программирование на F#</span><span class="sxs-lookup"><span data-stu-id="8828e-135">Async Programming in F#</span></span>](~/docs/fsharp/tutorials/asynchronous-and-concurrent-programming/async.md)   
- [<span data-ttu-id="8828e-136">Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8828e-136">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/concepts/async/index.md)
