---
title: Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem
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
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-disable-toolstripmenuitems"></a>Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem
Можно ограничить или расширить набор команд, которые может выбрать пользователь, включение и отключение элементов меню в ответ на действия пользователя. Пункты меню включены по умолчанию, если они были созданы, но это можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство. Можно изменить значение этого свойства во время разработки в **свойства** окна или программным путем установки его в код.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Чтобы отключить элемент меню программными средствами  
  
-   Внутри метода, в котором задаются свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.  
  
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
    >  Отключение элемента меню первой или верхнего уровня в меню скрывает все пункты меню, меню, но не отключает их. Аналогичным образом отключение пункта меню, который имеет вложенное скрывает элементы вложенного меню, но не отключает их. Если все команды конкретного меню недоступны пользователю, он считается хорошим стилем программирования, как скрыть и отключить всего меню, это представляет чистой пользовательского интерфейса. Необходимо скрыть и отключить меню и отключить каждый элемент и элемент вложенного меню в меню, поскольку скрытие меню не запрещает доступ к командам меню с помощью сочетаний клавиш. Задать <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства элемента меню верхнего уровня для `false` скрыть меню целиком.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Практическое руководство. Скрытие объектов ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
