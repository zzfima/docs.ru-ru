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
ms.openlocfilehash: 6cfce9a5b070a23ed9ac03473888bf572b61393b
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559642"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств. Чтобы анимировать свойство с помощью <xref:System.Windows.Media.Animation.Storyboard>, создайте анимацию для каждого свойства, которое необходимо анимировать, а также создайте <xref:System.Windows.Media.Animation.Storyboard> для хранения анимации.  
  
 Тип свойства определяет тип используемой анимации. Например, чтобы анимировать свойство, принимающее <xref:System.Double> значения, используйте <xref:System.Windows.Media.Animation.DoubleAnimation>. Присоединенные свойства <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> указывают объект и свойство, к которому применяется анимация.  
  
 Чтобы запустить раскадровку в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие и <xref:System.Windows.EventTrigger>. <xref:System.Windows.EventTrigger> начинает действие <xref:System.Windows.Media.Animation.BeginStoryboard>, когда происходит событие, заданное свойством <xref:System.Windows.EventTrigger.RoutedEvent%2A>. Действие <xref:System.Windows.Media.Animation.BeginStoryboard> запускает <xref:System.Windows.Media.Animation.Storyboard>.  
  
 В следующем примере объекты <xref:System.Windows.Media.Animation.Storyboard> используются для анимации двух элементов управления <xref:System.Windows.Controls.Button>. Чтобы изменить размер первой кнопки, ее <xref:System.Windows.FrameworkElement.Width%2A> анимируется. Чтобы изменить цвет второй кнопки, свойство <xref:System.Windows.Media.SolidColorBrush.Color%2A> <xref:System.Windows.Media.SolidColorBrush> используется для задания <xref:System.Windows.Controls.Control.Background%2A> анимированной кнопки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Хотя анимация может ориентироваться как на объект <xref:System.Windows.FrameworkElement>, например <xref:System.Windows.Controls.Control>, <xref:System.Windows.Controls.Panel>, так и на объект <xref:System.Windows.Freezable>, например <xref:System.Windows.Media.Brush> или <xref:System.Windows.Media.Transform>, только элементы платформы имеют свойство <xref:System.Windows.FrameworkElement.Name%2A>. Для назначения имени объекту freezable, чтобы его можно было использовать в анимации, следует использовать [директиву x:Name](../../../desktop-wpf/xaml-services/xname-directive.md), как показано в предыдущем примере.  
  
 При использовании кода необходимо создать <xref:System.Windows.NameScope> для <xref:System.Windows.FrameworkElement> и зарегистрировать имена объектов для анимации с этим <xref:System.Windows.FrameworkElement>. Чтобы начать анимацию в коде, используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие с <xref:System.Windows.EventTrigger>. При необходимости можно использовать обработчик событий и метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> <xref:System.Windows.Media.Animation.Storyboard>. В следующем примере показано, как использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Дополнительные сведения об анимации и раскадровках см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 Если вы используете код, вы не ограничены использованием объектов <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств. Дополнительные сведения и примеры см. в разделах [Анимация свойств без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md) и [Анимация свойств с помощью AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
