---
title: Практическое руководство. Перечисление содержимого изображения визуального элемента
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108008"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="2c7a4-102">Практическое руководство. Перечисление содержимого изображения визуального элемента</span><span class="sxs-lookup"><span data-stu-id="2c7a4-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="2c7a4-103"><xref:System.Windows.Media.Drawing> Объекта предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="2c7a4-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c7a4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2c7a4-104">Example</span></span>  
 <span data-ttu-id="2c7a4-105">В следующем примере метод <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> используется для извлечения значения <xref:System.Windows.Media.DrawingGroup> из <xref:System.Windows.Media.Visual> и перечисления содержимого группы.</span><span class="sxs-lookup"><span data-stu-id="2c7a4-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c7a4-106">При перечислении содержимого визуального элемента извлекаются объекты <xref:System.Windows.Media.Drawing>, а не базовое представление данных отрисовки в виде списка инструкций векторной графики.</span><span class="sxs-lookup"><span data-stu-id="2c7a4-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="2c7a4-107">Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](wpf-graphics-rendering-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c7a4-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="2c7a4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="2c7a4-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="2c7a4-109">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="2c7a4-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="2c7a4-110">Общие сведения об отрисовке графики в WPF</span><span class="sxs-lookup"><span data-stu-id="2c7a4-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
