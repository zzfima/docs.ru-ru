---
title: "Знакомство с элементами управления Line и Shape (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line - элемент управления, общие сведения"
  - "линии, рисование"
  - "Shape - элемент управления, общие сведения"
  - "фигуры, рисование"
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Знакомство с элементами управления Line и Shape (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Элементы управления Line и Shape пакетов Visual Basic Power Packs представляют собой набор из трех графических элементов управления, позволяющих по время разработки рисовать линии, овалы и прямоугольники в формах и контейнерах.  Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.LineShape> используется для рисования горизонтальных, вертикальных и диагональных линий.  Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> используется для рисования кругов и овалов, а элемент управления <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> используется для изображения прямоугольников и квадратов.  
  
## Элементы управления Line и Shape  
 Элементы управления Line и Shape инкапсулируют множество графических методов, содержащихся в пространстве имен <xref:System.Drawing>.  Это позволяет рисовать линии и фигуры одним действием без необходимости создавать графические объекты, перья и кисти.  Можно реализовывать сложные графические методы, такие как градиентные заливки, просто задав несколько свойств.  
  
 Хотя также возможно рисовать линии и фигуры при помощи графических методов, есть несколько преимуществ использования элементов управления Line и Shape:  
  
-   Графические методы можно вызвать только во время выполнения.  Элементы управления Line и Shape можно добавить в форму во время разработки.  Это позволяет оценить внешний вид и расположение точнее, чем при добавлении во время выполнения.  
  
-   Элементы управления Line и Shape доступны вовремя выполнения, предоставляя такие события, как <xref:Microsoft.VisualBasic.PowerPacks.Shape.Click> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>.  Выводы графических методов не выбираются и предоставляют события.  
  
-   Элементы управления Line и Shape предоставляют методы <xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A> и <xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A>, позволяющие контролировать их z\-порядок во время разработки и выполнения.  z\-порядок графических методов можно контролировать только изменяя порядок их выполнения во время выполнения.  
  
-   Элементы управления Line и Shape являются элементами управления без окна; у них нет обработчиков окон и, следовательно, они не могут использовать системные ресурсы.  
  
### Объектная модель  
 Элементы управления Line и Shape наследуют от базового класса <xref:Microsoft.VisualBasic.PowerPacks.Shape>, который определяет их общие свойства, методы и события.  
  
 Следующая картинка иллюстрирует наследование иерархию объектов Line и Shape.  
  
 ![Схема иерархий объектов Line и Shape](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Иерархия объектов Line и Shape  
  
 Наследуемый класс <xref:Microsoft.VisualBasic.PowerPacks.LineShape> содержит свойства, методы и события, которые являются уникальными для линий.  Наследуемый класс <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape> является базовым для <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; он содержит свойства, методы и события, общие для всех форм.  Также можно наследовать от <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>, чтобы создать свои собственные элементы управления `Shape`.  
  
 Классы <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> можно использовать для рисования кругов, овалов, прямоугольников и квадратов с закругленными углами.  
  
 При добавлении элемента управления Line или Shape в форму или контейнер, создается невидимый объект <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>.  Он <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> действует как поверхность конструирования для фигур в каждом контейнерном элементе управления; каждый объект <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> имеет соответствующий объект <xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection>, позволяющий выполнять итерацию элементов управления "Линия" и "Фигура".  Можно переместить фигуры из одного контейнера в другой при помощи вырезания и вставки или при помощи перетаскивания.  После удалении последней формы из контейнера контейнер <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer> тоже удаляется.  
  
> [!NOTE]
>  Не все элементы управления контейнера поддерживают элементы управления Line и Shape.  Нельзя разместить элементы управления Line или Shape в панели <xref:System.Windows.Forms.TableLayoutPanel> или в панели <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks>   
 [Пошаговое руководство. Изображение линий при помощи элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [Пошаговое руководство. Разрешение переходов между фигурами](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)