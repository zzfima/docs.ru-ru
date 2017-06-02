---
title: "Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления | Microsoft Docs"
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
  - "FocusVisualStyle - свойство"
  - "свойства, FocusVisualStyle"
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Применение стиля визуального отображения фокуса к элементу управления
В этом примере демонстрируется создание стиля визуального оформления фокуса в ресурсах и применение стиля к элементу управления, используя свойство <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
## Пример  
 В следующем примере определяется стиль, который создает дополнительные компоновки элемента управления, применяемые только тогда, когда этот элемент управления получает фокус от клавиатуры в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Это достигается путем определением стиля с <xref:System.Windows.Controls.ControlTemplate>, а затем путем обращения этого стиля в качестве ресурса при задании свойства <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Внешний прямоугольник, сходный с границей, помещается с внешней стороны прямоугольной области.  В противном случае изменение размера стиля использует <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> прямоугольного элемента управления, в котором применяется стиль визуального отображения фокуса.  Этот пример устанавливает отрицательные значения для <xref:System.Windows.FrameworkElement.Margin%2A>, чтобы граница появлялась с внешней стороны элемента управления, получившего фокус.  
  
 [!code-xml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> является дополнением к любому стилю шаблона элемента управления, поступающего из явного стиля или тематического стиля; основной стиль для элемента управления по\-прежнему может быть создан при помощи <xref:System.Windows.Controls.ControlTemplate> и путем установки этого стиля свойству <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 Стили визуального отображения фокуса следует использовать постоянно во всей теме или пользовательском интерфейсе, а не использовать различный стиль для каждого элемента, получившего фокус.  Дополнительные сведения см. в разделе [Стилизация фокуса в элементах управления и FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## См. также  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Стилизация фокуса в элементах управления и FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)