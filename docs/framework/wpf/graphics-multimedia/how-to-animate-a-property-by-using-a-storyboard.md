---
title: Практическое руководство. Анимация свойства с помощью раскадровки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], Storyboards
- Storyboards [WPF], animation
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
ms.openlocfilehash: a7a2656d84d37d3e2726df009a07ccf29661df07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963043"
---
# <a name="how-to-animate-a-property-by-using-a-storyboard"></a>Практическое руководство. Анимация свойства с помощью раскадровки
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств. Чтобы анимировать свойство с помощью <xref:System.Windows.Media.Animation.Storyboard>, создайте анимацию для каждого свойства, которое необходимо анимировать, а также создайте объект <xref:System.Windows.Media.Animation.Storyboard> для хранения анимации.  
  
 Тип свойства определяет тип используемой анимации. Например, чтобы анимировать свойство, принимающее <xref:System.Double> значения, <xref:System.Windows.Media.Animation.DoubleAnimation>используйте. Вложенные <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> свойства изадаютобъектисвойство,ккоторомуприменяетсяанимация.<xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>  
  
 Чтобы запустить раскадровку [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в, <xref:System.Windows.Media.Animation.BeginStoryboard> используйте действие и <xref:System.Windows.EventTrigger>. Запускает действие, когда происходит событие, заданное его <xref:System.Windows.EventTrigger.RoutedEvent%2A> свойством. <xref:System.Windows.Media.Animation.BeginStoryboard> <xref:System.Windows.EventTrigger> <xref:System.Windows.Media.Animation.BeginStoryboard> Действие<xref:System.Windows.Media.Animation.Storyboard>запускает.  
  
 В следующем примере объекты <xref:System.Windows.Media.Animation.Storyboard> используются для анимации двух <xref:System.Windows.Controls.Button> элементов управления. Чтобы изменить размер первой кнопки, <xref:System.Windows.FrameworkElement.Width%2A> она будет анимирована. Чтобы изменить цвет второй кнопки, <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство <xref:System.Windows.Media.SolidColorBrush> объекта используется для задания <xref:System.Windows.Controls.Control.Background%2A> анимированной кнопки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[AnimatePropertyStoryboards#1](~/samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
> Хотя анимация может ориентироваться и <xref:System.Windows.FrameworkElement> на объект, например <xref:System.Windows.Controls.Control> или <xref:System.Windows.Media.Brush> <xref:System.Windows.Freezable> <xref:System.Windows.Controls.Panel>, и на объект <xref:System.Windows.FrameworkElement.Name%2A> , например или <xref:System.Windows.Media.Transform>, только элементы платформы имеют свойство. Для назначения имени объекту freezable, чтобы его можно было использовать в анимации, следует использовать [директиву x:Name](../../xaml-services/x-name-directive.md), как показано в предыдущем примере.  
  
 При использовании кода необходимо создать <xref:System.Windows.NameScope> <xref:System.Windows.FrameworkElement> для и зарегистрировать имена <xref:System.Windows.FrameworkElement>объектов для анимации. Чтобы начать анимацию в коде, используйте <xref:System.Windows.Media.Animation.BeginStoryboard> действие <xref:System.Windows.EventTrigger>с. При необходимости можно использовать обработчик событий и <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> <xref:System.Windows.Media.Animation.Storyboard>метод. В следующем примере показано, как использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Дополнительные сведения об анимации и раскадровках см. в разделе [Общие сведения об эффектах анимации](animation-overview.md).  
  
 При использовании кода вы не ограничены использованием <xref:System.Windows.Media.Animation.Storyboard> объектов для анимации свойств. Дополнительные сведения и примеры см. в разделах [Анимация свойств без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md) и [Анимация свойств с помощью AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).
