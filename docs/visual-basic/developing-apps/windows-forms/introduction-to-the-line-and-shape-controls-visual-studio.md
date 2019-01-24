---
title: Знакомство с элементами управления Line и Shape (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3623c2363f39150fd4bb202ba61ebd51df383ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699926"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Знакомство с элементами управления Line и Shape (Visual Studio)
Элементы управления Visual Basic Power Packs, Line и Shape — это набор из трех графических элементов управления, которые позволяют рисовать линии и фигуры в формах и контейнерах. <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Управления используется для рисования горизонтальные, вертикальные и диагональные линии. <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Управления используется для рисования окружностей и овалов и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> управления используется для рисования прямоугольников и квадратов.  
  
## <a name="line-and-shape-controls"></a>Элементы управления Line и Shape  
 Элементы управления Line и Shape инкапсулируют множество графических методов, которые содержатся в <xref:System.Drawing> пространства имен. Это позволяет рисовать линии и фигуры за один шаг не требуется создавать графические объекты, перья и кисти. Достаточно настроить некоторые параметры могут выполняться сложные графические методы, такие как градиентные заливки.  
  
 Несмотря на то, что это также можно рисовать линии и фигуры с помощью графических методов, существует несколько преимуществ использования элементов управления Line и Shape.  
  
-   Графические методы могут вызываться только во время выполнения. Элементы управления Line и Shape можно добавить в форму во время разработки. Это позволяет увидеть, как они выглядят и точного их; они также могут быть добавлены во время выполнения.  
  
-   Элементы управления Line и Shape, могут быть выделены во время выполнения, предоставляющий события, такие как <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. Выходные данные графические методы не могут быть выбраны и предоставляют события.  
  
-   Элементы управления Line и Shape предоставляют <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> методы, которые позволяют управлять их z порядок во время разработки и во время выполнения. Z порядок графических методов можно управлять только путем изменения их порядка выполнения во время выполнения.  
  
-   Элементы управления Line и Shape, — это элементы управления без окон; у них нет дескрипторов окон и таким образом использовать меньше системных ресурсов.  
  
### <a name="object-model"></a>Объектная модель  
 Элементы управления Line и Shape, являются производными от базового <xref:Microsoft.VisualBasic.PowerPacks.Shape> класс, который определяет свои общие свойства, методы и события.  
  
 Ниже показана иерархия объектов Line и Shape.  
  
 ![Схема иерархии объектов Line и Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Иерархия объектов Line и Shape  
  
 Производные <xref:Microsoft.VisualBasic.PowerPacks.LineShape> класс содержит свойства, методы и события, которые являются уникальными для линий. Производные <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> класс является базовым классом для <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; он содержит свойства, методы и события, общие для всех фигур. Можно также являются производными от <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> для создания собственных `Shape` элементов управления.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> И <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> классы могут использоваться для рисования окружностей, овалы, прямоугольников и прямоугольников со скругленными углами.  
  
 Когда элемент управления линии или фигуры добавляется в форму или контейнер, создается невидимый <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> создается объект. <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> Выступает в качестве холста для фигур в каждый контейнерный элемент управления, каждый из которых <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> имеет соответствующий <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> , позволяющий выполнять итерацию всех элементов управления Line и Shape. Фигуры можно перемещать из одного контейнера в другой с помощью вырезания и вставки или перетаскивания. При удалении последней фигуры из контейнера, <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> тоже будет удалена.  
  
> [!NOTE]
>  Не все элементы управления контейнера поддерживают элементы управления Line и Shape. Нельзя разместить элемент управления линии или фигуры на <xref:System.Windows.Forms.TableLayoutPanel> или <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks>
- [Практическое руководство. Рисование линий с помощью элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [Практическое руководство. Рисование фигур при помощи OvalShape и RectangleShape элементов управления](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [Практическое руководство. Разрешение переходов между фигурами](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
