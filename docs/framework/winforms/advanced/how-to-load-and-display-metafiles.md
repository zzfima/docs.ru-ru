---
title: Практическое руководство. Загрузка и отображение метафайлов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424818"
---
# <a name="how-to-load-and-display-metafiles"></a>Практическое руководство. Загрузка и отображение метафайлов
Класс <xref:System.Drawing.Imaging.Metafile>, который наследует от класса <xref:System.Drawing.Image>, предоставляет методы для записи, отображения и проверки векторных изображений.  
  
## <a name="example"></a>Пример  
 Для отображения векторного изображения (метафайла) на экране необходим объект <xref:System.Drawing.Imaging.Metafile> и объект <xref:System.Drawing.Graphics>. Передайте имя файла (или потока) в конструктор <xref:System.Drawing.Imaging.Metafile>. После создания объекта <xref:System.Drawing.Imaging.Metafile> передайте этот <xref:System.Drawing.Imaging.Metafile> объект в метод <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.  
  
 В примере создается объект <xref:System.Drawing.Imaging.Metafile> из файла EMF (расширенный метафайл), а затем изображение рисуется с помощью левого верхнего угла в точке (60, 10).  
  
 На следующем рисунке показан метафайл, рисуемый в указанном месте.  
  
 ![Снимок экрана, показывающий расположение изображения.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром обработчика событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также

- [Работа с растровыми и векторными изображениями, значками и метафайлами](working-with-images-bitmaps-icons-and-metafiles.md)
