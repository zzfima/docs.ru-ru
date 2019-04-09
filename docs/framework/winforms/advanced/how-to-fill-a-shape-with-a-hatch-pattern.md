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
ms.openlocfilehash: f5399c4151b335090f4b93be041375b8c2781afa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118122"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="32559-102">Практическое руководство. Штриховая заливка фигуры</span><span class="sxs-lookup"><span data-stu-id="32559-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="32559-103">Шаблон штриховки осуществляется из двух цветов: один для фона и один для строк, которые образуют узор на фоне.</span><span class="sxs-lookup"><span data-stu-id="32559-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="32559-104">Для заполнения замкнутой фигуры, штриховая, использовать <xref:System.Drawing.Drawing2D.HatchBrush> объекта.</span><span class="sxs-lookup"><span data-stu-id="32559-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="32559-105">Следующий пример демонстрирует Штриховая заливка эллипса:</span><span class="sxs-lookup"><span data-stu-id="32559-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="32559-106">Пример</span><span class="sxs-lookup"><span data-stu-id="32559-106">Example</span></span>  
 <span data-ttu-id="32559-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Конструктор принимает три аргумента: стиль штриховки, цвет штриховой линии и цвет фона.</span><span class="sxs-lookup"><span data-stu-id="32559-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="32559-108">Стиль штриховки может быть любое значение от <xref:System.Drawing.Drawing2D.HatchStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="32559-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="32559-109">Существует более пятидесяти элементов в <xref:System.Drawing.Drawing2D.HatchStyle> перечисления; часть из них элементы показаны в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="32559-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="32559-110">На следующем рисунке заполненного эллипса.</span><span class="sxs-lookup"><span data-stu-id="32559-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="32559-111">![Шаблон штриховки](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="32559-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32559-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="32559-112">Compiling the Code</span></span>  
 <span data-ttu-id="32559-113">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs>`e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="32559-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32559-114">См. также</span><span class="sxs-lookup"><span data-stu-id="32559-114">See also</span></span>

- [<span data-ttu-id="32559-115">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="32559-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
