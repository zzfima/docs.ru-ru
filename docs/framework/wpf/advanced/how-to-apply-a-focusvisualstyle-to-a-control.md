---
title: Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459807"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
В этом примере показано, как создать визуальный стиль фокуса в ресурсах и применить стиль к элементу управления с помощью свойства <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется стиль, который создает дополнительный набор элементов управления, который применяется только в том случае, если этот элемент управления имеет фокус ввода в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, а затем ссылки на этот стиль как на ресурс при задании свойства <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Внешний прямоугольник, напоминающий границу, помещается за пределы прямоугольной области. Если не было изменено иное, при изменении размера стиля используется <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, в котором применяется визуальный стиль фокуса. В этом примере задаются отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A>, чтобы граница отображалась немного за пределами элемента управления.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> дополняет любой стиль шаблона элемента управления, который поступает либо из явного стиля, либо из стиля темы. Основной стиль элемента управления по-прежнему можно создать с помощью <xref:System.Windows.Controls.ControlTemplate> и присвоив этому стилю значение свойства <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 Визуальные стили фокуса должны постоянно использоваться в теме или пользовательском интерфейсе, вместо того чтобы использовать для каждого фокусного элемента другую. Дополнительные сведения см. [в разделе Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
