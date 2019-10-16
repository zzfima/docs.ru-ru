---
title: Практическое руководство. Штриховая заливка фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320054"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="a1877-102">Практическое руководство. Штриховая заливка фигуры</span><span class="sxs-lookup"><span data-stu-id="a1877-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="a1877-103">Шаблон штриховки состоит из двух цветов: один для фона, а другой для линий, образующих шаблон на фоне.</span><span class="sxs-lookup"><span data-stu-id="a1877-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="a1877-104">Для заполнения замкнутой фигуры шаблоном штриховки используйте объект <xref:System.Drawing.Drawing2D.HatchBrush>.</span><span class="sxs-lookup"><span data-stu-id="a1877-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="a1877-105">В следующем примере показано, как заполнить эллипс с помощью шаблона штриховки:</span><span class="sxs-lookup"><span data-stu-id="a1877-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1877-106">Пример</span><span class="sxs-lookup"><span data-stu-id="a1877-106">Example</span></span>  
 <span data-ttu-id="a1877-107">Конструктор <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> принимает три аргумента: стиль штриховки, цвет линии штриховки и цвет фона.</span><span class="sxs-lookup"><span data-stu-id="a1877-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="a1877-108">Аргумент стиля штриховки может быть любым значением перечисления <xref:System.Drawing.Drawing2D.HatchStyle>.</span><span class="sxs-lookup"><span data-stu-id="a1877-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="a1877-109">В перечислении <xref:System.Drawing.Drawing2D.HatchStyle> содержится более 50 элементов; Некоторые из этих элементов показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="a1877-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="a1877-110">На следующем рисунке показан закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="a1877-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="a1877-111">![Снимок экрана, как выглядит эллипс с шаблоном штриховки.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="a1877-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1877-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a1877-112">Compiling the Code</span></span>  
 <span data-ttu-id="a1877-113">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs>`e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="a1877-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1877-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a1877-114">See also</span></span>

- [<span data-ttu-id="a1877-115">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="a1877-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
