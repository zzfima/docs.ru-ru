---
title: Практическое руководство. Установка свойства после его анимации с помощью раскадровки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
ms.openlocfilehash: b8e9c08075b13f8d6f701d5ac6ae4f8ea8949184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a>Практическое руководство. Установка свойства после его анимации с помощью раскадровки
В некоторых случаях может оказаться, что не удается изменить значение свойства после его анимации.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.Storyboard> используется для анимации цвет <xref:System.Windows.Media.SolidColorBrush>. Раскадровка инициируется при нажатии кнопки. <xref:System.Windows.Media.Animation.Timeline.Completed> Событие обрабатывается, чтобы программа получает уведомление при <xref:System.Windows.Media.Animation.ColorAnimation> завершения.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a>Пример  
 После <xref:System.Windows.Media.Animation.ColorAnimation> завершения программа выполняет попытку изменить синий цвет кисти.  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 Предыдущий код не отображается никаких действий: кисть остается желтой, что является значением, предоставляемые <xref:System.Windows.Media.Animation.ColorAnimation> , анимация кисти. Значение базового свойства (базовое значение) фактически изменяется на синий. Тем не менее, действующие или текущая позиция, значение останется желтый поскольку <xref:System.Windows.Media.Animation.ColorAnimation> по-прежнему переопределяет базовое значение. Если требуется, чтобы базовое значение вновь стать действительное значение, необходимо остановить влияние свойства анимации. Это можно сделать с помощью анимации раскадровки тремя способами:  
  
-   Задать анимации <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
  
-   Удалите раскадровку целиком.  
  
-   Удаление анимации из отдельного свойства.  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a>Задать свойство режима FillBehavior анимации табуляции  
 Установив <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для <xref:System.Windows.Media.Animation.FillBehavior.Stop>, уведомляет анимацию о прекращении влияния на целевое свойство после достижения конца активного периода.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a>Удалите раскадровку целиком.  
 С помощью <xref:System.Windows.Media.Animation.RemoveStoryboard> триггера или <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> метода, вы анимациям раскадровки для остановки влияет на их целевого свойства. Разница между этим подходом и установкой <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство является раскадровки можно удалить в любое время, а <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойство действует только при достижении конца активного периода анимацией.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a>Удаление анимации из отдельного свойства  
 Другим способом остановки влияния свойство анимации заключается в использовании <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> метод анимируемого объекта. Укажите как первый параметр анимируемого свойства и `null` вторым.  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 Этот способ также работает для анимаций без раскадровки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
