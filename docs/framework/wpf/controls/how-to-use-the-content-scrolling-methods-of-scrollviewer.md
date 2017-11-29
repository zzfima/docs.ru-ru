---
title: "Практическое руководство. Использование методов прокрутки содержимого ScrollViewer"
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
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc9b79ae9b8078bbdc4c41fb0c952237f86fcac8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Практическое руководство. Использование методов прокрутки содержимого ScrollViewer
В этом примере показано использование методов прокрутки <xref:System.Windows.Controls.ScrollViewer> элемента. Эти методы предоставляют добавочное прокрутку содержимого по строкам или по странице, в <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается <xref:System.Windows.Controls.ScrollViewer> с именем `sv1`, который содержит дочерний <xref:System.Windows.Controls.TextBlock> элемента. Поскольку <xref:System.Windows.Controls.TextBlock> больше, чем родительский <xref:System.Windows.Controls.ScrollViewer>, полосы прокрутки отображается полоса прокрутки. <xref:System.Windows.Controls.Button>элементы, представляющие различные методы прокрутки закреплены в левой части в отдельном <xref:System.Windows.Controls.StackPanel>. Каждый <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла вызывает связанный пользовательский метод, который управляет поведением прокрутки в <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 В следующем примере используется <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> и <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> методы.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
