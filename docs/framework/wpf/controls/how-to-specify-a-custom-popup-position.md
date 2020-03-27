---
title: Практическое руководство. Указание пользовательского расположения контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Popup control [WPF], specifying custom position
ms.assetid: 28c24f39-d3aa-4ee2-b950-384b4a5dab92
ms.openlocfilehash: ea8d73c51dd018608b95104f00bf341ff434225c
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344954"
---
# <a name="how-to-specify-a-custom-popup-position"></a><span data-ttu-id="418b2-102">Практическое руководство. Указание пользовательского расположения контекстного меню</span><span class="sxs-lookup"><span data-stu-id="418b2-102">How to: Specify a Custom Popup Position</span></span>
<span data-ttu-id="418b2-103">В этом примере показано, как <xref:System.Windows.Controls.Primitives.Popup> указать <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> пользовательское <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>положение для элемента управления, когда свойство настроено на управление.</span><span class="sxs-lookup"><span data-stu-id="418b2-103">This example shows how to specify a custom position for a <xref:System.Windows.Controls.Primitives.Popup> control when the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="418b2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="418b2-104">Example</span></span>  
 <span data-ttu-id="418b2-105">Когда <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> свойство настроено <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> <xref:System.Windows.Controls.Primitives.Popup> на, вызовы <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> определенного экземпляра делегата.</span><span class="sxs-lookup"><span data-stu-id="418b2-105">When the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property is set to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>, the <xref:System.Windows.Controls.Primitives.Popup> calls a defined instance of the <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate.</span></span> <span data-ttu-id="418b2-106">Этот делегат возвращает набор возможных точек, которые по отношению к верхнему <xref:System.Windows.Controls.Primitives.Popup>левому углу целевой области и верхнему левому углу .</span><span class="sxs-lookup"><span data-stu-id="418b2-106">This delegate returns a set of possible points that are relative to the top left corner of the target area and the top left corner of the <xref:System.Windows.Controls.Primitives.Popup>.</span></span> <span data-ttu-id="418b2-107">Размещение <xref:System.Windows.Controls.Primitives.Popup> происходит в точке, которая обеспечивает лучшую видимость.</span><span class="sxs-lookup"><span data-stu-id="418b2-107">The <xref:System.Windows.Controls.Primitives.Popup> placement occurs at the point that provides the best visibility.</span></span>  
  
 <span data-ttu-id="418b2-108">Ниже приводится следующий <xref:System.Windows.Controls.Primitives.Popup> пример, как определить <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> положение <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>свойства, установив свойство для .</span><span class="sxs-lookup"><span data-stu-id="418b2-108">The following example shows how to define the position of a <xref:System.Windows.Controls.Primitives.Popup> by setting the <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> property to <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>.</span></span> <span data-ttu-id="418b2-109">Он также показывает, как создать <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> и назначить <xref:System.Windows.Controls.Primitives.Popup>делегата для того, чтобы позиционировать .</span><span class="sxs-lookup"><span data-stu-id="418b2-109">It also shows how to create and assign a <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> delegate in order to position the <xref:System.Windows.Controls.Primitives.Popup>.</span></span>  <span data-ttu-id="418b2-110">Делегат обратного вызова <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> возвращает два объекта.</span><span class="sxs-lookup"><span data-stu-id="418b2-110">The callback delegate returns two <xref:System.Windows.Controls.Primitives.CustomPopupPlacement> objects.</span></span>  <span data-ttu-id="418b2-111"><xref:System.Windows.Controls.Primitives.Popup> Если он скрыт краем экрана в <xref:System.Windows.Controls.Primitives.Popup> первом положении, то он помещается на втором.</span><span class="sxs-lookup"><span data-stu-id="418b2-111">If the <xref:System.Windows.Controls.Primitives.Popup> is hidden by a screen edge at the first position, the <xref:System.Windows.Controls.Primitives.Popup> is placed at the second position.</span></span>  
  
 [!code-xaml[PopupCustomPlacement#CustomPlacement](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml#customplacement)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateInstance](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegateinstance)]
 [!code-vb[PopupCustomPlacement#DelegateInstance](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegateinstance)]  
  
 [!code-csharp[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupCustomPlacement/CSharp/Window1.xaml.cs#delegatedefinition)]
 [!code-vb[PopupCustomPlacement#DelegateDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PopupCustomPlacement/visualbasic/window1.xaml.vb#delegatedefinition)]  
  
 <span data-ttu-id="418b2-112">Для полного образца [см.](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)</span><span class="sxs-lookup"><span data-stu-id="418b2-112">For the complete sample, see [Popup Placement Sample](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418b2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="418b2-113">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Popup>
- [<span data-ttu-id="418b2-114">Общие сведения о контекстном меню</span><span class="sxs-lookup"><span data-stu-id="418b2-114">Popup Overview</span></span>](popup-overview.md)
- [<span data-ttu-id="418b2-115">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="418b2-115">How-to Topics</span></span>](popup-how-to-topics.md)
