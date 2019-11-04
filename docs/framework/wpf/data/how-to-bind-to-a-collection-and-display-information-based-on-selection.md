---
title: Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459143"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="02bd1-102">Практическое руководство. Выполнение привязки к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="02bd1-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="02bd1-103">В простом сценарии "основной/подробности" имеется <xref:System.Windows.Controls.ItemsControl> с привязкой к данным, например <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="02bd1-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="02bd1-104">На основе выбора пользователя отображаются дополнительные сведения о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="02bd1-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="02bd1-105">В этом примере показано, как реализовать этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="02bd1-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02bd1-106">Пример</span><span class="sxs-lookup"><span data-stu-id="02bd1-106">Example</span></span>  
 <span data-ttu-id="02bd1-107">В этом примере `People` является <xref:System.Collections.ObjectModel.ObservableCollection%601> классов `Person`.</span><span class="sxs-lookup"><span data-stu-id="02bd1-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="02bd1-108">Этот `Person` класс содержит три свойства: `FirstName`, `LastName`и `HomeTown`, все типы `string`.</span><span class="sxs-lookup"><span data-stu-id="02bd1-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="02bd1-109"><xref:System.Windows.Controls.ContentControl> использует следующие <xref:System.Windows.DataTemplate>, определяющие, каким образом отображаются сведения о `Person`.</span><span class="sxs-lookup"><span data-stu-id="02bd1-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="02bd1-110">Ниже приведен снимок экрана, в котором создается пример.</span><span class="sxs-lookup"><span data-stu-id="02bd1-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="02bd1-111">В <xref:System.Windows.Controls.ContentControl> отображаются другие свойства выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="02bd1-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="02bd1-112">![Привязка к коллекции](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="02bd1-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="02bd1-113">В этом примере необходимо обратить внимание на два момента:</span><span class="sxs-lookup"><span data-stu-id="02bd1-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="02bd1-114"><xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ContentControl> привязываются к одному и тому же источнику.</span><span class="sxs-lookup"><span data-stu-id="02bd1-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="02bd1-115">Свойства <xref:System.Windows.Data.Binding.Path%2A> обеих привязок не указаны, так как оба элемента управления привязаны ко всему объекту коллекции.</span><span class="sxs-lookup"><span data-stu-id="02bd1-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="02bd1-116">Чтобы это работало, необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="02bd1-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="02bd1-117">Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="02bd1-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="02bd1-118">Кроме того, если <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource>, она автоматически синхронизирует выбор и валют.</span><span class="sxs-lookup"><span data-stu-id="02bd1-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="02bd1-119">Обратите внимание, что класс `Person` переопределяет метод `ToString` следующим образом.</span><span class="sxs-lookup"><span data-stu-id="02bd1-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="02bd1-120">По умолчанию <xref:System.Windows.Controls.ListBox> вызывает `ToString` и отображает строковое представление каждого объекта в привязанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="02bd1-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="02bd1-121">Именно поэтому каждый `Person` отображается как имя в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="02bd1-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="02bd1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="02bd1-122">See also</span></span>

- [<span data-ttu-id="02bd1-123">Использование шаблона "Основной/подробности" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="02bd1-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="02bd1-124">Использование шаблона "Основной/подробности" с иерархическими XML-данными</span><span class="sxs-lookup"><span data-stu-id="02bd1-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="02bd1-125">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="02bd1-125">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="02bd1-126">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="02bd1-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="02bd1-127">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="02bd1-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
