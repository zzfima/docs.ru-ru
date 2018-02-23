---
title: "Практическое руководство. Управление обновлением источника из поля TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00fc64938e6a063ffbda77961f967e08c169ebd7
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="8601b-102">Практическое руководство. Управление обновлением источника из поля TextBox</span><span class="sxs-lookup"><span data-stu-id="8601b-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="8601b-103">В этом разделе описывается использование <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойства для управления синхронизацией обновлений источника привязки.</span><span class="sxs-lookup"><span data-stu-id="8601b-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="8601b-104">В этом разделе используются <xref:System.Windows.Controls.TextBox> элемента управления в качестве примера.</span><span class="sxs-lookup"><span data-stu-id="8601b-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8601b-105">Пример</span><span class="sxs-lookup"><span data-stu-id="8601b-105">Example</span></span>  
 <span data-ttu-id="8601b-106"><xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Свойство имеет значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="8601b-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="8601b-107">Это означает, что если приложение имеет <xref:System.Windows.Controls.TextBox> с привязкой к данным <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> свойство, текст, вводимый в <xref:System.Windows.Controls.TextBox> обновляет источник до <xref:System.Windows.Controls.TextBox> теряет фокус (например, если щелкнуть вне <xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="8601b-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="8601b-108">Источник обновляться по мере ввода, установите <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="8601b-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="8601b-109">В следующем примере выделенные строки кода показывают, что `Text` свойства обоих <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBlock> связаны с теми же свойствами источника.</span><span class="sxs-lookup"><span data-stu-id="8601b-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="8601b-110"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Свойство <xref:System.Windows.Controls.TextBox> привязки имеет значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="8601b-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 <span data-ttu-id="8601b-111">В результате <xref:System.Windows.Controls.TextBlock> отображает текст (поскольку источник изменяется), как пользователь вводит в <xref:System.Windows.Controls.TextBox>, как показано на следующем снимке экрана образца:</span><span class="sxs-lookup"><span data-stu-id="8601b-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="8601b-112">![Снимок экрана примера простой привязки данных ](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="8601b-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="8601b-113">Если у вас есть диалоговое окно или редактируемая пользователем форма и требуется отложить обновление источника, пока пользователь не завершит редактирование поля и нажимает кнопку «ОК», можно задать <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение привязки в <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8601b-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="8601b-114">При задании <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, исходное значение изменяется, только когда приложение вызывает <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="8601b-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="8601b-115">В следующем примере демонстрируется вызов <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> для `itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="8601b-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="8601b-116">Можно использовать ту же методику для свойств других элементов управления, но имейте в виду, что большинство других свойств имеют значение по умолчанию <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="8601b-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="8601b-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="8601b-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8601b-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Свойство имеет дело с обновлениями источника и поэтому относится только к <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязки.</span><span class="sxs-lookup"><span data-stu-id="8601b-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="8601b-119">Для <xref:System.Windows.Data.BindingMode.TwoWay> и <xref:System.Windows.Data.BindingMode.OneWayToSource> привязки для работы, исходный объект должен предоставить уведомление об изменениях свойств.</span><span class="sxs-lookup"><span data-stu-id="8601b-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="8601b-120">Можно изучить примеры, приведенные в этом разделе, для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="8601b-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="8601b-121">Кроме того, см. раздел [Реализация уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="8601b-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8601b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="8601b-122">See Also</span></span>  
 [<span data-ttu-id="8601b-123">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="8601b-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
