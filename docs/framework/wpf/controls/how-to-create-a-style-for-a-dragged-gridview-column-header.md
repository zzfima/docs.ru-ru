---
title: Практическое руководство. Создание стиля для перетаскиваемого заголовка столбца GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: 442fff7a36a48d5df7ba9e07426e50f602cb93e8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357499"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="72dd7-102">Практическое руководство. Создание стиля для перетаскиваемого заголовка столбца GridView</span><span class="sxs-lookup"><span data-stu-id="72dd7-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="72dd7-103">В этом примере показано, как изменить внешний вид перетаскиваемого <xref:System.Windows.Controls.GridViewColumnHeader> когда пользователь изменяет положение столбца.</span><span class="sxs-lookup"><span data-stu-id="72dd7-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72dd7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="72dd7-104">Example</span></span>  
 <span data-ttu-id="72dd7-105">При перетаскивании заголовка столбца в другое расположение в <xref:System.Windows.Controls.ListView> , использующий <xref:System.Windows.Controls.GridView> для режима просмотра, столбец перемещается в новое положение.</span><span class="sxs-lookup"><span data-stu-id="72dd7-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="72dd7-106">При перетаскивании заголовка столбца, а также исходный заголовок появится с плавающей запятой копия заголовок.</span><span class="sxs-lookup"><span data-stu-id="72dd7-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="72dd7-107">Заголовок столбца в <xref:System.Windows.Controls.GridView> представленного <xref:System.Windows.Controls.GridViewColumnHeader> объекта.</span><span class="sxs-lookup"><span data-stu-id="72dd7-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="72dd7-108">Чтобы настроить внешний вид заголовков с плавающей запятой и исходное, можно задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменение <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="72dd7-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="72dd7-109">Эти <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> применяются при <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> свойство имеет значение `true` и <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> свойство имеет значение <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="72dd7-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="72dd7-110">Когда пользователь нажимает кнопку мыши и удерживании его, когда указатель мыши задерживается на <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> для изменения значения свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="72dd7-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="72dd7-111">Аналогичным образом, в том случае, когда пользователь начинает операцию перетаскивания, <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> изменения свойств <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span><span class="sxs-lookup"><span data-stu-id="72dd7-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="72dd7-112">В следующем примере показано, как задать <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> изменение <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.Background%2A> цвета заголовков исходного и с плавающей запятой, когда пользователь перетаскивает столбца в новую позицию.</span><span class="sxs-lookup"><span data-stu-id="72dd7-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="72dd7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="72dd7-113">See also</span></span>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="72dd7-114">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="72dd7-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="72dd7-115">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="72dd7-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="72dd7-116">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="72dd7-116">GridView Overview</span></span>](gridview-overview.md)
