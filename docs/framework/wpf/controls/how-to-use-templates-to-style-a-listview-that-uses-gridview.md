---
title: "Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="e6b89-102">Практическое руководство. Использование шаблонов для настройки представления ListView, использующего GridView</span><span class="sxs-lookup"><span data-stu-id="e6b89-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="e6b89-103">В этом примере показано, как использовать <xref:System.Windows.DataTemplate> и <xref:System.Windows.Style> объектов для определения внешнего вида <xref:System.Windows.Controls.ListView> управления, который использует <xref:System.Windows.Controls.GridView> режим просмотра.</span><span class="sxs-lookup"><span data-stu-id="e6b89-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6b89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e6b89-104">Example</span></span>  
 <span data-ttu-id="e6b89-105">В приведенных ниже примерах <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объектов, настроить внешний вид заголовка столбца для <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e6b89-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="e6b89-106">Приведенный ниже показано, как использовать эти <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> объекты для установки <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> свойства <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e6b89-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="e6b89-107"><xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Свойство определяет содержимое ячеек столбца.</span><span class="sxs-lookup"><span data-stu-id="e6b89-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="e6b89-108"><xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> И <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> только два из свойств, которые можно использовать для настройки внешнего вида заголовка столбца для <xref:System.Windows.Controls.GridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e6b89-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="e6b89-109">Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e6b89-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="e6b89-110">В следующем примере показан способ определения <xref:System.Windows.DataTemplate> , настраивает внешний вид ячеек в <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e6b89-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="e6b89-111">В следующем примере показано, как этот метод следует использовать <xref:System.Windows.DataTemplate> для определения содержимого <xref:System.Windows.Controls.GridViewColumn> ячейки.</span><span class="sxs-lookup"><span data-stu-id="e6b89-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="e6b89-112">Этот шаблон используется вместо <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> свойство, которое показано в предыдущем <xref:System.Windows.Controls.GridViewColumn> примере.</span><span class="sxs-lookup"><span data-stu-id="e6b89-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="e6b89-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e6b89-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="e6b89-114">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="e6b89-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="e6b89-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="e6b89-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="e6b89-116">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="e6b89-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
