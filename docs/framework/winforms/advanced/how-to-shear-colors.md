---
title: Практическое руководство. Сдвиг цветов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142398"
---
# <a name="how-to-shear-colors"></a>Практическое руководство. Сдвиг цветов
Стрижка увеличивает или уменьшает цветовую составляющую на сумму, пропорциональную другому цветовому компоненту. Например, рассмотрим преобразование, при котором красный компонент увеличивается на половину значения синего компонента. При таком преобразовании цветом (0,2, 0,5, 1) станет (0,7, 0,5, 1). Новый красный компонент составляет 0,2 х (1/2)(1) и 0,7.  
  
## <a name="example"></a>Пример  
 Следующий пример строит <xref:System.Drawing.Image> объект из файла ColorBars4.bmp. Затем код применяет преобразование сдвига, описанное в предыдущем абзаце, к каждому пикселю на изображении.  
  
 На следующем рисунке показано исходное изображение слева и сдещевое изображение справа:
  
 ![Два квадрата с цветными полосами бок о бок, иллюстрирующие исходное изображение и сложистые изображения.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 В следующей таблице перечислены цветовые векторы для четырех баров до и после преобразования стрижки.  
  
|Исходное значение|Стриженой|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для использования с формами Windows, и он требует, <xref:System.Windows.Forms.PaintEventArgs> `e`который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий. Замените `ColorBars.bmp` имя изображения и путь, действительный в вашей системе.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Перекрашивание изображений](recoloring-images.md)
