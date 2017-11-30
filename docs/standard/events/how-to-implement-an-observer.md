---
title: "Практическое руководство. Реализация объекта Observer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="690c6-102">Практическое руководство. Реализация объекта Observer</span><span class="sxs-lookup"><span data-stu-id="690c6-102">How to: Implement an Observer</span></span>
<span data-ttu-id="690c6-103">Шаблон разработки наблюдателя требует различения наблюдателя, который регистрируется для получения уведомлений, и поставщика, который проверяет данные и отправляет уведомления для одного или нескольких наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="690c6-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="690c6-104">В этом разделе описывается создание наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="690c6-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="690c6-105">Связанный раздел, [как: реализация поставщика](../../../docs/standard/events/how-to-implement-a-provider.md), рассматривается способ создания поставщика.</span><span class="sxs-lookup"><span data-stu-id="690c6-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="690c6-106">Создание наблюдателя</span><span class="sxs-lookup"><span data-stu-id="690c6-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="690c6-107">Определите наблюдатель, то есть тип, реализующий <xref:System.IObserver%601?displayProperty=nameWithType> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="690c6-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="690c6-108">Например, следующий код определяет тип с именем `TemperatureReporter` , представляющий собой созданную <xref:System.IObserver%601?displayProperty=nameWithType> реализации с помощью аргумента универсального типа `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="690c6-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="690c6-109">Если наблюдатель может прекратить получение уведомлений до вызова поставщиком его <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> реализацию, определить частную переменную, которая будет содержать <xref:System.IDisposable> реализацию, возвращенный поставщиком <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="690c6-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="690c6-110">Также следует определить метод подписки, который вызывает поставщика <xref:System.IObservable%601.Subscribe%2A> метод и хранящий возвращенный <xref:System.IDisposable> объекта.</span><span class="sxs-lookup"><span data-stu-id="690c6-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="690c6-111">Например, следующий код определяет закрытую переменную с именем `unsubscriber` и определяет `Subscribe` метод, который вызывает поставщика <xref:System.IObservable%601.Subscribe%2A> метод и назначает возвращаемый объект `unsubscriber` переменной.</span><span class="sxs-lookup"><span data-stu-id="690c6-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="690c6-112">Определите метод, позволяющий наблюдателю прекратить получение уведомлений до вызова поставщиком его <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> реализации, когда этот компонент является обязательным.</span><span class="sxs-lookup"><span data-stu-id="690c6-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="690c6-113">В следующем примере определяется `Unsubscribe` метод.</span><span class="sxs-lookup"><span data-stu-id="690c6-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="690c6-114">Определить реализации трех методов, определяемых <xref:System.IObserver%601> интерфейса: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, и <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="690c6-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="690c6-115">В зависимости от поставщика и потребностям приложения <xref:System.IObserver%601.OnError%2A> и <xref:System.IObserver%601.OnCompleted%2A> методы могут быть заглушки реализации.</span><span class="sxs-lookup"><span data-stu-id="690c6-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="690c6-116">Обратите внимание, что <xref:System.IObserver%601.OnError%2A> метод не должен обрабатывать переданный <xref:System.Exception> объект как исключение и <xref:System.IObserver%601.OnCompleted%2A> метод может вызывать поставщик <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> реализации.</span><span class="sxs-lookup"><span data-stu-id="690c6-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="690c6-117">В следующем примере показан <xref:System.IObserver%601> реализация `TemperatureReporter` класса.</span><span class="sxs-lookup"><span data-stu-id="690c6-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="690c6-118">Пример</span><span class="sxs-lookup"><span data-stu-id="690c6-118">Example</span></span>  
 <span data-ttu-id="690c6-119">В следующем примере содержится полный исходный код для `TemperatureReporter` класс, предоставляющий <xref:System.IObserver%601> реализацию для приложения контроля температуры.</span><span class="sxs-lookup"><span data-stu-id="690c6-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="690c6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="690c6-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="690c6-121">Шаблон разработки наблюдателя</span><span class="sxs-lookup"><span data-stu-id="690c6-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="690c6-122">Практическое руководство. Реализация поставщика</span><span class="sxs-lookup"><span data-stu-id="690c6-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="690c6-123">Рекомендации по шаблону разработки Observer</span><span class="sxs-lookup"><span data-stu-id="690c6-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
