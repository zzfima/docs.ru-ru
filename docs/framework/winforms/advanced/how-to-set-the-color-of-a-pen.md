---
title: Практическое руководство. Установка цвета пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: a2645112950be88cbc569e0be7889c0f1019223d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710394"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="ad235-102">Практическое руководство. Установка цвета пера</span><span class="sxs-lookup"><span data-stu-id="ad235-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="ad235-103">В этом примере изменяется цвет в существующем <xref:System.Drawing.Pen> объекта</span><span class="sxs-lookup"><span data-stu-id="ad235-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad235-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ad235-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad235-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ad235-105">Compiling the Code</span></span>  
 <span data-ttu-id="ad235-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ad235-106">This example requires:</span></span>  
  
-   <span data-ttu-id="ad235-107">Объект <xref:System.Drawing.Pen> объект с именем `myPen`.</span><span class="sxs-lookup"><span data-stu-id="ad235-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ad235-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ad235-108">Robust Programming</span></span>  
 <span data-ttu-id="ad235-109">Следует вызывать <xref:System.Drawing.Pen.Dispose%2A> на какие объекты используют системные ресурсы (такие как <xref:System.Drawing.Pen> объекты) после завершения их использования.</span><span class="sxs-lookup"><span data-stu-id="ad235-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad235-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ad235-110">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="ad235-111">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="ad235-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="ad235-112">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="ad235-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="ad235-113">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="ad235-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="ad235-114">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="ad235-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
