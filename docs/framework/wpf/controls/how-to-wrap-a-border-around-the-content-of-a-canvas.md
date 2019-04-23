---
title: Практическое руководство. Расположение границы вокруг содержимого холста
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Canvas
- controls [WPF], Border
- Canvas control [WPF], wrapping with Border
- Border control [WPF], wrapping Canvas
ms.assetid: caf0404f-f4e7-484f-9928-5dae1238d8ef
ms.openlocfilehash: 5d33af798d2e626cea08fa71c9b2c88acb22b5e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137101"
---
# <a name="how-to-wrap-a-border-around-the-content-of-a-canvas"></a><span data-ttu-id="a6236-102">Практическое руководство. Расположение границы вокруг содержимого холста</span><span class="sxs-lookup"><span data-stu-id="a6236-102">How to: Wrap a Border Around the Content of a Canvas</span></span>
<span data-ttu-id="a6236-103">В этом примере показано, как программы-оболочки для <xref:System.Windows.Controls.Canvas> элемент с <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a6236-103">This example shows how to wrap a <xref:System.Windows.Controls.Canvas> element with a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6236-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a6236-104">Example</span></span>  
 <span data-ttu-id="a6236-105">В следующем примере показано, как отобразить `Hello World!` внутри <xref:System.Windows.Controls.Canvas> элемент.</span><span class="sxs-lookup"><span data-stu-id="a6236-105">The following example shows how to display `Hello World!` inside a <xref:System.Windows.Controls.Canvas> element.</span></span> <span data-ttu-id="a6236-106"><xref:System.Windows.Controls.Canvas> Элемент помещается в оболочку <xref:System.Windows.Controls.Border> элемент таким образом, чтобы граница выделяет элемент.</span><span class="sxs-lookup"><span data-stu-id="a6236-106">The <xref:System.Windows.Controls.Canvas> element is wrapped by a <xref:System.Windows.Controls.Border> element so that a border outlines the element.</span></span>  
  
 [!code-xaml[CanvasHelloWorldBorder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasHelloWorldBorder/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a6236-107">См. также</span><span class="sxs-lookup"><span data-stu-id="a6236-107">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Border>
- [<span data-ttu-id="a6236-108">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="a6236-108">Panels Overview</span></span>](panels-overview.md)
