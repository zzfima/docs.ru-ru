---
title: Практическое руководство. Применение гамма-коррекции к градиенту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 9c3c9c5c63194b1dee8314a1ef96497a8b78b5ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="fa2e5-102">Практическое руководство. Применение гамма-коррекции к градиенту</span><span class="sxs-lookup"><span data-stu-id="fa2e5-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="fa2e5-103">Гамма-коррекцию для кисти линейного градиента можно включить, установив кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="fa2e5-104">Гамма-коррекцию можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="fa2e5-105">Гамма-коррекция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa2e5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="fa2e5-106">Example</span></span>  
 <span data-ttu-id="fa2e5-107">В примере создается кисти линейного градиента и используется, для заливки двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="fa2e5-108">Первый прямоугольник заполняется без гамма-коррекцию, и второй прямоугольник заполняется с гамма-коррекцией.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="fa2e5-109">На следующем рисунке двух заполненных прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="fa2e5-110">Верхний прямоугольник, который не имеет гамма-коррекцию, кажется темным в середине.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="fa2e5-111">Дополнительные интенсивность унифицированного появится нижний прямоугольник, имеющая гамма-коррекцию.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="fa2e5-112">![Градиент](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="fa2e5-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa2e5-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fa2e5-113">Compiling the Code</span></span>  
 <span data-ttu-id="fa2e5-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2e5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fa2e5-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [<span data-ttu-id="fa2e5-116">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="fa2e5-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
