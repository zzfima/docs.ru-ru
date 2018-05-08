---
title: Практическое руководство. Использование таблицы преобразования цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: ba763cc7960e71c6fc705d40eefdbde163d06181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-remap-table"></a>Практическое руководство. Использование таблицы преобразования цветов
Преобразование — это процесс преобразования цветов в изображении в соответствии с таблицей сопоставления цветов. Таблицы преобразования цветов представляет собой массив <xref:System.Drawing.Imaging.ColorMap> объектов. Каждый <xref:System.Drawing.Imaging.ColorMap> объект в массиве имеет <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> свойство и <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойства.  
  
 Когда [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] рисовании изображения каждого пикселя изображения с помощью сравнивается с элементами массива старых цветов. Если цвет пикселя совпадает со старым цветом, ее цвет меняется на соответствующий новый цвет. Цвета изменяются только для подготовки к просмотру — значения цвета самого изображения (хранимые в <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> объекта) не изменяются.  
  
 Чтобы нарисовать изображение с измененным сопоставлением, инициализируйте массив <xref:System.Drawing.Imaging.ColorMap> объектов. Передайте массив <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> , а затем передать <xref:System.Drawing.Imaging.ImageAttributes> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла RemapInput.bmp. Код создает таблицу преобразования цветов, состоящий из одного <xref:System.Drawing.Imaging.ColorMap> объекта. <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Свойство `ColorRemap` объекта отображается красным цветом и <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойства — синим. На рисунке показана формируемого один раз без изменения сопоставления и один раз с преобразованием. В процессе преобразования все Красные пиксели на синий.  
  
 Ниже показан исходный образ в левой части экрана и преобразованное изображение справа.  
  
 ![Цветовой ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
