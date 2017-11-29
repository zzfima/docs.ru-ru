---
title: "Построение и рисование кривых"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 801af10f7b9e5e7998fc061537977c5bced6bdb3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="d5ecb-102">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="d5ecb-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="d5ecb-103">поддерживает различные типы кривых: эллипсы, дуги, фундаментальные сплайны и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="d5ecb-104">Эллипс определяется его ограничивающего прямоугольника; дуга является частью эллипса, определяемого, начального угла и угла поворота.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="d5ecb-105">Фундаментальный сплайн определяется массивом точек и параметром натяжения: гладкая кривая проходит через все точки массива, а параметр натяжения влияет на изгиб кривой.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="d5ecb-106">Сплайн Безье определяется двумя конечными точками и двумя контрольными точками кривая не проходит через контрольные точки, но контрольные точки, влияют на и форму кривой переходит от одной конечной точки в другую.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5ecb-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="d5ecb-107">In This Section</span></span>  
 [<span data-ttu-id="d5ecb-108">Практическое руководство. Рисование фундаментальных сплайнов</span><span class="sxs-lookup"><span data-stu-id="d5ecb-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="d5ecb-109">Описывает фундаментальные сплайны и способов их рисования.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="d5ecb-110">Практическое руководство. Рисование отдельного сплайна Безье</span><span class="sxs-lookup"><span data-stu-id="d5ecb-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="d5ecb-111">Описание сплайнов Безье и способов их рисования.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="d5ecb-112">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="d5ecb-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="d5ecb-113">Объясняется, как рисование нескольких последовательных сплайнов Безье в последовательности.</span><span class="sxs-lookup"><span data-stu-id="d5ecb-113">Explains how to draw several Bézier splines in sequence.</span></span>
