---
title: "Практическое руководство. Сдвиг цветов"
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a>Практическое руководство. Сдвиг цветов
Наклон увеличивает или уменьшает компонент цвета на сумму пропорционально другому компоненту цвета. Например рассмотрим преобразование, в котором красный компонент увеличивается на половину значения синего компонента. При таком преобразовании цвет (0,2, 0,5, 1) станут (0,7, 0,5, 1). Новое значение красного компонента равняется 0,2 + (1/2)(1) = 0,7.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Drawing.Image> объекта из файла ColorBars4.bmp. Затем код применяет наклон преобразование, описанное в предыдущем абзаце к каждой точке в изображении.  
  
 Ниже показан исходный образ в левой части экрана и преобразованное изображение справа.  
  
 ![Сместить цвета](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 Ниже перечислены эти векторы четырех полос до и после преобразования.  
  
|До преобразования|Обрезается|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>. Замените `ColorBars.bmp` в вашей системе путь и имя образа.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)
