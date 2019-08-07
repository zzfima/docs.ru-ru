---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817909"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="334d2-102">Практическое руководство. Укажите направление привязки</span><span class="sxs-lookup"><span data-stu-id="334d2-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="334d2-103">В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.</span><span class="sxs-lookup"><span data-stu-id="334d2-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="334d2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="334d2-104">Example</span></span>  
 <span data-ttu-id="334d2-105"><xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> Свойство используется для указания направления привязки.</span><span class="sxs-lookup"><span data-stu-id="334d2-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="334d2-106">Ниже приведены доступные варианты обновления привязок.</span><span class="sxs-lookup"><span data-stu-id="334d2-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="334d2-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>обновляет целевое свойство или свойство, когда изменяется либо свойство Target, либо свойство Source.</span><span class="sxs-lookup"><span data-stu-id="334d2-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="334d2-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>обновляет свойство Target только при изменении свойства Source.</span><span class="sxs-lookup"><span data-stu-id="334d2-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="334d2-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>обновляет целевое свойство только при запуске приложения или при <xref:System.Windows.FrameworkElement.DataContext%2A> изменении.</span><span class="sxs-lookup"><span data-stu-id="334d2-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="334d2-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>обновляет свойство Source при изменении целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="334d2-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="334d2-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>вызывает использование значения <xref:System.Windows.Data.Binding.Mode%2A> по умолчанию целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="334d2-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="334d2-112">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="334d2-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="334d2-113">В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="334d2-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="334d2-114">Для обнаружения изменений источника (применимо <xref:System.Windows.Data.BindingMode.OneWay> к <xref:System.Windows.Data.BindingMode.TwoWay> привязкам и) источник должен реализовать подходящий механизм уведомления об <xref:System.ComponentModel.INotifyPropertyChanged>изменении свойств, например.</span><span class="sxs-lookup"><span data-stu-id="334d2-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="334d2-115">Пример<xref:System.ComponentModel.INotifyPropertyChanged> реализации см. в разделе [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md) .</span><span class="sxs-lookup"><span data-stu-id="334d2-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="334d2-116">Для <xref:System.Windows.Data.BindingMode.TwoWay> привязок или <xref:System.Windows.Data.BindingMode.OneWayToSource> можно управлять временем обновлений <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> источника, задав свойство.</span><span class="sxs-lookup"><span data-stu-id="334d2-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="334d2-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="334d2-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334d2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="334d2-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="334d2-119">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="334d2-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="334d2-120">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="334d2-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
