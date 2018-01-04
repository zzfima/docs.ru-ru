---
title: "Б &#233; Безье сплайны в GDI +"
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
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8cc06a81c879e6ebd50c4eb6a70590c28cc43f6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="b233zier-splines-in-gdi"></a>Б &#233; Безье сплайны в GDI +
Сплайн Безье — это кривая, задаваемая четырьмя точками: двумя конечными точками (p1 и p2) и двумя контрольными точками (c1 и c2). Кривая начинается в точке p1 и заканчивается в точке p2. Кривая не проходит через контрольные точки, но контрольные точки действуют как магниты удаление кривой в определенных направлениях и влияние на способ изгиба кривой. На следующем рисунке кривая Безье и ее конечные и контрольные точки.  
  
 ![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")  
  
 Кривая начинается в точке p1 и перемещается в направлении контрольной точки c1. Касательной к кривой в p1 — это линия, соединяющей p1 для c1. Касательной в конечной точке p2 — это линия, соединяющей c2 на p2.  
  
## <a name="drawing-bzier-splines"></a>Рисование сплайнов Безье  
 Чтобы нарисовать сплайн Безье, требуются объекты <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Pen>. Экземпляр <xref:System.Drawing.Graphics> класс предоставляет <xref:System.Drawing.Graphics.DrawBezier%2A> метода и <xref:System.Drawing.Pen> хранит атрибуты, такие как ширина и цвет линии, используемой для подготовки к просмотру кривой. <xref:System.Drawing.Pen> Передается в качестве одного из аргументов <xref:System.Drawing.Graphics.DrawBezier%2A> метод. Остальные аргументы, передаваемые <xref:System.Drawing.Graphics.DrawBezier%2A> метод — конечные точки и контрольные точки. В следующем примере рисуется сплайн Безье с начальной точкой (0, 0), управления точками (40, 20) и (80, 150) и конечную точку с координатами (100, 10):  
  
 [!code-csharp[LinesCurvesAndShapes#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 Кривая, контрольные точки и две касательные на следующем рисунке.  
  
 ![Сплайны Безье](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art12.gif "Aboutgdip02_art12")  
  
 Сплайны Безье изначально были разработаны Пьер Безье для использования в автомобильной промышленности. Они оказались во многих типов автоматизированного проектирования и также используются для определения структуры шрифтов. Сплайны Безье можно создавать множество различных фигур, некоторые из которых показаны на следующем рисунке.  
  
 ![Пути](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art13.gif "Aboutgdip02_art13")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Построение и рисование кривых](../../../../docs/framework/winforms/advanced/constructing-and-drawing-curves.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
