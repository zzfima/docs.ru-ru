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
ms.openlocfilehash: e812e441233c1d29a67dac639048e20a659549f0
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809486"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="0e6ce-102">Практическое руководство. Применение гамма-коррекции к градиенту</span><span class="sxs-lookup"><span data-stu-id="0e6ce-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="0e6ce-103">Гамма-коррекцию для кисти линейного градиента можно включить, задав кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="0e6ce-104">Гамма-коррекция можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="0e6ce-105">Гамма-коррекция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e6ce-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0e6ce-106">Example</span></span>  

<span data-ttu-id="0e6ce-107">Следующий пример — это метод, который вызывается из элемента управления <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-107">The following example is a method that is called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0e6ce-108">В примере создается кисть линейного градиента и использует этой кисти для заливки двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-108">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="0e6ce-109">Первый прямоугольник заполняется без гамма-коррекции, а второй прямоугольник заполняется гамма-коррекция.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-109">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="0e6ce-110">Ниже показан закрашенный двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-110">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="0e6ce-111">В середине верхним прямоугольником, не имеющем гамма-коррекция, кажется темным.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-111">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="0e6ce-112">Нижний прямоугольник, который гамма-коррекция, отображается интенсивность дополнительные универсальный код.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-112">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 ![Два градиентной заливкой прямоугольники, с и без гамма-коррекция.](./media/how-to-apply-gamma-correction-to-a-gradient/two-rectangles-gamma-gradient.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e6ce-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0e6ce-114">Compiling the Code</span></span>  
 <span data-ttu-id="0e6ce-115">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6ce-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0e6ce-116">See also</span></span>

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="0e6ce-117">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="0e6ce-117">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
