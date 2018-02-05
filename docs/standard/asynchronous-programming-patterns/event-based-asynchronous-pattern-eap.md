---
title: "Асинхронная модель на основе событий (EAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2a83d638255d27317ba5d566ab46b83526659365
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="3c345-102">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="3c345-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="3c345-103">Существует несколько способов предоставить асинхронные возможности клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="3c345-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="3c345-104">Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="3c345-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c345-105">Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], библиотека параллельных задач предоставляет новую модель для асинхронного и параллельного программирования.</span><span class="sxs-lookup"><span data-stu-id="3c345-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="3c345-106">Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c345-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c345-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3c345-107">In This Section</span></span>  
 [<span data-ttu-id="3c345-108">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="3c345-109">Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.</span><span class="sxs-lookup"><span data-stu-id="3c345-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="3c345-110">Реализация асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="3c345-111">Описывает стандартизированный способ упаковки класса, имеющего асинхронные возможности.</span><span class="sxs-lookup"><span data-stu-id="3c345-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="3c345-112">Рекомендации по реализации асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="3c345-113">Описывает требования для предоставления асинхронных возможностей в соответствии с асинхронной моделью на основе событий.</span><span class="sxs-lookup"><span data-stu-id="3c345-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="3c345-114">Определение, когда следует реализовать асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="3c345-115">Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="3c345-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="3c345-116">Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="3c345-117">Демонстрирует, как создать компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="3c345-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="3c345-118">Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента при любой модели приложения.</span><span class="sxs-lookup"><span data-stu-id="3c345-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="3c345-119">Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="3c345-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="3c345-120">Описывает использование компонента, поддерживающего асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="3c345-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3c345-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="3c345-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="3c345-122">Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="3c345-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="3c345-123">Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="3c345-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="3c345-124">Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="3c345-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c345-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3c345-125">Related Sections</span></span>  
 [<span data-ttu-id="3c345-126">Библиотека параллельных задач (TPL)</span><span class="sxs-lookup"><span data-stu-id="3c345-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="3c345-127">Описание модели программирования для асинхронных и параллельных операций.</span><span class="sxs-lookup"><span data-stu-id="3c345-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="3c345-128">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="3c345-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="3c345-129">Описание многопоточных функциональных возможностей платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c345-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="3c345-130">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="3c345-130">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="3c345-131">Описание возможностей многопоточности языков C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c345-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c345-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3c345-132">See Also</span></span>  
 [<span data-ttu-id="3c345-133">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="3c345-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="3c345-134">События</span><span class="sxs-lookup"><span data-stu-id="3c345-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="3c345-135">Многопоточность в компонентах</span><span class="sxs-lookup"><span data-stu-id="3c345-135">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="3c345-136">Шаблоны асинхронного программирования</span><span class="sxs-lookup"><span data-stu-id="3c345-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
