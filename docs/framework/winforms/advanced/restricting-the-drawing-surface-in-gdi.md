---
title: Ограничение поверхности для рисования в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: b457e94acb334dc012f017090c63189de372592d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523927"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a>Ограничение поверхности для рисования в GDI+
Отсечение заключается в запрете на рисование прямоугольника или области. Ниже показаны строки «Hello», ограничивается в область в форме основа.  
  
 ![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")  
  
## <a name="clipping-with-regions"></a>Задание области обрезки  
 Области могут быть созданы из пути и пути могут содержать границы строк, поэтому выделенный текст можно использовать для обрезки. Ниже показан набор концентрических эллипсов, усеченными до внутреннюю часть текстовой строки.  
  
 ![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")  
  
 Чтобы нарисовать с использованием обрезки, создайте <xref:System.Drawing.Graphics> , задайте его <xref:System.Drawing.Graphics.Clip%2A> свойство и затем вызвать методы рисования этого же <xref:System.Drawing.Graphics> объекта:  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Линии, кривые и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)
