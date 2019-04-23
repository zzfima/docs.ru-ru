---
title: Практическое руководство. Заливка фигуры сплошным цветом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: d6fe7a252029ff80f21d99f7342fabb1d29fbe24
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211677"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="bca98-102">Практическое руководство. Заливка фигуры сплошным цветом</span><span class="sxs-lookup"><span data-stu-id="bca98-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="bca98-103">Чтобы заливка фигуры сплошным цветом, создайте <xref:System.Drawing.SolidBrush> , а затем передать, <xref:System.Drawing.SolidBrush> объект в качестве аргумента одному из методов заливки класса <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="bca98-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="bca98-104">В следующем примере показано, как заливка эллипса красный цвет.</span><span class="sxs-lookup"><span data-stu-id="bca98-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca98-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bca98-105">Example</span></span>  
 <span data-ttu-id="bca98-106">В следующем коде <xref:System.Drawing.SolidBrush.%23ctor%2A> конструктор принимает <xref:System.Drawing.Color> объект в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="bca98-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="bca98-107">Значения, используемые <xref:System.Drawing.Color.FromArgb%2A> метод представляют альфа, красного, зеленого и синего компонентов цвета.</span><span class="sxs-lookup"><span data-stu-id="bca98-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="bca98-108">Каждое из этих значений должен быть в диапазоне от 0 до 255.</span><span class="sxs-lookup"><span data-stu-id="bca98-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="bca98-109">Первое число 255 означает, что цвет — полностью непрозрачный и второй 255 указывает, что красный компонент является полная насыщенность.</span><span class="sxs-lookup"><span data-stu-id="bca98-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="bca98-110">Два нуля означает, что зеленый и синий компоненты равна 0.</span><span class="sxs-lookup"><span data-stu-id="bca98-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="bca98-111">Четыре цифры (0, 0, 100, 60), передаваемый <xref:System.Drawing.Graphics.FillEllipse%2A> метод укажите расположение и размер прямоугольника, ограничивающего эллипса.</span><span class="sxs-lookup"><span data-stu-id="bca98-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="bca98-112">Прямоугольник имеет в левом верхнем углу (0, 0), шириной 100, а высота — 60.</span><span class="sxs-lookup"><span data-stu-id="bca98-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bca98-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bca98-113">Compiling the Code</span></span>  
 <span data-ttu-id="bca98-114">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="bca98-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca98-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bca98-115">See also</span></span>

- [<span data-ttu-id="bca98-116">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="bca98-116">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
