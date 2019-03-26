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
ms.openlocfilehash: 73f4f19229a31266b406214e93e2b59acd343ca2
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463895"
---
# <a name="how-to-use-a-color-remap-table"></a>Практическое руководство. Использование таблицы преобразования цветов
Преобразование — это процесс преобразования цветов в изображении в соответствии с таблицей сопоставления цветов. Таблицы преобразования цветов представляет собой массив <xref:System.Drawing.Imaging.ColorMap> объектов. Каждый <xref:System.Drawing.Imaging.ColorMap> объект в массиве имеет <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> свойство и <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойство.  
  
 Когда [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] рисовании изображения каждого пикселя изображения с помощью сравнивается с массив старых цветов. Если цвет пикселя совпадает со старым цветом, его цвет изменяется на соответствующий новый цвет. Цвета изменяются только для подготовки к просмотру — значения цвета самого изображения (хранящиеся в <xref:System.Drawing.Image> или <xref:System.Drawing.Bitmap> объекта), не изменяются.  
  
 Чтобы нарисовать пересопоставленный изображение, инициализируйте массив <xref:System.Drawing.Imaging.ColorMap> объектов. Передайте массив <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> , а затем передать <xref:System.Drawing.Imaging.ImageAttributes> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла RemapInput.bmp. Код создает таблицу преобразования цветов, состоящий из одного <xref:System.Drawing.Imaging.ColorMap> объекта. <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> Свойство `ColorRemap` объекта отображается красным цветом, а <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> свойство имеет значение blue. Изображение будет рисоваться один раз без изменения сопоставления и один раз с повторное сопоставление. В процессе преобразования все Красные пиксели на синий.  
  
 Ниже показан исходное изображение в левой части и преобразованное изображение справа.  
  
 ![Снимок экрана, показывающий исходного изображения, а преобразованное изображение.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика события <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [перекрашивание изображений](recoloring-images.md)
- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
