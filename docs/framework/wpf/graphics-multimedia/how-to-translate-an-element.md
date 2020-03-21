---
title: Практическое руководство. Смещение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: addff0e22fb3f27ea924887809c0635aeb3ad67d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111976"
---
# <a name="how-to-translate-an-element"></a>Практическое руководство. Смещение элемента
В этом примере показано, как переводить <xref:System.Windows.Media.TranslateTransform>(двигать) элемент с помощью .  
  
 Класс <xref:System.Windows.Media.TranslateTransform> особенно полезен для движущихся элементов внутри панелей, которые не поддерживают абсолютное позиционирование. Например, применяя <xref:System.Windows.Media.TranslateTransform> <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента, можно переместить элемент <xref:System.Windows.Controls.StackPanel> в <xref:System.Windows.Controls.DockPanel>пределах или .  
  
 Используйте <xref:System.Windows.Media.TranslateTransform.X%2A> свойство, <xref:System.Windows.Media.TranslateTransform> чтобы указать количество, в пикселях, чтобы переместить элемент вдоль оси x. Используйте <xref:System.Windows.Media.TranslateTransform.Y%2A> свойство, чтобы указать количество в пикселях, чтобы переместить элемент вдоль y-оси. Наконец, <xref:System.Windows.Media.TranslateTransform> примените свойство <xref:System.Windows.UIElement.RenderTransform%2A> элемента.  
  
 В следующем примере используется для перемещения элемента <xref:System.Windows.Media.TranslateTransform> 50 пикселей вправо и 50 пикселей вниз.  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о классах Transform](transforms-overview.md)
