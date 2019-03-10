---
title: Практическое руководство. Рисование существующего растрового изображения на экране
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: a23026e0ac377294e3e4356d341c45d31b4ecd79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724444"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Практическое руководство. Рисование существующего растрового изображения на экране
Существующий образ рисования на экране. Сначала необходимо создать <xref:System.Drawing.Bitmap> , используя конструктор точечного рисунка, который принимает имя файла, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Этот конструктор поддерживает изображения с нескольких форматов, включая BMP, GIF, JPEG, PNG и TIFF. После создания <xref:System.Drawing.Bitmap> , передать, <xref:System.Drawing.Bitmap> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="example"></a>Пример  
 В этом примере создается <xref:System.Drawing.Bitmap> объект из файла в формате JPEG и затем рисует растровое изображение с его верхнего левого угла в (60, 10).  
  
 Ниже показан точечный рисунок рисуется в указанном расположении.  
  
 ![Положение изображения](./media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](working-with-images-bitmaps-icons-and-metafiles.md)
