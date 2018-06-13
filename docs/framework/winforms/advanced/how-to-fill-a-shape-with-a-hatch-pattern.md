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
ms.openlocfilehash: 5b6b5b61b83e5be05999099f2cc6b9e715ca35c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521746"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="31cc5-102">Практическое руководство. Штриховая заливка фигуры</span><span class="sxs-lookup"><span data-stu-id="31cc5-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="31cc5-103">Шаблон штриховки, состоящее из двух цветов: один для фона и один для строк, формирующих шаблон на фоне.</span><span class="sxs-lookup"><span data-stu-id="31cc5-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="31cc5-104">Чтобы залить замкнутую фигуру штриховая, используйте <xref:System.Drawing.Drawing2D.HatchBrush> объекта.</span><span class="sxs-lookup"><span data-stu-id="31cc5-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="31cc5-105">Следующий пример демонстрирует Штриховая заливка эллипса:</span><span class="sxs-lookup"><span data-stu-id="31cc5-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="31cc5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="31cc5-106">Example</span></span>  
 <span data-ttu-id="31cc5-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> Конструктор принимает три аргумента: стиль штриховки, цвет штриховой линии и цвет фона.</span><span class="sxs-lookup"><span data-stu-id="31cc5-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="31cc5-108">Стиль штриховки может иметь любое значение от <xref:System.Drawing.Drawing2D.HatchStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="31cc5-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="31cc5-109">Существует более пятидесяти элементов в <xref:System.Drawing.Drawing2D.HatchStyle> перечисления; некоторые из этих элементов приведены в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="31cc5-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="31cc5-110">На следующем рисунке закрашенный эллипс.</span><span class="sxs-lookup"><span data-stu-id="31cc5-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="31cc5-111">![Шаблон штриховки](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="31cc5-111">![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31cc5-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="31cc5-112">Compiling the Code</span></span>  
 <span data-ttu-id="31cc5-113">Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.Control.Paint> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="31cc5-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cc5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="31cc5-114">See Also</span></span>  
 [<span data-ttu-id="31cc5-115">Использование кисти для заливки фигур</span><span class="sxs-lookup"><span data-stu-id="31cc5-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
