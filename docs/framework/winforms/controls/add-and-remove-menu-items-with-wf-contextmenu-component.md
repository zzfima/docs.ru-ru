---
title: Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 5d1862b1fc1398f0f8c2217b51c4efb93db639af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957023"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="31e9d-102">Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31e9d-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="31e9d-103">Объясняется, как добавлять и удалять элементы контекстного меню в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="31e9d-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="31e9d-104">Компонент Windows Forms <xref:System.Windows.Forms.ContextMenu> предоставляет меню часто используемых команд, относящихся к выбранному объекту.</span><span class="sxs-lookup"><span data-stu-id="31e9d-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="31e9d-105">В контекстное меню можно добавлять элементы, добавляя <xref:System.Windows.Forms.MenuItem> объекты <xref:System.Windows.Forms.Menu.MenuItems%2A> в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="31e9d-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="31e9d-106">Элементы контекстного меню можно удалить без возможности восстановления. Тем не менее во время выполнения может быть более уместно скрывать или отключать элементы.</span><span class="sxs-lookup"><span data-stu-id="31e9d-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="31e9d-107">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="31e9d-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="31e9d-108">Удаление элементов из контекстного меню</span><span class="sxs-lookup"><span data-stu-id="31e9d-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="31e9d-109">Используйте метод <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> коллекции<xref:System.Windows.Forms.ContextMenu>компонента или для удаления определенного элемента меню. <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> <xref:System.Windows.Forms.Menu.MenuItems%2A></span><span class="sxs-lookup"><span data-stu-id="31e9d-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="31e9d-110">-или-</span><span class="sxs-lookup"><span data-stu-id="31e9d-110">-or-</span></span>  
  
2. <span data-ttu-id="31e9d-111">`Clear` Используйте метод `MenuItems` коллекции компонента,чтобыудалитьвсеэлементыизменю.<xref:System.Windows.Forms.ContextMenu></span><span class="sxs-lookup"><span data-stu-id="31e9d-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="31e9d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="31e9d-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="31e9d-113">Компонент ContextMenu</span><span class="sxs-lookup"><span data-stu-id="31e9d-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="31e9d-114">Общие сведения об элементе управления ContextMenu</span><span class="sxs-lookup"><span data-stu-id="31e9d-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
