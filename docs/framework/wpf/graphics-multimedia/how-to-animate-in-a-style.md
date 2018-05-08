---
title: Практическое руководство. Применение анимации в стиле
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: e0741a869ab81875aaa25340de851ef939e11a6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-in-a-style"></a>Практическое руководство. Применение анимации в стиле
В этом примере показано, как для анимации свойства в стиле. При анимации в стиле элемент framework, для которого определен стиль можно применить напрямую. Целевой объект freezable, вам необходимо «поставить точку» из свойства элемента со стилем.  
  
 В следующем примере несколько анимаций определены в стиле и применены к <xref:System.Windows.Controls.Button>. Когда пользователь перемещает указатель мыши на кнопку, его из непрозрачного переходит в частично полупрозрачные и обратно еще раз, многократно. При наведении указателя мыши с кнопки, она становится полностью непрозрачной. При нажатии кнопки цвет ее фона меняется с оранжевого на белый и обратно. Поскольку <xref:System.Windows.Media.SolidColorBrush> используется для рисования кнопки нельзя обращаться непосредственно, она осуществляется вниз с помощью кнопки <xref:System.Windows.Controls.Control.Background%2A> свойство.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Обратите внимание, что при анимации с использованием стиля, возможных в целевые объекты, которые не существуют. Например, предположим, что стиль использует <xref:System.Windows.Media.SolidColorBrush> переопределяется, чтобы задать свойства фона кнопки, но в некоторый момент стиль и цвет фона кнопки устанавливается с <xref:System.Windows.Media.LinearGradientBrush>.  При попытке анимации <xref:System.Windows.Media.SolidColorBrush> не создается исключение; анимация не выполняется автоматически.  
  
 Дополнительные сведения о синтаксисе планирования раскадровки см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).
