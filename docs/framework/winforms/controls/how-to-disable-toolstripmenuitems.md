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
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046227"
---
# <a name="how-to-disable-toolstripmenuitems"></a>Практическое руководство. Отключение объектов ToolStripMenuItem
Вы можете ограничить или расширить команды, которые может выполнять пользователь, включив и отключив пункты меню в ответ на действия пользователя. Элементы меню включаются по умолчанию при их создании, но их можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства. Вы можете управлять этим свойством во время разработки в окне **свойств** или программным путем, настроив его в коде.  
  
### <a name="to-disable-a-menu-item-programmatically"></a>Отключение элемента меню программными средствами  
  
- В методе, где задаются свойства пункта меню, добавьте код для присвоения <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> `false`свойству значения.  
  
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
    > Отключение первого элемента меню или пункта верхнего уровня в меню скрывает все пункты меню, содержащиеся в меню, но не отключает их. Аналогично, отключение элемента меню с элементами подменю скрывает пункты подменю, но не отключает их. Если для пользователя недоступны все команды в данном меню, рекомендуется как скрывать, так и отключать все меню, так как это представляет собой чистый пользовательский интерфейс. Следует скрывать и отключать меню, а также отключать все элементы и пункты подменю в меню, поскольку скрытие отдельного элемента не мешает доступу к команде меню с помощью сочетания клавиш. `false` Задайте для свойства пункта меню верхнего уровня значение, чтобы скрыть меню целиком. <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Практическое руководство. Скрыть объектов ToolStripMenuItem](how-to-hide-toolstripmenuitems.md)
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
