---
title: Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: e1c46f805b7ba2e2f2a1eb52042cc2ca08e63e03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523046"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Автоматическое масштабирование образа при рисовании, снижает производительность. Кроме того, можно управлять масштабирования изображения, передав размеры прямоугольника назначения <xref:System.Drawing.Graphics.DrawImage%2A> метод.  
  
 Например, в следующем вызове <xref:System.Drawing.Graphics.DrawImage%2A> метод задает верхний левый угол (50, 30), но не указывает прямоугольника назначения.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Хотя это простейший вариант <xref:System.Drawing.Graphics.DrawImage%2A> метод с точки зрения число обязательных аргументов, не обязательно будет наиболее эффективным. Если используется разрешение [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (обычно 96 точек на дюйм) отличается от разрешения, указанного в <xref:System.Drawing.Image> объекта, а затем <xref:System.Drawing.Graphics.DrawImage%2A> метод будет масштабирования изображения. Например, предположим, что <xref:System.Drawing.Image> объект имеет ширину 216 точек, а хранимые разрешение по горизонтали составляет 72 точек на дюйм. Поскольку 216/72 равно 3, <xref:System.Drawing.Graphics.DrawImage%2A> будет масштабирования изображения, чтобы его ширину 3 дюйма с разрешением 96 точек на дюйм. То есть <xref:System.Drawing.Graphics.DrawImage%2A> выводит изображение шириной 96 x 3 = 288 пикселей.  
  
 Даже если разрешение экрана 96 точек на дюйм, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] будут, скорее всего, масштабирования изображения так, будто разрешение экрана 96 точек на дюйм. Причина этого заключается в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> объект связан с контекста устройства и когда [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] контекст устройства для разрешения экрана, результат обычно является 96, независимо от фактического экранного разрешения запросов. Можно избежать автоматического масштабирования, указав в прямоугольник назначения в <xref:System.Drawing.Graphics.DrawImage%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется дважды для одного изображения. В первом случае ширину и высоту прямоугольника назначения не указан, а изображение масштабируется автоматически. Во втором случае ширину и высоту прямоугольника назначения (измеряется в пикселях) для указания совпадать с ширину и высоту исходного изображения. На следующем рисунке изображение, рисуемое дважды.  
  
 ![Масштабировать текстуры](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Замените Texture.jpg в вашей системе путь и имя образа.  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
