---
title: Как привязать свойства двух элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: d38c473b8c4d3f71f1e3decd4f66be248665c57b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974817"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="ae72f-102">Как привязать свойства двух элементов управления</span><span class="sxs-lookup"><span data-stu-id="ae72f-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="ae72f-103">В этом примере показано, как привязать свойство одного экземпляра элемента управления к другому с помощью свойства <xref:System.Windows.Data.Binding.ElementName%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae72f-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="ae72f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ae72f-104">Example</span></span>

<span data-ttu-id="ae72f-105">В следующем примере показано, как привязать свойство <xref:System.Windows.Controls.Panel.Background%2A> <xref:System.Windows.Controls.Canvas> к свойству [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="ae72f-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="ae72f-106">После преобразования пример выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ae72f-106">When this example is rendered it looks like the following:</span></span>

![Снимок экрана, показывающий поле со списком со значением зеленого цвета и зеленым квадратом.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="ae72f-108">Свойство цели привязки (в этом примере свойство <xref:System.Windows.Controls.Panel.Background%2A>) должно быть свойством зависимостей.</span><span class="sxs-lookup"><span data-stu-id="ae72f-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="ae72f-109">Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ae72f-109">For more information, see [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae72f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ae72f-110">See also</span></span>

- [<span data-ttu-id="ae72f-111">Указание источника привязки</span><span class="sxs-lookup"><span data-stu-id="ae72f-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="ae72f-112">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ae72f-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
