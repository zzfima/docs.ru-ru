---
title: Как выполнить Применение гамма-коррекции к градиенту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: b3b45c312542a3f8410bd93fcbe4e4cb70aa8516
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527163"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="81994-102">Как выполнить Применение гамма-коррекции к градиенту</span><span class="sxs-lookup"><span data-stu-id="81994-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="81994-103">Гамма-коррекцию для кисти линейного градиента можно включить, задав кисти <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="81994-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="81994-104">Гамма-коррекция можно отключить, установив <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="81994-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="81994-105">Гамма-коррекция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81994-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81994-106">Пример</span><span class="sxs-lookup"><span data-stu-id="81994-106">Example</span></span>  
 <span data-ttu-id="81994-107">В примере создается кисть линейного градиента и использует этой кисти для заливки двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="81994-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="81994-108">Первый прямоугольник заполняется без гамма-коррекции, а второй прямоугольник заполняется гамма-коррекция.</span><span class="sxs-lookup"><span data-stu-id="81994-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="81994-109">Ниже показан закрашенный двух прямоугольников.</span><span class="sxs-lookup"><span data-stu-id="81994-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="81994-110">В середине верхним прямоугольником, не имеющем гамма-коррекция, кажется темным.</span><span class="sxs-lookup"><span data-stu-id="81994-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="81994-111">Нижний прямоугольник, который гамма-коррекция, отображается интенсивность дополнительные универсальный код.</span><span class="sxs-lookup"><span data-stu-id="81994-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="81994-112">![Градиента](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="81994-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="81994-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="81994-113">Compiling the Code</span></span>  
 <span data-ttu-id="81994-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="81994-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81994-115">См. также</span><span class="sxs-lookup"><span data-stu-id="81994-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush>
- [<span data-ttu-id="81994-116">Заливка фигур с помощью градиентной кисти</span><span class="sxs-lookup"><span data-stu-id="81994-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
