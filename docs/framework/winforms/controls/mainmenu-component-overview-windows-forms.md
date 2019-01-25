---
title: Общие сведения о компоненте MainMenu (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 529b57ed443791b87331358a7e6c420dd63933a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700628"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Общие сведения о компоненте MainMenu (Windows Forms)
> [!IMPORTANT]
>  Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления из предыдущих версий <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбран.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> компонент отображает меню во время выполнения. Все подменю из главного меню и отдельные элементы отображаются <xref:System.Windows.Forms.MenuItem> объектов.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Пункт меню может быть объявлен как элемент по умолчанию, задав <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> свойства `true`. Элемент по умолчанию отображается полужирным шрифтом, при выборе меню. Элемент меню <xref:System.Windows.Forms.MenuItem.Checked%2A> свойство `true` или `false`и указывает, выбран ли элемент меню. Элемент меню <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> свойство настраивает внешний вид выбранного элемента: Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> присваивается `true`, типа "переключатель" отображается рядом с элементом; Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> имеет значение `false`, появится флажок рядом с элементом.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
