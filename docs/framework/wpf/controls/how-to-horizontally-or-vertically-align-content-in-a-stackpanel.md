---
title: "Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали"
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bccf0455c736d14bd77113841603022d4c362787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="5a83b-102">Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали</span><span class="sxs-lookup"><span data-stu-id="5a83b-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="5a83b-103">В этом примере показано, как настроить <xref:System.Windows.Controls.StackPanel.Orientation%2A> содержимого в <xref:System.Windows.Controls.StackPanel> элемент, а также способы настройки <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="5a83b-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a83b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5a83b-104">Example</span></span>  
 <span data-ttu-id="5a83b-105">В следующем примере создается три <xref:System.Windows.Controls.ListBox> элементов в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a83b-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="5a83b-106">Каждый <xref:System.Windows.Controls.ListBox> представляет возможные значения <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="5a83b-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="5a83b-107">Когда пользователь выбирает значение в любом из <xref:System.Windows.Controls.ListBox> элементы, связанные свойства <xref:System.Windows.Controls.StackPanel> и его дочерних <xref:System.Windows.Controls.Button> изменить элементы.</span><span class="sxs-lookup"><span data-stu-id="5a83b-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="5a83b-108">Следующий файл кода определяет изменения на события, связанные с <xref:System.Windows.Controls.ListBox> изменения выделения.</span><span class="sxs-lookup"><span data-stu-id="5a83b-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="5a83b-109"><xref:System.Windows.Controls.StackPanel>определяется <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span><span class="sxs-lookup"><span data-stu-id="5a83b-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5a83b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5a83b-110">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [<span data-ttu-id="5a83b-111">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="5a83b-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
