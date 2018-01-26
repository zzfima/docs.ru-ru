---
title: "Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур"
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 40520f566beafc83075d0563148b5d0f9bd4fe85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Практическое руководство. Создание изображений из прямых и кривых линий и геометрических фигур
Чтобы создать изображение, построить <xref:System.Drawing.Drawing2D.GraphicsPath>и затем вызывать методы, такие как <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, для добавления в путь примитивов.  
  
## <a name="example"></a>Пример  
 В следующем примере кода создается контур, фигуры:  
  
-   В первом примере создается путь, состоящий из одной фигуры. На рисунке состоит из одного дуги. Дуга имеет угол поворота-180 градусов против часовой стрелки в системе координат по умолчанию.  
  
-   Во втором примере создается путь, состоящий из двух фигур. Первая фигура имеет дугу, за которым следует строка. Вторая фигура представляет собой строку, следуют за строка кривой. Первая фигура остается открытым, и второй рисунок закрывается.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
