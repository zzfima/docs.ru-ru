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
# <a name="easing-functions"></a>Функции плавности
Функции плавности позволяют применять к анимациям настраиваемые математические формулы. Например, требуется реалистичный отскок объекта или его поведение так, словно он подвешен на пружине. Для приблизительного воспроизведения этих эффектов можно использовать анимацию по ключевым кадрам или даже анимацию From/To/By, но это потребует значительного объема работы, и анимация будет менее точна, чем при использовании математических формул.  
  
 Помимо создания собственной функции облегчения, наследовав от, <xref:System.Windows.Media.Animation.EasingFunctionBase>вы можете использовать одну из нескольких функций облегчения, предоставляемых временвыполнения для создания общих эффектов.  
  
- <xref:System.Windows.Media.Animation.BackEase>: Убирает движение анимации немного, прежде чем он начинает анимировать в указанном пути.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: Создает эффект подпрыгивания.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью круговой функции.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f**(t)* *и т*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: Создает анимацию, которая напоминает весной, колеблющейся туда и обратно, пока она не дойдет до отдыха.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью экспоненциальной формулы.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f**(t)* *и т*<sup>р,</sup> где р равен свойству. <xref:System.Windows.Media.Animation.PowerEase.Power%2A>  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f**(t)* *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью формулы *f**(t)* *и т*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: Создайте анимацию, которая ускоряет и/или замедляется с помощью формулы *f**(t)* *и т*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: Создает анимацию, которая ускоряет и/или замедляется с помощью синусоидной формулы.  
  
 Чтобы применить функцию ослабления к `EasingFunction` анимации, используйте свойство анимации, укажите функцию ослабления, чтобы применить к анимации. В следующем примере <xref:System.Windows.Media.Animation.BounceEase> применяется <xref:System.Windows.Media.Animation.DoubleAnimation> функция ослабления для создания эффекта подпрыгивания.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 В предыдущем примере функция плавности применялась к анимации From/To/By. Эти функции плавности можно применять и к анимации по ключевым кадрам. В следующем примере показано, как использовать ключевые кадры с функциями плавности для создания анимации прямоугольника, который сокращается вверх, замедляется вниз, затем расширяется вниз (как будто падает), а затем подпрыгивает до остановки.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 Вы можете <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> использовать свойство, чтобы изменить, как функция ослабления ведет себя, то есть изменить, как анимация интерполирует. Есть три возможных значения, <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>которые вы можете дать для:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Интерполяция следует математической формуле, связанной с функцией ослабления.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Интерполяция следует 100% интерполяции за вычетом вывода формулы, связанной с функцией ослабления.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Интерполяция использует <xref:System.Windows.Media.Animation.EasingMode.EaseIn> для первой <xref:System.Windows.Media.Animation.EasingMode.EaseOut> половины анимации и для второй половины.  
  
 На приведенных ниже графиках <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> показаны различные значения того, где *f*(*x*) представляет прогресс анимации и *t* представляет время.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Графы BackEase при различных значениях EasingMode.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Графы BounceEase при различных значениях EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Графы CircleEase при различных значениях EasingMode.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Графы CubicEase при различных значениях EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![Графы ElasticEase при различных значениях EasingMode.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Графы ExponentialEase при различных значениях EasingMode.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![Графы QuarticEase при различных значениях EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![Квадратная легкость с графиками различных послабления](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![Графы QuarticEase при различных значениях EasingMode.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![Графы QuinticEase при различных значениях EasingMode.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![Графы SineEase при различных значениях EasingMode](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> Вы можете <xref:System.Windows.Media.Animation.PowerEase> использовать для создания <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>того <xref:System.Windows.Media.Animation.QuarticEase>же <xref:System.Windows.Media.Animation.QuinticEase> поведения, <xref:System.Windows.Media.Animation.PowerEase.Power%2A> как , и с помощью свойства. Например, если вы <xref:System.Windows.Media.Animation.PowerEase> хотите использовать <xref:System.Windows.Media.Animation.CubicEase>для <xref:System.Windows.Media.Animation.PowerEase.Power%2A> замены, укажите значение 3.  
  
 В дополнение к использованию функций ослабления, включенных в время выполнения, вы <xref:System.Windows.Media.Animation.EasingFunctionBase>можете создать свои собственные пользовательские функции облегчения, нанаследовав от . В следующем примере показано создание простой пользовательской функции плавности. Вы можете добавить свою собственную математическую логику, как функция облегчения ведет себя, переопределяя <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> метод.
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
