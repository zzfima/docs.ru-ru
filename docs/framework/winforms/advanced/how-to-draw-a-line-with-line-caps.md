---
title: "Практическое руководство. Рисование линий с наконечниками"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Практическое руководство. Рисование линий с наконечниками
В одном из нескольких фигур, называемых наконечниками можно нарисовать начала и конца строки. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]поддерживает несколько отрезков, например циклический, ромб, квадрат и стрелки.  
  
## <a name="example"></a>Пример  
 Можно указать отрезков в начале строки (начальный наконечник), в конец строки (конец) или дефисы пунктирная линия (тире cap).  
  
 В следующем примере рисуется линию со стрелкой на одном конце и кружком на другом конце. На рисунке показаны результирующие строки.  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий. Вставьте код в примере <xref:System.Windows.Forms.Control.Paint> обработчик события передачи `e` как <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
