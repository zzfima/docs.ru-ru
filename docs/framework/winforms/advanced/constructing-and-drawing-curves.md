---
title: Построение и рисование кривых
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506100"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="74574-102">Построение и рисование кривых</span><span class="sxs-lookup"><span data-stu-id="74574-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="74574-103">GDI + поддерживает различные типы кривых: эллипсы, дуги, фундаментальные сплайны и сплайнов Безье.</span><span class="sxs-lookup"><span data-stu-id="74574-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="74574-104">Эллипс, определяемый ограничивающим его прямоугольником; дуга является частью эллипса, определяемого, начальный угол и угол поворота.</span><span class="sxs-lookup"><span data-stu-id="74574-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="74574-105">Фундаментальный сплайн, определяется массив точек и параметром натяжение, гладкая кривая проходит через все точки в массиве, а параметр натяжение влияет изгиб кривой.</span><span class="sxs-lookup"><span data-stu-id="74574-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="74574-106">Сплайн Безье определяется двумя конечными точками и двумя контрольными точками кривая проходит через контрольные точки, но контрольные точки, влияют на и форму кривой переходит от одной конечной точки в другую.</span><span class="sxs-lookup"><span data-stu-id="74574-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74574-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="74574-107">In This Section</span></span>  
 [<span data-ttu-id="74574-108">Практическое руководство. Рисование фундаментальных сплайнов</span><span class="sxs-lookup"><span data-stu-id="74574-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="74574-109">Описывает фундаментальные сплайны и способов их рисования.</span><span class="sxs-lookup"><span data-stu-id="74574-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="74574-110">Практическое руководство. Рисование отдельного сплайна Безье</span><span class="sxs-lookup"><span data-stu-id="74574-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="74574-111">Описывает сплайн Безье, а также как их рисования.</span><span class="sxs-lookup"><span data-stu-id="74574-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="74574-112">Практическое руководство. Рисование последовательности сплайнов Безье</span><span class="sxs-lookup"><span data-stu-id="74574-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="74574-113">Объясняется, как нарисовать несколько сплайны Безье в последовательности.</span><span class="sxs-lookup"><span data-stu-id="74574-113">Explains how to draw several Bézier splines in sequence.</span></span>
