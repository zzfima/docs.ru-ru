---
title: Как привязать свойства двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 02e71bfcc41fc3d256ea95381ed27d36b289b8f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="aaa89-102">Как привязать свойства двух элементов управления</span><span class="sxs-lookup"><span data-stu-id="aaa89-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="aaa89-103">В этом примере показано, как привязать свойство одного элемента управления к другому с помощью <xref:System.Windows.Data.Binding.ElementName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="aaa89-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaa89-104">Пример</span><span class="sxs-lookup"><span data-stu-id="aaa89-104">Example</span></span>  
 <span data-ttu-id="aaa89-105">Следующий пример показывает, как привязать <xref:System.Windows.Controls.Panel.Background%2A> свойство <xref:System.Windows.Controls.Canvas> для <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="aaa89-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="aaa89-106">Свойство <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="aaa89-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="aaa89-107">После преобразования пример выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="aaa89-107">When this example is rendered it looks like the following:</span></span>  
  
 <span data-ttu-id="aaa89-108">![Холст с зеленым фоном](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span><span class="sxs-lookup"><span data-stu-id="aaa89-108">![A canvas with a green background](../../../../docs/framework/wpf/data/media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")</span></span>  
  
 <span data-ttu-id="aaa89-109">**Примечание** целевого свойства привязки (в этом примере <xref:System.Windows.Controls.Panel.Background%2A> свойство) должно быть свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="aaa89-109">**Note** The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="aaa89-110">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aaa89-110">For more information, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa89-111">См. также</span><span class="sxs-lookup"><span data-stu-id="aaa89-111">See Also</span></span>  
 [<span data-ttu-id="aaa89-112">Указание источника привязки</span><span class="sxs-lookup"><span data-stu-id="aaa89-112">Specify the Binding Source</span></span>](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)  
 [<span data-ttu-id="aaa89-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="aaa89-113">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
