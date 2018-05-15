---
title: Практическое руководство. Расположение границы вокруг содержимого элемента Canvas
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Canvas
- controls [WPF], Border
- Canvas control [WPF], wrapping with Border
- Border control [WPF], wrapping Canvas
ms.assetid: caf0404f-f4e7-484f-9928-5dae1238d8ef
ms.openlocfilehash: 424a8b56f0891a0b3bcab024817566998158f209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-wrap-a-border-around-the-content-of-a-canvas"></a><span data-ttu-id="eeb93-102">Практическое руководство. Расположение границы вокруг содержимого элемента Canvas</span><span class="sxs-lookup"><span data-stu-id="eeb93-102">How to: Wrap a Border Around the Content of a Canvas</span></span>
<span data-ttu-id="eeb93-103">В этом примере показано создание программы-оболочки <xref:System.Windows.Controls.Canvas> элемент с <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="eeb93-103">This example shows how to wrap a <xref:System.Windows.Controls.Canvas> element with a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeb93-104">Пример</span><span class="sxs-lookup"><span data-stu-id="eeb93-104">Example</span></span>  
 <span data-ttu-id="eeb93-105">В следующем примере показано, как отобразить `Hello World!` внутри <xref:System.Windows.Controls.Canvas> элемента.</span><span class="sxs-lookup"><span data-stu-id="eeb93-105">The following example shows how to display `Hello World!` inside a <xref:System.Windows.Controls.Canvas> element.</span></span> <span data-ttu-id="eeb93-106"><xref:System.Windows.Controls.Canvas> Элемент находится в оболочке <xref:System.Windows.Controls.Border> элемент, чтобы граница выделяет элемент.</span><span class="sxs-lookup"><span data-stu-id="eeb93-106">The <xref:System.Windows.Controls.Canvas> element is wrapped by a <xref:System.Windows.Controls.Border> element so that a border outlines the element.</span></span>  
  
 [!code-xaml[CanvasHelloWorldBorder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasHelloWorldBorder/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eeb93-107">См. также</span><span class="sxs-lookup"><span data-stu-id="eeb93-107">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Border>  
 [<span data-ttu-id="eeb93-108">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="eeb93-108">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
