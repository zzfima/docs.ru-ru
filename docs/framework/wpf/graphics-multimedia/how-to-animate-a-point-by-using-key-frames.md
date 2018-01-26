---
title: "Практическое руководство. Анимация точки с помощью ключевых кадров"
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
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c115d31c6ace26f8fd9dd6cff3fdeead89eea33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Практическое руководство. Анимация точки с помощью ключевых кадров
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Point>.  
  
## <a name="example"></a>Пример  
 В следующем примере эллипс перемещается по треугольному пути. В этом примере <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство <xref:System.Windows.Media.EllipseGeometry>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  Во время первого полсекунды используется экземпляр <xref:System.Windows.Media.Animation.LinearPointKeyFrame> класса для перемещения эллипса в пути с постоянной скоростью, с его начальной позиции. Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearPointKeyFrame> создать smooth линейную интерполяцию между значениями.  
  
2.  Во время окончания следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> класса для мгновенного перемещения эллипса по путям к следующей позиции. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> создают резкие переходы между значениями.  
  
3.  В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplinePointKeyFrame> класса для возврата эллипса в его начальное положение. Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplinePointKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> свойство. В этом примере анимация начинается медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Для совместимости с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>. Однако при применении одной анимации в коде, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо <xref:System.Windows.Media.Animation.Storyboard>. Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.EllipseGeometry>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
