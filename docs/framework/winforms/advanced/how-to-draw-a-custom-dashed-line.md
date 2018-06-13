---
title: Практическое руководство. Рисование пользовательских пунктирных линий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 39dde3bb45165783171326b79e98744807350952
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521619"
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Практическое руководство. Рисование пользовательских пунктирных линий
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет несколько стили штрихов, которые перечислены в <xref:System.Drawing.Drawing2D.DashStyle> перечисления. Если эти стандартные стили пунктирных линий не подходят, можно создать пользовательский шаблон пунктирной линии.  
  
## <a name="example"></a>Пример  
 Рисование пользовательских пунктирных линий, поместите длины штрихов и промежутков в массив и присвойте его значение <xref:System.Drawing.Pen.DashPattern%2A> свойство <xref:System.Drawing.Pen> объекта. В следующем примере рисуется пользовательская пунктирная линия на основе массива `{5, 2, 15, 4}`. Если умножить ширину пера 5 элементов массива, можно получить `{25, 10, 75, 20}`. Альтернативные отображаемых дефисы длиной от 25 до 75 и альтернативные пробелы в расстояние от 10 до 20.  
  
 Ниже показан результирующий пунктирной линией. Обратите внимание, что последний штрих должен быть короче 25 единиц, чтобы заканчиваться на строке (405, 5).  
  
 ![Перья](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Создайте форму Windows Form и обработки формы <xref:System.Windows.Forms.Control.Paint> событий. Вставьте приведенный выше код в <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
