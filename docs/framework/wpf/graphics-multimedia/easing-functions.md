---
title: Функции плавности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186497"
---
# <a name="easing-functions"></a><span data-ttu-id="4354b-102">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="4354b-102">Easing Functions</span></span>
<span data-ttu-id="4354b-103">Функции плавности позволяют применять к анимациям настраиваемые математические формулы.</span><span class="sxs-lookup"><span data-stu-id="4354b-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="4354b-104">Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине.</span><span class="sxs-lookup"><span data-stu-id="4354b-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="4354b-105">Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.</span><span class="sxs-lookup"><span data-stu-id="4354b-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="4354b-106">Помимо создания собственной функции облегчения, наследовав от, <xref:System.Windows.Media.Animation.EasingFunctionBase>вы можете использовать одну из нескольких функций облегчения, предоставляемых временвыполнения для создания общих эффектов.</span><span class="sxs-lookup"><span data-stu-id="4354b-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="4354b-107"><xref:System.Windows.Media.Animation.BackEase>: Убирает движение анимации немного, прежде чем он начинает анимировать в указанном пути.</span><span class="sxs-lookup"><span data-stu-id="4354b-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="4354b-108"><xref:System.Windows.Media.Animation.BounceEase>: Создает эффект подпрыгивания.</span><span class="sxs-lookup"><span data-stu-id="4354b-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="4354b-109"><xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью круговой функции.</span><span class="sxs-lookup"><span data-stu-id="4354b-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="4354b-110"><xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f\*\*(t)* *и т*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="4354b-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="4354b-111"><xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, которая напоминает весной, колеблющейся туда и обратно, пока она не дойдет до отдыха.</span><span class="sxs-lookup"><span data-stu-id="4354b-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="4354b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью экспоненциальной формулы.</span><span class="sxs-lookup"><span data-stu-id="4354b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="4354b-113"><xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f\*\*(t)* *и т*<sup>р,</sup> где р равен свойству. <xref:System.Windows.Media.Animation.PowerEase.Power%2A></span><span class="sxs-lookup"><span data-stu-id="4354b-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="4354b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f\*\*(t)* *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="4354b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="4354b-115"><xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f\*\*(t)* *и т*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="4354b-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="4354b-116"><xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряет и/или замедляется с помощью формулы *f\*\*(t)* *и т*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="4354b-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="4354b-117"><xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью синусоидной формулы.</span><span class="sxs-lookup"><span data-stu-id="4354b-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="4354b-118">Чтобы применить функцию ослабления к `EasingFunction` анимации, используйте свойство анимации, укажите функцию ослабления, чтобы применить к анимации.</span><span class="sxs-lookup"><span data-stu-id="4354b-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="4354b-119">В следующем примере <xref:System.Windows.Media.Animation.BounceEase> применяется <xref:System.Windows.Media.Animation.DoubleAnimation> функция ослабления для создания эффекта подпрыгивания.</span><span class="sxs-lookup"><span data-stu-id="4354b-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="4354b-120">В предыдущем примере функция плавности применялась к анимации From/To/By.</span><span class="sxs-lookup"><span data-stu-id="4354b-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="4354b-121">Эти функции плавности можно применять и к анимации по ключевым кадрам.</span><span class="sxs-lookup"><span data-stu-id="4354b-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="4354b-122">В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.</span><span class="sxs-lookup"><span data-stu-id="4354b-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="4354b-123">Вы можете <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> использовать свойство, чтобы изменить, как функция ослабления ведет себя, то есть изменить, как анимация интерполирует.</span><span class="sxs-lookup"><span data-stu-id="4354b-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="4354b-124">Есть три возможных значения, <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>которые вы можете дать для:</span><span class="sxs-lookup"><span data-stu-id="4354b-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="4354b-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Интерполяция следует математической формуле, связанной с функцией ослабления.</span><span class="sxs-lookup"><span data-stu-id="4354b-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="4354b-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Интерполяция следует 100% интерполяции за вычетом вывода формулы, связанной с функцией ослабления.</span><span class="sxs-lookup"><span data-stu-id="4354b-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="4354b-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Интерполяция использует <xref:System.Windows.Media.Animation.EasingMode.EaseIn> для первой <xref:System.Windows.Media.Animation.EasingMode.EaseOut> половины анимации и для второй половины.</span><span class="sxs-lookup"><span data-stu-id="4354b-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="4354b-128">На приведенных ниже графиках <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> показаны различные значения того, где *f*(*x*) представляет прогресс анимации и *t* представляет время.</span><span class="sxs-lookup"><span data-stu-id="4354b-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="4354b-129">![Графы BackEase при различных значениях EasingMode.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="4354b-130">![Графы BounceEase при различных значениях EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="4354b-131">![Графы CircleEase при различных значениях EasingMode.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="4354b-132">![Графы CubicEase при различных значениях EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="4354b-133">![Графы ElasticEase при различных значениях EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="4354b-134">![Графы ExponentialEase при различных значениях EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="4354b-135">![Графы QuarticEase при различных значениях EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="4354b-136">![Квадратная легкость с графиками различных послабления](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="4354b-137">![Графы QuarticEase при различных значениях EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="4354b-138">![Графы QuinticEase при различных значениях EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="4354b-139">![Графы SineEase при различных значениях EasingMode](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="4354b-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4354b-140">Вы можете <xref:System.Windows.Media.Animation.PowerEase> использовать для создания <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>того <xref:System.Windows.Media.Animation.QuarticEase>же <xref:System.Windows.Media.Animation.QuinticEase> поведения, <xref:System.Windows.Media.Animation.PowerEase.Power%2A> как , и с помощью свойства.</span><span class="sxs-lookup"><span data-stu-id="4354b-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="4354b-141">Например, если вы <xref:System.Windows.Media.Animation.PowerEase> хотите использовать <xref:System.Windows.Media.Animation.CubicEase>для <xref:System.Windows.Media.Animation.PowerEase.Power%2A> замены, укажите значение 3.</span><span class="sxs-lookup"><span data-stu-id="4354b-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="4354b-142">В дополнение к использованию функций ослабления, включенных в время выполнения, вы <xref:System.Windows.Media.Animation.EasingFunctionBase>можете создать свои собственные пользовательские функции облегчения, нанаследовав от .</span><span class="sxs-lookup"><span data-stu-id="4354b-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="4354b-143">В следующем примере показано создание простой пользовательской функции плавности.</span><span class="sxs-lookup"><span data-stu-id="4354b-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="4354b-144">Вы можете добавить свою собственную математическую логику, как функция облегчения ведет себя, переопределяя <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="4354b-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
