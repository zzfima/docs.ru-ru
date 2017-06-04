---
title: "Практическое руководство. Анимация свойства &quot;Цвет&quot; или &quot;Непрозрачность&quot; элемента SolidColorBrush | Microsoft Docs"
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
  - "анимация, цвет SolidColorBrush"
  - "анимация, непрозрачность SolidColorBrush"
  - "цвета, анимирование"
  - "непрозрачность, анимирование"
  - "SolidColorBrush, анимация цвета"
  - "SolidColorBrush, анимация прозрачности"
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Анимация свойства &quot;Цвет&quot; или &quot;Непрозрачность&quot; элемента SolidColorBrush
В следующем примере демонстрируется анимация свойств <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> элемента <xref:System.Windows.Media.SolidColorBrush>.  
  
## Пример  
 В следующем примере используется три анимации для анимирования свойств <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> элемента <xref:System.Windows.Media.SolidColorBrush>.  
  
-   Первая анимация, <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Gray%2A>, когда указатель мыши попадает на прямоугольник.  
  
-   Следующая анимация, другая <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Orange%2A>, когда указатель мыши выходит за пределы прямоугольника.  
  
-   Последняя анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, изменяет непрозрачность кисти на 0,0 при нажатии левой кнопки мыши.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Более полный пример, показывающий, как анимировать различные типы кистей см. на странице [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Для совместимости с другими примерами анимации, в разных версиях кода этого примера используется объект <xref:System.Windows.Media.Animation.Storyboard> для применения соответствующих анимаций.  Однако при применении одной анимации в коде проще использовать метод <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> вместо <xref:System.Windows.Media.Animation.Storyboard>.  Пример см. в разделе [Анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973)