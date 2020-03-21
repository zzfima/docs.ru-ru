---
title: Практическое руководство. Создание элемента Spin
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112080"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Практическое руководство. Создание элемента Spin
Этот пример показывает, как сделать <xref:System.Windows.Media.RotateTransform> элемент <xref:System.Windows.Media.Animation.DoubleAnimation>спина с помощью и .  
  
 Следующий пример <xref:System.Windows.Media.RotateTransform> применяется <xref:System.Windows.UIElement.RenderTransform%2A> к свойству элемента. Пример использует <xref:System.Windows.Media.Animation.DoubleAnimation> для анимировать <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>. Чтобы элемент вращаться на месте, <xref:System.Windows.UIElement.RenderTransformOrigin%2A> пример устанавливает свойство элемента в точку (0,5, 0,5).  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Для полного образца, который включает в себя больше примеров [трансформации, см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о классах Transform](transforms-overview.md)
