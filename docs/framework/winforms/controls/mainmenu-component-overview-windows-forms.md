---
title: Общие сведения о компоненте MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745112"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Общие сведения о компоненте MainMenu (Windows Forms)
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.  
  
 Компонент <xref:System.Windows.Forms.MainMenu> Windows Forms отображает меню во время выполнения. Все подменю главного меню и отдельные элементы являются <xref:System.Windows.Forms.MenuItem> объектами.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Элемент меню можно назначить в качестве элемента по умолчанию, задав свойству <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> значение `true`. Элемент по умолчанию отображается полужирным шрифтом при щелчке меню. <xref:System.Windows.Forms.MenuItem.Checked%2A>ым свойством элемента меню является `true` или `false`, а также показывает, выбран ли этот пункт меню. Свойство <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> элемента меню настраивает внешний вид выбранного элемента: Если для <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> задано значение `true`, рядом с элементом появляется переключатель. Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> имеет значение `false`, рядом с элементом отображается галочка.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
