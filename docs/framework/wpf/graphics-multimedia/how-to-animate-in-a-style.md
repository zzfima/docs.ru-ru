---
title: "Практическое руководство. Применение анимации в стиле"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10cd243c633e7a7e458d2026fc5e3d91d2996427
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-in-a-style"></a>Практическое руководство. Применение анимации в стиле
В этом примере показано, как для анимации свойства в стиле. При анимации в стиле элемент framework, для которого определен стиль можно применить напрямую. Целевой объект freezable, вам необходимо «поставить точку» из свойства элемента со стилем.  
  
 В следующем примере несколько анимаций определены в стиле и применены к <xref:System.Windows.Controls.Button>. Когда пользователь перемещает указатель мыши на кнопку, его из непрозрачного переходит в частично полупрозрачные и обратно еще раз, многократно. При наведении указателя мыши с кнопки, она становится полностью непрозрачной. При нажатии кнопки цвет ее фона меняется с оранжевого на белый и обратно. Поскольку <xref:System.Windows.Media.SolidColorBrush> используется для рисования кнопки нельзя обращаться непосредственно, она осуществляется вниз с помощью кнопки <xref:System.Windows.Controls.Control.Background%2A> свойство.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 Обратите внимание, что при анимации с использованием стиля, возможных в целевые объекты, которые не существуют. Например, предположим, что стиль использует <xref:System.Windows.Media.SolidColorBrush> переопределяется, чтобы задать свойства фона кнопки, но в некоторый момент стиль и цвет фона кнопки устанавливается с <xref:System.Windows.Media.LinearGradientBrush>.  При попытке анимации <xref:System.Windows.Media.SolidColorBrush> не создается исключение; анимация не выполняется автоматически.  
  
 Дополнительные сведения о синтаксисе планирования раскадровки см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md). Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).
