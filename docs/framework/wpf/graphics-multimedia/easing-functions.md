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
ms.openlocfilehash: 3ce7c1824dc53c154ba1091ea62c1b8950b757c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="easing-functions"></a><span data-ttu-id="74e71-102">Функции плавности</span><span class="sxs-lookup"><span data-stu-id="74e71-102">Easing Functions</span></span>
<span data-ttu-id="74e71-103">Функции плавности позволяют применять к анимациям настраиваемые математические формулы.</span><span class="sxs-lookup"><span data-stu-id="74e71-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="74e71-104">Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине.</span><span class="sxs-lookup"><span data-stu-id="74e71-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="74e71-105">Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.</span><span class="sxs-lookup"><span data-stu-id="74e71-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="74e71-106">Помимо создания собственной функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>, можно использовать одну из функций плавности, предоставляемых средой выполнения для создания распространенных эффектов.</span><span class="sxs-lookup"><span data-stu-id="74e71-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="74e71-107"><xref:System.Windows.Media.Animation.BackEase>: Отзывает движение анимации немного, прежде чем он начнет выполняться в указанном пути.</span><span class="sxs-lookup"><span data-stu-id="74e71-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="74e71-108"><xref:System.Windows.Media.Animation.BounceEase>: Создает эффект прыгающего.</span><span class="sxs-lookup"><span data-stu-id="74e71-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="74e71-109"><xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряется и замедляется с помощью тригонометрической функции.</span><span class="sxs-lookup"><span data-stu-id="74e71-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="74e71-110"><xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>3</sup>.</span><span class="sxs-lookup"><span data-stu-id="74e71-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="74e71-111"><xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, которая напоминает spring, мерцающую до rest.</span><span class="sxs-lookup"><span data-stu-id="74e71-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="74e71-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряется и замедляется с помощью экспоненциальной формулы.</span><span class="sxs-lookup"><span data-stu-id="74e71-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="74e71-113"><xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>p</sup> где p — <xref:System.Windows.Media.Animation.PowerEase.Power%2A>свойство.</span><span class="sxs-lookup"><span data-stu-id="74e71-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="74e71-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>2</sup>.</span><span class="sxs-lookup"><span data-stu-id="74e71-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="74e71-115"><xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>4</sup>.</span><span class="sxs-lookup"><span data-stu-id="74e71-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="74e71-116"><xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>5</sup>.</span><span class="sxs-lookup"><span data-stu-id="74e71-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="74e71-117"><xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы синуса.</span><span class="sxs-lookup"><span data-stu-id="74e71-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="74e71-118">Можно изучить поведение этих функций плавности с помощью следующего примера.</span><span class="sxs-lookup"><span data-stu-id="74e71-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="74e71-119">Запустите этот пример</span><span class="sxs-lookup"><span data-stu-id="74e71-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="74e71-120">Чтобы применить функции плавности анимации, используйте `EasingFunction` свойство анимации укажите функцию реалистичной анимации для применения в анимации.</span><span class="sxs-lookup"><span data-stu-id="74e71-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="74e71-121">В следующем примере применяется <xref:System.Windows.Media.Animation.BounceEase> функции для реалистичной анимации входа <xref:System.Windows.Media.Animation.DoubleAnimation> для создания эффекта прыгающего.</span><span class="sxs-lookup"><span data-stu-id="74e71-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="74e71-122">Запустите этот пример</span><span class="sxs-lookup"><span data-stu-id="74e71-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="74e71-123">В предыдущем примере функция плавности применялась к анимации From/To/By.</span><span class="sxs-lookup"><span data-stu-id="74e71-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="74e71-124">Эти функции плавности можно применять и к анимации по ключевым кадрам.</span><span class="sxs-lookup"><span data-stu-id="74e71-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="74e71-125">В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.</span><span class="sxs-lookup"><span data-stu-id="74e71-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="74e71-126">Запустите этот пример</span><span class="sxs-lookup"><span data-stu-id="74e71-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="74e71-127">Можно использовать <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> свойства для изменения, как ведет функции для реалистичной анимации, то есть изменить способ интерполяции анимации.</span><span class="sxs-lookup"><span data-stu-id="74e71-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="74e71-128">Существует три возможных значения, вы можете передать для <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="74e71-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="74e71-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>Интерполяция математической формуле, связанной с функцией плавности.</span><span class="sxs-lookup"><span data-stu-id="74e71-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="74e71-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>Интерполяция интерполяции 100%, за вычетом выходного формулы, связанные с функцией плавности.</span><span class="sxs-lookup"><span data-stu-id="74e71-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="74e71-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Использует интерполяцию <xref:System.Windows.Media.Animation.EasingMode.EaseIn> в первой половине анимации и <xref:System.Windows.Media.Animation.EasingMode.EaseOut> второй половине.</span><span class="sxs-lookup"><span data-stu-id="74e71-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="74e71-132">На следующих диаграммах показаны различные значения <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> где *f*(*x*) представляет ход выполнения анимации и *t* представляет время.</span><span class="sxs-lookup"><span data-stu-id="74e71-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="74e71-133">![Схемы BackEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="74e71-134">![Схемы BounceEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="74e71-135">![Схемы CircleEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="74e71-136">![Схемы CubicEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="74e71-137">![Схемы ElasticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="74e71-138">![Схемы ExponentialEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="74e71-139">![Схемы QuarticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="74e71-140">![Схемы QuadraticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="74e71-141">![Схемы QuarticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="74e71-142">![Схемы QuinticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="74e71-143">![Схемы SineEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="74e71-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74e71-144">Можно использовать <xref:System.Windows.Media.Animation.PowerEase> Создание совпадает с поведением <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, и <xref:System.Windows.Media.Animation.QuinticEase> с помощью <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="74e71-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="74e71-145">Например, если вы хотите использовать <xref:System.Windows.Media.Animation.PowerEase> для замены <xref:System.Windows.Media.Animation.CubicEase>, укажите <xref:System.Windows.Media.Animation.PowerEase.Power%2A> значение 3.</span><span class="sxs-lookup"><span data-stu-id="74e71-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="74e71-146">Помимо использования функций округления, включенных в среду выполнения, можно создать собственные функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span><span class="sxs-lookup"><span data-stu-id="74e71-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="74e71-147">В следующем примере показано создание простой пользовательской функции плавности.</span><span class="sxs-lookup"><span data-stu-id="74e71-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="74e71-148">Можно добавить собственную математическую логику для поведение функции для реалистичной анимации, переопределив <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="74e71-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="74e71-149">Запустите этот пример</span><span class="sxs-lookup"><span data-stu-id="74e71-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
