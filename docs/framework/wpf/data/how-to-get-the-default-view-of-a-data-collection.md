---
title: Практическое руководство. Получение представления по умолчанию для коллекции данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459128"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="8e073-102">Практическое руководство. Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="8e073-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="8e073-103">Представления позволяют просматривать одну и ту же коллекцию данных различными способами в зависимости от критериев сортировки, фильтрации или группирования.</span><span class="sxs-lookup"><span data-stu-id="8e073-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="8e073-104">Каждая коллекция имеет одно общее представление по умолчанию, которое используется в качестве фактического источника привязки, когда привязка указывает коллекцию в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="8e073-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="8e073-105">В этом примере показано, как получить представление коллекции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e073-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e073-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8e073-106">Example</span></span>  
 <span data-ttu-id="8e073-107">Чтобы создать представление, требуется ссылка на объект коллекции.</span><span class="sxs-lookup"><span data-stu-id="8e073-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="8e073-108">Этот объект данных можно получить, обратившись к собственному объекту кода программной части, получая контекст данных, получая свойство источника данных или получая свойство привязки.</span><span class="sxs-lookup"><span data-stu-id="8e073-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="8e073-109">В этом примере показано, как получить <xref:System.Windows.FrameworkElement.DataContext%2A> объекта данных и использовать его для непосредственного получения представления коллекции по умолчанию для этой коллекции.</span><span class="sxs-lookup"><span data-stu-id="8e073-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="8e073-110">В этом примере корневым элементом является <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="8e073-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="8e073-111">Для <xref:System.Windows.FrameworkElement.DataContext%2A> задано значение *myDataSource*, которое ссылается на поставщик данных, который является <xref:System.Collections.ObjectModel.ObservableCollection%601> объектов *Order* .</span><span class="sxs-lookup"><span data-stu-id="8e073-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="8e073-112">Кроме того, можно создать экземпляр и выполнить привязку к собственному представлению коллекции с помощью класса <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="8e073-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="8e073-113">Это представление коллекции совместно используется только элементами управления, которые привязаны непосредственно к нему.</span><span class="sxs-lookup"><span data-stu-id="8e073-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="8e073-114">Пример см. в разделе Создание представления в статье [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e073-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="8e073-115">Примеры функциональных возможностей, предоставляемых представлением коллекции, см. в разделе [Сортировка данных в](how-to-sort-data-in-a-view.md)представлении, [Фильтрация данных в представлении](how-to-filter-data-in-a-view.md)и [Перемещение по объектам в CollectionView данных](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="8e073-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e073-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8e073-116">See also</span></span>

- [<span data-ttu-id="8e073-117">Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="8e073-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="8e073-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="8e073-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
