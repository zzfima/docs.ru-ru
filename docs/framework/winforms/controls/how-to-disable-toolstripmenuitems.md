---
title: "Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3307da3e0810ea775c799a4b065e1f7484b5779
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="aaa40-102">Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="aaa40-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="aaa40-103">Можно ограничить или расширить набор команд, которые может выбрать пользователь, включение и отключение элементов меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="aaa40-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="aaa40-104">Пункты меню включены по умолчанию, если они были созданы, но это можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="aaa40-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="aaa40-105">Можно изменить значение этого свойства во время разработки в **свойства** окна или программным путем установки его в код.</span><span class="sxs-lookup"><span data-stu-id="aaa40-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="aaa40-106">Чтобы отключить элемент меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="aaa40-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="aaa40-107">Внутри метода, в котором задаются свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="aaa40-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="aaa40-108">Отключение элемента меню первой или верхнего уровня в меню скрывает все пункты меню, меню, но не отключает их.</span><span class="sxs-lookup"><span data-stu-id="aaa40-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="aaa40-109">Аналогичным образом отключение пункта меню, который имеет вложенное скрывает элементы вложенного меню, но не отключает их.</span><span class="sxs-lookup"><span data-stu-id="aaa40-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="aaa40-110">Если все команды конкретного меню недоступны пользователю, он считается хорошим стилем программирования, как скрыть и отключить всего меню, это представляет чистой пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="aaa40-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="aaa40-111">Необходимо скрыть и отключить меню и отключить каждый элемент и элемент вложенного меню в меню, поскольку скрытие меню не запрещает доступ к командам меню с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="aaa40-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="aaa40-112">Задать <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства элемента меню верхнего уровня для `false` скрыть меню целиком.</span><span class="sxs-lookup"><span data-stu-id="aaa40-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa40-113">См. также</span><span class="sxs-lookup"><span data-stu-id="aaa40-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="aaa40-114">Практическое руководство. Скрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="aaa40-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="aaa40-115">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="aaa40-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
