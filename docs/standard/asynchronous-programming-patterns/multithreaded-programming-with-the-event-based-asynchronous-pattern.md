---
title: "Многопоточное программирование с использованием асинхронной модели, основанной на событиях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 557d639cc8a4e7ade2cfbd1f5d7264bca226d273
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="2a0c0-102">Многопоточное программирование с использованием асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="2a0c0-103">Существует несколько способов предоставить асинхронные возможности клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="2a0c0-104">Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a0c0-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2a0c0-105">In This Section</span></span>  
 [<span data-ttu-id="2a0c0-106">Обзор асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="2a0c0-107">Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="2a0c0-108">Реализация асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2a0c0-109">Описывает стандартизированный способ упаковки класса, имеющего асинхронные возможности.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="2a0c0-110">Рекомендации по реализации асинхронной модели, основанной на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2a0c0-111">Описывает требования для предоставления асинхронных возможностей в соответствии с асинхронной моделью на основе событий.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="2a0c0-112">Определение, когда следует реализовать асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2a0c0-113">Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="2a0c0-114">Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2a0c0-115">Демонстрирует, как создать компонент, реализующий асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="2a0c0-116">Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента при любой модели приложения.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="2a0c0-117">Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях</span><span class="sxs-lookup"><span data-stu-id="2a0c0-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="2a0c0-118">Описывает использование компонента, поддерживающего асинхронную модель на основе событий.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2a0c0-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2a0c0-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="2a0c0-120">Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="2a0c0-121">Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="2a0c0-122">Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="2a0c0-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a0c0-123">См. также</span><span class="sxs-lookup"><span data-stu-id="2a0c0-123">See Also</span></span>  
 [<span data-ttu-id="2a0c0-124">Рекомендации по работе с потоками</span><span class="sxs-lookup"><span data-stu-id="2a0c0-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="2a0c0-125">События</span><span class="sxs-lookup"><span data-stu-id="2a0c0-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="2a0c0-126">Многопоточность в компонентах</span><span class="sxs-lookup"><span data-stu-id="2a0c0-126">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="2a0c0-127">Асинхронная модель на основе событий (EAP)</span><span class="sxs-lookup"><span data-stu-id="2a0c0-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
