---
title: "Практическое руководство. Применение свойства Stretch к содержимому элемента Viewbox | Microsoft Docs"
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
  - "элементы управления, Viewbox"
  - "Stretch - свойства"
  - "StretchDirection - свойства"
  - "Viewbox - элемент управления"
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Применение свойства Stretch к содержимому элемента Viewbox
## Пример  
 В этом примере описывается порядок изменения значений свойств <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> и <xref:System.Windows.Controls.Viewbox.Stretch%2A> элемента <xref:System.Windows.Controls.Viewbox>.  
  
 В первом примере используется [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения элемента <xref:System.Windows.Controls.Viewbox>.  Назначается значение 400 для свойств <xref:System.Windows.FrameworkElement.MaxWidth%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A>.  В примере в элемент <xref:System.Windows.Controls.Viewbox> вкладывается элемент <xref:System.Windows.Controls.Image>.  Элементы <xref:System.Windows.Controls.Button>, которые соответствуют значениям свойств для перечислений <xref:System.Windows.Controls.Viewbox.Stretch%2A> и <xref:System.Windows.Controls.StretchDirection>, управляют растяжением вложенного <xref:System.Windows.Controls.Image>.  
  
 [!code-xml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 В следующем файле кода программной части выполняется обработка событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> объекта <xref:System.Windows.Controls.Button>, которые определены в предыдущем примере [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.Viewbox>   
 <xref:System.Windows.Media.Stretch>   
 <xref:System.Windows.Controls.StretchDirection>