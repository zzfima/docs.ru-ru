---
title: Практическое руководство. Использование шаблона "главный-подчиненный" с иерархическими данными
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e18bc7d60b47b083a0b102938634473d85b39882
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463323"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="34db8-102">Практическое руководство. Использование шаблона "главный-подчиненный" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="34db8-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="34db8-103">В этом примере показано, как для реализации сценария «основной-подробности».</span><span class="sxs-lookup"><span data-stu-id="34db8-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34db8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="34db8-104">Example</span></span>  
 <span data-ttu-id="34db8-105">В этом примере `LeagueList` — это коллекция `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="34db8-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="34db8-106">Каждый `League` имеет `Name` и коллекцию `Divisions`и каждый `Division` имеет имя и коллекция `Teams`.</span><span class="sxs-lookup"><span data-stu-id="34db8-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="34db8-107">Каждый `Team` содержит имя команды.</span><span class="sxs-lookup"><span data-stu-id="34db8-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="34db8-108">Ниже приведен снимок экрана примера.</span><span class="sxs-lookup"><span data-stu-id="34db8-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="34db8-109">`Divisions` <xref:System.Windows.Controls.ListBox> Автоматически отслеживает выделение в `Leagues` <xref:System.Windows.Controls.ListBox> и отображают соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="34db8-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="34db8-110">`Teams` <xref:System.Windows.Controls.ListBox> Отслеживает выбранные параметры в двух других <xref:System.Windows.Controls.ListBox> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="34db8-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Снимок экрана, показывающий шаблона&#45;пример сценария детализации.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="34db8-112">В этом примере следует обратить внимание на два обстоятельства:</span><span class="sxs-lookup"><span data-stu-id="34db8-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="34db8-113">Три <xref:System.Windows.Controls.ListBox> привязать элементы управления с одним источником.</span><span class="sxs-lookup"><span data-stu-id="34db8-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="34db8-114">Можно задать <xref:System.Windows.Data.Binding.Path%2A> свойство привязки, чтобы указать, какой уровень данных <xref:System.Windows.Controls.ListBox> для отображения.</span><span class="sxs-lookup"><span data-stu-id="34db8-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="34db8-115">Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` на <xref:System.Windows.Controls.ListBox> элементов управления, из которых осуществляется отслеживание выбора.</span><span class="sxs-lookup"><span data-stu-id="34db8-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="34db8-116">Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="34db8-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="34db8-117">Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.</span><span class="sxs-lookup"><span data-stu-id="34db8-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="34db8-118">Метод немного отличается при использовании [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных.</span><span class="sxs-lookup"><span data-stu-id="34db8-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="34db8-119">Например, см. в разделе [использование шаблона «основной-подробности» с иерархическими данными XML](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="34db8-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34db8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="34db8-120">See also</span></span>
- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="34db8-121">Привязка к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="34db8-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="34db8-122">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="34db8-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="34db8-123">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="34db8-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="34db8-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="34db8-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
