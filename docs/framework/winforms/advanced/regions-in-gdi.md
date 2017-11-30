---
title: "Области в GDI+"
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a>Области в GDI+
Область — это часть области отображения устройство вывода. Области могут быть простой (один прямоугольник) или сложными (набор многоугольников и замкнутых кривых). На следующем рисунке показано две области: один из них образована прямоугольником, а другая образована путь.  
  
 ![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Использование областей  
 Области часто используются для обрезки и проверка нажатия. Отсечение заключается в запрете на рисование определенной области отображения, обычно это область, необходимо обновить. Проверка на наличие данных включает в себя проверку, чтобы определить, находится ли курсор в области экрана при нажатии кнопки мыши.  
  
 Можно создать регион из прямоугольника или путь. Можно также создавать сложные области путем объединения существующих областей. <xref:System.Drawing.Region> Класс предоставляет следующие методы для объединения областей: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, и <xref:System.Drawing.Region.Complement%2A>.  
  
 Пересечение двух областей — это совокупность всех точек, принадлежащих обоих регионах. Объединение — это набор всех точек, принадлежащих одной или обеих областей. Дополнение области — это набор всех точек, которые не находятся в области. Пересечение и объединение двух областей, на предыдущем рисунке показано на следующем рисунке.  
  
 ![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 <xref:System.Drawing.Region.Xor%2A> Метод, примененный к паре областей, выдает область, содержащую все точки, которые принадлежат к одной области или другой, но не оба. <xref:System.Drawing.Region.Exclude%2A> Метод, примененный к паре областей, выдает область, содержащую все точки первой области, которые не являются второй области. На следующем рисунке показан областей, которые являются результатом применения <xref:System.Drawing.Region.Xor%2A> и <xref:System.Drawing.Region.Exclude%2A> методы для двух регионах, показанный в начале этого раздела.  
  
 ![Регионы](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Чтобы заполнить область, необходимо <xref:System.Drawing.Graphics> объекта, <xref:System.Drawing.Brush> объекта и <xref:System.Drawing.Region> объекта. <xref:System.Drawing.Graphics> Объект предоставляет <xref:System.Drawing.Graphics.FillRegion%2A> метода и <xref:System.Drawing.Brush> объект хранилищем атрибутов, таких как цвета или узора заливки. Следующий пример заполняет область сплошным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)
