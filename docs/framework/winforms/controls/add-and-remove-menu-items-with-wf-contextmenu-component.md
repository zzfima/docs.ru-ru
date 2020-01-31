---
title: Добавление и удаление пунктов меню с помощью компонента ContextMenu
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
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746270"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Практическое руководство. Добавление и удаление элементов меню с помощью компонента ContextMenu в Windows Forms
Объясняется, как добавлять и удалять элементы контекстного меню в Windows Forms.  
  
 Компонент Windows Forms <xref:System.Windows.Forms.ContextMenu> предоставляет меню часто используемых команд, относящихся к выбранному объекту. Вы можете добавить элементы в контекстное меню, добавив <xref:System.Windows.Forms.MenuItem> объекты в коллекцию <xref:System.Windows.Forms.Menu.MenuItems%2A>.  
  
 Элементы контекстного меню можно удалить без возможности восстановления. Тем не менее во время выполнения может быть более уместно скрывать или отключать элементы.  
  
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Удаление элементов из контекстного меню  
  
1. Чтобы удалить определенный пункт меню, используйте метод <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> или <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> коллекции <xref:System.Windows.Forms.Menu.MenuItems%2A> компонента <xref:System.Windows.Forms.ContextMenu>.  
  
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
  
     \- или -  
  
2. Используйте метод `Clear` коллекции `MenuItems` компонента <xref:System.Windows.Forms.ContextMenu>, чтобы удалить все элементы из меню.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ContextMenu>
- [Компонент ContextMenu](contextmenu-component-windows-forms.md)
- [Общие сведения об элементе управления ContextMenu](contextmenu-component-overview-windows-forms.md)
