---
title: "Практическое руководство. Рисование линии с текстурным заполнением"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 33374a16e6fee80dd45227acd4c5860d5bfc4545
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a>Практическое руководство. Рисование линии с текстурным заполнением
Вместо рисования линии сплошным цветом, можно нарисовать линии с текстурным заполнением. Рисование линий и кривых с текстурным заполнением, создайте <xref:System.Drawing.TextureBrush> и передать, <xref:System.Drawing.TextureBrush> объект <xref:System.Drawing.Pen.%23ctor%2A> конструктор. Растровое изображение, связанное с кистью текстуры используется для мозаичного плоскости (незаметно), и когда перо рисует линию или кривую, соответствующие пиксели мозаичную текстуру пера, становятся видимыми.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Bitmap> объекта из файла `Texture1.jpg`. Это растровое изображение используется для создания <xref:System.Drawing.TextureBrush> объекта и <xref:System.Drawing.TextureBrush> объект используется для создания <xref:System.Drawing.Pen> объекта. Вызов метода <xref:System.Drawing.Graphics.DrawImage%2A> рисуется растровое изображение с его верхнего левого угла на (0, 0). Вызов <xref:System.Drawing.Graphics.DrawEllipse%2A> использует <xref:System.Drawing.Pen> объекта, чтобы нарисовать эллипс текстуры.  
  
 Точечный рисунок и текстуры эллипс на следующем рисунке.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий. Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчика событий. Замените `Texture.jpg` с изображением в вашей системе.  
  
## <a name="see-also"></a>См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
