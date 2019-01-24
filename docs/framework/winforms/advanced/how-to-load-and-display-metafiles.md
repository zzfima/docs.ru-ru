---
title: Как выполнить Загрузка и отображение метафайлов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: d0835d7f2c5ffea44f22661a765ab16b1d0130c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619562"
---
# <a name="how-to-load-and-display-metafiles"></a>Как выполнить Загрузка и отображение метафайлов
<xref:System.Drawing.Imaging.Metafile> Класс, унаследованный от <xref:System.Drawing.Image> класса, предоставляет методы для записи, отображения и анализа векторных изображений.  
  
## <a name="example"></a>Пример  
 Чтобы отобразить векторного изображения (метафайла) на экране, вам потребуется <xref:System.Drawing.Imaging.Metafile> объекта и <xref:System.Drawing.Graphics> объекта. Передать имя файла (или потока) <xref:System.Drawing.Imaging.Metafile> конструктор. После создания <xref:System.Drawing.Imaging.Metafile> , передать, <xref:System.Drawing.Imaging.Metafile> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
 В примере создается <xref:System.Drawing.Imaging.Metafile> объект из файла EMF (расширенный метафайл) и затем рисует изображение с его верхнего левого угла в (60, 10).  
  
 Ниже показан метафайла, содержащейся в указанном расположении.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
