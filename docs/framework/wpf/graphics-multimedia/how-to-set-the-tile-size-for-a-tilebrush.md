---
title: Как установить размер мозаики для TileBrush
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186838"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Как установить размер мозаики для TileBrush

В этом примере показано, как <xref:System.Windows.Media.TileBrush>установить размер плитки для . По умолчанию, <xref:System.Windows.Media.TileBrush> производит одну плитку, которая полностью заполняет область, которую вы рисуете. Это поведение можно переопределить, <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> установив и свойства.

Свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> определяет размер плитки для <xref:System.Windows.Media.TileBrush>. По умолчанию значение <xref:System.Windows.Media.TileBrush.Viewport%2A> свойства относительно размера окрашенной площади. Чтобы сделать свойство <xref:System.Windows.Media.TileBrush.Viewport%2A> указать абсолютный размер плитки, установите свойство <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> на <xref:System.Windows.Media.BrushMappingMode.Absolute>.

## <a name="example"></a>Пример

Следующий пример <xref:System.Windows.Media.ImageBrush>использует, тип <xref:System.Windows.Media.TileBrush>, для рисования прямоугольника с плиткой. Пример устанавливает каждую плитку до 50 процентов на 50 процентов от выходной области (прямоугольник). В результате прямоугольник заполняется четырьмя проекциями изображения.

На следующей иллюстрации показан выход, который приводит пример:

![Прямоугольник с четырьмя вишнями, демонстрирующими плитку с изображением кисти.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

Следующий пример <xref:System.Windows.Media.ImageBrush>создает, <xref:System.Windows.Media.TileBrush.Viewport%2A> устанавливает `0,0,25,25` его <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>к и его к, и использует его для того чтобы покрасить другой прямоугольник. В результате кисть создает мозаику размером 25 пикселей в ширину и 25 пикселей в высоту.

На следующей иллюстрации показан выход, который приводит пример:

![Прямоугольник с сорока восемью вишнями, демонстрирующими черепицу TileBrush с Viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Следующий пример является частью большого примера. Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)

Хотя этот пример <xref:System.Windows.Media.ImageBrush> использует <xref:System.Windows.Media.TileBrush.Viewport%2A> класс, <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> и свойства ведут <xref:System.Windows.Media.TileBrush> себя одинаково для <xref:System.Windows.Media.DrawingBrush> других <xref:System.Windows.Media.VisualBrush>объектов, то есть для и . Для получения <xref:System.Windows.Media.ImageBrush> дополнительной информации о и других <xref:System.Windows.Media.TileBrush> объектов, см Картина с [изображениями, рисунки, и визуальные эффекты](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.TileBrush>
- [Заполнение с использованием изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md)
- [Создание различных шаблонов мозаики с помощью TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
