---
title: Как выполнить Использование методов прокрутки содержимого ScrollViewer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: 0f2ed1c0ac0d29a47ab98e0329ff161fd54daba6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547044"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="c511d-102">Как выполнить Использование методов прокрутки содержимого ScrollViewer</span><span class="sxs-lookup"><span data-stu-id="c511d-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="c511d-103">В этом примере показано использование методов прокрутки <xref:System.Windows.Controls.ScrollViewer> элемент.</span><span class="sxs-lookup"><span data-stu-id="c511d-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="c511d-104">Эти методы предоставляют добавочные прокрутку содержимого строки или страницы, в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="c511d-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c511d-105">Пример</span><span class="sxs-lookup"><span data-stu-id="c511d-105">Example</span></span>  
 <span data-ttu-id="c511d-106">В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> с именем `sv1`, который содержит дочерний <xref:System.Windows.Controls.TextBlock> элемент.</span><span class="sxs-lookup"><span data-stu-id="c511d-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="c511d-107">Так как <xref:System.Windows.Controls.TextBlock> больше, чем у родительского объекта <xref:System.Windows.Controls.ScrollViewer>, появляются полосы прокрутки, чтобы включить прокрутку.</span><span class="sxs-lookup"><span data-stu-id="c511d-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="c511d-108"><xref:System.Windows.Controls.Button> элементы, представляющие различные методы прокрутки закрепляются в левой части в отдельном <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="c511d-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="c511d-109">Каждый <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл вызывает связанный пользовательский метод, который управляет поведением прокрутки в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="c511d-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="c511d-110">В следующем примере используется <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> и <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="c511d-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c511d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c511d-111">See also</span></span>
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
