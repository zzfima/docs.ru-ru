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
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369101"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="3324a-102">Практическое руководство. Создание эффекта выделения с помощью событий</span><span class="sxs-lookup"><span data-stu-id="3324a-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="3324a-103">В этом примере показано, как изменение цвета элемента, как указатель мыши и покидает область, занимаемая элементом.</span><span class="sxs-lookup"><span data-stu-id="3324a-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="3324a-104">В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл с выделенным кодом.</span><span class="sxs-lookup"><span data-stu-id="3324a-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3324a-105">В этом примере показано, как использовать события, но для достижения такого же эффекта рекомендуется использовать <xref:System.Windows.Trigger> в стиле.</span><span class="sxs-lookup"><span data-stu-id="3324a-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="3324a-106">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="3324a-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3324a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3324a-107">Example</span></span>  
 <span data-ttu-id="3324a-108">Следующие [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] создает пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.Border> вокруг <xref:System.Windows.Controls.TextBlock>и присоединяет <xref:System.Windows.Input.Mouse.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> обработчики событий для <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="3324a-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="3324a-109">Следующий код создает <xref:System.Windows.UIElement.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> обработчики событий.</span><span class="sxs-lookup"><span data-stu-id="3324a-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="3324a-110">Когда указатель мыши попадает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется на красный.</span><span class="sxs-lookup"><span data-stu-id="3324a-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="3324a-111">Когда указатель мыши покидает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> изменяется обратно на белое.</span><span class="sxs-lookup"><span data-stu-id="3324a-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
