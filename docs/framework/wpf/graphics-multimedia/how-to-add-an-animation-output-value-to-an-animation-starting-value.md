---
title: "Практическое руководство. Добавление выходного значения анимации к начальному значению анимации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF]
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a670a29e4bd982418ac92ef0e2ac65635763671
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-an-animation-output-value-to-an-animation-starting-value"></a>Практическое руководство. Добавление выходного значения анимации к начальному значению анимации
В этом примере показано, как добавить выходное значение анимации к начальному значению анимации.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> Свойство указывает, следует ли выходное значение анимации добавлен к начальному значению (базовое значение) анимированного свойства. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> свойство с большинством базовых анимаций и большинство анимации ключевого кадра. Дополнительные сведения см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В следующем примере показано применение <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimation> и с помощью <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=nameWithType> свойство с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  
  
 [!code-xaml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Накапливание значений анимации в повторяющихся циклах](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Анимация и расчет времени](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
