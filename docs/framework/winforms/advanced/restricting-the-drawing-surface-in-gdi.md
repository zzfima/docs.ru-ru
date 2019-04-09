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
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074967"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="9b2d7-102">Ограничение поверхности для рисования в GDI+</span><span class="sxs-lookup"><span data-stu-id="9b2d7-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="9b2d7-103">Обрезка заключается в ограничении Рисование прямоугольника или области.</span><span class="sxs-lookup"><span data-stu-id="9b2d7-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="9b2d7-104">На следующем рисунке строку «Hello», была выполнена Обрезка область в форме сердца.</span><span class="sxs-lookup"><span data-stu-id="9b2d7-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="9b2d7-105">![Ограничение поверхности для рисования](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="9b2d7-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="9b2d7-106">Задание области обрезки</span><span class="sxs-lookup"><span data-stu-id="9b2d7-106">Clipping with Regions</span></span>  
 <span data-ttu-id="9b2d7-107">Регионы могут создаваться из пути и пути могут содержать границы строк, поэтому контурного текста можно использовать для обрезки.</span><span class="sxs-lookup"><span data-stu-id="9b2d7-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="9b2d7-108">Ниже показан набор концентрических эллипсов, была выполнена Обрезка внутреннюю часть текстовой строки.</span><span class="sxs-lookup"><span data-stu-id="9b2d7-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="9b2d7-109">![Ограничение поверхности для рисования](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="9b2d7-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="9b2d7-110">Для рисования с использованием обрезки, создание <xref:System.Drawing.Graphics> , задать его <xref:System.Drawing.Graphics.Clip%2A> свойство и затем вызвать методы рисования этого же <xref:System.Drawing.Graphics> объекта:</span><span class="sxs-lookup"><span data-stu-id="9b2d7-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="9b2d7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9b2d7-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="9b2d7-112">Прямые и кривые линии и фигуры</span><span class="sxs-lookup"><span data-stu-id="9b2d7-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="9b2d7-113">Использование областей</span><span class="sxs-lookup"><span data-stu-id="9b2d7-113">Using Regions</span></span>](using-regions.md)
