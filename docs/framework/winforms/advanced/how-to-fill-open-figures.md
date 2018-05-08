---
title: Практическое руководство. Заливка открытых фигур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-fill-open-figures"></a>Практическое руководство. Заливка открытых фигур
Можно ввести путь, передав <xref:System.Drawing.Drawing2D.GraphicsPath> объект <xref:System.Drawing.Graphics.FillPath%2A> метод. <xref:System.Drawing.Graphics.FillPath%2A> Метод заливку пути в соответствии с режимом заполнения (чередование или поворот) в настоящее время, заданное для пути. Если путь содержит незамкнутые фигуры, контур заполняется, как если бы фигуры были замкнутыми. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Рисование прямой линии в конечной точке для начальной точкой замыкает фигуру.  
  
## <a name="example"></a>Пример  
 В следующем примере создается путь, который имеет одну открытую фигуру (дугу) и одну замкнутую фигуру (эллипс). <xref:System.Drawing.Graphics.FillPath%2A> Метод заливку пути в соответствии с режимом заполнения по умолчанию является <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Ниже показан результат выполнения примера кода. Обратите внимание, что путь заполняется (согласно <xref:System.Drawing.Drawing2D.FillMode.Alternate>) как если бы было закрыто незамкнутую фигуру прямую линию от его конечной точки к начальной точке.  
  
 ![Путь для открытия](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Контуры в GDI+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
