---
title: "Как создать стиль для перетаскиваемого заголовка столбца GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 001d0ec45ad990ef366e7fc1216a7370aade9cb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="521d5-102">Как создать стиль для перетаскиваемого заголовка столбца GridView</span><span class="sxs-lookup"><span data-stu-id="521d5-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="521d5-103">В этом примере показано, как изменить внешний вид перетаскиваемого <xref:System.Windows.Controls.GridViewColumnHeader> когда пользователь изменяет положение столбца.</span><span class="sxs-lookup"><span data-stu-id="521d5-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="521d5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="521d5-104">Example</span></span>  
 <span data-ttu-id="521d5-105">Если перетащить заголовок столбца в другое место <xref:System.Windows.Controls.ListView> , использующий <xref:System.Windows.Controls.GridView> для режима просмотра, столбец перемещается на новое место.</span><span class="sxs-lookup"><span data-stu-id="521d5-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="521d5-106">При перетаскивании заголовка столбца, перемещаемая копия заголовка возникает вместе с исходного заголовка.</span><span class="sxs-lookup"><span data-stu-id="521d5-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="521d5-107">Заголовок столбца в <xref:System.Windows.Controls.GridView> представленного <xref:System.Windows.Controls.GridViewColumnHeader> объекта.</span><span class="sxs-lookup"><span data-stu-id="521d5-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="521d5-108">Чтобы настроить внешний вид перемещаемого и исходного заголовка, можно задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменить <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="521d5-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="521d5-109">Эти <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> применяются при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> значение свойства `true` и <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> значение свойства <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="521d5-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="521d5-110">Когда пользователь нажимает кнопку мыши и удерживании его, когда указатель мыши задерживается на <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> примет значение свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="521d5-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="521d5-111">Аналогичным образом, в том случае, когда пользователь начинает операцию перетаскивания, <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> изменения свойств <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="521d5-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="521d5-112">Следующий пример показывает, как задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменение <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.Background%2A> цвета заголовков исходного и с плавающей запятой при перетаскивании столбец в новое место.</span><span class="sxs-lookup"><span data-stu-id="521d5-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="521d5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="521d5-113">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="521d5-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="521d5-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="521d5-115">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="521d5-115">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="521d5-116">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="521d5-116">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
