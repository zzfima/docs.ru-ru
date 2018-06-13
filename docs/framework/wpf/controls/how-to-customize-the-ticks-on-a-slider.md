---
title: Практическое руководство. Настройка делений на ползунке
ms.date: 03/30/2017
helpviewer_keywords:
- TickBar [WPF]
- Slider control [WPF], creating with TickBar
ms.assetid: 4fa694f2-a620-4b15-be78-5f4286f89361
ms.openlocfilehash: 667ec5d5504e18449800598f0b14548b7463bdf3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550882"
---
# <a name="how-to-customize-the-ticks-on-a-slider"></a>Практическое руководство. Настройка делений на ползунке
В этом примере показано, как создать <xref:System.Windows.Controls.Slider> элемента управления, содержащего деления.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Controls.Primitives.TickBar> Отображается при установке <xref:System.Windows.Controls.Slider.TickPlacement%2A> свойство в значение, отличное от <xref:System.Windows.Controls.Primitives.TickPlacement.None>, который является значением по умолчанию.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Slider> с <xref:System.Windows.Controls.Primitives.TickBar> отображает метки деления. <xref:System.Windows.Controls.Slider.TickPlacement%2A> И <xref:System.Windows.Controls.Slider.TickFrequency%2A> определяют расположение делений и интервал между ними. При перемещении <xref:System.Windows.Controls.Primitives.Thumb>, всплывающие подсказки отображают значение <xref:System.Windows.Controls.Slider>. <xref:System.Windows.Controls.Slider.AutoToolTipPlacement%2A> Свойство определяет, где появляется подсказка. <xref:System.Windows.Controls.Primitives.Thumb> Перемещений соответствуют расположение делений, так как <xref:System.Windows.Controls.Slider.IsSnapToTickEnabled%2A> равно `true`.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.Slider.Ticks%2A> свойства для создания метки вдоль деления <xref:System.Windows.Controls.Slider> через нерегулярные интервалы времени.  
  
 [!code-xaml[Slider#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Slider/xaml/window1.xaml#4)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Slider>  
 <xref:System.Windows.Controls.Primitives.TickBar>  
 <xref:System.Windows.Controls.Slider.TickPlacement%2A>  
 [Практические руководства, посвященные элементу управления Slider](http://msdn.microsoft.com/library/534be86c-afb2-425d-8186-631278a9925e)
