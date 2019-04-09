---
title: Практическое руководство. Привязка к коллекции и вывод сведений в зависимости от выделенного элемента
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
ms.openlocfilehash: 61ced27ed80adf8ac5d543584f71794b9ee59676
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188751"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="675bb-102">Практическое руководство. Привязка к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="675bb-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="675bb-103">В простом сценарии «основной-подробности», у вас есть привязкой к данным <xref:System.Windows.Controls.ItemsControl> например <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="675bb-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="675bb-104">В зависимости от выбора пользователя можно отобразить дополнительные сведения о выбранном элементе.</span><span class="sxs-lookup"><span data-stu-id="675bb-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="675bb-105">В этом примере показано, как реализовать этот сценарий.</span><span class="sxs-lookup"><span data-stu-id="675bb-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="675bb-106">Пример</span><span class="sxs-lookup"><span data-stu-id="675bb-106">Example</span></span>  
 <span data-ttu-id="675bb-107">В этом примере `People` — <xref:System.Collections.ObjectModel.ObservableCollection%601> из `Person` классы.</span><span class="sxs-lookup"><span data-stu-id="675bb-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="675bb-108">Это `Person` класс содержит три свойства: `FirstName`, `LastName`, и `HomeTown`, все типа `string`.</span><span class="sxs-lookup"><span data-stu-id="675bb-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="675bb-109"><xref:System.Windows.Controls.ContentControl> Использует следующие <xref:System.Windows.DataTemplate> определяет, как данные `Person` представлены:</span><span class="sxs-lookup"><span data-stu-id="675bb-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="675bb-110">Ниже приведен снимок экрана примера.</span><span class="sxs-lookup"><span data-stu-id="675bb-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="675bb-111"><xref:System.Windows.Controls.ContentControl> Показаны другие свойства выбранного лица.</span><span class="sxs-lookup"><span data-stu-id="675bb-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="675bb-112">![Привязка к коллекции](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="675bb-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="675bb-113">В этом примере следует обратить внимание на два обстоятельства:</span><span class="sxs-lookup"><span data-stu-id="675bb-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="675bb-114"><xref:System.Windows.Controls.ListBox> И <xref:System.Windows.Controls.ContentControl> привязать к одному источнику.</span><span class="sxs-lookup"><span data-stu-id="675bb-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="675bb-115"><xref:System.Windows.Data.Binding.Path%2A> Свойства обе привязки не заданы, так как оба элемента управления привязаны к всему объекту коллекции.</span><span class="sxs-lookup"><span data-stu-id="675bb-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="675bb-116">Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="675bb-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="675bb-117">Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="675bb-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="675bb-118">Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.</span><span class="sxs-lookup"><span data-stu-id="675bb-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="675bb-119">Обратите внимание, что `Person` класса переопределения `ToString` метод следующим образом.</span><span class="sxs-lookup"><span data-stu-id="675bb-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="675bb-120">По умолчанию <xref:System.Windows.Controls.ListBox> вызовы `ToString` и отображает строковое представление каждого объекта в привязанной коллекции.</span><span class="sxs-lookup"><span data-stu-id="675bb-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="675bb-121">Вот почему каждый `Person` отображается как имя в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="675bb-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="675bb-122">См. также</span><span class="sxs-lookup"><span data-stu-id="675bb-122">See also</span></span>

- [<span data-ttu-id="675bb-123">Использование шаблона "Основной/подробности" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="675bb-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="675bb-124">Использование шаблона "Основной/подробности" с иерархическими XML-данными</span><span class="sxs-lookup"><span data-stu-id="675bb-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="675bb-125">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="675bb-125">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="675bb-126">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="675bb-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="675bb-127">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="675bb-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
