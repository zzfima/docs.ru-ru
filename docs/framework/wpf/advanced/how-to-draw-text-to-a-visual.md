---
title: "Практическое руководство. Рисование текста в визуальном элементе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765d2102bc4466c2b194e03c9688212e04005ca2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="b9a44-102">Практическое руководство. Рисование текста в визуальном элементе</span><span class="sxs-lookup"><span data-stu-id="b9a44-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="b9a44-103">В следующем примере показано, как нарисовать текст <xref:System.Windows.Media.DrawingVisual> с помощью <xref:System.Windows.Media.DrawingContext> объекта.</span><span class="sxs-lookup"><span data-stu-id="b9a44-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="b9a44-104">Контекст рисования возвращается путем вызова <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> метод <xref:System.Windows.Media.DrawingVisual> объекта.</span><span class="sxs-lookup"><span data-stu-id="b9a44-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="b9a44-105">Можно нарисовать изображения и текст в контексте рисования.</span><span class="sxs-lookup"><span data-stu-id="b9a44-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="b9a44-106">Чтобы нарисовать текст в контексте рисования, используйте <xref:System.Windows.Media.DrawingContext.DrawText%2A> метод <xref:System.Windows.Media.DrawingContext> объекта.</span><span class="sxs-lookup"><span data-stu-id="b9a44-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="b9a44-107">Когда вы закончите рисование содержимого в контексте рисования, вызовите <xref:System.Windows.Media.DrawingContext.Close%2A> метод, чтобы закрыть контекст рисования и сохранить содержимое.</span><span class="sxs-lookup"><span data-stu-id="b9a44-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9a44-108">Пример</span><span class="sxs-lookup"><span data-stu-id="b9a44-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="b9a44-109">Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).</span><span class="sxs-lookup"><span data-stu-id="b9a44-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](http://go.microsoft.com/fwlink/?LinkID=159994).</span></span>
