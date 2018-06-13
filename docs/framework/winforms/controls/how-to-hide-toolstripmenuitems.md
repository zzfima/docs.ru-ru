---
title: Практическое руководство. Сокрытие объектов ToolStripMenuItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 73f67bbe6b2d51a59b6f72ab5faf21db9d6db12d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531957"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="cad26-102">Практическое руководство. Сокрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="cad26-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="cad26-103">Скрытие пунктов меню служит для управления пользовательским интерфейсом приложения и ограничивать использование команд пользователями.</span><span class="sxs-lookup"><span data-stu-id="cad26-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="cad26-104">Часто необходимо скрыть меню целиком, когда все элементы меню недоступны.</span><span class="sxs-lookup"><span data-stu-id="cad26-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="cad26-105">Это меньше отвлекаться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="cad26-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="cad26-106">Кроме того может потребоваться скрыть и отключить меню или пункта меню, как скрытие не запрещает пользователю доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="cad26-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="cad26-107">Чтобы скрыть любой элемент меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="cad26-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="cad26-108">Внутри метода, в котором задаются свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="cad26-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cad26-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cad26-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="cad26-110">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="cad26-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="cad26-111">Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="cad26-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
