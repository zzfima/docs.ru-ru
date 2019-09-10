---
title: Практическое руководство. Управление заливкой составных фигур
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 89f69d392e8838af99538c759a2f06453e1bcd60
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855908"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Практическое руководство. Управление заливкой составных фигур

<xref:System.Windows.Media.GeometryGroup.FillRule%2A> Свойство объектаили<xref:System.Windows.Media.PathGeometry>указывает"правило", которое используется составной фигурой для определения того, является ли данная точка частью геометрии. <xref:System.Windows.Media.GeometryGroup> Существует два возможных значения для <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> и <xref:System.Windows.Media.FillRule.Nonzero>. Следующие разделы описывают использование этих двух правил.

**EvenOdd** Это правило определяет, находится ли точка в области заливки, путем рисования луча от этой точки до бесконечности в любом направлении и подсчета количества сегментов контура в данной фигуре, пересекающих луч. Если это число нечетное, точка находится внутри; если четное — точка находится снаружи.

Например, приведенный ниже XAML создает составную фигуру, состоящие из серии концентрических колец (Target) с <xref:System.Windows.Media.GeometryGroup.FillRule%2A> параметром <xref:System.Windows.Media.FillRule.EvenOdd>, имеющим значение.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]

На следующем рисунке показана фигура, созданная в предыдущем примере.

![Круг, состоящие из ряда концентрических колец с чередованием цветов.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)

На предыдущем рисунке обратите внимание, что центр и третье кольцо не заполнены. Это потому, что луч, нарисованный из любой точки в одном из этих двух колец проходит через четное число сегментов. См. следующую иллюстрацию:

![Схема, на которой показаны лучи EvenOdd, рисуемые в окружности.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)

**Отличные** Это правило определяет, находится ли точка в области заливки пути, рисуя луч с этой точки до бесконечности в любом направлении, а затем изучая места, где сегмент фигуры пересекает луч. Начиная с нуля, добавляется единица каждый раз, когда сегмент пересекает луч слева направо, и вычитается единица каждый раз, когда сегмент пересекает луч справа налево. Если после подсчета пересечений результат равен нулю, то точка находится снаружи пути. В противном случае — она находится внутри.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]

Используя предыдущий пример, значение <xref:System.Windows.Media.FillRule.Nonzero> для <xref:System.Windows.Media.GeometryGroup.FillRule%2A> дает следующую иллюстрацию в результате:

![Окружность, состоящие из ряда концентрических колец, заполненных одним и тем же цветом.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)

Как можно видеть, все кольца заполнены. Это связано с тем, что все сегменты идут в одном направлении и поэтому луч, рисуемый из любой точки, будет пересекать один или несколько сегментов и сумма пересечений не будет равна нулю. Например, на следующем рисунке красные стрелки обозначают направление прорисовки сегментов, а белая стрелка — произвольный луч, выполняемый с точки во внутреннем кольце. Начиная с нуля, для каждого сегмента, который пересекает луч, значение 1 добавляется, так как сегмент пересекает луч слева направо.

![Схема, показывающая значение свойства FillRule, равное нулю.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)

Чтобы лучше продемонстрировать поведение <xref:System.Windows.Media.FillRule.Nonzero> правила, требуется более сложная форма с сегментами, работающими в разных направлениях. Приведенный ниже код XAML создает аналогичную форму, как в предыдущем примере, за исключением того <xref:System.Windows.Media.PathGeometry> , что он <xref:System.Windows.Media.EllipseGeometry> создается с помощью, а затем создает четыре Концентрические дуги, а затем полностью замыкая концентрические круги.

[!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]

На следующем рисунке показана фигура, созданная в предыдущем примере.

![Круг, состоящие из ряда концентрических колец с чередованием цветов с третьей дугой, не заполнен.](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)

Обратите внимание, что третья дуга от центра не заполнена. На следующем рисунке показано, почему это так. На рисунке красные стрелки обозначают направление, в котором рисуются сегменты. Две белые стрелки показывают два произвольных луча, которые выходят из точки в «незаполненной» области. Как видно из рисунка, сумма значений для луча, пересекающего сегменты в пути, равна нулю. Как указано выше, сумма ноль означает, что точка не является частью геометрии (не является частью заливки), а сумма, которая *не равна* нулю, в том числе отрицательное значение, является частью геометрии.

![Диаграмма, показывающая произвольные лучи, пересекающие сегменты.](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)

> [!NOTE]
> В целях <xref:System.Windows.Media.FillRule>все фигуры считаются закрытыми. Если в сегменте есть разрыв, нарисуйте воображаемую линию, чтобы его закрыть. В приведенном выше примере имеются небольшие разрывы в кольцах. Учитывая это, можно предположить, что луч, проходящий через разрыв, даст другой результат, чем луч, проходящий в другом направлении. Ниже приведена увеличенная Иллюстрация одного из этих пропусков и «воображаемый сегмент» (сегмент, рисуемый для применения <xref:System.Windows.Media.FillRule>), который закрывает его.

![Диаграмма, показывающая FillRule сегменты, которые всегда закрыты.](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)

## <a name="example"></a>Пример

## <a name="see-also"></a>См. также

- [Создание составной фигуры](how-to-create-a-composite-shape.md)
- [Общие сведения о классе Geometry](geometry-overview.md)
