---
title: Как выполнить Заливка фигуры текстурой с изображением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: bf1e09548ff9bc4eb650048eb21a9c300f3f6405
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601783"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Как выполнить Заливка фигуры текстурой с изображением
Можно заполнить замкнутой фигуры текстурой, созданной с помощью <xref:System.Drawing.Image> класс и <xref:System.Drawing.TextureBrush> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере заполняется эллипс с изображением. Код создает <xref:System.Drawing.Image> объекта, а затем передает адрес объекта <xref:System.Drawing.Image> объект в качестве аргумента для <xref:System.Drawing.TextureBrush.%23ctor%2A> конструктор. Третья инструкция изменяет масштаб изображения, а четвертый оператор выполняет заливку эллипса повторяющиеся копии масштабированное изображение.  
  
 В следующем коде <xref:System.Drawing.TextureBrush.Transform%2A> свойство содержит преобразование, которое применяется к изображению перед его рисованием. Предположим, что исходное изображение имеет 640 пикселей в ширину и высоту 480 пикселей. Преобразование сжимает изображение до 75 × 75, задав значения масштабирования по горизонтали и вертикали.  
  
> [!NOTE]
>  В следующем примере размер изображения равно 75 × 75 и размер эллипса — 150 × 250. Так как изображение меньше заполняемой эллипса, эллипса выполняется мозаичное заполнение с использованием образа. Достигнут мозаичное заполнение означает, что изображение повторяется горизонтально и вертикально до границы фигуры. Дополнительные сведения о мозаичного заполнения, см. в разделе [как: Мозаичное заполнение фигуры заданным изображением](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
