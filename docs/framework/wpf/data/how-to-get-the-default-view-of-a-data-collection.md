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
ms.openlocfilehash: 746331e69ee1e5eee795a0e35202f4889b72c53f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931530"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="5de89-102">Практическое руководство. Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="5de89-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="5de89-103">Представления позволяют просматривать по-разному в зависимости от сортировки, фильтрации и группировки условий же коллекцию данных.</span><span class="sxs-lookup"><span data-stu-id="5de89-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="5de89-104">Каждая коллекция имеет одно общее представление по умолчанию, который используется в качестве фактического источника привязки, если привязка задает коллекцию в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="5de89-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="5de89-105">В этом примере показано, как получение представления по умолчанию для коллекции.</span><span class="sxs-lookup"><span data-stu-id="5de89-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5de89-106">Пример</span><span class="sxs-lookup"><span data-stu-id="5de89-106">Example</span></span>  
 <span data-ttu-id="5de89-107">Чтобы создать представление, требуется ссылка на объект в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="5de89-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="5de89-108">Этот объект данных можно получить, ссылаясь на собственный объект кода, получив контекст данных свойства источника данных или путем получения свойства привязки.</span><span class="sxs-lookup"><span data-stu-id="5de89-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="5de89-109">В этом примере показано, как получить <xref:System.Windows.FrameworkElement.DataContext%2A> объект данных и используйте его для непосредственного получения коллекции по умолчанию просмотра для данной коллекции.</span><span class="sxs-lookup"><span data-stu-id="5de89-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="5de89-110">В этом примере корневым элементом является <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="5de89-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="5de89-111"><xref:System.Windows.FrameworkElement.DataContext%2A> Присваивается *myDataSource*, который ссылается на поставщик данных, который является <xref:System.Collections.ObjectModel.ObservableCollection%601> из *порядок* объектов.</span><span class="sxs-lookup"><span data-stu-id="5de89-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="5de89-112">Кроме того, можно создать экземпляр и привязка к собственные представления коллекции с помощью <xref:System.Windows.Data.CollectionViewSource> класса.</span><span class="sxs-lookup"><span data-stu-id="5de89-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="5de89-113">Данное представление коллекции совместно используется только элементами управления, которые привязаны к нему напрямую.</span><span class="sxs-lookup"><span data-stu-id="5de89-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="5de89-114">Пример, см. в разделе для создания представления статьи [Общие сведения о привязке данных](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5de89-114">For an example, see the How to Create a View section in the [Data Binding Overview](data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="5de89-115">Примеры функциональных возможностях, предоставляемых представлением коллекции, см. в разделе [сортировка данных в представлении](how-to-sort-data-in-a-view.md), [данные фильтра в представлении](how-to-filter-data-in-a-view.md), и [перемещение по объектам в Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="5de89-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](how-to-sort-data-in-a-view.md), [Filter Data in a View](how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de89-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5de89-116">See also</span></span>

- [<span data-ttu-id="5de89-117">Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="5de89-117">Sort and Group Data Using a View in XAML</span></span>](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [<span data-ttu-id="5de89-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="5de89-118">How-to Topics</span></span>](data-binding-how-to-topics.md)
