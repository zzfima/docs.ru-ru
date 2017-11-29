---
title: "Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f614e244293d08cd836edaf82496ca9e7b51423e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
В этом примере показано, как создать стиль визуального отображения фокуса в ресурсах и применение стиля к элементу управления с помощью <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется стиль, который создает дополнительный контроль композиции, только тогда, когда этот элемент управления получает фокус от клавиатуры в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Это достигается путем определения стиля с <xref:System.Windows.Controls.ControlTemplate>, то обращения этого стиля как ресурса при задании <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> свойство.  
  
 Внешний прямоугольник, сходный с границей помещается за пределами прямоугольной области. В противном случае изменение размера стиля использует <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, где применяется стиль визуального отображения фокуса. Этот пример устанавливает отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A> вносить граница появлялась вне элемента управления с фокусом.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Объект <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> является дополнением к любой стиля шаблона элемента управления, поступающие из явного стиля или тематического стиля; Основной стиль для элемента управления по-прежнему создаются с помощью <xref:System.Windows.Controls.ControlTemplate> и установив для этого стиля <xref:System.Windows.FrameworkElement.Style%2A> свойство.  
  
 Фокус визуальные стили следует использовать постоянно во всей темы или пользовательского интерфейса, вместо того чтобы использовать его для каждого элемента может иметь фокус. Дополнительные сведения см. в разделе [стиля фокуса в элементах управления и стиля визуального отображения фокуса](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Стилизация фокуса в элементах управления и FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
