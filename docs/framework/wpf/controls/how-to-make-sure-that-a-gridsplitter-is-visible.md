---
title: Практическое руководство. Проверка видимости GridSplitter
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147151"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="1a58f-102">Практическое руководство. Проверка видимости GridSplitter</span><span class="sxs-lookup"><span data-stu-id="1a58f-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="1a58f-103">В этом примере показано, как убедитесь, что <xref:System.Windows.Controls.GridSplitter> элемент управления не скрыт другими элементами управления в <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="1a58f-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a58f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1a58f-104">Example</span></span>  
 <span data-ttu-id="1a58f-105"><xref:System.Windows.Controls.Panel.Children%2A> Из <xref:System.Windows.Controls.Grid> управления отображаются в порядке, в котором они определены в разметку или код.</span><span class="sxs-lookup"><span data-stu-id="1a58f-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <xref:System.Windows.Controls.GridSplitter> <span data-ttu-id="1a58f-106">элементы управления могут быть скрыты другими элементами управления, если их не следует определять как последними элементами в <xref:System.Windows.Controls.Panel.Children%2A> коллекции или задать для других элементов более высокое <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="1a58f-106">controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="1a58f-107">Чтобы избежать скрытого <xref:System.Windows.Controls.GridSplitter> элементов управления, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1a58f-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="1a58f-108">Убедитесь, что <xref:System.Windows.Controls.GridSplitter> элементы управления являются последнего <xref:System.Windows.Controls.Panel.Children%2A> добавляемый <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="1a58f-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="1a58f-109">В следующем примере показан <xref:System.Windows.Controls.GridSplitter> как последний элемент в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="1a58f-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="1a58f-110">Задайте <xref:System.Windows.Controls.Panel.ZIndexProperty> на <xref:System.Windows.Controls.GridSplitter> будет больше, чем элемент управления, в противном случае будет скрыть его.</span><span class="sxs-lookup"><span data-stu-id="1a58f-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="1a58f-111">Следующий пример дает <xref:System.Windows.Controls.GridSplitter> управления выше <xref:System.Windows.Controls.Panel.ZIndexProperty> чем <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a58f-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="1a58f-112">Установка полей элемента управления, в противном случае скроет <xref:System.Windows.Controls.GridSplitter> таким образом, чтобы <xref:System.Windows.Controls.GridSplitter> предоставляется.</span><span class="sxs-lookup"><span data-stu-id="1a58f-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="1a58f-113">В следующем примере задается поля на элемент управления, в противном случае будет наложения и скрыть <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="1a58f-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="1a58f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1a58f-114">See also</span></span>

- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="1a58f-115">Практические руководства</span><span class="sxs-lookup"><span data-stu-id="1a58f-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
