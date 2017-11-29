---
title: "Практическое руководство. Использование шаблона \"основной-подчиненный\" с иерархическими данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="54533-102">Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="54533-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="54533-103">В этом примере показано, как реализовать сценарий основной подробности.</span><span class="sxs-lookup"><span data-stu-id="54533-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54533-104">Пример</span><span class="sxs-lookup"><span data-stu-id="54533-104">Example</span></span>  
 <span data-ttu-id="54533-105">В этом примере `LeagueList` — это совокупность `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="54533-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="54533-106">Каждый `League` имеет `Name` и коллекцию `Divisions`и каждый `Division` имеет имя и коллекция `Teams`.</span><span class="sxs-lookup"><span data-stu-id="54533-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="54533-107">Каждый `Team` содержит имя команды.</span><span class="sxs-lookup"><span data-stu-id="54533-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="54533-108">Ниже приведен снимок экрана примера.</span><span class="sxs-lookup"><span data-stu-id="54533-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="54533-109">`Divisions` <xref:System.Windows.Controls.ListBox> Автоматически отслеживает выделение в `Leagues` <xref:System.Windows.Controls.ListBox> и отображают соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="54533-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="54533-110">`Teams` <xref:System.Windows.Controls.ListBox> Отслеживает выбор в двух других <xref:System.Windows.Controls.ListBox> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="54533-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="54533-111">![Образец &#45; пример использования типа detail](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="54533-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="54533-112">В этом примере следует обратить внимание на два обстоятельства:</span><span class="sxs-lookup"><span data-stu-id="54533-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="54533-113">Три <xref:System.Windows.Controls.ListBox> привязать элементы управления с одним источником.</span><span class="sxs-lookup"><span data-stu-id="54533-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="54533-114">Задать <xref:System.Windows.Data.Binding.Path%2A> свойства привязки, чтобы указать, какой уровень данных <xref:System.Windows.Controls.ListBox> для отображения.</span><span class="sxs-lookup"><span data-stu-id="54533-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="54533-115">Необходимо задать <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> свойства `true` на <xref:System.Windows.Controls.ListBox> элементов управления, из которого осуществляется отслеживание выбора.</span><span class="sxs-lookup"><span data-stu-id="54533-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="54533-116">Задание этого свойства гарантирует, что выбранный элемент всегда задается как <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="54533-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="54533-117">Кроме того Если <xref:System.Windows.Controls.ListBox> получает данные от <xref:System.Windows.Data.CollectionViewSource>, он автоматически синхронизирует Выбор и денежные единицы.</span><span class="sxs-lookup"><span data-stu-id="54533-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="54533-118">Метод немного отличается при использовании [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных.</span><span class="sxs-lookup"><span data-stu-id="54533-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="54533-119">Пример см. в разделе [использовать шаблон «основной-подробности» с иерархическими данными XML](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="54533-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54533-120">См. также</span><span class="sxs-lookup"><span data-stu-id="54533-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="54533-121">Привязка к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="54533-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="54533-122">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="54533-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="54533-123">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="54533-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="54533-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="54533-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
