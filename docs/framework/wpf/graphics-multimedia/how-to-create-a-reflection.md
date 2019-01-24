---
title: Как выполнить Создание отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 0fae98966481003c7906f5cbb34afaea666d583d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559038"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="0c048-102">Как выполнить Создание отражения</span><span class="sxs-lookup"><span data-stu-id="0c048-102">How to: Create a Reflection</span></span>
<span data-ttu-id="0c048-103">В этом примере показано, как использовать <xref:System.Windows.Media.VisualBrush> для создания отражения.</span><span class="sxs-lookup"><span data-stu-id="0c048-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="0c048-104">Так как <xref:System.Windows.Media.VisualBrush> можно отображать существующие визуальные, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.</span><span class="sxs-lookup"><span data-stu-id="0c048-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c048-105">Пример</span><span class="sxs-lookup"><span data-stu-id="0c048-105">Example</span></span>  
 <span data-ttu-id="0c048-106">В следующем примере используется <xref:System.Windows.Media.VisualBrush> для создания отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="0c048-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="0c048-107">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="0c048-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="0c048-108">![Объект отражены визуальный объект](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="0c048-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="0c048-109">Отраженный объект Visual</span><span class="sxs-lookup"><span data-stu-id="0c048-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="0c048-110">Полный образец, который включает примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [пример VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="0c048-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c048-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0c048-111">See also</span></span>
- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="0c048-112">Заполнение с использованием изображений, рисунков и визуальных элементов</span><span class="sxs-lookup"><span data-stu-id="0c048-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
