---
title: Практическое руководство. Создание элемента Spin
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 56385d7c31465e25f19486ea5cdaa8876cdb30ff
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43784449"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Практическое руководство. Создание элемента Spin
В этом примере показано, как создать элемент spin с помощью <xref:System.Windows.Media.RotateTransform> и <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 В следующем примере применяется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента. В примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> из <xref:System.Windows.Media.RotateTransform>. Чтобы сделать элемент spin на месте, в этом примере <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство элемента до точки (0,5, 0,5).  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Полный пример, который включает дополнительные примеры преобразования, см. в разделе [2 примеров](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
