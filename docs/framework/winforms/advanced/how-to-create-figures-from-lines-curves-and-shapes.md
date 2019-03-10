---
title: Практическое руководство. Создание изображений из линий, кривых и фигур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 1977f1c9efe2c379ef6039870aade300efca2bdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709501"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Практическое руководство. Создание изображений из линий, кривых и фигур
Чтобы создать изображение, создайте <xref:System.Drawing.Drawing2D.GraphicsPath>, а затем вызывать методы, такие как <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, чтобы добавить путь к примитивы.  
  
## <a name="example"></a>Пример  
 В следующих примерах кода создаются путей, содержащих данные:  
  
-   В первом примере создается путь, состоящий из одной фигуры. Рисунок состоит из одного дуги. Дуга имеет угол поворота, равный-180 градусов, который является против часовой стрелки в системе координат по умолчанию.  
  
-   Во втором примере создается путь, состоящий из двух фигур. Первая фигура является дуги, за которым следует строка. Вторая – это линия, за которым следует строка кривую следует. Первая фигура останется открытым, а второй замкнутой.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Построение и рисование контуров](constructing-and-drawing-paths.md)
- [Рисование линий и фигур с помощью пера](using-a-pen-to-draw-lines-and-shapes.md)
