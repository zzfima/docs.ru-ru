---
title: "Практическое руководство. Применение преобразования к элементу при возникновении события"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58ef8c008eea4c10228ebb10ceadb5806dfbc0f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Практическое руководство. Применение преобразования к элементу при возникновении события
В этом примере показано, как применить <xref:System.Windows.Media.ScaleTransform> при возникновении события. Показанный подход аналогичен тому, который используется при применении других типов преобразований. Дополнительные сведения о доступных типах преобразований см. в разделе <xref:System.Windows.Media.Transform> класса или [преобразует Обзор](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Преобразование можно применить к элементу любым из двух следующих способов:  
  
-   Если сделать *не* требуется преобразование влияет на макет, используйте <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента.  
  
-   Преобразование, влияет на макет, используйте <xref:System.Windows.FrameworkElement.LayoutTransform%2A> свойство элемента.  
  
 В следующем примере применяется <xref:System.Windows.Media.ScaleTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства кнопки. При перемещении указателя мыши на кнопку <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> свойства <xref:System.Windows.Media.ScaleTransform> присваиваются `2`, что приводит к увеличению кнопки. При перемещении указателя мыши с кнопки <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> присваивается значение `1`, которое вызывает кнопку, чтобы вернуться к исходному размеру.  
  
## <a name="example"></a>Пример  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
