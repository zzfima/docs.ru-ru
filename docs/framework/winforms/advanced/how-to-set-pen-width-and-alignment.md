---
title: Практическое руководство. Задание толщины и выравнивания пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: 8ac125978405f39cd26680338cdabb661ad92d16
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522286"
---
# <a name="how-to-set-pen-width-and-alignment"></a>Практическое руководство. Задание толщины и выравнивания пера
При создании <xref:System.Drawing.Pen>, указать толщину пера в качестве одного из аргументов конструктора. Можно также изменить ширину пера <xref:System.Drawing.Pen.Width%2A> свойство <xref:System.Drawing.Pen> класса.  
  
 Абстрактная линия имеет ширину 0. При рисовании линии толщиной в одну точку точки центрируются по абстрактной линии. Если нарисовать линии более чем одному пикселю пиксели либо центрируются по абстрактной линии или отображаться к одной стороне абстрактной линии. Можно установить свойство выравнивания пера <xref:System.Drawing.Pen> для определяют расположение точек, рисуемых пером, относительно абстрактной линии.  
  
 Значения <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, и <xref:System.Drawing.Drawing2D.PenAlignment.Inset> , отображаемые в следующих примерах кода являются членами <xref:System.Drawing.Drawing2D.PenAlignment> перечисления.  
  
 В следующем примере кода проводит линию дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.  
  
### <a name="to-vary-the-width-of-a-pen"></a>Чтобы изменять ширину пера  
  
-   Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> (по умолчанию) для указания, что будет по центру точек, рисуемых зеленым пером, по абстрактной линии. На следующем рисунке результирующей строки.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")  
  
     В следующем примере рисуется прямоугольник дважды: один раз черным пером толщиной в 1 и один раз с помощью зеленого пера шириной 10.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>Изменение выравнивания пера  
  
-   Установите для параметра <xref:System.Drawing.Pen.Alignment%2A> свойства <xref:System.Drawing.Drawing2D.PenAlignment.Center> , рисуемые зеленым пером пиксели будет по границе прямоугольника.  
  
     На следующем рисунке полученный прямоугольник.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>Для создания вложенного пера  
  
-   Измените выравнивание зеленого пера, изменив третья инструкция в предыдущем примере кода следующим образом:  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     Теперь пикселей в ширину зеленая линия отображаются внутри прямоугольника, как показано на следующем рисунке.  
  
     ![Перья](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")  
  
## <a name="see-also"></a>См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
