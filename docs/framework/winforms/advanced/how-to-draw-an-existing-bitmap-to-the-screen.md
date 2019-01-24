---
title: Как выполнить Рисование существующего растрового изображения на экране
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: d8c118d9561c0fe993228cb6bd8cebcd156d411d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586726"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Как выполнить Рисование существующего растрового изображения на экране
Существующий образ рисования на экране. Сначала необходимо создать <xref:System.Drawing.Bitmap> , используя конструктор точечного рисунка, который принимает имя файла, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Этот конструктор поддерживает изображения с нескольких форматов, включая BMP, GIF, JPEG, PNG и TIFF. После создания <xref:System.Drawing.Bitmap> , передать, <xref:System.Drawing.Bitmap> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="example"></a>Пример  
 В этом примере создается <xref:System.Drawing.Bitmap> объект из файла в формате JPEG и затем рисует растровое изображение с его верхнего левого угла в (60, 10).  
  
 Ниже показан точечный рисунок рисуется в указанном расположении.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
