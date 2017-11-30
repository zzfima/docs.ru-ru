---
title: "Практическое руководство. Анимация EllipseGeometry"
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
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 948aa340436b51b6e8cbb09f4b0791535ca5ecd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="12f74-102">Практическое руководство. Анимация EllipseGeometry</span><span class="sxs-lookup"><span data-stu-id="12f74-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="12f74-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.Geometry> в <xref:System.Windows.Shapes.Path> элемент.</span><span class="sxs-lookup"><span data-stu-id="12f74-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="12f74-104">В следующем примере <xref:System.Windows.Media.Animation.PointAnimation> используется для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> из <xref:System.Windows.Media.EllipseGeometry>.</span><span class="sxs-lookup"><span data-stu-id="12f74-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12f74-105">Пример</span><span class="sxs-lookup"><span data-stu-id="12f74-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="12f74-106">См. также</span><span class="sxs-lookup"><span data-stu-id="12f74-106">See Also</span></span>  
 [<span data-ttu-id="12f74-107">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="12f74-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="12f74-108">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="12f74-108">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
