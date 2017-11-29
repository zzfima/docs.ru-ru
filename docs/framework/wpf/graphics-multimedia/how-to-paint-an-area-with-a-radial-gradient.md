---
title: "Практическое руководство. Закраска области с применением радиального градиента"
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
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55b707e4738a77a8fb093071ef6f5105b2200c16
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="8c3eb-102">Практическое руководство. Закраска области с применением радиального градиента</span><span class="sxs-lookup"><span data-stu-id="8c3eb-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="8c3eb-103">В этом примере показано, как использовать <xref:System.Windows.Media.RadialGradientBrush> класса Закраска области с применением радиального градиента.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c3eb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8c3eb-104">Example</span></span>  
 <span data-ttu-id="8c3eb-105">В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> Рисование прямоугольника с применением радиального градиента, изменяющегося от желтого до красного и синего и зеленого.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="8c3eb-106">Ниже показан градиент из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="8c3eb-107">Были выделены градиента.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="8c3eb-108">![Ограничения градиента в радиальном градиенте](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="8c3eb-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c3eb-109">В примерах в этом разделе используется система координат по умолчанию для задания контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="8c3eb-110">Система координат по умолчанию задается относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 — 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="8c3eb-111">Можно изменить эту систему координат, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="8c3eb-112">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="8c3eb-113">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="8c3eb-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="8c3eb-114">Для дополнительных <xref:System.Windows.Media.RadialGradientBrush> примеры см. в разделе [образец кисти](http://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="8c3eb-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="8c3eb-115">Дополнительные сведения о градиенте и других типах кистей см. в разделе [Рисование с сплошные цвета и градиенты Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c3eb-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
