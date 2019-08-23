---
title: Практическое руководство. Создание эффекта выделения с помощью событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960389"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="57d15-102">Практическое руководство. Создание эффекта выделения с помощью событий</span><span class="sxs-lookup"><span data-stu-id="57d15-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="57d15-103">В этом примере показано, как изменить цвет элемента, когда указатель мыши попадает в область, занимаемую элементом.</span><span class="sxs-lookup"><span data-stu-id="57d15-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="57d15-104">Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="57d15-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57d15-105">В этом примере показано, как использовать события, но рекомендуемым способом добиться такого же результата является использование <xref:System.Windows.Trigger> в стиле.</span><span class="sxs-lookup"><span data-stu-id="57d15-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="57d15-106">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="57d15-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57d15-107">Пример</span><span class="sxs-lookup"><span data-stu-id="57d15-107">Example</span></span>  
 <span data-ttu-id="57d15-108">Следующий пример [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, состоящий из <xref:System.Windows.UIElement.MouseLeave> <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.TextBlock>, и <xref:System.Windows.Controls.Border>присоединяет <xref:System.Windows.Input.Mouse.MouseEnter> обработчики событий и к.</span><span class="sxs-lookup"><span data-stu-id="57d15-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="57d15-109">Следующий программный код создает <xref:System.Windows.UIElement.MouseEnter> обработчики событий и. <xref:System.Windows.UIElement.MouseLeave></span><span class="sxs-lookup"><span data-stu-id="57d15-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="57d15-110">Когда указатель мыши попадает в <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> элемента изменяется на красный.</span><span class="sxs-lookup"><span data-stu-id="57d15-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="57d15-111">Когда указатель мыши покидает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется обратно на белый.</span><span class="sxs-lookup"><span data-stu-id="57d15-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
