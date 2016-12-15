---
title: "Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape (Visual Studio) | Microsoft Docs"
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
  - "OvalShape - элемент управления"
  - "RectangleShape - элемент управления"
  - "фигуры, рисование"
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Рисование фигур при помощи элементов управления OvalShape и RectangleShape (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> для рисования окружностей и овалов на формах и контейнерах и во время создания, и во время выполнения.  Можно использовать элемент управления <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> для рисования квадратов, прямоугольников и прямоугольников со скругленными углами на формах и контейнерах.  С помощью этого элемента управления также можно рисовать фигуры и во время создания, и во время выполнения.  
  
 Можно настраивать внешний вид фигур, изменяя их толщину, цвет и стиль рамки.  По умолчанию у фигур прозрачный фон. Можно настроить фон, отображая сплошной цвет, узор, градиентную заливку \(плавный переход от одного цвета к другому\) или рисунок.  
  
### Рисование простых фигур во время создания  
  
1.  Перетащите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> или <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> с вкладки **Visual Basic PowerPacks** \(сведения по установке см. в разделе [Элементы управления Visual Basic Power Packs](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)\) на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры размера и перемещения, чтобы придать фигуре нужный размер и положение.  
  
     Также можно изменять размер и положение фигур, изменяя свойства `Size` и `Position` в окне **Свойства**.  
  
     Чтобы создать прямоугольник со скругленными углами, выберите свойство `CornerRadius` в окне **Свойства** и задайте для него значение больше 0.  
  
3.  В окне **Свойства** можно задать дополнительные свойства, чтобы изменить внешний вид фигуры.  
  
### Рисование простых фигур во время выполнения  
  
1.  В меню **Проект** щелкните команду **Добавить ссылку**.  
  
2.  В диалоговом окне **Добавление ссылки** выберите **Microsoft.VisualBasic.PowerPacks.VS**, затем нажмите кнопку **ОК**.  
  
3.  В окне **Редактор кода** добавьте оператор `Imports` или `using` в верхней части модуля:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
4.  Добавьте следующий код в процедуру `Event`:  
  
     [!code-cs[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## Настройка фигур  
 При использовании параметров по умолчанию элементы управления <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> и <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> отображаются со сплошной черной рамкой шириной в один пиксель и с прозрачным фоном.  С помощью свойств можно изменить ширину, стиль и цвет рамки.  Дополнительные свойства позволяют изменить фон фигуры на заливку сплошным цветом, узор, градиентную заливку или рисунок.  
  
 Перед изменением фона фигур обратите внимание, как взаимодействуют друг с другом некоторые свойства.  
  
-   Значение свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> не будет учитываться, если не задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle>.  
  
-   Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle>, то <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> переопределяет <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.  
  
-   Если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> задано значение узора, такое как <xref:Microsoft.VisualBasic.PowerPacks.FillStyle> или <xref:Microsoft.VisualBasic.PowerPacks.FillStyle>, узор будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.  Фон будет показан в <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, если для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> задано значение <xref:Microsoft.VisualBasic.PowerPacks.BackStyle>.  
  
-   Для отображения градиентной заливки нужно установить для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> значение <xref:Microsoft.VisualBasic.PowerPacks.FillStyle>, а для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> — значение, отличное от <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle>.  
  
-   Если задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> рисунок, все прочие параметры фона переопределяются.  
  
#### Рисование окружности с настраиваемой рамкой  
  
1.  Перетащите элемент управления `OvalShape` с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  В окне **Свойства** для свойства `Size` установите одинаковые значения для `Height` и `Width`.  
  
3.  Задайте для свойства `BorderColor` нужный цвет.  
  
4.  Задайте для свойства `BorderStyle` любое значение, отличное от `Solid`.  
  
5.  Задайте для свойства `BorderWidth` нужный размер в пикселях.  
  
#### Рисование окружности с заливкой сплошным цветом  
  
1.  Перетащите элемент управления `OvalShape` с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  В окне **Свойства** для свойства `Size` установите одинаковые значения для `Height` и `Width`.  
  
3.  Задайте для свойства `BackColor` нужный цвет.  
  
4.  Задайте для свойства `BackStyle` значение `Opaque`.  
  
#### Рисование окружности с заливкой узором  
  
1.  Перетащите элемент управления `OvalShape` с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  В окне **Свойства** для свойства `Size` установите одинаковые значения для `Height` и `Width`.  
  
3.  Задайте для свойства `BackColor` нужный цвет фона.  
  
4.  Задайте для свойства `BackStyle` значение `Opaque`.  
  
5.  Задайте для свойства `FillColor` нужный цвет фонового узора.  
  
6.  Задайте для свойства `FillStyle` любое значение, отличное от `Transparent` или `Solid`.  
  
#### Рисование окружности с градиентной заливкой  
  
1.  Перетащите элемент управления `OvalShape` с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  В окне **Свойства** для свойства `Size` установите одинаковые значения для `Height` и `Width`.  
  
3.  Задайте для свойства `FillColor` нужный начальный цвет.  
  
4.  Задайте для свойства `FillGradientColor` нужный конечный цвет.  
  
5.  Задайте для свойства `FillGradientStyle` значение, отличное от `None`.  
  
#### Рисование окружности, заполненной рисунком  
  
1.  Перетащите элемент управления `OvalShape` с вкладки **Visual Basic PowerPacks** на **панели инструментов** в форму или контейнерный элемент управления.  
  
2.  В окне **Свойства** для свойства `Size` установите одинаковые значения для `Height` и `Width`.  
  
3.  Выберите свойство `BackgroundImage` и щелкните кнопку с **многоточием** \(...\).  
  
4.  В диалоговом окне **Выберите ресурс** выберите рисунок для отображения.  Если в списке нет ресурсов с рисунками, нажмите кнопку **Импорт**, чтобы открыть расположение рисунка.  
  
5.  Нажмите кнопку **ОК** для вставки изображения.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>   
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>   
 [Знакомство с элементами управления Line и Shape](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)   
 [Пошаговое руководство. Изображение линий при помощи элемента управления LineShape](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)