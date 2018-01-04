---
title: "Практическое руководство. Заливка фигуры сплошным цветом"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f016404feeac47c5f77527b8baa68d70742d4763
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="96274-102">Практическое руководство. Заливка фигуры сплошным цветом</span><span class="sxs-lookup"><span data-stu-id="96274-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="96274-103">Чтобы заливка фигуры сплошным цветом, создайте <xref:System.Drawing.SolidBrush> , а затем передать, <xref:System.Drawing.SolidBrush> объект в качестве аргумента для одного из методов заливки класса <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="96274-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="96274-104">В следующем примере показано, как заливка эллипса сплошным красным цветом.</span><span class="sxs-lookup"><span data-stu-id="96274-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96274-105">Пример</span><span class="sxs-lookup"><span data-stu-id="96274-105">Example</span></span>  
 <span data-ttu-id="96274-106">В следующем коде <xref:System.Drawing.SolidBrush.%23ctor%2A> конструктор принимает <xref:System.Drawing.Color> объект в качестве ее единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="96274-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="96274-107">Значения, используемые <xref:System.Drawing.Color.FromArgb%2A> метод представления альфа, красного, зеленого и синего компонентов цвета.</span><span class="sxs-lookup"><span data-stu-id="96274-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="96274-108">Каждое из этих значений должно быть в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="96274-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="96274-109">Первое число 255 указывает, цвет — полностью непрозрачный, а второй 255 показывает, что красный компонент имеет полный интенсивность.</span><span class="sxs-lookup"><span data-stu-id="96274-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="96274-110">Два нуля показывают, что зеленый и синий компоненты имеют интенсивность равна 0.</span><span class="sxs-lookup"><span data-stu-id="96274-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="96274-111">Четыре цифры (0, 0, 100, 60), передаваемый <xref:System.Drawing.Graphics.FillEllipse%2A> метода укажите расположение и размер эллипса ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="96274-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="96274-112">Прямоугольник имеет верхний левый угол (0, 0), ширина 100, а высота — 60.</span><span class="sxs-lookup"><span data-stu-id="96274-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96274-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="96274-113">Compiling the Code</span></span>  
 <span data-ttu-id="96274-114">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="96274-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96274-115">См. также</span><span class="sxs-lookup"><span data-stu-id="96274-115">See Also</span></span>  
 [<span data-ttu-id="96274-116">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="96274-116">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
