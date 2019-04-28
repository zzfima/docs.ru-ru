---
title: Практическое руководство. Определение пользовательского расположения контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: dc516f0eb1cfcbac6662497eb4019041eefec2a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61911213"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="ca1ac-102">Практическое руководство. Определение пользовательского расположения контекстного меню</span><span class="sxs-lookup"><span data-stu-id="ca1ac-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="ca1ac-103">В этом примере показано, как указать положение условных <xref:System.Windows.Controls.Primitives.Popup> управления <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1ac-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ca1ac-104">Example</span></span>  
 <span data-ttu-id="ca1ac-105">Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойству <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, <xref:System.Windows.Controls.Primitives.Popup> вызывает определенный экземпляр <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегировать.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="ca1ac-106">Этот делегат возвращает набор возможных точек относительно верхнего левого угла области назначения и в верхний левый угол <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="ca1ac-107"><xref:System.Windows.Controls.Primitives.Popup> Размещения происходит в момент, который предоставляет наилучшую видимость.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="ca1ac-108">В следующем примере показано, как определить положение <xref:System.Windows.Controls.Primitives.Popup> , задав <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойства <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="ca1ac-109">Также показано, как создать и назначить <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> делегат для расположения <xref:System.Windows.Controls.Primitives.Popup>.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="ca1ac-110">Делегат обратного вызова возвращает два <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> объектов.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="ca1ac-111">Если <xref:System.Windows.Controls.Primitives.Popup> скрыта за границу экрана позиции первого <xref:System.Windows.Controls.Primitives.Popup> помещается во второе положение.</span><span class="sxs-lookup"><span data-stu-id="ca1ac-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="ca1ac-112">Полный пример см. в разделе [пример размещения всплывающего окна](https://go.microsoft.com/fwlink/?LinkID=160032).</span><span class="sxs-lookup"><span data-stu-id="ca1ac-112">For the complete sample, see [Popup Placement Sample](https://go.microsoft.com/fwlink/?LinkID=160032).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1ac-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ca1ac-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="ca1ac-114">Общие сведения о контекстном меню</span><span class="sxs-lookup"><span data-stu-id="ca1ac-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="ca1ac-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="ca1ac-115">How-to Topics</span></span>](popup-how-to-topics.md)
