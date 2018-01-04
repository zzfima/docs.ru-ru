---
title: "Практическое руководство. Рисование линии в Windows Forms"
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
f1_keywords: Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78ad7d455f1de4b7077288d9575ea4907c3f218d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Практическое руководство. Рисование линии в Windows Forms
В этом примере рисование линии в форме. Как правило, при рисовании в форме обработки формы <xref:System.Windows.Forms.Control.Paint> событий и выполнять рисование с помощью <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> свойство <xref:System.Windows.Forms.PaintEventArgs>, как показано в следующем примере  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Следует всегда вызывать <xref:System.IDisposable.Dispose%2A> на все объекты, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> объектов.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
