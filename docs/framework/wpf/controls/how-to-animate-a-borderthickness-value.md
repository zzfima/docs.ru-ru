---
title: Практическое руководство. Анимирование значения BorderThickness
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: d1ead0493d75f708557f0598d603440221182ebc
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44700670"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Практическое руководство. Анимирование значения BorderThickness
В этом примере показано, как анимировать изменения толщины границы с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation> класса.  
  
## <a name="example"></a>Пример  
 Следующий пример анимирует толщины границы с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation>. В примере используется <xref:System.Windows.Controls.Border.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Полный пример см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.ThicknessAnimation>  
 <xref:System.Windows.Controls.Border.BorderThickness%2A>  
 <xref:System.Windows.Controls.Border>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Анимация и расчет времени](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [Анимация толщины границы с помощью ключевых кадров](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
