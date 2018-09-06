---
title: Практическое руководство. Создание пользовательского режима представления для ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799714"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a><span data-ttu-id="6f96c-102">Практическое руководство. Создание пользовательского режима представления для ListView</span><span class="sxs-lookup"><span data-stu-id="6f96c-102">How to: Create a Custom View Mode for a ListView</span></span>
<span data-ttu-id="6f96c-103">В этом примере показано, как можно создавать пользовательские <xref:System.Windows.Controls.ListView.View%2A> режим для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6f96c-103">This example shows how to create a custom <xref:System.Windows.Controls.ListView.View%2A> mode for a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f96c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="6f96c-104">Example</span></span>  
 <span data-ttu-id="6f96c-105">Необходимо использовать <xref:System.Windows.Controls.ViewBase> класса при создании настраиваемого представления для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6f96c-105">You must use the <xref:System.Windows.Controls.ViewBase> class when you create a custom view for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="6f96c-106">В следующем примере показан режим представления, который называется `PlainView`, который является производным от <xref:System.Windows.Controls.ViewBase> класса.</span><span class="sxs-lookup"><span data-stu-id="6f96c-106">The following example shows a view mode that is called `PlainView`, which is derived from the <xref:System.Windows.Controls.ViewBase> class.</span></span>  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 <span data-ttu-id="6f96c-107">Чтобы применить стиль к пользовательскому представлению, используйте <xref:System.Windows.Style> класса.</span><span class="sxs-lookup"><span data-stu-id="6f96c-107">To apply a style to the custom view, use the <xref:System.Windows.Style> class.</span></span> <span data-ttu-id="6f96c-108">В следующем примере определяется <xref:System.Windows.Style> для `PlainView` режим просмотра.</span><span class="sxs-lookup"><span data-stu-id="6f96c-108">The following example defines a <xref:System.Windows.Style> for the `PlainView` view mode.</span></span> <span data-ttu-id="6f96c-109">В предыдущем примере, этот стиль имеет значение для параметра <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> свойство, которое определено для `PlainView`.</span><span class="sxs-lookup"><span data-stu-id="6f96c-109">In the previous example, this style is set as the value of the <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> property that is defined for `PlainView`.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 <span data-ttu-id="6f96c-110">Чтобы определить структуру данных в режиме представления, определите <xref:System.Windows.DataTemplate> объекта.</span><span class="sxs-lookup"><span data-stu-id="6f96c-110">To define the layout of data in a custom view mode, define a <xref:System.Windows.DataTemplate> object.</span></span> <span data-ttu-id="6f96c-111">В следующем примере определяется <xref:System.Windows.DataTemplate> , можно использовать для отображения данных в `PlainView` режим просмотра.</span><span class="sxs-lookup"><span data-stu-id="6f96c-111">The following example defines a <xref:System.Windows.DataTemplate> that can be used to display data in the `PlainView` view mode.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 <span data-ttu-id="6f96c-112">В следующем примере показано определение <xref:System.Windows.ResourceKey> для `PlainView` режим просмотра, который использует <xref:System.Windows.DataTemplate> , определенный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="6f96c-112">The following example shows how to define a <xref:System.Windows.ResourceKey> for the `PlainView` view mode that uses the <xref:System.Windows.DataTemplate> that is defined in the previous example.</span></span>  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 <span data-ttu-id="6f96c-113">Объект <xref:System.Windows.Controls.ListView> управления можно использовать представления, если задать <xref:System.Windows.Controls.ListView.View%2A> значение ключа ресурса.</span><span class="sxs-lookup"><span data-stu-id="6f96c-113">A <xref:System.Windows.Controls.ListView> control can use a custom view if you set the <xref:System.Windows.Controls.ListView.View%2A> property to the resource key.</span></span> <span data-ttu-id="6f96c-114">В следующем примере показано, как указать `PlainView` в качестве режима представления для <xref:System.Windows.Controls.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6f96c-114">The following example shows how to specify `PlainView` as the view mode for a <xref:System.Windows.Controls.ListView>.</span></span>  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 <span data-ttu-id="6f96c-115">Полный пример см. в разделе [ListView пример представления](https://go.microsoft.com/fwlink/?LinkID=160013).</span><span class="sxs-lookup"><span data-stu-id="6f96c-115">For the complete sample, see [ListView with Multiple Views Sample](https://go.microsoft.com/fwlink/?LinkID=160013).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f96c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f96c-116">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="6f96c-117">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="6f96c-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="6f96c-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="6f96c-118">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="6f96c-119">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="6f96c-119">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
