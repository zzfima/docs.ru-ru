---
title: Как выполнить Рисование текста в элемент управления&#39;фона s
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: d580330de5ef3841979fffc61db336064f1643f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740433"
---
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="85c7b-102">Как выполнить Рисование текста в элемент управления&#39;фона s</span><span class="sxs-lookup"><span data-stu-id="85c7b-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="85c7b-103">Можно рисовать текст непосредственно на фоне элемента управления, преобразовав строку текста в <xref:System.Windows.Media.FormattedText> объекта, а затем рисуя объект элемента управления <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="85c7b-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="85c7b-104">Этот метод также можно использовать для рисования на фоне объектов, производных от <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="85c7b-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="85c7b-105">![Элементы управления, отображающие текст в качестве фона](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="85c7b-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="85c7b-106">Пример элементов управления с фоном из пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="85c7b-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="85c7b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="85c7b-107">Example</span></span>  
 <span data-ttu-id="85c7b-108">Для рисования фона элемента управления, создайте новый <xref:System.Windows.Media.DrawingBrush> объекта и нарисуйте преобразованный текст объекта <xref:System.Windows.Media.DrawingContext>.</span><span class="sxs-lookup"><span data-stu-id="85c7b-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="85c7b-109">Затем назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству фона элемента управления.</span><span class="sxs-lookup"><span data-stu-id="85c7b-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="85c7b-110">В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> и рисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.</span><span class="sxs-lookup"><span data-stu-id="85c7b-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="85c7b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="85c7b-111">See also</span></span>
- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="85c7b-112">Рисование форматированного текста</span><span class="sxs-lookup"><span data-stu-id="85c7b-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
