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
# <a name="easing-functions"></a>Функции плавности
Функции плавности позволяют применять к анимациям настраиваемые математические формулы. Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине. Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.  
  
 Помимо создания собственной функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>, можно использовать одну из функций плавности, предоставляемых средой выполнения для создания распространенных эффектов.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Отзывает движение анимации немного, прежде чем он начнет выполняться в указанном пути.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Создает эффект прыгающего.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряется и замедляется с помощью тригонометрической функции.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, которая напоминает spring, мерцающую до rest.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряется и замедляется с помощью экспоненциальной формулы.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>p</sup> где p — <xref:System.Windows.Media.Animation.PowerEase.Power%2A>свойство.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряется и замедляется с помощью формулы *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряется и замедляется с помощью формулы синуса.  
  
 Можно изучить поведение этих функций плавности с помощью следующего примера.  
  
 [Запустите этот пример](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Чтобы применить функции плавности анимации, используйте `EasingFunction` свойство анимации укажите функцию реалистичной анимации для применения в анимации. В следующем примере применяется <xref:System.Windows.Media.Animation.BounceEase> функции для реалистичной анимации входа <xref:System.Windows.Media.Animation.DoubleAnimation> для создания эффекта прыгающего.  
  
 [Запустите этот пример](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 В предыдущем примере функция плавности применялась к анимации From/To/By. Эти функции плавности можно применять и к анимации по ключевым кадрам. В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.  
  
 [Запустите этот пример](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Можно использовать <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> свойства для изменения, как ведет функции для реалистичной анимации, то есть изменить способ интерполяции анимации. Существует три возможных значения, вы можете передать для <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>Интерполяция математической формуле, связанной с функцией плавности.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>Интерполяция интерполяции 100%, за вычетом выходного формулы, связанные с функцией плавности.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Использует интерполяцию <xref:System.Windows.Media.Animation.EasingMode.EaseIn> в первой половине анимации и <xref:System.Windows.Media.Animation.EasingMode.EaseOut> второй половине.  
  
 На следующих диаграммах показаны различные значения <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> где *f*(*x*) представляет ход выполнения анимации и *t* представляет время.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Схемы BackEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Схемы BounceEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Схемы CircleEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Схемы CubicEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![Схемы ElasticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Схемы ExponentialEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![Схемы QuarticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![Схемы QuadraticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![Схемы QuarticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![Схемы QuinticEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![Схемы SineEase для различных значений EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Можно использовать <xref:System.Windows.Media.Animation.PowerEase> Создание совпадает с поведением <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, и <xref:System.Windows.Media.Animation.QuinticEase> с помощью <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойство. Например, если вы хотите использовать <xref:System.Windows.Media.Animation.PowerEase> для замены <xref:System.Windows.Media.Animation.CubicEase>, укажите <xref:System.Windows.Media.Animation.PowerEase.Power%2A> значение 3.  
  
 Помимо использования функций округления, включенных в среду выполнения, можно создать собственные функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>. В следующем примере показано создание простой пользовательской функции плавности. Можно добавить собственную математическую логику для поведение функции для реалистичной анимации, переопределив <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.  
  
 [Запустите этот пример](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
