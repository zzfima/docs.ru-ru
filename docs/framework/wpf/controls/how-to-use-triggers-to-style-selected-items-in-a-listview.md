---
title: "Практическое руководство. Применение триггеров для определения стиля выбранных элементов в ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f8965ee524d6a5cb03a54ac07d8889ff9801440
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="1e70d-102">Практическое руководство. Применение триггеров для определения стиля выбранных элементов в ListView</span><span class="sxs-lookup"><span data-stu-id="1e70d-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="1e70d-103">В этом примере показан способ определения <xref:System.Windows.Style.Triggers%2A> для <xref:System.Windows.Controls.ListViewItem> управления, чтобы при изменении значения свойства из <xref:System.Windows.Controls.ListViewItem> изменений, <xref:System.Windows.Style> из <xref:System.Windows.Controls.ListViewItem> изменениях в ответ.</span><span class="sxs-lookup"><span data-stu-id="1e70d-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e70d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1e70d-104">Example</span></span>  
 <span data-ttu-id="1e70d-105">Если вы хотите <xref:System.Windows.Style> из <xref:System.Windows.Controls.ListViewItem> для изменения в ответ на изменения свойств, определите <xref:System.Windows.Style.Triggers%2A> для <xref:System.Windows.Style> изменения.</span><span class="sxs-lookup"><span data-stu-id="1e70d-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="1e70d-106">В следующем примере определяется <xref:System.Windows.Trigger> , которая устанавливает <xref:System.Windows.Controls.Control.Foreground%2A> свойства <xref:System.Windows.Media.Brushes.Blue%2A> и изменяет <xref:System.Windows.FrameworkElement.Cursor%2A> для отображения <xref:System.Windows.Input.CursorType.Hand> при <xref:System.Windows.UIElement.IsMouseOver%2A> изменения свойств `true`.</span><span class="sxs-lookup"><span data-stu-id="1e70d-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="1e70d-107">В следующем примере определяется <xref:System.Windows.MultiTrigger> , которая устанавливает <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.ListViewItem> для <xref:System.Windows.Media.Brushes.Yellow%2A> при <xref:System.Windows.Controls.ListViewItem> выбранного элемента и имеет фокус клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="1e70d-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="1e70d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1e70d-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="1e70d-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="1e70d-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="1e70d-110">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="1e70d-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="1e70d-111">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="1e70d-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
