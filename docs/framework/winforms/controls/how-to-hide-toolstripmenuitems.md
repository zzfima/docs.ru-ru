---
title: Практическое руководство. Скрытие объектов ToolStripMenuItem
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
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127430"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="89ccd-102">Практическое руководство. Скрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="89ccd-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="89ccd-103">Скрытие пунктов меню — это способ управления пользовательским интерфейсом приложения и ограничить команды пользователя.</span><span class="sxs-lookup"><span data-stu-id="89ccd-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="89ccd-104">Часто требуется скрыть меню целиком, когда все элементы меню на нем будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="89ccd-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="89ccd-105">Это меньше отвлекаться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="89ccd-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="89ccd-106">Кроме того можно скрыть и отключить меню или пункта меню, как скрытие не запрещает пользователю доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="89ccd-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="89ccd-107">Чтобы скрыть любой элемент меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="89ccd-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="89ccd-108">В методе, где задать свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="89ccd-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="89ccd-109">См. также</span><span class="sxs-lookup"><span data-stu-id="89ccd-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="89ccd-110">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="89ccd-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="89ccd-111">Практическое руководство. Отключение объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="89ccd-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
