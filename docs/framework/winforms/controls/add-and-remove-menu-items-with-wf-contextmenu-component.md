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
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms
Объясняется, как добавлять и удалять элементы контекстного меню в Windows Forms.  
  
 Компонент Windows Forms <xref:System.Windows.Forms.ContextMenu> предоставляет меню часто используемых команд, относящихся к выбранному объекту. В контекстное меню можно добавлять элементы, добавляя <xref:System.Windows.Forms.MenuItem> объекты <xref:System.Windows.Forms.Menu.MenuItems%2A> в коллекцию.  
  
 Элементы контекстного меню можно удалить без возможности восстановления. Тем не менее во время выполнения может быть более уместно скрывать или отключать элементы.  
  
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Удаление элементов из контекстного меню  
  
1. Используйте метод <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> коллекции<xref:System.Windows.Forms.ContextMenu>компонента или для удаления определенного элемента меню. <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> <xref:System.Windows.Forms.Menu.MenuItems%2A>  
  
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
  
     -или-  
  
2. `Clear` Используйте метод `MenuItems` коллекции компонента,чтобыудалитьвсеэлементыизменю.<xref:System.Windows.Forms.ContextMenu>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ContextMenu>
- [Компонент ContextMenu](contextmenu-component-windows-forms.md)
- [Общие сведения об элементе управления ContextMenu](contextmenu-component-overview-windows-forms.md)
