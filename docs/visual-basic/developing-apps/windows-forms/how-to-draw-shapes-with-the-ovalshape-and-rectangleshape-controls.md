---
title: Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: f87865ba3aebe5739b87d6ae6bfeaa957af726d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape (Visual Studio)
Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> для рисования окружностей и овалов на формах и контейнерах и во время создания, и во время выполнения. Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> для рисования квадратов, прямоугольников и прямоугольников со скругленными углами на формах и контейнерах. С помощью этого элемента управления также можно рисовать фигуры и во время создания, и во время выполнения.  
  
 Можно настраивать внешний вид фигур, изменяя их толщину, цвет и стиль рамки. По умолчанию у фигур прозрачный фон. Можно настроить фон, отображая сплошной цвет, узор, градиентную заливку (плавный переход от одного цвета к другому) или рисунок.  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>Рисование простых фигур во время создания  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> или <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> управления из **Visual Basic PowerPacks** вкладка (для установки см [элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) в **элементов** форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры размера и перемещения, чтобы придать фигуре нужный размер и положение.  
  
     Можно также изменить размер и расположение фигуры, изменив `Size` и `Position` свойства в **свойства** окна.  
  
     Чтобы создать прямоугольник со скругленными углами, выберите `CornerRadius` свойство в **свойства** окна и задать для него значение, большее 0.  
  
3.  В **свойства** окна, можно задать дополнительные свойства для изменения внешнего вида фигуры.  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>Рисование простых фигур во время выполнения  
  
1.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
2.  В **добавить ссылку** выберите **Microsoft.VisualBasic.PowerPacks.VS**, а затем нажмите кнопку **ОК**.  
  
3.  В **редактор кода**, добавьте `Imports` или `using` инструкции в верхней части модуля:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  Добавьте следующий код в процедуру `Event`:  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>Настройка фигур  
 При использовании параметров по умолчанию элементы управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> отображаются со сплошной черной рамкой шириной в один пиксель и с прозрачным фоном. С помощью свойств можно изменить ширину, стиль и цвет рамки. Дополнительные свойства позволяют изменить фон фигуры на заливку сплошным цветом, узор, градиентную заливку или рисунок.  
  
 Перед изменением фона фигур обратите внимание, как взаимодействуют друг с другом некоторые свойства.  
  
-   Значение свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> не будет учитываться, если не задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, то <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> переопределяет <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.  
  
-   Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение узора, такое как <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> или <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, узор будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>. Фон будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.  
  
-   Для отображения градиентной заливки нужно установить для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, а для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> — значение, отличное от <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.  
  
-   Если задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> рисунок, все прочие параметры фона переопределяются.  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>Рисование окружности с настраиваемой рамкой  
  
1.  Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  В **свойства** окна в `Size` , установите `Height` и `Width` одинаковые значения для.  
  
3.  Задайте для свойства `BorderColor` нужный цвет.  
  
4.  Задайте для свойства `BorderStyle` любое значение, отличное от `Solid`.  
  
5.  Задайте для свойства `BorderWidth` нужный размер в пикселях.  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>Рисование окружности с заливкой сплошным цветом  
  
1.  Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  В **свойства** окна в `Size` , установите `Height` и `Width` одинаковые значения для.  
  
3.  Задайте для свойства `BackColor` нужный цвет.  
  
4.  Задайте для свойства `BackStyle` значение `Opaque`.  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>Рисование окружности с заливкой узором  
  
1.  Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  В **свойства** окна в `Size` , установите `Height` и `Width` одинаковые значения для.  
  
3.  Задайте для свойства `BackColor` нужный цвет фона.  
  
4.  Задайте для свойства `BackStyle` значение `Opaque`.  
  
5.  Задайте для свойства `FillColor` нужный цвет фонового узора.  
  
6.  Задайте для свойства `FillStyle` любое значение, отличное от `Transparent` или `Solid`.  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>Рисование окружности с градиентной заливкой  
  
1.  Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  В **свойства** окна в `Size` , установите `Height` и `Width` одинаковые значения для.  
  
3.  Задайте для свойства `FillColor` нужный начальный цвет.  
  
4.  Задайте для свойства `FillGradientColor` нужный конечный цвет.  
  
5.  Задайте для свойства `FillGradientStyle` значение, отличное от `None`.  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>Рисование окружности, заполненной рисунком  
  
1.  Перетащите `OvalShape` управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  В **свойства** окна в `Size` , установите `Height` и `Width` одинаковые значения для.  
  
3.  Выберите `BackgroundImage` свойство и нажмите кнопку **многоточие** кнопку (...).  
  
4.  В **выберите ресурс** диалоговое окно, выберите рисунок для отображения. Если в списке нет ресурсов, нажмите кнопку **импорта** для указания местоположения изображения.  
  
5.  Нажмите кнопку **ОК** для вставки изображения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [Пошаговое руководство. Изображение линий при помощи элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
