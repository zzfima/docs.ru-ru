---
title: Практическое руководство. Создание отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 716adff5c5c41e6601e384b6669516cb6ba1041d
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332498"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="0c586-102">Практическое руководство. Создание отражения</span><span class="sxs-lookup"><span data-stu-id="0c586-102">How to: Create a Reflection</span></span>
<span data-ttu-id="0c586-103">В этом примере показано, как использовать <xref:System.Windows.Media.VisualBrush> для создания отражения.</span><span class="sxs-lookup"><span data-stu-id="0c586-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="0c586-104">Так как <xref:System.Windows.Media.VisualBrush> можно отображать существующие визуальные, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.</span><span class="sxs-lookup"><span data-stu-id="0c586-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c586-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0c586-105">Example</span></span>  
 <span data-ttu-id="0c586-106">В следующем примере используется <xref:System.Windows.Media.VisualBrush> для создания отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="0c586-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="0c586-107">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="0c586-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0c586-108">![Объект отражены визуальный объект](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="0c586-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="0c586-109">Отраженный объект Visual</span><span class="sxs-lookup"><span data-stu-id="0c586-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="0c586-110">Полный образец, который включает примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [пример VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="0c586-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c586-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0c586-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="0c586-112">Заливка с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="0c586-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
