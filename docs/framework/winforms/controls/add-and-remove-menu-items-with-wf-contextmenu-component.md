---
title: Как выполнить Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms
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
ms.openlocfilehash: ac554f080cdabc7034ca839c3a9086e927429f7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520039"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="d451c-102">Как выполнить Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d451c-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="d451c-103">Объясняется, как добавлять и удалять элементы контекстного меню в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d451c-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="d451c-104">Windows Forms <xref:System.Windows.Forms.ContextMenu> компонент предоставляет меню часто используемых команд, относящихся к выбранному объекту.</span><span class="sxs-lookup"><span data-stu-id="d451c-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="d451c-105">Элементы добавляются в контекстное меню, добавив <xref:System.Windows.Forms.MenuItem> объектов <xref:System.Windows.Forms.Menu.MenuItems%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d451c-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="d451c-106">Элементы контекстного меню можно удалить без возможности восстановления; Тем не менее во время выполнения он может быть более подходящим для скрытия или отключение элементов.</span><span class="sxs-lookup"><span data-stu-id="d451c-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d451c-107">Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления из предыдущих версий <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбран.</span><span class="sxs-lookup"><span data-stu-id="d451c-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="d451c-108">Чтобы удалить элементы из контекстного меню</span><span class="sxs-lookup"><span data-stu-id="d451c-108">To remove items from a shortcut menu</span></span>  
  
1.  <span data-ttu-id="d451c-109">Используйте <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> или <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> метод <xref:System.Windows.Forms.Menu.MenuItems%2A> коллекцию <xref:System.Windows.Forms.ContextMenu> компонента для удаления определенного элемента меню.</span><span class="sxs-lookup"><span data-stu-id="d451c-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="d451c-110">- или -</span><span class="sxs-lookup"><span data-stu-id="d451c-110">-or-</span></span>  
  
2.  <span data-ttu-id="d451c-111">Используйте `Clear` метод `MenuItems` коллекцию <xref:System.Windows.Forms.ContextMenu> компонента для удаления всех элементов в меню.</span><span class="sxs-lookup"><span data-stu-id="d451c-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d451c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d451c-112">See also</span></span>
- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="d451c-113">Компонент ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d451c-113">ContextMenu Component</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)
- [<span data-ttu-id="d451c-114">Общие сведения об элементе управления ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d451c-114">ContextMenu Component Overview</span></span>](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)
