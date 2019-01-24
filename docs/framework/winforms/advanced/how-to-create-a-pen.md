---
title: Как выполнить Создание пера
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: b8a61e554ef58ca216050d34269e44355f7c1aaf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527449"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="ed147-102">Как выполнить Создание пера</span><span class="sxs-lookup"><span data-stu-id="ed147-102">How to: Create a Pen</span></span>
<span data-ttu-id="ed147-103">В этом примере создается <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="ed147-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed147-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ed147-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="ed147-105">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="ed147-105">Robust Programming</span></span>  
 <span data-ttu-id="ed147-106">После завершения использования объектов, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> объектов, необходимо вызвать <xref:System.Drawing.Pen.Dispose%2A> на них.</span><span class="sxs-lookup"><span data-stu-id="ed147-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed147-107">См. также</span><span class="sxs-lookup"><span data-stu-id="ed147-107">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="ed147-108">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="ed147-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="ed147-109">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="ed147-109">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
