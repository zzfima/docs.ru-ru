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
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124667"
---
# <a name="how-to-animate-a-borderthickness-value"></a>Практическое руководство. Анимирование значения BorderThickness
В этом примере показано, как анимировать изменения толщины границы с помощью класса <xref:System.Windows.Media.Animation.ThicknessAnimation>.  
  
## <a name="example"></a>Пример  
 В следующем примере Толщина границы анимируется с помощью <xref:System.Windows.Media.Animation.ThicknessAnimation>. В примере используется свойство <xref:System.Windows.Controls.Border.BorderThickness%2A> <xref:System.Windows.Controls.Border>.  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 Полный пример см. в разделе [Коллекция примеров анимации](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md)
- [Разделы руководства по анимации и времени](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [Анимация толщины границы с помощью ключевых кадров](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
