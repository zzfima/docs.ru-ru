---
title: Практическое руководство. Указание направления привязки
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206438"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="4046b-102">Практическое руководство. Указание направления привязки</span><span class="sxs-lookup"><span data-stu-id="4046b-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="4046b-103">В этом примере показано, как указать, что привязка обновляет только свойство цели привязки (цель), свойство источника привязки (источник) или обновляет свойство цели и свойство источника.</span><span class="sxs-lookup"><span data-stu-id="4046b-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4046b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4046b-104">Example</span></span>  
 <span data-ttu-id="4046b-105">Использовании <xref:System.Windows.Data.Binding.Mode%2A> свойство, чтобы указать направление привязки.</span><span class="sxs-lookup"><span data-stu-id="4046b-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="4046b-106">В следующем списке перечислены доступные параметры для обновлений привязки.</span><span class="sxs-lookup"><span data-stu-id="4046b-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> <span data-ttu-id="4046b-107">обновляет свойство цели или свойство, при каждом изменении целевого свойства или свойства источника.</span><span class="sxs-lookup"><span data-stu-id="4046b-107">updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> <span data-ttu-id="4046b-108">обновляет свойство цели только при изменении свойства источника.</span><span class="sxs-lookup"><span data-stu-id="4046b-108">updates the target property only when the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> <span data-ttu-id="4046b-109">обновляет свойство цели только при запуске приложения или при <xref:System.Windows.FrameworkElement.DataContext%2A> подвергается изменению.</span><span class="sxs-lookup"><span data-stu-id="4046b-109">updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> <span data-ttu-id="4046b-110">Обновляет свойство источника при изменении свойства цели.</span><span class="sxs-lookup"><span data-stu-id="4046b-110">updates the source property when the target property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.Default> <span data-ttu-id="4046b-111">по умолчанию <xref:System.Windows.Data.Binding.Mode%2A> значение целевого свойства для использования.</span><span class="sxs-lookup"><span data-stu-id="4046b-111">causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="4046b-112">Дополнительные сведения см. в описании перечисления <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="4046b-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="4046b-113">В следующем примере показано, как задать свойство <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="4046b-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="4046b-114">Для обнаружения изменений в источнике (применимо к <xref:System.Windows.Data.BindingMode.OneWay> и <xref:System.Windows.Data.BindingMode.TwoWay> привязок), источник должен реализовывать механизм уведомлений об изменениях соответствующее свойство <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="4046b-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="4046b-115">См. в разделе [реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md) пример <xref:System.ComponentModel.INotifyPropertyChanged> реализации.</span><span class="sxs-lookup"><span data-stu-id="4046b-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="4046b-116">Для <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource> привязок, можно управлять временем обновлений источника, задав <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4046b-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="4046b-117">Дополнительные сведения см. в разделе <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="4046b-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4046b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4046b-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="4046b-119">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="4046b-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="4046b-120">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="4046b-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
