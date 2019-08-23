---
title: Практическое руководство. Анимация прозрачности элемента или кисти
ms.date: 03/30/2017
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
ms.openlocfilehash: 2f18861eb18f81b631245d1d933b7acb1b3e0e42
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950510"
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a>Практическое руководство. Анимация прозрачности элемента или кисти
Чтобы сделать элемент платформы неограниченным, можно анимировать его <xref:System.Windows.UIElement.Opacity%2A> свойство или <xref:System.Windows.Media.Brush.Opacity%2A> анимировать свойство объекта <xref:System.Windows.Media.Brush> (или кисти), используемого для его рисования. Анимация прозрачности элемента делает его и его дочерние элементы недоступными для просмотра, но анимация кисти, используемой для рисования элемента, позволяет более избирательно выбирать часть элемента. Например, можно анимировать прозрачность кисти, используемой для рисования фона кнопки. Это приведет к появлению и исчезновению фона кнопки, при этом текст полностью непрозрачен.  
  
> [!NOTE]
> Анимация объекта предоставляет преимущества производительности по сравнению с анимацией свойстваэлемента.<xref:System.Windows.UIElement.Opacity%2A> <xref:System.Windows.Media.Brush> <xref:System.Windows.Media.Brush.Opacity%2A>  
  
 В следующем примере две кнопки анимированы, чтобы они исчезали и рассматриваются. Прозрачность первого <xref:System.Windows.Controls.Button> элемента анимации анимируется от `1.0` до `0.0` <xref:System.Windows.Media.Animation.Timeline.Duration%2A> пяти секунд. Вторая кнопка также анимируется, но непрозрачность SolidColorBrush, используемая для ее <xref:System.Windows.Controls.Control.Background%2A> рисования, анимируется, а не прозрачность всей кнопки. При выполнении этого примера первая кнопка полностью исчезает и выходит из представления, а только фон второй кнопки постепенно исчезает и не отображается. Его текст и граница остаются полностью непрозрачными.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#10](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 В этом примере код пропущен. В полном примере также показано, как анимировать непрозрачность <xref:System.Windows.Media.Color> <xref:System.Windows.Media.LinearGradientBrush>элемента в.  Полный пример см. в разделе [Анимация прозрачности образца элемента](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/OpacityAnimation).
