---
title: Практическое руководство. Создание изображений из линий, кривых и фигур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 1977f1c9efe2c379ef6039870aade300efca2bdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709501"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="08218-102">Практическое руководство. Создание изображений из линий, кривых и фигур</span><span class="sxs-lookup"><span data-stu-id="08218-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="08218-103">Чтобы создать изображение, создайте <xref:System.Drawing.Drawing2D.GraphicsPath>, а затем вызывать методы, такие как <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> и <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, чтобы добавить путь к примитивы.</span><span class="sxs-lookup"><span data-stu-id="08218-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08218-104">Пример</span><span class="sxs-lookup"><span data-stu-id="08218-104">Example</span></span>  
 <span data-ttu-id="08218-105">В следующих примерах кода создаются путей, содержащих данные:</span><span class="sxs-lookup"><span data-stu-id="08218-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="08218-106">В первом примере создается путь, состоящий из одной фигуры.</span><span class="sxs-lookup"><span data-stu-id="08218-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="08218-107">Рисунок состоит из одного дуги. Дуга имеет угол поворота, равный-180 градусов, который является против часовой стрелки в системе координат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08218-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="08218-108">Во втором примере создается путь, состоящий из двух фигур.</span><span class="sxs-lookup"><span data-stu-id="08218-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="08218-109">Первая фигура является дуги, за которым следует строка.</span><span class="sxs-lookup"><span data-stu-id="08218-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="08218-110">Вторая – это линия, за которым следует строка кривую следует.</span><span class="sxs-lookup"><span data-stu-id="08218-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="08218-111">Первая фигура останется открытым, а второй замкнутой.</span><span class="sxs-lookup"><span data-stu-id="08218-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="08218-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="08218-112">Compiling the Code</span></span>  
 <span data-ttu-id="08218-113">Предыдущий пример предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="08218-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08218-114">См. также</span><span class="sxs-lookup"><span data-stu-id="08218-114">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="08218-115">Построение и рисование контуров</span><span class="sxs-lookup"><span data-stu-id="08218-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="08218-116">Рисование линий и фигур с помощью пера</span><span class="sxs-lookup"><span data-stu-id="08218-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
