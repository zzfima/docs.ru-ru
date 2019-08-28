---
title: Практическое руководство. Отключение объектов ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046227"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="1564e-102">Практическое руководство. Отключение объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="1564e-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="1564e-103">Вы можете ограничить или расширить команды, которые может выполнять пользователь, включив и отключив пункты меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="1564e-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="1564e-104">Элементы меню включаются по умолчанию при их создании, но их можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="1564e-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="1564e-105">Вы можете управлять этим свойством во время разработки в окне **свойств** или программным путем, настроив его в коде.</span><span class="sxs-lookup"><span data-stu-id="1564e-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="1564e-106">Отключение элемента меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="1564e-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="1564e-107">В методе, где задаются свойства пункта меню, добавьте код для присвоения <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false`свойству значения.</span><span class="sxs-lookup"><span data-stu-id="1564e-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="1564e-108">Отключение первого элемента меню или пункта верхнего уровня в меню скрывает все пункты меню, содержащиеся в меню, но не отключает их.</span><span class="sxs-lookup"><span data-stu-id="1564e-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="1564e-109">Аналогично, отключение элемента меню с элементами подменю скрывает пункты подменю, но не отключает их.</span><span class="sxs-lookup"><span data-stu-id="1564e-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="1564e-110">Если для пользователя недоступны все команды в данном меню, рекомендуется как скрывать, так и отключать все меню, так как это представляет собой чистый пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1564e-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="1564e-111">Следует скрывать и отключать меню, а также отключать все элементы и пункты подменю в меню, поскольку скрытие отдельного элемента не мешает доступу к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="1564e-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="1564e-112">`false` Задайте для свойства пункта меню верхнего уровня значение, чтобы скрыть меню целиком. <xref:System.Windows.Forms.ToolStripItem.Visible%2A></span><span class="sxs-lookup"><span data-stu-id="1564e-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1564e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="1564e-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="1564e-114">Практическое руководство. Скрыть объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="1564e-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="1564e-115">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="1564e-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
