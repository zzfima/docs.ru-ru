---
title: "Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, Раскадровки"
  - "Раскадровки, анимация"
ms.assetid: f4a314e9-1da2-4367-85fc-1232487efa7a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Анимирование свойства с помощью раскадровки (класс Storyboard)
В этом примере показано использование <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств.  Для анимации свойства с помощью <xref:System.Windows.Media.Animation.Storyboard>, создайте анимацию для каждого свойства, которое требуется анимировать, а также создайте <xref:System.Windows.Media.Animation.Storyboard> для хранения анимации.  
  
 Тип свойства определяет тип используемой анимации.  Например, чтобы анимация свойства, которое принимает значения <xref:System.Double>, используйте <xref:System.Windows.Media.Animation.DoubleAnimation>.  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> и <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> [вложенные свойства](GTMT) определяют объект и свойства, к которым применяется анимация.  
  
 Чтобы запустить раскадровку в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], используйте действия <xref:System.Windows.Media.Animation.BeginStoryboard> и <xref:System.Windows.EventTrigger>.  <xref:System.Windows.EventTrigger> начинает действие <xref:System.Windows.Media.Animation.BeginStoryboard> при возникновении события, заданного его свойством <xref:System.Windows.EventTrigger.RoutedEvent%2A>.  Действие <xref:System.Windows.Media.Animation.BeginStoryboard> запускает <xref:System.Windows.Media.Animation.Storyboard>.  
  
 В следующем примере используются объекты <xref:System.Windows.Media.Animation.Storyboard> для анимации двух элементов управления <xref:System.Windows.Controls.Button>.  Чтобы заставить первую кнопку изменить размер, анимируется ее <xref:System.Windows.FrameworkElement.Width%2A>.  Чтобы заставить вторую кнопку изменить цвета, свойство <xref:System.Windows.Media.SolidColorBrush.Color%2A> элемента <xref:System.Windows.Media.SolidColorBrush> используется для установки <xref:System.Windows.Controls.Control.Background%2A> анимированной кнопки.  
  
## Пример  
 [!code-xml[AnimatePropertyStoryboards#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/StoryboardExample.xaml#1)]  
  
> [!NOTE]
>  Несмотря на то, что анимация может ориентироваться и на объект <xref:System.Windows.FrameworkElement>, например <xref:System.Windows.Controls.Control> или <xref:System.Windows.Controls.Panel>, и на объект <xref:System.Windows.Freezable>, например <xref:System.Windows.Media.Brush> или <xref:System.Windows.Media.Transform>, только элементы структуры имеют свойство <xref:System.Windows.FrameworkElement.Name%2A>.  Чтобы назначить имя замороженному объекту таким образом, чтобы на него могла быть ориентирована анимация, используйте [Директива x:Name](../../../../docs/framework/xaml-services/x-name-directive.md), как показано в предыдущем примере.  
  
 Если используется код, необходимо создать <xref:System.Windows.NameScope> для <xref:System.Windows.FrameworkElement> и зарегистрировать имена объектов для анимации с этим <xref:System.Windows.FrameworkElement>.  Для запуска анимации из кода используйте действие <xref:System.Windows.Media.Animation.BeginStoryboard> с <xref:System.Windows.EventTrigger>.  При необходимости можно использовать обработчик событий и метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> класса <xref:System.Windows.Media.Animation.Storyboard>.  В следующем примере показано, как использовать метод <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>.  
  
 [!code-csharp[AnimatePropertyStoryboards#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatePropertyStoryboards/CSharp/StoryboardExample.cs#11)]
 [!code-vb[AnimatePropertyStoryboards#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimatePropertyStoryboards/VisualBasic/StoryboardExample.vb#11)]  
  
 Дополнительные сведения об анимации и раскадровках см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Если используется код, не ограничивайте использование объектов <xref:System.Windows.Media.Animation.Storyboard> для анимации свойств.  Дополнительные сведения и примеры см. в разделах [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md) и [Анимирование свойства с помощью AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).