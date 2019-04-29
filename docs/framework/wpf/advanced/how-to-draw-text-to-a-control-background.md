---
title: Практическое руководство. Рисование текста для фона элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 76449c88f9a720741c8ed61255e04a40e6a8613f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776213"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="2964e-102">Практическое руководство. Рисование текста для фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="2964e-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="2964e-103">Можно рисовать текст непосредственно на фоне элемента управления, преобразовав строку текста в <xref:System.Windows.Media.FormattedText> объекта, а затем рисуя объект элемента управления <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="2964e-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2964e-104">Этот метод также можно использовать для рисования на фоне объектов, производных от <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="2964e-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="2964e-105">![Элементы управления, отображающие текст в качестве фона](./media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="2964e-105">![Controls displaying text as background](./media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="2964e-106">Пример элементов управления с фоном из пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="2964e-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="2964e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2964e-107">Example</span></span>  
 <span data-ttu-id="2964e-108">Для рисования фона элемента управления, создайте новый <xref:System.Windows.Media.DrawingBrush> объекта и нарисуйте преобразованный текст объекта <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="2964e-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2964e-109">Затем назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству фона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2964e-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="2964e-110">В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> и рисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.</span><span class="sxs-lookup"><span data-stu-id="2964e-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="2964e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="2964e-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="2964e-112">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="2964e-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
