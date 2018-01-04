---
title: "Практическое руководство. Заливка открытых фигур"
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
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c020e5f7306e73ee97dff0b492b04b5a153059cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="fb0dd-102">Практическое руководство. Заливка открытых фигур</span><span class="sxs-lookup"><span data-stu-id="fb0dd-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="fb0dd-103">Можно ввести путь, передав <xref:System.Drawing.Drawing2D.GraphicsPath> объект <xref:System.Drawing.Graphics.FillPath%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="fb0dd-104"><xref:System.Drawing.Graphics.FillPath%2A> Метод заливку пути в соответствии с режимом заполнения (чередование или поворот) в настоящее время, заданное для пути.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="fb0dd-105">Если путь содержит незамкнутые фигуры, контур заполняется, как если бы фигуры были замкнутыми.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fb0dd-106">Рисование прямой линии в конечной точке для начальной точкой замыкает фигуру.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-106"> closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb0dd-107">Пример</span><span class="sxs-lookup"><span data-stu-id="fb0dd-107">Example</span></span>  
 <span data-ttu-id="fb0dd-108">В следующем примере создается путь, который имеет одну открытую фигуру (дугу) и одну замкнутую фигуру (эллипс).</span><span class="sxs-lookup"><span data-stu-id="fb0dd-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="fb0dd-109"><xref:System.Drawing.Graphics.FillPath%2A> Метод заливку пути в соответствии с режимом заполнения по умолчанию является <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="fb0dd-110">Ниже показан результат выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="fb0dd-111">Обратите внимание, что путь заполняется (согласно <xref:System.Drawing.Drawing2D.FillMode.Alternate>) как если бы было закрыто незамкнутую фигуру прямую линию от его конечной точки к начальной точке.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="fb0dd-112">![Путь для открытия](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="fb0dd-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fb0dd-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fb0dd-113">Compiling the Code</span></span>  
 <span data-ttu-id="fb0dd-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="fb0dd-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb0dd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fb0dd-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="fb0dd-116">Контуры в GDI+</span><span class="sxs-lookup"><span data-stu-id="fb0dd-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
