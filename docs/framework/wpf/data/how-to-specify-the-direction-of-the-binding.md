---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 265271cee16d203d7652281c5416b93759e66d4b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378227"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="c6a15-102">Практическое руководство. Указание направления привязки</span><span class="sxs-lookup"><span data-stu-id="c6a15-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="c6a15-103">В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.</span><span class="sxs-lookup"><span data-stu-id="c6a15-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6a15-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c6a15-104">Example</span></span>  
 <span data-ttu-id="c6a15-105">Использовании <xref:System.Windows.Data.Binding.Mode%2A> свойство, чтобы указать направление привязки.</span><span class="sxs-lookup"><span data-stu-id="c6a15-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="c6a15-106">В следующем списке перечислены доступные параметры для обновлений привязки.</span><span class="sxs-lookup"><span data-stu-id="c6a15-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="c6a15-107"><xref:System.Windows.Data.BindingMode.TwoWay> обновляет свойство цели или свойство, при каждом изменении целевого свойства или свойства источника.</span><span class="sxs-lookup"><span data-stu-id="c6a15-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="c6a15-108"><xref:System.Windows.Data.BindingMode.OneWay> обновляет свойство цели только при изменении свойства источника.</span><span class="sxs-lookup"><span data-stu-id="c6a15-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="c6a15-109"><xref:System.Windows.Data.BindingMode.OneTime> обновляет свойство цели только при запуске приложения или при <xref:System.Windows.FrameworkElement.DataContext%2A> подвергается изменению.</span><span class="sxs-lookup"><span data-stu-id="c6a15-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="c6a15-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> Обновляет свойство источника при изменении свойства цели.</span><span class="sxs-lookup"><span data-stu-id="c6a15-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="c6a15-111"><xref:System.Windows.Data.BindingMode.Default> по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> значение целевого свойства для использования.</span><span class="sxs-lookup"><span data-stu-id="c6a15-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="c6a15-112">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="c6a15-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="c6a15-113">В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6a15-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="c6a15-114">Для обнаружения изменений в источнике (применимо к <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay> привязок), источник должен реализовывать механизм уведомлений об изменениях соответствующее свойство <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="c6a15-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="c6a15-115">См. в разделе [реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md) пример <xref:System.ComponentModel.INotifyPropertyChanged> реализации.</span><span class="sxs-lookup"><span data-stu-id="c6a15-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="c6a15-116">Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязок, можно управлять временем обновлений источника, задав <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="c6a15-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="c6a15-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="c6a15-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a15-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c6a15-118">See also</span></span>
- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="c6a15-119">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="c6a15-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="c6a15-120">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="c6a15-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
