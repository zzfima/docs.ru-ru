---
title: "Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях"
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
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dde9417782e4404237a995364d65058f023c3e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Практическое руководство. Использование матрицы цветов для задания значений прозрачности в изображениях
<xref:System.Drawing.Bitmap> Класса (который наследуется от <xref:System.Drawing.Image> класса) и <xref:System.Drawing.Imaging.ImageAttributes> предоставляют функции для получения и задания значений пикселей. Можно использовать <xref:System.Drawing.Imaging.ImageAttributes> класс для изменения альфа-канал значения для всего изображения, или можно вызвать <xref:System.Drawing.Bitmap.SetPixel%2A> метод <xref:System.Drawing.Bitmap> класса для изменения значений отдельных пикселей.  
  
## <a name="example"></a>Пример  
 <xref:System.Drawing.Imaging.ImageAttributes> Класс имеет множество свойств, которые можно использовать для изменения во время подготовки к просмотру изображений. В следующем примере <xref:System.Drawing.Imaging.ImageAttributes> объект используется для равным 80% от их первоначальных альфа-значения. Это делается, инициализация матрицы цветов и установив значение в матрице 0,8 масштабирования альфа-канал. Адрес матрицы цветов передается <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> метод <xref:System.Drawing.Imaging.ImageAttributes> объекта и <xref:System.Drawing.Imaging.ImageAttributes> объект передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
 Во время подготовки к просмотру, альфа-факторы в битовой карте преобразуются в 80 процентов они были. Это приводит к изображение, смешивается с цветом фона. Как показано на следующем рисунке, растровое изображение выглядит прозрачным; Появится сплошная линия черным через него.  
  
 ![Альфа-смешение цвета с помощью матрицы](../../../../docs/framework/winforms/advanced/media/image2.png "изображение2")  
  
 Местах, где изображение покрывает белые участки фона, оно смешивается с белым цветом. Где изображение пересекает черную линию, изображение смешивается с черным цветом.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Альфа-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
