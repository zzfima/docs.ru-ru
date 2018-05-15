---
title: Практическое руководство. Привязка к перечислению
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: 921f15a32eeb5ccb20e879466fcfee3233bbd29e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="85e5d-102">Практическое руководство. Привязка к перечислению</span><span class="sxs-lookup"><span data-stu-id="85e5d-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="85e5d-103">В этом примере показано, как выполнить привязку к перечислению путем привязки к методу GetValues перечисления.</span><span class="sxs-lookup"><span data-stu-id="85e5d-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85e5d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="85e5d-104">Example</span></span>  
 <span data-ttu-id="85e5d-105">В следующем примере <xref:System.Windows.Controls.ListBox> отображает список <xref:System.Windows.HorizontalAlignment> значения перечисления с помощью привязки данных.</span><span class="sxs-lookup"><span data-stu-id="85e5d-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="85e5d-106"><xref:System.Windows.Controls.ListBox> И <xref:System.Windows.Controls.Button> связаны таким образом, вы можете изменить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение свойства <xref:System.Windows.Controls.Button> , выбрав значение в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="85e5d-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="85e5d-107">См. также</span><span class="sxs-lookup"><span data-stu-id="85e5d-107">See Also</span></span>  
 [<span data-ttu-id="85e5d-108">Создание привязки к методу</span><span class="sxs-lookup"><span data-stu-id="85e5d-108">Bind to a Method</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-method.md)  
 [<span data-ttu-id="85e5d-109">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="85e5d-109">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="85e5d-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="85e5d-110">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
