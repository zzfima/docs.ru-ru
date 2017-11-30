---
title: "Практическое руководство. Указание направления привязки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdcda02a61f0114bfbbe5d5c411cb397cddcf683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="bf153-102">Практическое руководство. Указание направления привязки</span><span class="sxs-lookup"><span data-stu-id="bf153-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="bf153-103">В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.</span><span class="sxs-lookup"><span data-stu-id="bf153-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf153-104">Пример</span><span class="sxs-lookup"><span data-stu-id="bf153-104">Example</span></span>  
 <span data-ttu-id="bf153-105">Вы используете <xref:System.Windows.Data.Binding.Mode%2A> свойство, чтобы указать направление привязки.</span><span class="sxs-lookup"><span data-stu-id="bf153-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="bf153-106">В следующем списке перечислены доступные параметры для обновлений привязки.</span><span class="sxs-lookup"><span data-stu-id="bf153-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="bf153-107"><xref:System.Windows.Data.BindingMode.TwoWay>обновляет целевое свойство или свойства при каждом изменении целевого свойства или свойства source.</span><span class="sxs-lookup"><span data-stu-id="bf153-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="bf153-108"><xref:System.Windows.Data.BindingMode.OneWay>обновляет свойство целевого только при изменении свойства источника.</span><span class="sxs-lookup"><span data-stu-id="bf153-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="bf153-109"><xref:System.Windows.Data.BindingMode.OneTime>обновляет свойство целевого только в том случае, если приложение запускается или если <xref:System.Windows.FrameworkElement.DataContext%2A> меняется.</span><span class="sxs-lookup"><span data-stu-id="bf153-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="bf153-110"><xref:System.Windows.Data.BindingMode.OneWayToSource>обновляет исходное свойство при изменении целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="bf153-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="bf153-111"><xref:System.Windows.Data.BindingMode.Default>по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> значение целевого свойства для использования.</span><span class="sxs-lookup"><span data-stu-id="bf153-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="bf153-112">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="bf153-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="bf153-113">В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf153-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="bf153-114">Для обнаружения изменений в источнике (применимо к <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay> привязок), источник должен применять механизм уведомлений об изменениях подходящего свойства <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="bf153-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="bf153-115">В разделе [реализуют уведомления об изменении свойства](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) пример <xref:System.ComponentModel.INotifyPropertyChanged> реализации.</span><span class="sxs-lookup"><span data-stu-id="bf153-115">See [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="bf153-116">Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязки, задав может управлять временем обновлений источника <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bf153-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="bf153-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf153-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf153-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bf153-118">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="bf153-119">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="bf153-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="bf153-120">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="bf153-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
