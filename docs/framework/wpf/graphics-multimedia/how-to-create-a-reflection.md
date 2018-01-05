---
title: "Практическое руководство. Создание отражения"
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
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 157bc01e23c304531f04b0a1cc7a66bad4bb3934
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="b6fc4-102">Практическое руководство. Создание отражения</span><span class="sxs-lookup"><span data-stu-id="b6fc4-102">How to: Create a Reflection</span></span>
<span data-ttu-id="b6fc4-103">В этом примере показано, как использовать <xref:System.Windows.Media.VisualBrush> будет создано отражение.</span><span class="sxs-lookup"><span data-stu-id="b6fc4-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="b6fc4-104">Поскольку <xref:System.Windows.Media.VisualBrush> может отображать существующие визуальные, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.</span><span class="sxs-lookup"><span data-stu-id="b6fc4-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6fc4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b6fc4-105">Example</span></span>  
 <span data-ttu-id="b6fc4-106">В следующем примере используется <xref:System.Windows.Media.VisualBrush> создание отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов.</span><span class="sxs-lookup"><span data-stu-id="b6fc4-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="b6fc4-107">На следующей иллюстрации показан результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="b6fc4-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="b6fc4-108">![Объект отражены визуального объекта](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="b6fc4-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="b6fc4-109">Отраженный объект Visual</span><span class="sxs-lookup"><span data-stu-id="b6fc4-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="b6fc4-110">Полный пример включает примеры, демонстрирующие создание отражения и увеличения части экрана, в разделе [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="b6fc4-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6fc4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b6fc4-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="b6fc4-112">Заливка с помощью объектов Image, Drawing и Visual</span><span class="sxs-lookup"><span data-stu-id="b6fc4-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
