---
title: Практическое руководство. Установка цвета фона для пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: 37bc289fa1eeb7ef5510474dff062ae76be5fc65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522386"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="3fd2d-102">Практическое руководство. Установка цвета фона для пера</span><span class="sxs-lookup"><span data-stu-id="3fd2d-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="3fd2d-103">В этом примере изменяется цвет существующем <xref:System.Drawing.Pen> объекта</span><span class="sxs-lookup"><span data-stu-id="3fd2d-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fd2d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3fd2d-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fd2d-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3fd2d-105">Compiling the Code</span></span>  
 <span data-ttu-id="3fd2d-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3fd2d-106">This example requires:</span></span>  
  
-   <span data-ttu-id="3fd2d-107">Объект <xref:System.Drawing.Pen> объект с именем `myPen`.</span><span class="sxs-lookup"><span data-stu-id="3fd2d-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3fd2d-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="3fd2d-108">Robust Programming</span></span>  
 <span data-ttu-id="3fd2d-109">Необходимо вызвать <xref:System.Drawing.Pen.Dispose%2A> на объекты, которые потребляют системные ресурсы (такие как <xref:System.Drawing.Pen> объекты) после завершения работы с ними.</span><span class="sxs-lookup"><span data-stu-id="3fd2d-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd2d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd2d-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="3fd2d-111">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="3fd2d-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="3fd2d-112">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="3fd2d-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="3fd2d-113">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="3fd2d-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="3fd2d-114">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="3fd2d-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
