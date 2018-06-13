---
title: Практическое руководство. Выполнение привязки данных к объекту класса InkCanvas
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 4081ae7dd6854934804062cfce60d10106c1e1d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543174"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a><span data-ttu-id="2eff5-102">Практическое руководство. Выполнение привязки данных к объекту класса InkCanvas</span><span class="sxs-lookup"><span data-stu-id="2eff5-102">How to: Data Bind to an InkCanvas</span></span>
## <a name="example"></a><span data-ttu-id="2eff5-103">Пример</span><span class="sxs-lookup"><span data-stu-id="2eff5-103">Example</span></span>  
 <span data-ttu-id="2eff5-104">Ниже приведен пример, как привязать <xref:System.Windows.Controls.InkCanvas.Strokes%2A> свойство <xref:System.Windows.Controls.InkCanvas> в другой <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="2eff5-104">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.Strokes%2A> property of an <xref:System.Windows.Controls.InkCanvas> to another <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 <span data-ttu-id="2eff5-105">Ниже приведен пример, как привязать <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="2eff5-105">The following example demonstrates how to bind the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property to a data source.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 <span data-ttu-id="2eff5-106">В следующем примере объявляется два <xref:System.Windows.Controls.InkCanvas> объектов в XAML и устанавливается привязка данных между ними и другими источниками данных.</span><span class="sxs-lookup"><span data-stu-id="2eff5-106">The following example declares two <xref:System.Windows.Controls.InkCanvas> objects in XAML and establishes data binding between them and other data sources.</span></span>  <span data-ttu-id="2eff5-107">Первый <xref:System.Windows.Controls.InkCanvas>, который называется `ic`, привязанный к двух источников данных.</span><span class="sxs-lookup"><span data-stu-id="2eff5-107">The first <xref:System.Windows.Controls.InkCanvas>, called `ic`, is bound to two data sources.</span></span>  <span data-ttu-id="2eff5-108"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A> И <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства `ic` привязаны к <xref:System.Windows.Controls.ListBox> объекты, которые в свою очередь привязан к массивам, определенным в XAML.</span><span class="sxs-lookup"><span data-stu-id="2eff5-108">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> and <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties on `ic` are bound to <xref:System.Windows.Controls.ListBox> objects, which are in turn bound to arrays defined in the XAML.</span></span>  <span data-ttu-id="2eff5-109"><xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, И <xref:System.Windows.Controls.InkCanvas.Strokes%2A> второго <xref:System.Windows.Controls.InkCanvas> привязаны к первому <xref:System.Windows.Controls.InkCanvas>, `ic`.</span><span class="sxs-lookup"><span data-stu-id="2eff5-109">The <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, and <xref:System.Windows.Controls.InkCanvas.Strokes%2A> properties of the second <xref:System.Windows.Controls.InkCanvas> are bound to the first <xref:System.Windows.Controls.InkCanvas>, `ic`.</span></span>  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
