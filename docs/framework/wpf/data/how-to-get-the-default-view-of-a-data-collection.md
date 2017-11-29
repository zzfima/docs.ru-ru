---
title: "Практическое руководство. Получение представления по умолчанию для коллекции данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a><span data-ttu-id="bbb86-102">Практическое руководство. Получение представления по умолчанию для коллекции данных</span><span class="sxs-lookup"><span data-stu-id="bbb86-102">How to: Get the Default View of a Data Collection</span></span>
<span data-ttu-id="bbb86-103">Представления позволяют просматривать различными способами, в зависимости от сортировки, фильтрации и группирования критерии одну коллекцию данных.</span><span class="sxs-lookup"><span data-stu-id="bbb86-103">Views allow the same data collection to be viewed in different ways, depending on sorting, filtering, or grouping criteria.</span></span> <span data-ttu-id="bbb86-104">Каждая коллекция имеет одно общее представление по умолчанию, который используется в качестве фактического источника привязки, если привязка задает коллекцию в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="bbb86-104">Every collection has one shared default view, which is used as the actual binding source when a binding specifies a collection as its source.</span></span> <span data-ttu-id="bbb86-105">В этом примере показано, как получить представление коллекции по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bbb86-105">This example shows how to get the default view of a collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbb86-106">Пример</span><span class="sxs-lookup"><span data-stu-id="bbb86-106">Example</span></span>  
 <span data-ttu-id="bbb86-107">Для создания представления требуется ссылка на объект в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bbb86-107">To create the view, you need an object reference to the collection.</span></span> <span data-ttu-id="bbb86-108">Этот объект данных можно получить с помощью ссылки на собственный объект кода путем получения контекста данных, свойства источника данных или свойства привязки.</span><span class="sxs-lookup"><span data-stu-id="bbb86-108">This data object can be obtained by referencing your own code-behind object, by getting the data context, by getting a property of the data source, or by getting a property of the binding.</span></span> <span data-ttu-id="bbb86-109">В этом примере показано, как получить <xref:System.Windows.FrameworkElement.DataContext%2A> объекта данных и использовать его для непосредственного получения коллекции по умолчанию просмотра для данной коллекции.</span><span class="sxs-lookup"><span data-stu-id="bbb86-109">This example shows how to get the <xref:System.Windows.FrameworkElement.DataContext%2A> of a data object and use it to directly obtain the default collection view for this collection.</span></span>  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="bbb86-110">В этом примере корневым элементом является <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="bbb86-110">In this example, the root element is a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="bbb86-111"><xref:System.Windows.FrameworkElement.DataContext%2A> Задано значение *myDataSource*, которая относится к поставщику данных, <xref:System.Collections.ObjectModel.ObservableCollection%601> из *порядок* объектов.</span><span class="sxs-lookup"><span data-stu-id="bbb86-111">The <xref:System.Windows.FrameworkElement.DataContext%2A> is set to *myDataSource*, which refers to a data provider that is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of *Order* objects.</span></span>  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 <span data-ttu-id="bbb86-112">Можно также создать и привязать собственную коллекцию представления с помощью <xref:System.Windows.Data.CollectionViewSource> класса.</span><span class="sxs-lookup"><span data-stu-id="bbb86-112">Alternatively, you can instantiate and bind to your own collection view using the <xref:System.Windows.Data.CollectionViewSource> class.</span></span> <span data-ttu-id="bbb86-113">Это представление коллекции совместно используется только элементами управления, которые привязаны непосредственно к нему.</span><span class="sxs-lookup"><span data-stu-id="bbb86-113">This collection view is only shared by controls that bind to it directly.</span></span> <span data-ttu-id="bbb86-114">Пример см. в разделе способы создания представления статьи [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bbb86-114">For an example, see the How to Create a View section in the [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="bbb86-115">Примеры функциональных возможностей, предоставляемых представления коллекции, в разделе [сортировка данных в представлении](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [фильтрации данных в представлении](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), и [перейдите через объекты данных CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span><span class="sxs-lookup"><span data-stu-id="bbb86-115">For examples of the functionality provided by a collection view, see [Sort Data in a View](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), and [Navigate Through the Objects in a Data CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb86-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb86-116">See Also</span></span>  
 [<span data-ttu-id="bbb86-117">Сортировка и группировка данных с помощью представления в XAML</span><span class="sxs-lookup"><span data-stu-id="bbb86-117">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [<span data-ttu-id="bbb86-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="bbb86-118">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
