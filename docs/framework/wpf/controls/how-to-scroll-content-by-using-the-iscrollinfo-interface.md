---
title: "Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo"
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
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae6d9439ad76258105d615960bd05ecf458eb613
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo
В этом примере показано, как выполнять прокрутку содержимого с помощью <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейса.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует функции <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейса. В примере создается <xref:System.Windows.Controls.StackPanel> элемент в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , вложенный в родительский элемент <xref:System.Windows.Controls.ScrollViewer>. Дочерние элементы <xref:System.Windows.Controls.StackPanel> можно прокручивать логически с помощью методов, определенных <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейс и приведение к экземпляру <xref:System.Windows.Controls.StackPanel> (`sp1`) в коде.  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Каждый <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла вызывает связанный настраиваемый метод, который управляет поведением прокрутки в <xref:System.Windows.Controls.StackPanel>. В следующем примере показано, как использовать <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> методов; также в целом показано, как использовать все методы позиционирования, <xref:System.Windows.Controls.Primitives.IScrollInfo> класс определяет.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 <xref:System.Windows.Controls.StackPanel>  
 [Общие сведения об элементе управления ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
