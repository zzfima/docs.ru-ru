---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459095"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="63c11-102">Как указать направление привязки</span><span class="sxs-lookup"><span data-stu-id="63c11-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="63c11-103">В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.</span><span class="sxs-lookup"><span data-stu-id="63c11-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63c11-104">Пример</span><span class="sxs-lookup"><span data-stu-id="63c11-104">Example</span></span>  
 <span data-ttu-id="63c11-105">Для указания направления привязки используется свойство <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="63c11-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="63c11-106">Ниже приведены доступные варианты обновления привязок.</span><span class="sxs-lookup"><span data-stu-id="63c11-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="63c11-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> обновляет целевое свойство или свойство, когда изменяется либо свойство Target, либо свойство Source.</span><span class="sxs-lookup"><span data-stu-id="63c11-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="63c11-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> обновляет свойство цели только при изменении свойства Source.</span><span class="sxs-lookup"><span data-stu-id="63c11-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="63c11-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> обновляет целевое свойство только при запуске приложения или при изменении <xref:System.Windows.FrameworkElement.DataContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="63c11-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="63c11-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> обновляет свойство источника при изменении целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="63c11-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="63c11-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> вызывает использование <xref:System.Windows.Data.Binding.Mode%2A> значения по умолчанию для целевого свойства.</span><span class="sxs-lookup"><span data-stu-id="63c11-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="63c11-112">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="63c11-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="63c11-113">В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="63c11-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="63c11-114">Чтобы обнаружить изменения источника (применимые к привязкам <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay>), источник должен реализовать подходящий механизм уведомления об изменении свойств, например <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="63c11-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="63c11-115">Пример реализации <xref:System.ComponentModel.INotifyPropertyChanged> см. в разделе Реализация [уведомления об изменении свойства](how-to-implement-property-change-notification.md) .</span><span class="sxs-lookup"><span data-stu-id="63c11-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="63c11-116">Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource>ных привязок можно управлять временем обновления источника, установив свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="63c11-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="63c11-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="63c11-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c11-118">См. также</span><span class="sxs-lookup"><span data-stu-id="63c11-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="63c11-119">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="63c11-119">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="63c11-120">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="63c11-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
