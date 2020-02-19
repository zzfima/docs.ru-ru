---
title: Практическое руководство. Фильтрация данных в представлении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: f15bcfd1e3c4175f8b4b97244f120d5edbdec9b8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453082"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="72e53-102">Практическое руководство. Фильтрация данных в представлении</span><span class="sxs-lookup"><span data-stu-id="72e53-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="72e53-103">В этом примере показано, как фильтровать данные в представлении.</span><span class="sxs-lookup"><span data-stu-id="72e53-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72e53-104">Пример</span><span class="sxs-lookup"><span data-stu-id="72e53-104">Example</span></span>  
 <span data-ttu-id="72e53-105">Чтобы создать фильтр, определите метод, который предоставляет логику фильтрации.</span><span class="sxs-lookup"><span data-stu-id="72e53-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="72e53-106">Метод используется в качестве обратного вызова и принимает параметр типа `object`.</span><span class="sxs-lookup"><span data-stu-id="72e53-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="72e53-107">Следующий метод возвращает все объекты `Order` со свойством `filled`, для которого задано значение "нет", отфильтровывая остальные объекты.</span><span class="sxs-lookup"><span data-stu-id="72e53-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="72e53-108">Затем можно применить фильтр, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="72e53-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="72e53-109">В этом примере `myCollectionView` является объектом <xref:System.Windows.Data.ListCollectionView>.</span><span class="sxs-lookup"><span data-stu-id="72e53-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="72e53-110">Чтобы отменить фильтрацию, можно задать для свойства <xref:System.Windows.Data.CollectionView.Filter%2A> значение `null`.</span><span class="sxs-lookup"><span data-stu-id="72e53-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="72e53-111">Сведения о создании или получении представления см. [в разделе Получение представления по умолчанию для коллекции данных](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="72e53-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="72e53-112">Полный пример см. в разделе [Сортировка и фильтрация элементов в образце представления](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span><span class="sxs-lookup"><span data-stu-id="72e53-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span></span>  
  
 <span data-ttu-id="72e53-113">Если объект представления поступает из <xref:System.Windows.Data.CollectionViewSource> объекта, логику фильтрации необходимо задать с помощью обработчика событий для события <xref:System.Windows.Data.CollectionViewSource.Filter>.</span><span class="sxs-lookup"><span data-stu-id="72e53-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="72e53-114">В следующем примере `listingDataView` является экземпляром <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="72e53-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="72e53-115">Ниже показана реализация примера обработчика событий фильтра `ShowOnlyBargainsFilter`.</span><span class="sxs-lookup"><span data-stu-id="72e53-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="72e53-116">Этот обработчик событий использует свойство <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> для фильтрации `AuctionItem` объектов, имеющих `CurrentPrice` $25 или более.</span><span class="sxs-lookup"><span data-stu-id="72e53-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="72e53-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72e53-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="72e53-118">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="72e53-118">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="72e53-119">Сортировка данных в представлении</span><span class="sxs-lookup"><span data-stu-id="72e53-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="72e53-120">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="72e53-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
