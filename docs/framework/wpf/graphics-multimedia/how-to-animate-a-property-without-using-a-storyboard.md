---
title: Практическое руководство. Анимация свойства без использования раскадровки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- non-Storyboard animation
- local animation [WPF]
- animation [WPF], non-Storyboard (local)
ms.assetid: d411db70-4df7-487d-82bc-95a7c1b2e7f8
ms.openlocfilehash: 71711c0392576930e97986078ec5926ff6ca9813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963011"
---
# <a name="how-to-animate-a-property-without-using-a-storyboard"></a>Практическое руководство. Анимация свойства без использования раскадровки
В этом примере показан один из способов применения анимации к свойству без использования <xref:System.Windows.Media.Animation.Storyboard>.  
  
> [!NOTE]
> Эта функциональность недоступна в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Дополнительные сведения об анимации свойств в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md).  
  
 Чтобы применить локальную анимацию к свойству, используйте <xref:System.Windows.UIElement.BeginAnimation%2A> метод. Этот метод принимает два параметра: значение <xref:System.Windows.DependencyProperty> типа, указывающее свойство для анимации, и анимацию, применяемую к этому свойству.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как анимировать ширину и цвет <xref:System.Windows.Controls.Button>фона для.  
  
 [!code-cpp[animateproperty#11](~/samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](~/samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
 Для анимации различных типов свойств существуют разнообразные <xref:System.Windows.Media.Animation> классы анимации в пространстве имен. Дополнительные сведения об анимации свойств см. в разделе [Общие сведения об эффектах анимации](animation-overview.md). Дополнительные сведения о свойствах зависимостей (тип свойств, приведенных в этих примерах) и их функциях см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md).  
  
 Существуют и другие способы анимации без использования <xref:System.Windows.Media.Animation.Storyboard> объектов. Дополнительные сведения см. в разделе [Обзор методов анимации свойств](property-animation-techniques-overview.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>
- <xref:System.Windows.Media.Animation>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
