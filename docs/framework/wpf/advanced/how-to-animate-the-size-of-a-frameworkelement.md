---
title: Практическое руководство. Анимация размера элемента FrameworkElement
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
ms.openlocfilehash: 148e3d592e129984bd2f7ac062340c5169e48d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>Практическое руководство. Анимация размера элемента FrameworkElement
Для анимации размера <xref:System.Windows.FrameworkElement>, можно анимировать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства или использовать анимированное <xref:System.Windows.Media.ScaleTransform>.  
  
 В следующем примере анимируется размер двух кнопок с помощью этих двух подходов. Размер одной кнопки изменяется с помощью анимации его <xref:System.Windows.FrameworkElement.Width%2A> свойства, а другой изменяется с помощью анимации <xref:System.Windows.Media.ScaleTransform> применены к его <xref:System.Windows.UIElement.RenderTransform%2A> свойство. Каждая кнопка содержит текст. Изначально текст отображается одинаково на обеих кнопок, но как кнопок изменяются, текст на второй кнопке искажается.  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 При преобразовании элемента преобразуется весь элемент и его содержимое. При непосредственном изменении размер элемента, как в случае первой кнопки, содержимое элемента не изменяются, если их размер и положение зависят от размера родительского элемента.  
  
 Анимация размера элемента с применением анимированного преобразования к его <xref:System.Windows.UIElement.RenderTransform%2A> свойство обеспечивает более высокую производительность, чем анимировать его <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> напрямую, так как <xref:System.Windows.UIElement.RenderTransform%2A> свойство не вызывает передачи макета.  
  
 Дополнительные сведения о свойствах анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Дополнительные сведения о преобразованиях см. в разделе [преобразует Обзор](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).
