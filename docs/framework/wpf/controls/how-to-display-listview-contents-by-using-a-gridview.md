---
title: Как выполнить Отображение содержимого ListView с помощью GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], displaying contents with GridView
- GridView [WPF], displaying ListView contents
ms.assetid: 5bc1e767-ab46-4f14-bd41-3d5d39e1d000
ms.openlocfilehash: 0e2b37cb061cc92b34c3a4f94bcd42e8ffc69ab5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606011"
---
# <a name="how-to-display-listview-contents-by-using-a-gridview"></a><span data-ttu-id="af264-102">Как выполнить Отображение содержимого ListView с помощью GridView</span><span class="sxs-lookup"><span data-stu-id="af264-102">How to: Display ListView Contents by Using a GridView</span></span>
<span data-ttu-id="af264-103">В этом примере показан способ определения <xref:System.Windows.Controls.GridView> режим просмотра для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af264-103">This example shows how to define a <xref:System.Windows.Controls.GridView> view mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af264-104">Пример</span><span class="sxs-lookup"><span data-stu-id="af264-104">Example</span></span>  
 <span data-ttu-id="af264-105">Можно определить режим представления <xref:System.Windows.Controls.GridView> , указав <xref:System.Windows.Controls.GridViewColumn> объектов.</span><span class="sxs-lookup"><span data-stu-id="af264-105">You can define the view mode of a <xref:System.Windows.Controls.GridView> by specifying <xref:System.Windows.Controls.GridViewColumn> objects.</span></span> <span data-ttu-id="af264-106">В следующем примере показано определение <xref:System.Windows.Controls.GridViewColumn> объектов, которые привязаны к содержимому данных, который указан для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af264-106">The following example shows how to define <xref:System.Windows.Controls.GridViewColumn> objects that bind to the data content that is specified for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="af264-107">Это <xref:System.Windows.Controls.GridView> пример указывает три <xref:System.Windows.Controls.GridViewColumn> объектов, сопоставляемых с `FirstName`, `LastName`, и `EmployeeNumber` поля `EmployeeInfoDataSource` , для которой включено как <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> из <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af264-107">This <xref:System.Windows.Controls.GridView> example specifies three <xref:System.Windows.Controls.GridViewColumn> objects that map to the `FirstName`, `LastName`, and `EmployeeNumber` fields of the `EmployeeInfoDataSource` that is set as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> of the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 <span data-ttu-id="af264-108">Ниже показано, как будет выглядеть этот пример.</span><span class="sxs-lookup"><span data-stu-id="af264-108">The following illustration shows how this example appears.</span></span>  
  
 <span data-ttu-id="af264-109">![ListView с выходными данными GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span><span class="sxs-lookup"><span data-stu-id="af264-109">![ListView with GridView output](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af264-110">См. также</span><span class="sxs-lookup"><span data-stu-id="af264-110">See also</span></span>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="af264-111">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="af264-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
- [<span data-ttu-id="af264-112">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="af264-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
- [<span data-ttu-id="af264-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="af264-113">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
