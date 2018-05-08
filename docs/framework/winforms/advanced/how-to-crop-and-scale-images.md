---
title: Практическое руководство. Обрезка и масштабирование изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: d5acda50a1aa0f0cae6e77a748b011908fcc8c34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-crop-and-scale-images"></a>Практическое руководство. Обрезка и масштабирование изображений
<xref:System.Drawing.Graphics> Класс предоставляет несколько <xref:System.Drawing.Graphics.DrawImage%2A> методы, некоторые из которых имеют параметры прямоугольника источника и назначения, которые можно использовать для обрезки и масштабирования изображений.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта на основе файла Apple.gif. Код рисует изображение яблока, полностью исходный размер. Затем код вызывает <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта для рисования фрагмента изображения яблока в прямоугольнике назначения, большего, чем исходное изображение apple.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, какая часть apple для рисования, анализируя исходный прямоугольник, задаваемый третьим, четвертым, пятая и шестая параметрами. В этом случае apple обрезается 75% от ширины и 75% высоты.  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> Метод определяет, где рисовать обрезанное изображение яблока и как вносить обрезанное изображение яблока, анализируя прямоугольник назначения, который указан с помощью второго аргумента. В этом случае прямоугольника назначения — 30% шире и 30% выше, чем исходное изображение.  
  
 Ниже показан исходный apple и масштабированное обрезанное изображение.  
  
 ![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Обязательно замените `Apple.gif` в вашей системе путь и имя файла изображения.  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
