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
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952132"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Общие сведения о компоненте MainMenu (Windows Forms)
> [!IMPORTANT]
> Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip>  
  
 Компонент Windows Forms <xref:System.Windows.Forms.MainMenu> отображает меню во время выполнения. Все подменю главного меню и отдельных элементов являются <xref:System.Windows.Forms.MenuItem> объектами.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Элемент меню можно назначить в качестве элемента по умолчанию, задав <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> `true`свойству значение. Элемент по умолчанию отображается полужирным шрифтом при щелчке меню. <xref:System.Windows.Forms.MenuItem.Checked%2A> Свойство элемента меню имеет значение `true` или `false`, а также указывает, выбран ли пункт меню. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> Свойство элемента меню настраивает внешний вид выбранного элемента: Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> для `true`задано значение, рядом `false`с элементом появляется переключатель. Если <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> параметр имеет значение, рядом с элементом отображается галочка.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Общие сведения об элементе управления MenuStrip](menustrip-control-overview-windows-forms.md)
