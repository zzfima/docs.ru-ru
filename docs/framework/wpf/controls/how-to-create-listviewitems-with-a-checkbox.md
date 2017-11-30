---
title: "Практическое руководство. Создание ListViewItems с CheckBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="099f7-102">Практическое руководство. Создание ListViewItems с CheckBox</span><span class="sxs-lookup"><span data-stu-id="099f7-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="099f7-103">В этом примере показано, как отобразить столбец <xref:System.Windows.Controls.CheckBox> элементы управления в <xref:System.Windows.Controls.ListView> элемент управления, использующий <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="099f7-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="099f7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="099f7-104">Example</span></span>  
 <span data-ttu-id="099f7-105">Чтобы создать столбец, содержащий <xref:System.Windows.Controls.CheckBox> элементы управления в <xref:System.Windows.Controls.ListView>, создайте <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="099f7-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="099f7-106">Затем установите <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> из <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="099f7-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="099f7-107">В следующем примере показан <xref:System.Windows.DataTemplate> , содержащий <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="099f7-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="099f7-108">В примере выполняется привязка <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> свойство <xref:System.Windows.Controls.CheckBox> для <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> значение свойства <xref:System.Windows.Controls.ListViewItem> , которая его содержит.</span><span class="sxs-lookup"><span data-stu-id="099f7-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="099f7-109">Таким образом, когда <xref:System.Windows.Controls.ListViewItem> , содержащий <xref:System.Windows.Controls.CheckBox> выбран, <xref:System.Windows.Controls.CheckBox> проверяется.</span><span class="sxs-lookup"><span data-stu-id="099f7-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="099f7-110">В следующем примере показано, как создать столбец <xref:System.Windows.Controls.CheckBox> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="099f7-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="099f7-111">Чтобы сделать столбец, в примере задается <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> свойство <xref:System.Windows.Controls.GridViewColumn> для <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="099f7-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="099f7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="099f7-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="099f7-113">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="099f7-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="099f7-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="099f7-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="099f7-115">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="099f7-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
