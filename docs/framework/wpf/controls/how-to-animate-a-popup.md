---
title: "Практическое руководство. Анимация контекстного меню | Microsoft Docs"
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
  - "анимация, Popup - элементы управления"
  - "Popup - элемент управления, анимирование"
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Анимация контекстного меню
В этом примере показаны два способа анимации элемента управления <xref:System.Windows.Controls.Primitives.Popup>.  
  
## Пример  
 В примере свойству <xref:System.Windows.Controls.Primitives.PopupAnimation> присваивается значение <xref:System.Windows.Controls.Primitives.PopupAnimation>, в результате чего достигается эффект «скольжения» при появлении элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Чтобы повернуть элемент управления <xref:System.Windows.Controls.Primitives.Popup>, в этом примере значение <xref:System.Windows.Media.RotateTransform> присваивается свойству <xref:System.Windows.UIElement.RenderTransform%2A> объекта <xref:System.Windows.Controls.Canvas>, который является дочерним элементом <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Для корректной работы преобразования в примере необходимо присвоить свойству <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> значение `true`.  Кроме того, в свойстве <xref:System.Windows.FrameworkElement.Margin%2A> содержимого объекта <xref:System.Windows.Controls.Canvas> должно быть задано достаточно места для поворота элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 В следующем примере показано, как событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, которое возникает при щелчке кнопки <xref:System.Windows.Controls.Button>, инициирует событие <xref:System.Windows.Media.Animation.Storyboard>, запускающее анимацию.  
  
 [!code-xml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## См. также  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Controls.Primitives.BulletDecorator>   
 <xref:System.Windows.Media.RotateTransform>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Практические руководства](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Общие сведения о контекстном меню](../../../../docs/framework/wpf/controls/popup-overview.md)