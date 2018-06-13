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
ms.openlocfilehash: 5d548815533e8f9bb37ad00129a5ae526612ea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526127"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Общие сведения о компоненте ContextMenu (Windows Forms)
> [!IMPORTANT]
>  Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функциональные возможности в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбрать.  
  
 С помощью Windows Forms <xref:System.Windows.Forms.ContextMenu> компонента, вы можете предоставить пользователям доступного контекстного меню часто используемых команд, связанных с выделенным объектом. Элементы контекстного меню часто представляют собой подмножество элементов из главного меню, которые отображаются в другом месте в приложении. Как правило, пользователь может открыть контекстное меню щелчком правой кнопки мыши. В формах Windows Forms контекстные меню связаны с элементами управления.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Контекстное меню можно связать с элементом управления, присвоив свойству элемента управления <xref:System.Windows.Forms.Control.ContextMenu%2A> свойства <xref:System.Windows.Forms.ContextMenu> компонента. Одно контекстное меню можно связать с несколькими элементами управления, но каждый элемент управления может иметь только одно контекстное меню.  
  
 Ключевое свойство <xref:System.Windows.Forms.ContextMenu> компонент является <xref:System.Windows.Forms.Menu.MenuItems%2A> свойства. Можно добавить элементы меню, создание программным путем <xref:System.Windows.Forms.MenuItem> объектов и добавления их в <xref:System.Windows.Forms.Menu.MenuItemCollection> контекстного меню. Так как элементы в контекстном меню, обычно являются производными от других меню, чаще всего будет добавления элементов в контекстном меню, скопировав их.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
