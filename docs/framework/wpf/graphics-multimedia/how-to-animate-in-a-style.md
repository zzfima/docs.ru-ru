---
title: Как анимировать в стиле (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
ms.openlocfilehash: 617d41ca1c97463bf1c61c0d1e2728756fd8f1fb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459241"
---
# <a name="how-to-animate-in-a-style"></a>Как анимировать в стиле

В этом примере показано, как анимировать свойства в стиле. При анимации в стиле только элемент Framework, для которого определен стиль, может быть нацелен напрямую. Чтобы ориентироваться на объект Freezable, необходимо «переключить» свойство элемента styleed.

В следующем примере несколько анимаций определяются в стиле и применяются к <xref:System.Windows.Controls.Button>. Когда пользователь наводит указатель мыши на кнопку, он плавно переключается от непрозрачного на частично прозрачный и обратно. Когда пользователь наводит кнопку мыши за пределы кнопки, он становится полностью непрозрачным. При нажатии кнопки ее цвет фона меняется с оранжевого на белый и обратно. Так как <xref:System.Windows.Media.SolidColorBrush>, используемые для рисования кнопки, не могут быть направлены напрямую, доступ к ней осуществляется путем нужной из свойства <xref:System.Windows.Controls.Control.Background%2A> кнопки.

## <a name="example"></a>Пример

[!code-xaml[timingbehaviors_snip#21](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]

Обратите внимание, что при анимации в стиле можно ориентироваться на несуществующие объекты. Например, предположим, что в стиле используется <xref:System.Windows.Media.SolidColorBrush> для задания свойства фона кнопки, но в какой-то момент стиль переопределяется, а для фона кнопки устанавливается <xref:System.Windows.Media.LinearGradientBrush>.  При попытке анимировать <xref:System.Windows.Media.SolidColorBrush> не создается исключение. анимация просто не будет работать автоматически.

Дополнительные сведения о синтаксисе нацеливания раскадровки см. в разделе [Общие сведения о раскадровках](storyboards-overview.md). Дополнительные сведения о анимации см. в разделе [Общие сведения об анимации](animation-overview.md). Дополнительные сведения о стилях см. в разделе Стили [и шаблоны](../../../desktop-wpf/fundamentals/styles-templates-overview.md).
