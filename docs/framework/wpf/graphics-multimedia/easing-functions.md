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
ms.openlocfilehash: 72118711dfd40ad8c665157e09f01c60085db903
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965734"
---
# <a name="easing-functions"></a><span data-ttu-id="e472a-102">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="e472a-102">Easing Functions</span></span>
<span data-ttu-id="e472a-103">Функции плавности позволяют применять к анимациям настраиваемые математические формулы.</span><span class="sxs-lookup"><span data-stu-id="e472a-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="e472a-104">Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине.</span><span class="sxs-lookup"><span data-stu-id="e472a-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="e472a-105">Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.</span><span class="sxs-lookup"><span data-stu-id="e472a-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="e472a-106">Помимо создания собственной пользовательской функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>, можно использовать одну из нескольких функций плавности, предоставляемых средой выполнения для создания распространенных эффектов.</span><span class="sxs-lookup"><span data-stu-id="e472a-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="e472a-107"><xref:System.Windows.Media.Animation.BackEase>: Отменяет движение анимации немного перед началом анимации по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="e472a-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="e472a-108"><xref:System.Windows.Media.Animation.BounceEase>: Создает эффекты отскока.</span><span class="sxs-lookup"><span data-stu-id="e472a-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="e472a-109"><xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью циклической функции.</span><span class="sxs-lookup"><span data-stu-id="e472a-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="e472a-110"><xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="e472a-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="e472a-111"><xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, напоминающую пружинный осЦиллатинг назад и вперед, пока не поступает на оставшуюся.</span><span class="sxs-lookup"><span data-stu-id="e472a-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="e472a-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью экспоненциальной формулы.</span><span class="sxs-lookup"><span data-stu-id="e472a-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="e472a-113"><xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>p</sup> , где p равно <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойству.</span><span class="sxs-lookup"><span data-stu-id="e472a-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="e472a-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="e472a-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="e472a-115"><xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="e472a-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="e472a-116"><xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="e472a-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="e472a-117"><xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы синуса.</span><span class="sxs-lookup"><span data-stu-id="e472a-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="e472a-118">Чтобы применить функцию плавности к анимации, используйте `EasingFunction` свойство анимации. Укажите функцию плавности, которая будет применяться к анимации.</span><span class="sxs-lookup"><span data-stu-id="e472a-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="e472a-119">В следующем примере функция <xref:System.Windows.Media.Animation.BounceEase> плавности применяется к элементу <xref:System.Windows.Media.Animation.DoubleAnimation> для создания отскока.</span><span class="sxs-lookup"><span data-stu-id="e472a-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="e472a-120">В предыдущем примере функция плавности применялась к анимации From/To/By.</span><span class="sxs-lookup"><span data-stu-id="e472a-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="e472a-121">Эти функции плавности можно применять и к анимации по ключевым кадрам.</span><span class="sxs-lookup"><span data-stu-id="e472a-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="e472a-122">В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.</span><span class="sxs-lookup"><span data-stu-id="e472a-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="e472a-123"><xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Свойство можно использовать, чтобы изменить принцип работы функции плавности, то есть изменить способ интерполяции анимации.</span><span class="sxs-lookup"><span data-stu-id="e472a-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="e472a-124">Существует три возможных значения, которые можно задать для <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="e472a-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="e472a-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Интерполяция следует математической формуле, связанной с функцией плавности.</span><span class="sxs-lookup"><span data-stu-id="e472a-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="e472a-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Интерполяция следует за 100% интерполяции за вычетом выходных данных формулы, связанной с функцией плавности.</span><span class="sxs-lookup"><span data-stu-id="e472a-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="e472a-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Интерполяция использует <xref:System.Windows.Media.Animation.EasingMode.EaseIn> для первой половины анимации и <xref:System.Windows.Media.Animation.EasingMode.EaseOut> для второй половины.</span><span class="sxs-lookup"><span data-stu-id="e472a-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="e472a-128">На приведенных ниже диаграммах показаны различные <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> значения, где *f*(*x*) представляет ход выполнения анимации, а *t* представляет время.</span><span class="sxs-lookup"><span data-stu-id="e472a-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="e472a-129">![Схемы BackEase EasingMode.](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="e472a-130">![Схемы BounceEase EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="e472a-131">![Схемы CircleEase EasingMode.](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="e472a-132">![Схемы CubicEase EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="e472a-133">![Схемы ElasticEase для различных значений EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="e472a-134">![Схемы ExponentialEase для различных значений EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="e472a-135">![Схемы QuarticEase для различных значений EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="e472a-136">![Схемы QuadraticEase для различных значений EasingMode.](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="e472a-137">![Схемы QuarticEase для различных значений EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="e472a-138">![Схемы QuinticEase для различных значений EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="e472a-139">![Схемы SineEase для различных значений EasingMode.](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="e472a-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e472a-140">Можно <xref:System.Windows.Media.Animation.PowerEase> использовать для создания такого же поведения, как <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase> <xref:System.Windows.Media.Animation.QuinticEase> и с помощью <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="e472a-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="e472a-141">Например, если вы хотите использовать <xref:System.Windows.Media.Animation.PowerEase> для <xref:System.Windows.Media.Animation.CubicEase>замены, укажите <xref:System.Windows.Media.Animation.PowerEase.Power%2A> значение 3.</span><span class="sxs-lookup"><span data-stu-id="e472a-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="e472a-142">Помимо использования функций плавности, входящих в время выполнения, можно создавать собственные пользовательские функции плавности, наследуя от <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="e472a-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="e472a-143">В следующем примере показано создание простой пользовательской функции плавности.</span><span class="sxs-lookup"><span data-stu-id="e472a-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="e472a-144">Можно добавить собственную математическую логику, определяющую поведение функции плавности, переопределив <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e472a-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
