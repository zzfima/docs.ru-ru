---
title: Практическое руководство. Сортировка данных в представлении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 32f73d3c3ba213778654f0d1ee7bbae16b9d845b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020729"
---
# <a name="how-to-sort-data-in-a-view"></a><span data-ttu-id="7ff7f-102">Практическое руководство. Сортировка данных в представлении</span><span class="sxs-lookup"><span data-stu-id="7ff7f-102">How to: Sort Data in a View</span></span>
<span data-ttu-id="7ff7f-103">В этом примере описывается порядок сортировки данных в представлении.</span><span class="sxs-lookup"><span data-stu-id="7ff7f-103">This example describes how to sort data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ff7f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7ff7f-104">Example</span></span>  
 <span data-ttu-id="7ff7f-105">В следующем примере создается простой <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Button>:</span><span class="sxs-lookup"><span data-stu-id="7ff7f-105">The following example creates a simple <xref:System.Windows.Controls.ListBox> and a <xref:System.Windows.Controls.Button>:</span></span>  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <span data-ttu-id="7ff7f-106"><xref:System.Windows.Controls.Primitives.ButtonBase.Click> Обработчик событий кнопки содержит логику для сортировки элементов в <xref:System.Windows.Controls.ListBox> в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="7ff7f-106">The <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler of the button contains logic to sort the items in the <xref:System.Windows.Controls.ListBox> in the descending order.</span></span> <span data-ttu-id="7ff7f-107">Это можно сделать, так как добавление элементов в <xref:System.Windows.Controls.ListBox> таким образом они добавляются в <xref:System.Windows.Controls.ItemCollection> из <xref:System.Windows.Controls.ListBox>, и <xref:System.Windows.Controls.ItemCollection> является производным от <xref:System.Windows.Data.CollectionView> класса.</span><span class="sxs-lookup"><span data-stu-id="7ff7f-107">You can do this because adding items to a <xref:System.Windows.Controls.ListBox> this way adds them to the <xref:System.Windows.Controls.ItemCollection> of the <xref:System.Windows.Controls.ListBox>, and <xref:System.Windows.Controls.ItemCollection> derives from the <xref:System.Windows.Data.CollectionView> class.</span></span> <span data-ttu-id="7ff7f-108">При связывании вашей <xref:System.Windows.Controls.ListBox> в коллекции с помощью <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство, можно использовать ту же методику для сортировки.</span><span class="sxs-lookup"><span data-stu-id="7ff7f-108">If you are binding your <xref:System.Windows.Controls.ListBox> to a collection using the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property, you can use the same technique to sort.</span></span>  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 <span data-ttu-id="7ff7f-109">До тех пор, пока у вас есть ссылку на объект представления, можно использовать ту же методику для сортировки содержимого других представлений коллекции.</span><span class="sxs-lookup"><span data-stu-id="7ff7f-109">As long as you have a reference to the view object, you can use the same technique to sort the content of other collection views.</span></span> <span data-ttu-id="7ff7f-110">Пример получения представления, см. в разделе [получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="7ff7f-110">For an example of how to obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="7ff7f-111">Еще один пример см. в разделе [сортировки GridView столбца при нажатии на заголовок](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span><span class="sxs-lookup"><span data-stu-id="7ff7f-111">For another example, see [Sort a GridView Column When a Header Is Clicked](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).</span></span> <span data-ttu-id="7ff7f-112">Дополнительные сведения о представлениях см [Общие сведения о привязке данных](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ff7f-112">For more information about views, see Binding to Collections in [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="7ff7f-113">Например, как применить логику сортировки в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], см. в разделе [сортировки и группы данных с помощью представления в XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="7ff7f-113">For an example of how to apply sorting logic in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], see [Sort and Group Data Using a View in XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff7f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ff7f-114">See also</span></span>

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [<span data-ttu-id="7ff7f-115">Сортировка столбцов GridView при нажатии на заголовок</span><span class="sxs-lookup"><span data-stu-id="7ff7f-115">Sort a GridView Column When a Header Is Clicked</span></span>](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [<span data-ttu-id="7ff7f-116">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="7ff7f-116">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="7ff7f-117">Фильтрация данных в представлении</span><span class="sxs-lookup"><span data-stu-id="7ff7f-117">Filter Data in a View</span></span>](how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="7ff7f-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="7ff7f-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
