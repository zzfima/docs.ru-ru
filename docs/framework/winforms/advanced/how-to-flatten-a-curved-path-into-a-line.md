---
title: "Практическое руководство. Спрямление участков кривой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334fc0fee7166f8f8c5c1db61d3b9e370da72f87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a>Практическое руководство. Спрямление участков кривой
Объект <xref:System.Drawing.Drawing2D.GraphicsPath> объект хранит последовательности линий и сплайнов Безье. Можно добавить различные типы кривых (эллипсы, дуги, фундаментальные сплайны) с путем, но каждая кривая преобразуется в сплайн Безье перед сохранением в пути. Спрямление контура заключается в преобразовании всех сплайнов Безье в пути в последовательность прямых линий. На следующем рисунке путь до и после выравнивания.  
  
 ![Прямые линии и кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")  
  
### <a name="to-flatten-a-path"></a>Спрямление контура  
  
-   Вызовите <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> метод <xref:System.Drawing.Drawing2D.GraphicsPath> объекта. <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> Метод получает спрямления аргумент, который указывает максимальное расстояние между плоский пути и исходный путь.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
