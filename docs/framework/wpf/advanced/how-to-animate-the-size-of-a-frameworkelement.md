---
title: "Практическое руководство. Анимация размера элемента FrameworkElement | Microsoft Docs"
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
  - "анимация, FrameworkElement - размер"
  - "FrameworkElement, анимация размера"
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Анимация размера элемента FrameworkElement
Для анимации размера элемента <xref:System.Windows.FrameworkElement> можно анимировать его свойства <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> или использовать анимированное преобразование <xref:System.Windows.Media.ScaleTransform>.  
  
 В следующем примере анимируется размер двух кнопок с помощью этих двух подходов.  Размер одной кнопки изменяется анимированием его свойства <xref:System.Windows.FrameworkElement.Width%2A>, а размер другой изменяется анимированием преобразования <xref:System.Windows.Media.ScaleTransform>, применяемого к свойству <xref:System.Windows.UIElement.RenderTransform%2A>.  Каждая кнопка содержит текст.  Изначально текст отображается одинаково на обеих кнопках, но так как размеры кнопок изменяются, текст на второй кнопке искажается.  
  
## Пример  
 [!code-xml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 При преобразовании элемента преобразуется весь элемент и его содержимое.  При непосредственном изменении размер элемента, как в случае первой кнопки, размер содержимого элемента не изменяется, так как его размер и положение не зависят от размера родительского элемента.  
  
 Анимация размера элемента с применением анимированного преобразования к его свойству <xref:System.Windows.UIElement.RenderTransform%2A> обеспечивает большую производительность, чем непосредственная анимация свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A>, так как свойство <xref:System.Windows.UIElement.RenderTransform%2A> не запускает цикл обработки макета.  
  
 Дополнительные сведения о свойствах анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  Дополнительные сведения о преобразованиях см. в разделе [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).