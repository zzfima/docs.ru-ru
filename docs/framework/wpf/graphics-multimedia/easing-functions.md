---
title: "Функции плавности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "применение математических функций к анимации [WPF]"
  - "применение функций плавности к анимации [WPF]"
  - "математические формулы [WPF] Применение к анимации"
  - "анимации [WPF] реалистичные движения"
  - "функции плавности [WPF]"
  - "настройка функций плавности [WPF]"
  - "функции плавности [WPF], определение"
  - "функции плавности [WPF], Настройка"
  - "Применение анимации [WPF]"
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Функции плавности
Функции плавности позволяют применять настраиваемые математические формулы для анимаций. Например требуется объект реалистично Ударьте или ведут себя как если бы он был на весны. Можно использовать кадрам или даже анимацией From/To/By, чтобы приблизительно воспроизвести эти эффекты, но занимает значительный объем работы и анимация будет менее точен, чем математических формул.  
  
 Кроме создания собственной функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>, можно использовать один из функций плавности, предоставляемых средой выполнения для создания распространенных эффектов.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: отзывает движение анимации немного, прежде чем она начнет выполняться в указанном пути.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: создает эффект подпрыгивания.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: создает анимацию, которая ускоряется и замедляется с помощью тригонометрической функции.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: создает анимацию, которая ускоряется и замедляется с помощью формулы *f*( *t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: создает анимацию, которая напоминает весна, мерцающую до rest.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: создает анимацию, которая ускоряется и замедляется с помощью экспоненциальной формулы.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: создает анимацию, которая ускоряется и замедляется с помощью формулы *f*( *t*) = *t*<sup>p</sup> где p — <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойство.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: создает анимацию, которая ускоряется и замедляется с помощью формулы *f*( *t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: создает анимацию, которая ускоряется и замедляется с помощью формулы *f*( *t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: создать анимацию, которая ускоряется и замедляется с помощью формулы *f*( *t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: создает анимацию, которая ускоряется и замедляется с помощью формулы синуса.  
  
 Можно изучить поведение этих функций плавности, с помощью следующего примера.  
  
 [Запуск образца](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Для применения функции плавности к анимации используется `EasingFunction` свойства анимации укажите функцию плавности для применения в анимации. В следующем примере применяется <xref:System.Windows.Media.Animation.BounceEase> функции плавности <xref:System.Windows.Media.Animation.DoubleAnimation> для создания эффекта прыгающего.  
  
 [Запуск образца](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 В предыдущем примере функция плавности применялась к From/To/By анимации. Также можно применять эти функции плавности к анимации по полным кадрам. В следующем примере показано, как использовать опорные кадры с связанных с ними функции плавности для создания анимации прямоугольника, контракты снизу вверх, замедляется, затем расширяется вниз (будто заполняется) и отскакивает до остановки.  
  
 [Запуск образца](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Можно использовать <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> изменения свойств для изменения, как работает функция плавности, то есть способ интерполяции анимации. Существует три возможных значения, можно задать для <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: интерполяция математической формуле, связанной с функцией плавности.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: интерполяция интерполяции 100%, за вычетом выходного формулы, связанные с функцией плавности.  
  
-   <xref:System.Windows.Media.Animation.EasingMode>: используется для интерполяции <xref:System.Windows.Media.Animation.EasingMode> в первой половине анимации и <xref:System.Windows.Media.Animation.EasingMode> на вторую половину.  
  
 На следующих диаграммах показаны различные значения <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> где *f*( *x*) представляет ход выполнения анимации и *t* представляет время.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Графы backease при различных значениях EasingMode. ] (../Image/BackEase_Graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Графы bounceease при различных значениях EasingMode. ] (../Image/BounceEase_Graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Графы circleease при различных значениях EasingMode. ] (../Image/CircleEase_Graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Графы cubicease при различных значениях EasingMode. ] (../Image/CubicEase_Graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase при различных значениях easingmode. ] (../Image/ElasticEase_Graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Графы ExponentialEase при различных значениях easingmode. ] (../Image/ExponentialEase_Graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase при различных значениях easingmode. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![Графы QuadraticEase при различных значениях easingmode](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase при различных значениях easingmode. ] (../Image/QuarticEase_Graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase при различных значениях easingmode. ] (../Image/QuinticEase_Graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase при различных значениях EasingMode](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  Можно использовать <xref:System.Windows.Media.Animation.PowerEase> создать такое же поведение, как <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, и <xref:System.Windows.Media.Animation.QuinticEase> с помощью <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойство. Например, если вы хотите использовать <xref:System.Windows.Media.Animation.PowerEase> для замены <xref:System.Windows.Media.Animation.CubicEase>, укажите <xref:System.Windows.Media.Animation.PowerEase.Power%2A> значение 3.  
  
 Помимо использования функций округления, включенных в среду выполнения, можно создать собственные функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>. В следующем примере демонстрируется создание простой пользовательской функции округления. Можно добавить собственную математическую логику для поведения функции плавности путем переопределения <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.  
  
 [Запуск образца](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]