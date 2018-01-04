---
title: "Практическое руководство. Анимация свойства \"Прозрачность\" элемента или кисти"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3b750e6ee21c8347d3896ec290f0ff564cc0a2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Практическое руководство. Анимация свойства "Прозрачность" элемента или кисти
Чтобы сделать элемент структуры исчезновения и появления, анимация его <xref:System.Windows.UIElement.Opacity%2A> свойство или анимировать <xref:System.Windows.Media.Brush.Opacity%2A> свойство <xref:System.Windows.Media.Brush> (или кисти) используется для рисования. Анимация прозрачности элемента упрощает исчезновения и появления его дочерних элементов, но анимации кисть, используемую для рисования элемента позволяет иметь большую избирательность о Плавное какая часть элемента. Например вы Анимация прозрачности кисть, используемую для рисования фона кнопки. Это приведет к тому и исчезновения представления, оставив его текст полностью непрозрачный фон кнопки.  
  
> [!NOTE]
>  Анимация <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.Brush> дает выигрыш в производительности, чем анимация <xref:System.Windows.UIElement.Opacity%2A> свойства элемента.  
  
 В следующем примере две кнопки анимированных, чтобы они исчезновения и появления. Непрозрачность первого <xref:System.Windows.Controls.Button> анимация от `1.0` для `0.0` над <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 секунд. Вторая кнопка также анимации, но непрозрачность SolidColorBrush используется для рисования его <xref:System.Windows.Controls.Control.Background%2A> анимировано вместо непрозрачность кнопка целиком. При запуске данного примера первая кнопка проявляется и исчезает вся, пока фон вторая кнопка исчезает и появляется. Текст и границы остаются полностью непрозрачными.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 В этом примере отсутствует код. Полный пример также показано, как анимация прозрачности <xref:System.Windows.Media.Color> в <xref:System.Windows.Media.LinearGradientBrush>.  Полный пример см. в разделе [Анимация прозрачности элемента-пример](http://go.microsoft.com/fwlink/?LinkID=159968).
