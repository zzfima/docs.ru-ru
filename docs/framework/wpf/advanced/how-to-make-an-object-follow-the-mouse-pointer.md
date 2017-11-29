---
title: "Практическое руководство. Создание объекта, следующего за указателем мыши"
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
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1991d2a4b43c679fe7e30f633742e01e281e19b3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="72542-102">Практическое руководство. Создание объекта, следующего за указателем мыши</span><span class="sxs-lookup"><span data-stu-id="72542-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="72542-103">В этом примере показано, как изменить размеры объекта, когда указатель мыши перемещается на экране.</span><span class="sxs-lookup"><span data-stu-id="72542-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="72542-104">Пример включает [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, который создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] и файл кода, который создает обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="72542-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72542-105">Пример</span><span class="sxs-lookup"><span data-stu-id="72542-105">Example</span></span>  
 <span data-ttu-id="72542-106">Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который состоит из <xref:System.Windows.Shapes.Ellipse> внутри <xref:System.Windows.Controls.StackPanel>и присоединяет обработчик событий для <xref:System.Windows.UIElement.MouseMove> события.</span><span class="sxs-lookup"><span data-stu-id="72542-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="72542-107">Следующий код создает <xref:System.Windows.UIElement.MouseMove> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="72542-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="72542-108">При перемещении указателя мыши, высоту и ширину <xref:System.Windows.Shapes.Ellipse> увеличивается и уменьшается.</span><span class="sxs-lookup"><span data-stu-id="72542-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="72542-109">См. также</span><span class="sxs-lookup"><span data-stu-id="72542-109">See Also</span></span>  
 [<span data-ttu-id="72542-110">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="72542-110">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)
