---
title: Использование объемного преобразования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: 6a029e17096222d7ed80dea16f91b83a813039f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="ed66e-102">Использование объемного преобразования</span><span class="sxs-lookup"><span data-stu-id="ed66e-102">Using the World Transformation</span></span>
<span data-ttu-id="ed66e-103">Мировое преобразование — это свойство <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="ed66e-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="ed66e-104">Числа, определяющие мировое преобразование хранятся в <xref:System.Drawing.Drawing2D.Matrix> объект, который представляет матрицу 3 × 3.</span><span class="sxs-lookup"><span data-stu-id="ed66e-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="ed66e-105"><xref:System.Drawing.Drawing2D.Matrix> И <xref:System.Drawing.Graphics> классы имеют различные методы для установки числа в матрицу мирового преобразования.</span><span class="sxs-lookup"><span data-stu-id="ed66e-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="ed66e-106">Различные типы преобразований</span><span class="sxs-lookup"><span data-stu-id="ed66e-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="ed66e-107">В следующем примере код сначала создает прямоугольник 50 × 50 и помещает его в точку начала координат (0, 0).</span><span class="sxs-lookup"><span data-stu-id="ed66e-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="ed66e-108">Источником является в левом верхнем углу клиентской области.</span><span class="sxs-lookup"><span data-stu-id="ed66e-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="ed66e-109">Следующий код применяется масштабирования преобразование, которое увеличивает прямоугольник с коэффициентом 1,75 по оси x и уменьшает прямоугольник с коэффициентом 0,5 по оси y.</span><span class="sxs-lookup"><span data-stu-id="ed66e-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="ed66e-110">Результатом является прямоугольник, который длиннее по оси x и по оси y меньше исходного.</span><span class="sxs-lookup"><span data-stu-id="ed66e-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="ed66e-111">Чтобы сменить прямоугольник вместо его масштабирования, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="ed66e-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="ed66e-112">Чтобы преобразовать прямоугольник, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="ed66e-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="ed66e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ed66e-113">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [<span data-ttu-id="ed66e-114">Системы координат и преобразования</span><span class="sxs-lookup"><span data-stu-id="ed66e-114">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [<span data-ttu-id="ed66e-115">Использование преобразований в управляемом GDI+</span><span class="sxs-lookup"><span data-stu-id="ed66e-115">Using Transformations in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
