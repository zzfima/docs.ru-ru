---
title: "Практическое руководство. Рисование существующего точечного рисунка на экране"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f435c397832e8f64b2bf911a59aae7578ffd3bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Практическое руководство. Рисование существующего точечного рисунка на экране
Можно легко нарисовать существующее изображение на экране. Сначала необходимо создать <xref:System.Drawing.Bitmap> объекта, используя конструктор точечного рисунка, который принимает имя файла, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Этот конструктор поддерживает изображения нескольких форматов, включая BMP, GIF, JPEG, PNG и TIFF. После создания <xref:System.Drawing.Bitmap> объекта, передать этот <xref:System.Drawing.Bitmap> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
## <a name="example"></a>Пример  
 В этом примере создается <xref:System.Drawing.Bitmap> объекта из файла в формате JPEG и рисуется растровое изображение, с его верхнего левого угла в (60, 10).  
  
 На следующем рисунке точечный рисунок рисуется в указанном месте.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
