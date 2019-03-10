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
ms.openlocfilehash: b8238a4f0ce482d63ab33833c4bceaaa2814253d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705350"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>Практическое руководство. Повышение производительности за счет отключения автоматического масштабирования
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Автоматическое масштабирование образа при рисовании, снижает производительность. Кроме того, можно управлять масштабирования изображения, передав размеры прямоугольника назначения <xref:System.Drawing.Graphics.DrawImage%2A> метод.  
  
 Например, следующий вызов <xref:System.Drawing.Graphics.DrawImage%2A> метод задает верхний левый угол (50, 30), но не указывает прямоугольник назначения.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 Несмотря на то, что это простейший вариант <xref:System.Drawing.Graphics.DrawImage%2A> метод с точки зрения количества обязательных аргументов, не обязательно наиболее эффективен. Если используется разрешение [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] (обычно 96 точек на дюйм) отличается от разрешения, указанного в <xref:System.Drawing.Image> объекта, а затем <xref:System.Drawing.Graphics.DrawImage%2A> метод производит масштабирование рисунка. Например, предположим, что <xref:System.Drawing.Image> объект имеет 216 пикселей в ширину и значение хранимых разрешение по горизонтали 72 точек на дюйм. Поскольку 216/72 равно 3, <xref:System.Drawing.Graphics.DrawImage%2A> производит масштабирование рисунка, чтобы он включал линию толщиной 3 дюйма с разрешением 96 точек на дюйм. То есть <xref:System.Drawing.Graphics.DrawImage%2A> выводит изображение шириной 96 x 3 = 288 пикселей.  
  
 Даже если разрешение экрана 96 точек на дюйм, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , вероятно масштабирования изображения так, будто разрешение экрана 96 точек на дюйм. Это потому, что [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> связывается с контекста устройства и когда [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] контекст устройства для разрешения экрана и результат обычно является 96, независимо от фактического экранного разрешения запросов. Можно избежать автоматического масштабирования, указав в прямоугольник назначения в <xref:System.Drawing.Graphics.DrawImage%2A> метод.  
  
## <a name="example"></a>Пример  
 В следующем примере рисуется тот же образ дважды. В первом случае ширина и высота прямоугольника назначения не указаны, а изображение масштабируется автоматически. Во втором случае ширину и высоту (измеряется в пикселях) прямоугольника назначения указываются должны совпадать как ширину и высоту исходного изображения. Ниже показано изображение, рисуемое дважды.  
  
 ![Масштабировать текстуры](./media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Замените Texture.jpg в вашей системе путь и имя образа.  
  
## <a name="see-also"></a>См. также
- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](working-with-images-bitmaps-icons-and-metafiles.md)
