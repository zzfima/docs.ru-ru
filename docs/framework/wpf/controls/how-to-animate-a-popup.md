---
title: "Практическое руководство. Анимация контекстного меню"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd79b29849510f40034dd0e2f1d9668c9b742929
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-popup"></a>Практическое руководство. Анимация контекстного меню
В этом примере показаны два способа анимации <xref:System.Windows.Controls.Primitives.Popup> элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере задается <xref:System.Windows.Controls.Primitives.PopupAnimation> свойство в значение <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, чего <xref:System.Windows.Controls.Primitives.Popup> для «слайд в» когда он появится.  
  
 Чтобы повернуть <xref:System.Windows.Controls.Primitives.Popup>, этот пример назначает <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойство <xref:System.Windows.Controls.Canvas>, который является дочерним элементом элемента <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Для корректной работы преобразования в примере необходимо присвоить <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> свойства `true`. Кроме того <xref:System.Windows.FrameworkElement.Margin%2A> на <xref:System.Windows.Controls.Canvas> содержимого необходимо указать достаточно места для <xref:System.Windows.Controls.Primitives.Popup> для поворота.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 В следующем примере показан способ <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие, возникающее при <xref:System.Windows.Controls.Button> нажатии триггеры <xref:System.Windows.Media.Animation.Storyboard> , запускающее анимацию.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Общие сведения о контекстном меню](../../../../docs/framework/wpf/controls/popup-overview.md)
