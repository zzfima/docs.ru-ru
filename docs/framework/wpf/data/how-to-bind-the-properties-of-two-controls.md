---
title: Практическое руководство. Привязка свойств двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "63809521"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="3565b-102">Практическое руководство. Привязка свойств двух элементов управления</span><span class="sxs-lookup"><span data-stu-id="3565b-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="3565b-103">В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью <xref:System.Windows.Data.Binding.ElementName%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3565b-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3565b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3565b-104">Example</span></span>  
 <span data-ttu-id="3565b-105">В следующем примере показано, как привязать <xref:System.Windows.Controls.Panel.Background%2A> свойство <xref:System.Windows.Controls.Canvas> для <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="3565b-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="3565b-106">Свойство <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="3565b-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="3565b-107">После преобразования пример выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3565b-107">When this example is rendered it looks like the following:</span></span>  
  
![Снимок экрана: поле со списком установлен со значением зеленый и зеленый квадратик.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="3565b-109">Свойство цели привязки (в этом примере <xref:System.Windows.Controls.Panel.Background%2A> свойство) должно быть свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="3565b-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="3565b-110">Более подробную информацию см. в разделе [Общие сведения о связывании данных](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3565b-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3565b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3565b-111">See also</span></span>

- [<span data-ttu-id="3565b-112">Указание источника привязки</span><span class="sxs-lookup"><span data-stu-id="3565b-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="3565b-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="3565b-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
