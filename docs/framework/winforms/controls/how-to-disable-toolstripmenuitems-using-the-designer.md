---
title: Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046240"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="e6c49-102">Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e6c49-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="e6c49-103">Вы можете ограничить или расширить команды, которые может выполнять пользователь, включив и отключив пункты меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="e6c49-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="e6c49-104">Элементы меню включаются по умолчанию при их создании, но их можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="e6c49-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="e6c49-105">Вы можете управлять этим свойством во время разработки в окне **свойств** или программным путем, настроив его в коде.</span><span class="sxs-lookup"><span data-stu-id="e6c49-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="e6c49-106">Дополнительные сведения см. в разделе [Практическое руководство. Отключите объектов ToolStripMenuItem](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="e6c49-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="e6c49-107">Отключение элемента меню во время разработки</span><span class="sxs-lookup"><span data-stu-id="e6c49-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="e6c49-108">Выбрав пункт меню в форме, задайте <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> для `false`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="e6c49-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="e6c49-109">Отключение первого элемента меню или пункта верхнего уровня в меню отключает все пункты меню, содержащиеся в нем.</span><span class="sxs-lookup"><span data-stu-id="e6c49-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="e6c49-110">Аналогично, отключение элемента меню с элементами подменю отключает элементы вложенного меню.</span><span class="sxs-lookup"><span data-stu-id="e6c49-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="e6c49-111">Если для пользователя недоступны все команды в данном меню, рекомендуется как скрывать, так и отключать все меню, так как это представляет собой чистый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e6c49-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="e6c49-112">Следует скрывать и отключать меню, так как скрытие не запрещает доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="e6c49-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="e6c49-113">`false` Задайте для свойства пункта меню верхнего уровня значение, чтобы скрыть меню целиком. <xref:System.Windows.Forms.ToolStripItem.Visible%2A></span><span class="sxs-lookup"><span data-stu-id="e6c49-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6c49-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e6c49-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="e6c49-115">Практическое руководство. Скрыть объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="e6c49-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="e6c49-116">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="e6c49-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
