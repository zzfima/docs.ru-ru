---
title: Асинхронная модель на основе событий (EAP)
ms.date: 07/23/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
ms.openlocfilehash: ee8c90d63478e444b7d25cb7cbb5c969963d7c63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130943"
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="872d2-102">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="872d2-102">Event-based Asynchronous Pattern (EAP)</span></span>

<span data-ttu-id="872d2-103">Существует несколько способов предоставить асинхронные возможности клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="872d2-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="872d2-104">Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="872d2-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="872d2-105">Начиная с версии .NET Framework 4 библиотека параллельных задач предоставляет новую модель для асинхронного и параллельного программирования.</span><span class="sxs-lookup"><span data-stu-id="872d2-105">Starting with the .NET Framework 4, the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="872d2-106">Дополнительные сведения см. в разделах [Библиотека параллельных задач (TPL)](../parallel-programming/task-parallel-library-tpl.md) и [Асинхронная модель на основе задач (TAP)](task-based-asynchronous-pattern-tap.md).</span><span class="sxs-lookup"><span data-stu-id="872d2-106">For more information, see [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) and [Task-based Asynchronous Pattern (TAP)](task-based-asynchronous-pattern-tap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="872d2-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="872d2-107">In This Section</span></span>

 [<span data-ttu-id="872d2-108">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="872d2-108">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="872d2-109">Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.</span><span class="sxs-lookup"><span data-stu-id="872d2-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="872d2-110">Реализация асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="872d2-110">Implementing the Event-based Asynchronous Pattern</span></span>](implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-111">Описывает стандартизированный способ упаковки класса, имеющего асинхронные возможности.</span><span class="sxs-lookup"><span data-stu-id="872d2-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="872d2-112">Рекомендации по реализации асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="872d2-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-113">Описывает требования для предоставления асинхронных возможностей в соответствии с асинхронной моделью на основе событий.</span><span class="sxs-lookup"><span data-stu-id="872d2-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="872d2-114">Определение, когда следует реализовать асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="872d2-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-115">Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>, представленного [асинхронной моделью программирования (APM)](asynchronous-programming-model-apm.md)</span><span class="sxs-lookup"><span data-stu-id="872d2-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern represented by the [Asynchronous Programming Model (APM)](asynchronous-programming-model-apm.md)</span></span>
  
 [<span data-ttu-id="872d2-116">Практическое руководство. Реализация компонента, поддерживающего асинхронную модель на основе событий</span><span class="sxs-lookup"><span data-stu-id="872d2-116">How to: Implement a Component That Supports the Event-based Asynchronous Pattern</span></span>](component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-117">Описывает, как создать компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="872d2-117">Describes how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="872d2-118">Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента при любой модели приложения.</span><span class="sxs-lookup"><span data-stu-id="872d2-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  

 [<span data-ttu-id="872d2-119">Практическое руководство. Реализация клиента асинхронной модели на основе событий</span><span class="sxs-lookup"><span data-stu-id="872d2-119">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>](how-to-implement-a-client-of-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-120">Описывает, как создать клиент, который использует компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="872d2-120">Describes how to create a client that uses a component that implements the Event-based Asynchronous Pattern.</span></span>
  
 [<span data-ttu-id="872d2-121">Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="872d2-121">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="872d2-122">Описывает использование компонента, поддерживающего асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="872d2-122">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="872d2-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="872d2-123">Reference</span></span>

 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="872d2-124">Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="872d2-124">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="872d2-125">Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="872d2-125">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="872d2-126">Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="872d2-126">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="872d2-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="872d2-127">Related Sections</span></span>

 [<span data-ttu-id="872d2-128">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="872d2-128">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="872d2-129">Описание модели программирования для асинхронных и параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="872d2-129">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="872d2-130">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="872d2-130">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="872d2-131">Описывает многопоточные функциональные возможности в .NET.</span><span class="sxs-lookup"><span data-stu-id="872d2-131">Describes multithreading features in .NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872d2-132">См. также</span><span class="sxs-lookup"><span data-stu-id="872d2-132">See also</span></span>

- [<span data-ttu-id="872d2-133">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="872d2-133">Managed Threading Best Practices</span></span>](../threading/managed-threading-best-practices.md)
- [<span data-ttu-id="872d2-134">События</span><span class="sxs-lookup"><span data-stu-id="872d2-134">Events</span></span>](../events/index.md)
- [<span data-ttu-id="872d2-135">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="872d2-135">Asynchronous Programming Design Patterns</span></span>](index.md)
