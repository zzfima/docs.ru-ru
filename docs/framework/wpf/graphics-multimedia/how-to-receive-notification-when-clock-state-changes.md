---
title: "Как: уведомить при часов &#39; s изменения состояния"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="86ee2-102">Как: уведомить при часов &#39; s изменения состояния</span><span class="sxs-lookup"><span data-stu-id="86ee2-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="86ee2-103">Часы <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> событие возникает при его <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> становится недействительным, например при запуске или остановке часов.</span><span class="sxs-lookup"><span data-stu-id="86ee2-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="86ee2-104">Можно зарегистрировать для этого события непосредственно с помощью <xref:System.Windows.Media.Animation.Clock>, или можно зарегистрировать с помощью <xref:System.Windows.Media.Animation.Timeline>.</span><span class="sxs-lookup"><span data-stu-id="86ee2-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="86ee2-105">В следующем примере <xref:System.Windows.Media.Animation.Storyboard> и два <xref:System.Windows.Media.Animation.DoubleAnimation> объекты используются для анимации ширины двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="86ee2-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="86ee2-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Событие используется для прослушивания изменений состояния часов.</span><span class="sxs-lookup"><span data-stu-id="86ee2-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86ee2-107">Пример</span><span class="sxs-lookup"><span data-stu-id="86ee2-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="86ee2-108">На следующем рисунке показан различные состояния анимаций введите в качестве родительской временной шкалы (*раскадровки*) продвижения.</span><span class="sxs-lookup"><span data-stu-id="86ee2-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="86ee2-109">![Синхронизация состояния для раскадровки с двумя анимациями](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="86ee2-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="86ee2-110">В следующей таблице показаны значения времени, по которому *Animation1* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> события:</span><span class="sxs-lookup"><span data-stu-id="86ee2-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="86ee2-111">Время (в секундах)</span><span class="sxs-lookup"><span data-stu-id="86ee2-111">Time (Seconds)</span></span>|<span data-ttu-id="86ee2-112">1</span><span class="sxs-lookup"><span data-stu-id="86ee2-112">1</span></span>|<span data-ttu-id="86ee2-113">10</span><span class="sxs-lookup"><span data-stu-id="86ee2-113">10</span></span>|<span data-ttu-id="86ee2-114">19</span><span class="sxs-lookup"><span data-stu-id="86ee2-114">19</span></span>|<span data-ttu-id="86ee2-115">21</span><span class="sxs-lookup"><span data-stu-id="86ee2-115">21</span></span>|<span data-ttu-id="86ee2-116">30</span><span class="sxs-lookup"><span data-stu-id="86ee2-116">30</span></span>|<span data-ttu-id="86ee2-117">39</span><span class="sxs-lookup"><span data-stu-id="86ee2-117">39</span></span>|  
|<span data-ttu-id="86ee2-118">Регион</span><span class="sxs-lookup"><span data-stu-id="86ee2-118">State</span></span>|<span data-ttu-id="86ee2-119">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-119">Active</span></span>|<span data-ttu-id="86ee2-120">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-120">Active</span></span>|<span data-ttu-id="86ee2-121">Остановлено</span><span class="sxs-lookup"><span data-stu-id="86ee2-121">Stopped</span></span>|<span data-ttu-id="86ee2-122">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-122">Active</span></span>|<span data-ttu-id="86ee2-123">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-123">Active</span></span>|<span data-ttu-id="86ee2-124">Остановлено</span><span class="sxs-lookup"><span data-stu-id="86ee2-124">Stopped</span></span>|  
  
 <span data-ttu-id="86ee2-125">В следующей таблице показаны значения времени, по которому *Animation2* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> события:</span><span class="sxs-lookup"><span data-stu-id="86ee2-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="86ee2-126">Время (в секундах)</span><span class="sxs-lookup"><span data-stu-id="86ee2-126">Time (Seconds)</span></span>|<span data-ttu-id="86ee2-127">1</span><span class="sxs-lookup"><span data-stu-id="86ee2-127">1</span></span>|<span data-ttu-id="86ee2-128">9</span><span class="sxs-lookup"><span data-stu-id="86ee2-128">9</span></span>|<span data-ttu-id="86ee2-129">11</span><span class="sxs-lookup"><span data-stu-id="86ee2-129">11</span></span>|<span data-ttu-id="86ee2-130">19</span><span class="sxs-lookup"><span data-stu-id="86ee2-130">19</span></span>|<span data-ttu-id="86ee2-131">21</span><span class="sxs-lookup"><span data-stu-id="86ee2-131">21</span></span>|<span data-ttu-id="86ee2-132">29</span><span class="sxs-lookup"><span data-stu-id="86ee2-132">29</span></span>|<span data-ttu-id="86ee2-133">31</span><span class="sxs-lookup"><span data-stu-id="86ee2-133">31</span></span>|<span data-ttu-id="86ee2-134">39</span><span class="sxs-lookup"><span data-stu-id="86ee2-134">39</span></span>|  
|<span data-ttu-id="86ee2-135">Регион</span><span class="sxs-lookup"><span data-stu-id="86ee2-135">State</span></span>|<span data-ttu-id="86ee2-136">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-136">Active</span></span>|<span data-ttu-id="86ee2-137">Заполнение</span><span class="sxs-lookup"><span data-stu-id="86ee2-137">Filling</span></span>|<span data-ttu-id="86ee2-138">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-138">Active</span></span>|<span data-ttu-id="86ee2-139">Остановлено</span><span class="sxs-lookup"><span data-stu-id="86ee2-139">Stopped</span></span>|<span data-ttu-id="86ee2-140">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-140">Active</span></span>|<span data-ttu-id="86ee2-141">Заполнение</span><span class="sxs-lookup"><span data-stu-id="86ee2-141">Filling</span></span>|<span data-ttu-id="86ee2-142">Активно</span><span class="sxs-lookup"><span data-stu-id="86ee2-142">Active</span></span>|<span data-ttu-id="86ee2-143">Остановлено</span><span class="sxs-lookup"><span data-stu-id="86ee2-143">Stopped</span></span>|  
  
 <span data-ttu-id="86ee2-144">Обратите внимание, что *Animation1* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> событие запускается через 10 секунд, даже если его состояние остается <xref:System.Windows.Media.Animation.ClockState.Active>.</span><span class="sxs-lookup"><span data-stu-id="86ee2-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="86ee2-145">Это, так как ее состояние изменилось на 10 секунд, но ее изменить <xref:System.Windows.Media.Animation.ClockState.Active> для <xref:System.Windows.Media.Animation.ClockState.Filling> и обратно <xref:System.Windows.Media.Animation.ClockState.Active> в же делений.</span><span class="sxs-lookup"><span data-stu-id="86ee2-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
