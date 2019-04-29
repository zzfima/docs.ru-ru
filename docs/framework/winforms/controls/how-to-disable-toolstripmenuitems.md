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
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954236"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="84558-102">Практическое руководство. Отключение объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="84558-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="84558-103">Можно ограничить или расширить набор команд, которые может выполнять пользователь, включение и отключение элементов меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="84558-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="84558-104">Пункты меню включены по умолчанию, когда они создаются, но его можно настроить через <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="84558-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="84558-105">Можно изменить значение этого свойства во время разработки в **свойства** окна или программным способом, задав его в код.</span><span class="sxs-lookup"><span data-stu-id="84558-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="84558-106">Чтобы отключить пункт меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="84558-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="84558-107">В методе, где задать свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="84558-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="84558-108">Отключение элемента меню первый или верхнего уровня в меню скрывает все пункты меню, меню, но не их отключению.</span><span class="sxs-lookup"><span data-stu-id="84558-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="84558-109">Аналогичным образом отключение элемента меню, который имеет вложенное скрывает элементы вложенного меню, но не их отключению.</span><span class="sxs-lookup"><span data-stu-id="84558-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="84558-110">Если все команды конкретного меню недоступны для пользователя, он считается хорошим стилем программирования, как скрыть и отключить всего меню, как это представляет собой интерфейс пользователя.</span><span class="sxs-lookup"><span data-stu-id="84558-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="84558-111">Следует скрыть и отключить меню и отключить каждый элемент и элемент вложенного меню в меню, так как скрытие не запрещает доступ к командам меню с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="84558-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="84558-112">Задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство пункта меню верхнего уровня к `false` скрыть меню целиком.</span><span class="sxs-lookup"><span data-stu-id="84558-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84558-113">См. также</span><span class="sxs-lookup"><span data-stu-id="84558-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="84558-114">Практическое руководство. Скрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="84558-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="84558-115">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="84558-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
