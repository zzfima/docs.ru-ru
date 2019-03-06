---
title: Практическое руководство. Проверка видимости GridSplitter
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 0e1984241c07a69e2b350a61dc5873716c6fa5df
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375692"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a><span data-ttu-id="4cb2c-102">Практическое руководство. Проверка видимости GridSplitter</span><span class="sxs-lookup"><span data-stu-id="4cb2c-102">How to: Make Sure That a GridSplitter Is Visible</span></span>
<span data-ttu-id="4cb2c-103">В этом примере показано, как убедитесь, что <xref:System.Windows.Controls.GridSplitter> элемент управления не скрыт другими элементами управления в <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-103">This example shows how to make sure a <xref:System.Windows.Controls.GridSplitter> control is not hidden by the other controls in a <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cb2c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4cb2c-104">Example</span></span>  
 <span data-ttu-id="4cb2c-105"><xref:System.Windows.Controls.Panel.Children%2A> Из <xref:System.Windows.Controls.Grid> управления отображаются в порядке, в котором они определены в разметку или код.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-105">The <xref:System.Windows.Controls.Panel.Children%2A> of a <xref:System.Windows.Controls.Grid> control are rendered in the order that they are defined in markup or code.</span></span> <span data-ttu-id="4cb2c-106"><xref:System.Windows.Controls.GridSplitter> элементы управления могут быть скрыты другими элементами управления, если их не следует определять как последними элементами в <xref:System.Windows.Controls.Panel.Children%2A> коллекции или задать для других элементов более высокое <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-106"><xref:System.Windows.Controls.GridSplitter> controls can be hidden by other controls if you do not define them as the last elements in the <xref:System.Windows.Controls.Panel.Children%2A> collection or if you give other controls a higher <xref:System.Windows.Controls.Panel.ZIndexProperty>.</span></span>  
  
 <span data-ttu-id="4cb2c-107">Чтобы избежать скрытого <xref:System.Windows.Controls.GridSplitter> элементов управления, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-107">To prevent hidden <xref:System.Windows.Controls.GridSplitter> controls, do one of the following.</span></span>  
  
-   <span data-ttu-id="4cb2c-108">Убедитесь, что <xref:System.Windows.Controls.GridSplitter> элементы управления являются последнего <xref:System.Windows.Controls.Panel.Children%2A> добавляемый <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-108">Make sure that <xref:System.Windows.Controls.GridSplitter> controls are the last <xref:System.Windows.Controls.Panel.Children%2A> added to the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="4cb2c-109">В следующем примере показан <xref:System.Windows.Controls.GridSplitter> как последний элемент в <xref:System.Windows.Controls.Panel.Children%2A> коллекцию <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-109">The following example shows the <xref:System.Windows.Controls.GridSplitter> as the last element in the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <span data-ttu-id="4cb2c-110">Задайте <xref:System.Windows.Controls.Panel.ZIndexProperty> на <xref:System.Windows.Controls.GridSplitter> будет больше, чем элемент управления, в противном случае будет скрыть его.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-110">Set the <xref:System.Windows.Controls.Panel.ZIndexProperty> on the <xref:System.Windows.Controls.GridSplitter> to be higher than a control that would otherwise hide it.</span></span> <span data-ttu-id="4cb2c-111">Следующий пример дает <xref:System.Windows.Controls.GridSplitter> управления выше <xref:System.Windows.Controls.Panel.ZIndexProperty> чем <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-111">The following example gives the <xref:System.Windows.Controls.GridSplitter> control a higher <xref:System.Windows.Controls.Panel.ZIndexProperty> than the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <span data-ttu-id="4cb2c-112">Установка полей элемента управления, в противном случае скроет <xref:System.Windows.Controls.GridSplitter> таким образом, чтобы <xref:System.Windows.Controls.GridSplitter> предоставляется.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-112">Set margins on the control that would otherwise hide the <xref:System.Windows.Controls.GridSplitter> so that the <xref:System.Windows.Controls.GridSplitter> is exposed.</span></span> <span data-ttu-id="4cb2c-113">В следующем примере задается поля на элемент управления, в противном случае будет наложения и скрыть <xref:System.Windows.Controls.GridSplitter>.</span><span class="sxs-lookup"><span data-stu-id="4cb2c-113">The following example sets margins on a control that would otherwise overlay and hide the <xref:System.Windows.Controls.GridSplitter>.</span></span>  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a><span data-ttu-id="4cb2c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4cb2c-114">See also</span></span>
- <xref:System.Windows.Controls.GridSplitter>
- [<span data-ttu-id="4cb2c-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="4cb2c-115">How-to Topics</span></span>](gridsplitter-how-to-topics.md)
