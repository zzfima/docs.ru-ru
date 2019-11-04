---
title: Практическое руководство. Рисование текста на фоне элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424371"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="93032-102">Практическое руководство. Рисование текста на фоне элемента управления</span><span class="sxs-lookup"><span data-stu-id="93032-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="93032-103">Можно нарисовать текст непосредственно на фоне элемента управления, преобразовав текстовую строку в <xref:System.Windows.Media.FormattedText> объект, а затем вырисуя объект в <xref:System.Windows.Media.DrawingContext>элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93032-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="93032-104">Эту методику также можно использовать для рисования в фоновом режиме объектов, производных от <xref:System.Windows.Controls.Panel>, таких как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="93032-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="93032-105">![Снимок экрана элементов управления, отображающих текст как фон.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="93032-105">![Screenshot of controls displaying text as background.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")</span></span>  
<span data-ttu-id="93032-106">Пример элементов управления с фоном из пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="93032-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="93032-107">Пример</span><span class="sxs-lookup"><span data-stu-id="93032-107">Example</span></span>  
 <span data-ttu-id="93032-108">Чтобы нарисовать фон элемента управления, создайте новый объект <xref:System.Windows.Media.DrawingBrush> и нарисуйте преобразованный текст в <xref:System.Windows.Media.DrawingContext>объекта.</span><span class="sxs-lookup"><span data-stu-id="93032-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="93032-109">Затем назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству Background элемента управления.</span><span class="sxs-lookup"><span data-stu-id="93032-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="93032-110">В следующем примере кода показано, как создать объект <xref:System.Windows.Media.FormattedText> и нарисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.</span><span class="sxs-lookup"><span data-stu-id="93032-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="93032-111">См. также</span><span class="sxs-lookup"><span data-stu-id="93032-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="93032-112">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="93032-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
