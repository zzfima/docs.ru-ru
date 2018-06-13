---
title: Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: 7e67fb07a05d474999515a678fd72ac6b96953c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561076"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации свойства. Для анимации свойства с помощью <xref:System.Windows.Media.Animation.Storyboard>, создайте анимацию для каждого свойства, которое необходимо анимировать, а также для создания <xref:System.Windows.Media.Animation.Storyboard> для хранения анимации.  
  
 Тип свойства определяет тип используемой анимации. Например, для анимации свойства, которое принимает <xref:System.Double> значения, используйте <xref:System.Windows.Media.Animation.DoubleAnimation>. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> И <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> вложенные свойства укажите объект и свойство, к которому применяется анимация.  
  
 Запуск раскадровки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действия и <xref:System.Windows.EventTrigger>. <xref:System.Windows.EventTrigger> Начинает <xref:System.Windows.Media.Animation.BeginStoryboard> действия, если событие, определяемое его <xref:System.Windows.EventTrigger.RoutedEvent%2A> происходит свойство. <xref:System.Windows.Media.Animation.BeginStoryboard> Запускает действие <xref:System.Windows.Media.Animation.Storyboard>.  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.Storyboard> объектов анимации два <xref:System.Windows.Controls.Button> элементов управления. Чтобы сделать первую кнопку Изменение размера, его <xref:System.Windows.FrameworkElement.Width%2A> выполняется анимация. Чтобы изменить цвет, вторая кнопка <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Controls.Control.Background%2A> кнопки, выполняется анимация.  
  
## <a name="example"></a>Пример  
 [!code-xaml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Несмотря на то, что анимация может ориентироваться и <xref:System.Windows.FrameworkElement> объект, такой как <xref:System.Windows.Controls.Control> или <xref:System.Windows.Controls.Panel>и <xref:System.Windows.Freezable> объект, такой как <xref:System.Windows.Media.Brush> или <xref:System.Windows.Media.Transform>, только элементы структуры имеют <xref:System.Windows.FrameworkElement.Name%2A> свойство. Для назначения имени объекту freezable, чтобы его можно было использовать в анимации, следует использовать [директиву x:Name](../../../../docs/framework/xaml-services/x-name-directive.md), как показано в предыдущем примере.  
  
 Если используется код, необходимо создать <xref:System.Windows.NameScope> для <xref:System.Windows.FrameworkElement> и зарегистрируйте имена объектов анимации с помощью <xref:System.Windows.FrameworkElement>. Чтобы запустить анимацию в коде, используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие с <xref:System.Windows.EventTrigger>. При необходимости можно использовать обработчик событий и <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод <xref:System.Windows.Media.Animation.Storyboard>. В следующем примере показано, как использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Дополнительные сведения об анимации и раскадровках см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Если используется код, вы не ограничены использованием <xref:System.Windows.Media.Animation.Storyboard> объекты для анимации свойства. Дополнительные сведения и примеры см. в разделах [Анимация свойств без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) и [Анимация свойств с помощью AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).
