---
title: Как привязать свойства двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 66c759c28747de5b0288c906f5d51e4253fb7d52
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459179"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="8cb38-102">Как привязать свойства двух элементов управления</span><span class="sxs-lookup"><span data-stu-id="8cb38-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="8cb38-103">В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью свойства <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cb38-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cb38-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8cb38-104">Example</span></span>  
 <span data-ttu-id="8cb38-105">В следующем примере показано, как привязать свойство <xref:System.Windows.Controls.Panel.Background%2A> <xref:System.Windows.Controls.Canvas> к <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="8cb38-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="8cb38-106">свойства <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="8cb38-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="8cb38-107">После преобразования пример выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8cb38-107">When this example is rendered it looks like the following:</span></span>  
  
![Снимок экрана, показывающий поле со списком со значением зеленого цвета и зеленым квадратом.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="8cb38-109">Свойство цели привязки (в этом примере свойство <xref:System.Windows.Controls.Panel.Background%2A>) должно быть свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="8cb38-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="8cb38-110">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8cb38-110">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb38-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8cb38-111">See also</span></span>

- [<span data-ttu-id="8cb38-112">Указание источника привязки</span><span class="sxs-lookup"><span data-stu-id="8cb38-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="8cb38-113">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="8cb38-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
