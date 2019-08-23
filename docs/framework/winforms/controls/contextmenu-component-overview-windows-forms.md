---
title: Общие сведения о компоненте ContextMenu (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962189"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Общие сведения о компоненте ContextMenu (Windows Forms)
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip>  
  
 С помощью компонента <xref:System.Windows.Forms.ContextMenu> Windows Forms можно предоставить пользователям легко доступное контекстное меню часто используемых команд, связанных с выбранным объектом. Элементы в контекстном меню часто являются подмножеством элементов из главных меню, которые появляются в других частях приложения. Обычно пользователь может получить доступ к контекстному меню, щелкнув его правой кнопкой мыши. В Windows Forms контекстные меню связаны с элементами управления.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Контекстное меню можно связать с элементом управления, присвоив <xref:System.Windows.Forms.Control.ContextMenu%2A> свойству <xref:System.Windows.Forms.ContextMenu> элемента управления компонент. Одно контекстное меню может быть связано с несколькими элементами управления, но у каждого элемента управления может быть только одно контекстное меню.  
  
 Ключевым свойством <xref:System.Windows.Forms.ContextMenu> компонента <xref:System.Windows.Forms.Menu.MenuItems%2A> является свойство. Элементы меню можно добавлять путем программного создания <xref:System.Windows.Forms.MenuItem> объектов и их добавления <xref:System.Windows.Forms.Menu.MenuItemCollection> в контекстное меню. Поскольку элементы в контекстном меню обычно выводятся из других меню, чаще всего добавляются элементы в контекстное меню путем их копирования.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
