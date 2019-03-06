---
title: Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: c4b379d3c57b6d0ae29952c23a35d7cc2cdf7f96
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366605"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
В этом примере показано, как создать визуальный стиль фокуса в ресурсах и применить стиль к элементу управления с помощью <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется стиль, который создает дополнительный контроль композиции, который применяется, только если этот элемент управления получает фокус от клавиатуры в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, то ссылки на этот стиль как ресурс, при задании <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.  
  
 Внешний прямоугольник, сходный с границей помещается за пределами прямоугольной области. В противном случае изменение размера стиля использует <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, где применяется визуальный стиль фокуса. В этом примере задает отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A> чтобы сделать границу немного находиться за пределами элемента управления с фокусом.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Объект <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> является дополнением к любой стиль шаблона элемента управления, поступающие из явного стиля или стиля темы; основной стиль для элемента управления можно по-прежнему создаваться с помощью <xref:System.Windows.Controls.ControlTemplate> и установив для этого стиля <xref:System.Windows.FrameworkElement.Style%2A> свойство.  
  
 Фокус, визуальные стили должен последовательно использоваться между тем и пользовательский Интерфейс, вместо того чтобы использовать его для каждого элемента, способному получать фокус. Дополнительные сведения см. в разделе [Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Стилизация и использование шаблонов](../controls/styling-and-templating.md)
- [Стилизация фокуса в элементах управления и FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
