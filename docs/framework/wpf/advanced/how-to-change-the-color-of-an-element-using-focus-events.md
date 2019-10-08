---
title: Практическое руководство. Изменение цвета элемента с помощью событий фокуса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004834"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="e7ec3-102">Практическое руководство. Изменение цвета элемента с помощью событий фокуса</span><span class="sxs-lookup"><span data-stu-id="e7ec3-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="e7ec3-103">В этом примере показано, как изменить цвет элемента при получении и потере фокуса с помощью событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="e7ec3-104">Этот пример состоит из файла [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и файла кода программной части.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7ec3-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e7ec3-105">Example</span></span>  
 <span data-ttu-id="e7ec3-106">Следующий код XAML создает пользовательский интерфейс, состоящий из двух объектов <xref:System.Windows.Controls.Button>, и присоединяет обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus> к объектам <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="e7ec3-107">Следующий программный код создает обработчики событий <xref:System.Windows.UIElement.GotFocus> и <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="e7ec3-108">Когда <xref:System.Windows.Controls.Button> получает фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> меняется на красный.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="e7ec3-109">Когда <xref:System.Windows.Controls.Button> теряет фокус клавиатуры, <xref:System.Windows.Controls.Control.Background%2A> из <xref:System.Windows.Controls.Button> меняется обратно на белый.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="e7ec3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e7ec3-110">See also</span></span>

- [<span data-ttu-id="e7ec3-111">Общие сведения о входных данных</span><span class="sxs-lookup"><span data-stu-id="e7ec3-111">Input Overview</span></span>](input-overview.md)
