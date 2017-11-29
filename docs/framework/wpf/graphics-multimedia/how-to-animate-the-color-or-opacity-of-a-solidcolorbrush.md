---
title: "Практическое руководство. Анимация свойства \"Цвет\" или \"Непрозрачность\" элемента SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03052cdf68a5a8564d5a24c91521749c10afa6cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Практическое руководство. Анимация свойства "Цвет" или "Непрозрачность" элемента SolidColorBrush
В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется три анимации для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> и <xref:System.Windows.Media.Brush.Opacity%2A> из <xref:System.Windows.Media.SolidColorBrush>.  
  
-   Первая анимация <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Gray%2A> когда указатель мыши попадает на прямоугольник.  
  
-   Далее анимации другой <xref:System.Windows.Media.Animation.ColorAnimation>, изменяет цвет кисти на <xref:System.Windows.Media.Colors.Orange%2A> когда указатель мыши выходит за пределы прямоугольника.  
  
-   Последняя анимация <xref:System.Windows.Media.Animation.DoubleAnimation>, изменяет непрозрачность кисти 0,0 при нажатии левой кнопки мыши.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Более полный пример, в котором показано, как анимировать различные типы кистей, в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973). Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Для совместимости с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения соответствующих анимаций. Однако при применении одной анимации в коде, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо <xref:System.Windows.Media.Animation.Storyboard>. Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973)
