---
title: Практическое руководство. Применение триггеров для определения стиля выбранных элементов в ListView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: 1741ce84fab1639409a7c834845573239c51cc35
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="49fd6-102">Практическое руководство. Применение триггеров для определения стиля выбранных элементов в ListView</span><span class="sxs-lookup"><span data-stu-id="49fd6-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="49fd6-103">В этом примере показан способ определения <xref:System.Windows.Style.Triggers%2A> для <xref:System.Windows.Controls.ListViewItem> управления, чтобы при изменении значения свойства из <xref:System.Windows.Controls.ListViewItem> изменений, <xref:System.Windows.Style> из <xref:System.Windows.Controls.ListViewItem> изменениях в ответ.</span><span class="sxs-lookup"><span data-stu-id="49fd6-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49fd6-104">Пример</span><span class="sxs-lookup"><span data-stu-id="49fd6-104">Example</span></span>  
 <span data-ttu-id="49fd6-105">Если вы хотите <xref:System.Windows.Style> из <xref:System.Windows.Controls.ListViewItem> для изменения в ответ на изменения свойств, определите <xref:System.Windows.Style.Triggers%2A> для <xref:System.Windows.Style> изменения.</span><span class="sxs-lookup"><span data-stu-id="49fd6-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="49fd6-106">В следующем примере определяется <xref:System.Windows.Trigger> , которая устанавливает <xref:System.Windows.Controls.Control.Foreground%2A> свойства <xref:System.Windows.Media.Brushes.Blue%2A> и изменяет <xref:System.Windows.FrameworkElement.Cursor%2A> для отображения <xref:System.Windows.Input.CursorType.Hand> при <xref:System.Windows.UIElement.IsMouseOver%2A> изменения свойств `true`.</span><span class="sxs-lookup"><span data-stu-id="49fd6-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="49fd6-107">В следующем примере определяется <xref:System.Windows.MultiTrigger> , которая устанавливает <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.ListViewItem> для <xref:System.Windows.Media.Brushes.Yellow%2A> при <xref:System.Windows.Controls.ListViewItem> выбранного элемента и имеет фокус клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="49fd6-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="49fd6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="49fd6-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="49fd6-109">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="49fd6-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="49fd6-110">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="49fd6-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="49fd6-111">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="49fd6-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
