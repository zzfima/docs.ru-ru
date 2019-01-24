---
title: Как выполнить Рисование линий с наконечниками
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: a0d4d92d7201c4ac09eadd11d8f2e38a3c80c287
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713144"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Как выполнить Рисование линий с наконечниками
Можно нарисовать начала и конца строки в одну из нескольких фигур, называемых наконечниками. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] поддерживает несколько отрезков, например циклический, квадрат, ромб и стрелки с наконечником.  
  
## <a name="example"></a>Пример  
 Можно указать отрезков в начале строки (начала штриха), в конец строки (конечного элемента) или дефисы пунктирной линии (штриховой наконечник).  
  
 В следующем примере рисуется линию со стрелкой на одном конце и кружком на другом конце. На рисунке показаны результирующие строки.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Создайте форму Windows и обработки формы <xref:System.Windows.Forms.Control.Paint> событий. Вставьте код в примере <xref:System.Windows.Forms.Control.Paint> обработчик событий передачи `e` как <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
