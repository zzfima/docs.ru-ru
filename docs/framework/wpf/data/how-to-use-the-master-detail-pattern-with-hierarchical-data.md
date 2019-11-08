---
title: Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733484"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="73176-102">Практическое руководство. Использование шаблона "основной-подчиненный" с иерархическими данными</span><span class="sxs-lookup"><span data-stu-id="73176-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="73176-103">В этом примере показано, как реализовать сценарий "основной-подробности".</span><span class="sxs-lookup"><span data-stu-id="73176-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73176-104">Пример</span><span class="sxs-lookup"><span data-stu-id="73176-104">Example</span></span>  
 <span data-ttu-id="73176-105">В этом примере `LeagueList` является коллекцией `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="73176-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="73176-106">Каждый `League` имеет `Name` и коллекцию `Divisions`, а каждый `Division` имеет имя и коллекцию `Teams`.</span><span class="sxs-lookup"><span data-stu-id="73176-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="73176-107">Каждый `Team` имеет имя команды.</span><span class="sxs-lookup"><span data-stu-id="73176-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="73176-108">Ниже приведен снимок экрана примера.</span><span class="sxs-lookup"><span data-stu-id="73176-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="73176-109">`Divisions` <xref:System.Windows.Controls.ListBox> автоматически отслеживает выделенные элементы в `Leagues` <xref:System.Windows.Controls.ListBox> и отображает соответствующие данные.</span><span class="sxs-lookup"><span data-stu-id="73176-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="73176-110">`Teams` <xref:System.Windows.Controls.ListBox> отслеживает выделение в других двух элементах управления <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="73176-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Снимок экрана, на котором&#45;показан пример сценария главной детализации.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="73176-112">В этом примере необходимо обратить внимание на два момента:</span><span class="sxs-lookup"><span data-stu-id="73176-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="73176-113">Три элемента управления <xref:System.Windows.Controls.ListBox> привязываются к одному и тому же источнику.</span><span class="sxs-lookup"><span data-stu-id="73176-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="73176-114">Свойство <xref:System.Windows.Data.Binding.Path%2A> привязки задается, чтобы указать, какой уровень данных будет отображаться в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="73176-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="73176-115">Необходимо задать для свойства <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> значение `true` в элементах управления <xref:System.Windows.Controls.ListBox>, для которых отслеживается выбранный объект.</span><span class="sxs-lookup"><span data-stu-id="73176-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="73176-116">Задание этого свойства гарантирует, что выбранный элемент всегда будет установлен в качестве <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="73176-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="73176-117">Кроме того, если <xref:System.Windows.Controls.ListBox> получает данные из <xref:System.Windows.Data.CollectionViewSource>, она автоматически синхронизирует выбор и валют.</span><span class="sxs-lookup"><span data-stu-id="73176-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="73176-118">При использовании XML-данных метод слегка отличается.</span><span class="sxs-lookup"><span data-stu-id="73176-118">The technique is slightly different when you are using XML data.</span></span> <span data-ttu-id="73176-119">Пример см. в разделе [Использование шаблона "основной/подробности" с иерархическими XML-данными](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="73176-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73176-120">См. также</span><span class="sxs-lookup"><span data-stu-id="73176-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="73176-121">Привязка к коллекции и вывод сведений в зависимости от выделенного элемента</span><span class="sxs-lookup"><span data-stu-id="73176-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="73176-122">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="73176-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="73176-123">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="73176-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="73176-124">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="73176-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
