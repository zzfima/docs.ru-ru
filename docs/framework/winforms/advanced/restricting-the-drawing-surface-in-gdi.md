---
title: "Ограничение поверхности для рисования в GDI+"
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
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 213f0afefa1f8635d2b70d2e3626b7fbe748b42c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="87619-102">Ограничение поверхности для рисования в GDI+</span><span class="sxs-lookup"><span data-stu-id="87619-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="87619-103">Отсечение заключается в запрете на рисование прямоугольника или области.</span><span class="sxs-lookup"><span data-stu-id="87619-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="87619-104">Ниже показаны строки «Hello», ограничивается в область в форме основа.</span><span class="sxs-lookup"><span data-stu-id="87619-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="87619-105">![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="87619-105">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="87619-106">Задание области обрезки</span><span class="sxs-lookup"><span data-stu-id="87619-106">Clipping with Regions</span></span>  
 <span data-ttu-id="87619-107">Области могут быть созданы из пути и пути могут содержать границы строк, поэтому выделенный текст можно использовать для обрезки.</span><span class="sxs-lookup"><span data-stu-id="87619-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="87619-108">Ниже показан набор концентрических эллипсов, усеченными до внутреннюю часть текстовой строки.</span><span class="sxs-lookup"><span data-stu-id="87619-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="87619-109">![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="87619-109">![Restricted Drawing Surface](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="87619-110">Чтобы нарисовать с использованием обрезки, создайте <xref:System.Drawing.Graphics> , задайте его <xref:System.Drawing.Graphics.Clip%2A> свойство и затем вызвать методы рисования этого же <xref:System.Drawing.Graphics> объекта:</span><span class="sxs-lookup"><span data-stu-id="87619-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="87619-111">См. также</span><span class="sxs-lookup"><span data-stu-id="87619-111">See Also</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [<span data-ttu-id="87619-112">Линии, кривые и фигуры</span><span class="sxs-lookup"><span data-stu-id="87619-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="87619-113">Использование областей</span><span class="sxs-lookup"><span data-stu-id="87619-113">Using Regions</span></span>](../../../../docs/framework/winforms/advanced/using-regions.md)
