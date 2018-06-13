---
title: Практическое руководство. Создание пера
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
ms.openlocfilehash: aff1771af12a9f59127a9f21f4b692d6214c457d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520982"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="869dd-102">Практическое руководство. Создание пера</span><span class="sxs-lookup"><span data-stu-id="869dd-102">How to: Create a Pen</span></span>
<span data-ttu-id="869dd-103">В этом примере создается <xref:System.Drawing.Pen> объекта.</span><span class="sxs-lookup"><span data-stu-id="869dd-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="869dd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="869dd-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="869dd-105">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="869dd-105">Robust Programming</span></span>  
 <span data-ttu-id="869dd-106">После завершения использования объектов, которые потребляют системные ресурсы, такие как <xref:System.Drawing.Pen> объектов, необходимо вызвать <xref:System.Drawing.Pen.Dispose%2A> на них.</span><span class="sxs-lookup"><span data-stu-id="869dd-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869dd-107">См. также</span><span class="sxs-lookup"><span data-stu-id="869dd-107">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="869dd-108">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="869dd-108">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="869dd-109">Перья, линии и прямоугольники в GDI+</span><span class="sxs-lookup"><span data-stu-id="869dd-109">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
