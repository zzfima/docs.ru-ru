---
title: Как выполнить Отключение объектов ToolStripMenuItem
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
ms.openlocfilehash: 2516080708bba207c3a1d028f2e5a2411974ae5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705340"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Как выполнить Отключение объектов ToolStripMenuItem
Можно ограничить или расширить набор команд, которые может выполнять пользователь, включение и отключение элементов меню в ответ на действия пользователя. Пункты меню включены по умолчанию, когда они создаются, но его можно настроить через <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство. Можно изменить значение этого свойства во время разработки в **свойства** окна или программным способом, задав его в код.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Чтобы отключить пункт меню программными средствами  
  
-   В методе, где задать свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.  
  
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
    >  Отключение элемента меню первый или верхнего уровня в меню скрывает все пункты меню, меню, но не их отключению. Аналогичным образом отключение элемента меню, который имеет вложенное скрывает элементы вложенного меню, но не их отключению. Если все команды конкретного меню недоступны для пользователя, он считается хорошим стилем программирования, как скрыть и отключить всего меню, как это представляет собой интерфейс пользователя. Следует скрыть и отключить меню и отключить каждый элемент и элемент вложенного меню в меню, так как скрытие не запрещает доступ к командам меню с помощью сочетаний клавиш. Задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство пункта меню верхнего уровня к `false` скрыть меню целиком.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Практическое руководство. Скрытие объектов ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)
- [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
