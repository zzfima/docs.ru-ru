---
title: Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: 42c456137f84c6fa657ba5a09727eae052a45376
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911680"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения
Замкнутую фигуру можно заполнить текстурой с помощью <xref:System.Drawing.Image> класса <xref:System.Drawing.TextureBrush> и класса.  
  
## <a name="example"></a>Пример  
 В следующем примере заливка эллипса осуществляется с помощью изображения. Код конструирует <xref:System.Drawing.Image> объект, а затем передает адрес этого <xref:System.Drawing.Image> объекта в <xref:System.Drawing.TextureBrush.%23ctor%2A> качестве аргумента в конструктор. Третья инструкция масштабирует изображение, а четвертый оператор заполняет эллипс повторяющимися копиями масштабированного изображения.  
  
 В следующем коде <xref:System.Drawing.TextureBrush.Transform%2A> свойство содержит преобразование, которое применяется к изображению перед его прорисовкой. Предположим, что исходное изображение имеет ширину 640 пикселей и высоту 480 пикселей. Преобразование сжимает изображение до 75 × 75, устанавливая горизонтальные и вертикальные значения масштабирования.  
  
> [!NOTE]
> В следующем примере размер изображения составляет 75 × 75, а размер эллипса — 150 × 250. Поскольку изображение меньше, чем заливка, эллипс заполняется изображением. Мозаичное заполнение означает, что изображение повторяется горизонтально и вертикально до тех пор, пока не будет достигнута граница фигуры. Дополнительные сведения о мозаичном заполнении [см. в разделе как Мозаичное заполнение фигуры изображением](how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, что <xref:System.Windows.Forms.Control.Paint> является параметром обработчика событий.  
  
## <a name="see-also"></a>См. также

- [Использование кисти для заливки фигур](using-a-brush-to-fill-shapes.md)
