---
title: Рисование линий и фигур с помощью пера
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: 3846c59712cec6003c35f336714041544dec94b3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777251"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="6a64e-102">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="6a64e-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="6a64e-103">Используйте [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` объектов, чтобы нарисовать сегменты линии, кривые и контуры фигуры.</span><span class="sxs-lookup"><span data-stu-id="6a64e-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="6a64e-104">В этом разделе *строки* ссылается на любой из них, если не указано для обозначения только сегмент линии.</span><span class="sxs-lookup"><span data-stu-id="6a64e-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="6a64e-105">Задание свойств пера для управления цвет, ширину, выравнивание и стиль линий, нарисованных при помощи этого пера.</span><span class="sxs-lookup"><span data-stu-id="6a64e-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a64e-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6a64e-106">In This Section</span></span>  
 [<span data-ttu-id="6a64e-107">Практическое руководство. С помощью пера для рисования линий</span><span class="sxs-lookup"><span data-stu-id="6a64e-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="6a64e-108">Объясняется, как для рисования линий.</span><span class="sxs-lookup"><span data-stu-id="6a64e-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="6a64e-109">Практическое руководство. Рисование прямоугольников с помощью пера</span><span class="sxs-lookup"><span data-stu-id="6a64e-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="6a64e-110">Описывает, как Рисование прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="6a64e-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="6a64e-111">Практическое руководство. Набор толщины и выравнивания пера</span><span class="sxs-lookup"><span data-stu-id="6a64e-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="6a64e-112">Объясняется, как изменить ширину и выравнивание `Pen` объекта.</span><span class="sxs-lookup"><span data-stu-id="6a64e-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="6a64e-113">Практическое руководство. Рисование линий с наконечниками</span><span class="sxs-lookup"><span data-stu-id="6a64e-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="6a64e-114">В этой статье описывается добавление оконечных, линиям.</span><span class="sxs-lookup"><span data-stu-id="6a64e-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="6a64e-115">Практическое руководство. Соединение линий</span><span class="sxs-lookup"><span data-stu-id="6a64e-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="6a64e-116">Показано, как соединить две строки.</span><span class="sxs-lookup"><span data-stu-id="6a64e-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="6a64e-117">Практическое руководство. Рисование пользовательских пунктирных линий</span><span class="sxs-lookup"><span data-stu-id="6a64e-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="6a64e-118">Описывает способ рисования пунктирной линией.</span><span class="sxs-lookup"><span data-stu-id="6a64e-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="6a64e-119">Практическое руководство. Рисование линии с текстурным заполнением</span><span class="sxs-lookup"><span data-stu-id="6a64e-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="6a64e-120">Объясняется, как рисование линии с текстурным заполнением.</span><span class="sxs-lookup"><span data-stu-id="6a64e-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6a64e-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6a64e-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="6a64e-122">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="6a64e-122">Describes this class and has links to all its members.</span></span>
