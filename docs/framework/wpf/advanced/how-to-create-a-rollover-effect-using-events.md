---
title: Инструкция по Созданию Эффекта Выделения с Помощью Событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: ccdc8aeb26b538814b2f9020e1e3a5b311fa5a99
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460161"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="d91f7-102">Инструкция по Созданию Эффекта Выделения с Помощью Событий</span><span class="sxs-lookup"><span data-stu-id="d91f7-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="d91f7-103">В этом примере показано, как изменить цвет элемента, когда указатель мыши попадает в область, занимаемую элементом.</span><span class="sxs-lookup"><span data-stu-id="d91f7-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="d91f7-104">Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="d91f7-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d91f7-105">В этом примере показано, как использовать события, но рекомендуемым способом добиться такого же результата является использование <xref:System.Windows.Trigger> в стиле.</span><span class="sxs-lookup"><span data-stu-id="d91f7-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="d91f7-106">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d91f7-106">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d91f7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d91f7-107">Example</span></span>  
 <span data-ttu-id="d91f7-108">Следующий код XAML создает пользовательский интерфейс, состоящий из <xref:System.Windows.Controls.Border> вокруг <xref:System.Windows.Controls.TextBlock>и присоединяет обработчики событий <xref:System.Windows.Input.Mouse.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave> к <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="d91f7-108">The following XAML creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="d91f7-109">Следующий программный код создает обработчики событий <xref:System.Windows.UIElement.MouseEnter> и <xref:System.Windows.UIElement.MouseLeave>.</span><span class="sxs-lookup"><span data-stu-id="d91f7-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="d91f7-110">Когда указатель мыши попадает в <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> меняется на красный.</span><span class="sxs-lookup"><span data-stu-id="d91f7-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="d91f7-111">Когда указатель мыши покидает <xref:System.Windows.Controls.Border>, фон <xref:System.Windows.Controls.Border> меняется обратно на белый.</span><span class="sxs-lookup"><span data-stu-id="d91f7-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
