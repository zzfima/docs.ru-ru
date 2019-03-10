---
title: Практическое руководство. Рисование линии с текстурным заполнением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: fd7a2aa2f6d930b0de29d8b8cbd3feacdb7a81e3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718601"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Практическое руководство. Рисование линии с текстурным заполнением
Вместо рисования линии сплошным цветом, можно рисовать линии с текстурным заполнением. Для рисования линий и кривых с текстурой, создание <xref:System.Drawing.TextureBrush> и передать, <xref:System.Drawing.TextureBrush> объект <xref:System.Drawing.Pen.%23ctor%2A> конструктор. Растровое изображение, связанное с кистью текстуры используется для мозаичного плоскостью (незаметно), и когда перо рисует линий или кривых, пиксели мозаичную текстуру пера, становятся видимыми.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Bitmap> объекта из файла `Texture1.jpg`. Это растровое изображение используется для создания <xref:System.Drawing.TextureBrush> объекта и <xref:System.Drawing.TextureBrush> объект используется для создания <xref:System.Drawing.Pen> объекта. Вызов <xref:System.Drawing.Graphics.DrawImage%2A> рисует растровое изображение с его верхнего левого угла в (0, 0). Вызов <xref:System.Drawing.Graphics.DrawEllipse%2A> использует <xref:System.Drawing.Pen> для рисования текстурированного эллипса.  
  
 Ниже показан растрового изображения и текстуры эллипса.  
  
 ![Перья](./media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте форму Windows и обработки формы <xref:System.Windows.Forms.Control.Paint> событий. Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчик событий. Замените `Texture.jpg` с изображением в вашей системе.  
  
## <a name="see-also"></a>См. также
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
- [Объекты Graphics и Drawing в Windows Forms](graphics-and-drawing-in-windows-forms.md)
