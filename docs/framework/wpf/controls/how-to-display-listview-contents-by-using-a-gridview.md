---
title: Практическое руководство. Отображение содержимого ListView с помощью GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 103a439b9cee959d0077e5a759364eb9b943905d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554055"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="d7237-102">Практическое руководство. Отображение содержимого ListView с помощью GridView</span><span class="sxs-lookup"><span data-stu-id="d7237-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="d7237-103">В этом примере показан способ определения <xref:System.Windows.Controls.GridView> режим просмотра для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7237-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7237-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d7237-104">Example</span></span>  
 <span data-ttu-id="d7237-105">Можно определить режим просмотра для <xref:System.Windows.Controls.GridView> , указав <xref:System.Windows.Controls.GridViewColumn> объектов.</span><span class="sxs-lookup"><span data-stu-id="d7237-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="d7237-106">В следующем примере показан способ определения <xref:System.Windows.Controls.GridViewColumn> объектов, которые привязаны к содержимому данных, указанный для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7237-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="d7237-107">Это <xref:System.Windows.Controls.GridView> примере задаются три <xref:System.Windows.Controls.GridViewColumn> объектов, которые сопоставляются `FirstName`, `LastName`, и `EmployeeNumber` поля `EmployeeInfoDataSource` задан в качестве <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> из <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d7237-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="d7237-108">Ниже показано, как выглядит в этом примере.</span><span class="sxs-lookup"><span data-stu-id="d7237-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="d7237-109">![ListView с выходными данными GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="d7237-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7237-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d7237-110">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="d7237-111">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="d7237-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="d7237-112">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="d7237-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="d7237-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="d7237-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
