---
title: "Знакомство с элементами управления Line и Shape (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e691d57c6de640c83556937eeddedf89e79b6846
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Знакомство с элементами управления Line и Shape (Visual Studio)
Элементы управления Visual Basic Power Packs, Line и Shape представляют собой набор из трех графических элементов управления, позволяющие Рисование линий и фигур в формах и контейнерах. <xref:Microsoft.VisualBasic.PowerPacks.LineShape> Элемент управления используется для рисовать горизонтальные, вертикальные и диагональные линии. <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> Управления используется для рисования окружностей и овалов и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> управления используется для рисования, прямоугольники и квадраты.  
  
## <a name="line-and-shape-controls"></a>Элементы управления Line и Shape  
 Элементы управления Line и Shape инкапсулируют множество графических методов, содержащихся в <xref:System.Drawing> пространства имен. Это позволяет без необходимости создавать графические объекты, перья и кисти рисования линий и фигур за один шаг. Можно сделать сложные графики методы, такие как градиентные заливки, просто задав несколько свойств.  
  
 Несмотря на то, что можно также для рисования линий и фигур с помощью методов графики, существует несколько преимуществ использования элементов управления Line и Shape.  
  
-   Графики методы могут вызываться только во время выполнения. Элементы управления Line и Shape можно добавить в форму во время разработки. Это позволяет понять то, что они выглядят и точного их; они также могут добавляться во время выполнения.  
  
-   Элементы управления Line и Shape доступны для выбора во время выполнения, предоставляющий события, такие как <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>. Выводы графических методов не могут быть выделены и не предоставляют события.  
  
-   Элементы управления Line и Shape предоставляют <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A> методы, которые позволяют управлять z порядком во время разработки и во время выполнения. Z порядок графических методов можно управлять только путем изменения порядка выполнения во время выполнения.  
  
-   Элементы управления Line и Shape, поддерживающих элементы управления; у них нет дескрипторами окон и поэтому потреблять меньше системных ресурсов.  
  
### <a name="object-model"></a>Объектная модель  
 Элементы управления Line и Shape, являются производными от базового <xref:Microsoft.VisualBasic.PowerPacks.Shape> класс, который определяет их общие свойства, методы и события.  
  
 На следующем рисунке иерархии объектов Line и Shape.  
  
 ![Схема иерархии объектов Line и Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Иерархия объектов Line и Shape  
  
 Производные <xref:Microsoft.VisualBasic.PowerPacks.LineShape> класс содержит свойства, методы и события, которые являются уникальными для линий. Производные <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> класс является базовым классом для <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; он содержит свойства, методы и события, общие для всех фигур. Можно также создавать производные <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> для создания собственных `Shape` элементов управления.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> И <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> классы можно использовать для рисования окружностей, овалы, прямоугольников и прямоугольников со скругленными углами.  
  
 При добавлении элемента управления Line или Shape формы или контейнер, создается невидимый <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> создан объект. <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> Выступает в качестве холста для фигур в каждый контейнерный элемент управления, каждый из которых <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> имеет соответствующий <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection> , позволяющий выполнять итерацию элементов управления Line и Shape. Фигуры можно перемещать из одного контейнера в другой с помощью вырезания и вставки или перетаскивания. При удалении последней формы из контейнера, <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> тоже будет удалена.  
  
> [!NOTE]
>  Не все элементы управления контейнера поддерживают элементы управления Line и Shape. Невозможно разместить элемент управления линии или фигуры на <xref:System.Windows.Forms.TableLayoutPanel> или <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [Пошаговое руководство. Изображение линий при помощи элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Пошаговое руководство. Разрешение переходов между фигурами](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
