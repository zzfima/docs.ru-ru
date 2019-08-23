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
# <a name="easing-functions"></a>Функции плавности
Функции плавности позволяют применять к анимациям настраиваемые математические формулы. Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине. Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.  
  
 Помимо создания собственной пользовательской функции плавности путем наследования от <xref:System.Windows.Media.Animation.EasingFunctionBase>, можно использовать одну из нескольких функций плавности, предоставляемых средой выполнения для создания распространенных эффектов.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Отменяет движение анимации немного перед началом анимации по указанному пути.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Создает эффекты отскока.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью циклической функции.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, напоминающую пружинный осЦиллатинг назад и вперед, пока не поступает на оставшуюся.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью экспоненциальной формулы.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>p</sup> , где p равно <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойству.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряется и/или замедляется с помощью формулы *f*(*t*) = *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряется и/или замедляется с помощью формулы синуса.  
  
 Чтобы применить функцию плавности к анимации, используйте `EasingFunction` свойство анимации. Укажите функцию плавности, которая будет применяться к анимации. В следующем примере функция <xref:System.Windows.Media.Animation.BounceEase> плавности применяется к элементу <xref:System.Windows.Media.Animation.DoubleAnimation> для создания отскока.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 В предыдущем примере функция плавности применялась к анимации From/To/By. Эти функции плавности можно применять и к анимации по ключевым кадрам. В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> Свойство можно использовать, чтобы изменить принцип работы функции плавности, то есть изменить способ интерполяции анимации. Существует три возможных значения, которые можно задать для <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Интерполяция следует математической формуле, связанной с функцией плавности.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Интерполяция следует за 100% интерполяции за вычетом выходных данных формулы, связанной с функцией плавности.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Интерполяция использует <xref:System.Windows.Media.Animation.EasingMode.EaseIn> для первой половины анимации и <xref:System.Windows.Media.Animation.EasingMode.EaseOut> для второй половины.  
  
 На приведенных ниже диаграммах показаны различные <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> значения, где *f*(*x*) представляет ход выполнения анимации, а *t* представляет время.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Схемы BackEase EasingMode.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Схемы BounceEase EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Схемы CircleEase EasingMode.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Схемы CubicEase EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![Схемы ElasticEase для различных значений EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Схемы ExponentialEase для различных значений EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![Схемы QuarticEase для различных значений EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![Схемы QuadraticEase для различных значений EasingMode.](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![Схемы QuarticEase для различных значений EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![Схемы QuinticEase для различных значений EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![Схемы SineEase для различных значений EasingMode.](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> Можно <xref:System.Windows.Media.Animation.PowerEase> использовать для создания такого же поведения, как <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase> <xref:System.Windows.Media.Animation.QuinticEase> и с помощью <xref:System.Windows.Media.Animation.PowerEase.Power%2A> свойства. Например, если вы хотите использовать <xref:System.Windows.Media.Animation.PowerEase> для <xref:System.Windows.Media.Animation.CubicEase>замены, укажите <xref:System.Windows.Media.Animation.PowerEase.Power%2A> значение 3.  
  
 Помимо использования функций плавности, входящих в время выполнения, можно создавать собственные пользовательские функции плавности, наследуя от <xref:System.Windows.Media.Animation.EasingFunctionBase>. В следующем примере показано создание простой пользовательской функции плавности. Можно добавить собственную математическую логику, определяющую поведение функции плавности, переопределив <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
