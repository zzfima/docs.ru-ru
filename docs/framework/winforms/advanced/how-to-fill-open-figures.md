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
ms.openlocfilehash: e9743d3268a7a2acfb6266872c3346a05269c369
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702737"
---
# <a name="how-to-fill-open-figures"></a>Практическое руководство. Заливка открытых фигур
Вы можете указать путь, передав <xref:System.Drawing.Drawing2D.GraphicsPath> объект <xref:System.Drawing.Graphics.FillPath%2A> метод. <xref:System.Drawing.Graphics.FillPath%2A> Метод заполняет пути в соответствии с режимом заполнения (чередование или поворот), заданных в настоящее время для пути. Если путь содержит незамкнутые фигуры, путь будет заполнено так, как если бы эти цифры были закрыты. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] замыкает фигуру рисования прямую линию от его конечной точки до ее начала.  
  
## <a name="example"></a>Пример  
 В следующем примере создается путь, который имеет один незамкнутую фигуру (дугу) и одну замкнутую фигуру (эллипс). <xref:System.Drawing.Graphics.FillPath%2A> Метод заливку пути в соответствии с режимом заполнения по умолчанию, который является <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Ниже показан результат выполнения примера кода. Обратите внимание, что путь заполняется (согласно <xref:System.Drawing.Drawing2D.FillMode.Alternate>) как будто открытая фигура замкнута прямой линией в конечной точке для начальной точкой.  
  
 ![Путь для открытия файла](./media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Контуры в GDI+](graphics-paths-in-gdi.md)
