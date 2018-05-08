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
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Практическое руководство. Выполнение привязки данных к объекту класса InkCanvas
## <a name="example"></a>Пример  
 Ниже приведен пример, как привязать <xref:System.Windows.Controls.InkCanvas.Strokes%2A> свойство <xref:System.Windows.Controls.InkCanvas> в другой <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Ниже приведен пример, как привязать <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства к источнику данных.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 В следующем примере объявляется два <xref:System.Windows.Controls.InkCanvas> объектов в XAML и устанавливается привязка данных между ними и другими источниками данных.  Первый <xref:System.Windows.Controls.InkCanvas>, который называется `ic`, привязанный к двух источников данных.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> И <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства `ic` привязаны к <xref:System.Windows.Controls.ListBox> объекты, которые в свою очередь привязан к массивам, определенным в XAML.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, И <xref:System.Windows.Controls.InkCanvas.Strokes%2A> второго <xref:System.Windows.Controls.InkCanvas> привязаны к первому <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xaml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
