---
title: Практическое руководство. Вызов и обработка событий
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 256b5ae9ac2145e339136985872dfa5423aca730
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131584"
---
# <a name="how-to-raise-and-consume-events"></a><span data-ttu-id="f14b8-102">Практическое руководство. Вызов и обработка событий</span><span class="sxs-lookup"><span data-stu-id="f14b8-102">How to: Raise and Consume Events</span></span>
<span data-ttu-id="f14b8-103">В примерах в этом разделе показано, как работать с событиями.</span><span class="sxs-lookup"><span data-stu-id="f14b8-103">The examples in this topic show how to work with events.</span></span> <span data-ttu-id="f14b8-104">Даны примеры делегата <xref:System.EventHandler>, делегата <xref:System.EventHandler%601> и пользовательского делегата, иллюстрирующие события как с данными, так и без.</span><span class="sxs-lookup"><span data-stu-id="f14b8-104">They include examples of the <xref:System.EventHandler> delegate, the <xref:System.EventHandler%601> delegate, and a custom delegate, to illustrate events with and without data.</span></span>  
  
 <span data-ttu-id="f14b8-105">В примерах используются понятия, описанные в руководстве по [событиям](../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="f14b8-105">The examples use concepts described in the [Events](../../../docs/standard/events/index.md) article.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14b8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f14b8-106">Example</span></span>  
 <span data-ttu-id="f14b8-107">В первом примере показано, как вызывать и использовать событие, не содержащее данные.</span><span class="sxs-lookup"><span data-stu-id="f14b8-107">The first example shows how to raise and consume an event that doesn't have data.</span></span> <span data-ttu-id="f14b8-108">Он содержит класс `Counter` с событием `ThresholdReached`.</span><span class="sxs-lookup"><span data-stu-id="f14b8-108">It contains a class named `Counter` that has an event named `ThresholdReached`.</span></span> <span data-ttu-id="f14b8-109">Это событие возникает, когда значение счетчика больше порогового значения или равно ему.</span><span class="sxs-lookup"><span data-stu-id="f14b8-109">This event is raised when a counter value equals or exceeds a threshold value.</span></span> <span data-ttu-id="f14b8-110">Делегат <xref:System.EventHandler> связан с событием, потому что данные события не предоставляются.</span><span class="sxs-lookup"><span data-stu-id="f14b8-110">The <xref:System.EventHandler> delegate is associated with the event, because no event data is provided.</span></span>  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="f14b8-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f14b8-111">Example</span></span>  
 <span data-ttu-id="f14b8-112">В следующем примере показано, как вызывать и использовать событие, предоставляющее данные.</span><span class="sxs-lookup"><span data-stu-id="f14b8-112">The next example shows how to raise and consume an event that provides data.</span></span> <span data-ttu-id="f14b8-113">Делегат <xref:System.EventHandler%601> связан с событием; предоставляется экземпляр объекта данных пользовательского события.</span><span class="sxs-lookup"><span data-stu-id="f14b8-113">The <xref:System.EventHandler%601> delegate is associated with the event, and an instance of a custom event data object is provided.</span></span>  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="f14b8-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f14b8-114">Example</span></span>  
 <span data-ttu-id="f14b8-115">В следующем примере показано объявление делегата для события.</span><span class="sxs-lookup"><span data-stu-id="f14b8-115">The next example shows how to declare a delegate for an event.</span></span> <span data-ttu-id="f14b8-116">Имя делегата — `ThresholdReachedEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="f14b8-116">The delegate is named `ThresholdReachedEventHandler`.</span></span> <span data-ttu-id="f14b8-117">Это всего лишь пример.</span><span class="sxs-lookup"><span data-stu-id="f14b8-117">This is just an illustration.</span></span> <span data-ttu-id="f14b8-118">Как правило, не требуется объявлять делегат для события, поскольку можно использовать делегат <xref:System.EventHandler> или <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="f14b8-118">Typically, you do not have to declare a delegate for an event, because you can use either the <xref:System.EventHandler> or the <xref:System.EventHandler%601> delegate.</span></span> <span data-ttu-id="f14b8-119">Объявлять делегат необходимо только в редких случаях, например чтобы сделать класс доступным для устаревшего кода, который не может использовать универсальные классы.</span><span class="sxs-lookup"><span data-stu-id="f14b8-119">You should declare a delegate only in rare scenarios, such as making your class available to legacy code that cannot use generics.</span></span>  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="f14b8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f14b8-120">See also</span></span>

- [<span data-ttu-id="f14b8-121">События</span><span class="sxs-lookup"><span data-stu-id="f14b8-121">Events</span></span>](../../../docs/standard/events/index.md)
