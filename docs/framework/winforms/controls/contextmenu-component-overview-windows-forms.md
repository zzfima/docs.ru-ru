---
title: Общие сведения об элементе управления ContextMenu
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746196"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Общие сведения о компоненте ContextMenu (Windows Forms)
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.  
  
 С помощью компонента Windows Forms <xref:System.Windows.Forms.ContextMenu> можно предоставить пользователям легко доступное контекстное меню часто используемых команд, связанных с выбранным объектом. Элементы в контекстном меню часто являются подмножеством элементов из главных меню, которые появляются в других частях приложения. Обычно пользователь может получить доступ к контекстному меню, щелкнув его правой кнопкой мыши. В Windows Forms контекстные меню связаны с элементами управления.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Контекстное меню можно связать с элементом управления, присвоив свойству <xref:System.Windows.Forms.Control.ContextMenu%2A> элемента управления компоненту <xref:System.Windows.Forms.ContextMenu>. Одно контекстное меню может быть связано с несколькими элементами управления, но у каждого элемента управления может быть только одно контекстное меню.  
  
 Ключевым свойством <xref:System.Windows.Forms.ContextMenu> компонента является свойство <xref:System.Windows.Forms.Menu.MenuItems%2A>. Элементы меню можно добавлять путем программного создания объектов <xref:System.Windows.Forms.MenuItem> и их добавления в <xref:System.Windows.Forms.Menu.MenuItemCollection> контекстного меню. Поскольку элементы в контекстном меню обычно выводятся из других меню, чаще всего добавляются элементы в контекстное меню путем их копирования.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
