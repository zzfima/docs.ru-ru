---
title: Координаты Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: ba6bf8c1a8ae5ab14a9b33ae431e34310046b2a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-coordinates"></a>Координаты Windows Forms
Система координат для формы Windows Forms основана на координатах устройства, и основной единицей измерения при рисовании в формах Windows Forms является единица устройства (обычно точки). Точки на экране описываются парами координат x и y Координата x увеличивается вправо, а координата y увеличивается сверху вниз. Расположение источника, относительно экрана, будет зависеть от указываются ли экранные или клиентские координаты.  
  
## <a name="screen-coordinates"></a>Экранные координаты  
 Приложение Windows Forms указывает положение окна на экране в экранных координатах. Для экранные координаты находятся верхнего левого угла экрана. Полное положение окна часто описывается <xref:System.Drawing.Rectangle> структуры, содержащей экранные координаты двух точек, которые определяют верхний левый и правый нижний угол окна.  
  
## <a name="client-coordinates"></a>Клиентские координаты  
 Приложение Windows Forms указывает положение точек в формы или элемента управления с помощью клиентских координат. Источником для клиентских координат является верхнего левого угла клиентской области элемента управления или формы. Координаты клиента убедитесь, что приложение может использовать согласованные значения координат во время рисования в формы или элемента управления, независимо от положения формы или элемента управления на экране.  
  
 Размеры клиентской области также описываются <xref:System.Drawing.Rectangle> структуру, содержащую клиентские координаты области. Во всех случаях координаты левого верхнего прямоугольника включается в клиентской области при исключении правая нижняя координата. Графические операции не включают правой и нижней границ клиентской области. Например <xref:System.Drawing.Graphics.FillRectangle%2A> метод будет заполнить правой и нижней границ заданного прямоугольника, но не будет включать эти границы.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Сопоставление одного типа координат  
 В некоторых случаях может потребоваться сопоставить из экранных координат в клиентские координаты. Это можно легко сделать с помощью <xref:System.Windows.Forms.Control.PointToClient%2A> и <xref:System.Windows.Forms.Control.PointToScreen%2A> методов, доступных в <xref:System.Windows.Forms.Control> класса. Например <xref:System.Windows.Forms.Control.MousePosition%2A> свойство <xref:System.Windows.Forms.Control> сообщается в экранных координатах, но может потребоваться преобразовать их в клиентских координатах.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
