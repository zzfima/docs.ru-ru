---
title: "Общие сведения об элементе управления MenuStrip (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06cd4e812f4acf546dad577a2e1ddc571281ebe3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="menustrip-control-overview-windows-forms"></a>Общие сведения об элементе управления MenuStrip (Windows Forms)
Меню предоставляют функциональные возможности для пользователей, удерживая команды, сгруппированные по общей теме.  
  
 <xref:System.Windows.Forms.MenuStrip> Управления является новой возможностью в этой версии Visual Studio и .NET Framework. С помощью элемента управления можно легко создать меню, например в Microsoft Office.  
  
 <xref:System.Windows.Forms.MenuStrip> Элемент управления поддерживает многодокументного интерфейса (MDI) и слияние меню, всплывающие подсказки и переполнения. Можно улучшить удобство использования и меню, добавив ключи доступа, сочетания клавиш, метки, изображения и разделителей.  
  
 <xref:System.Windows.Forms.MenuStrip> Управления заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.MainMenu> управления; Однако <xref:System.Windows.Forms.MainMenu> Если выбрать элемент управления можно сохранить для обратной совместимости и использования в будущем.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Способы использования элемента управления MenuStrip  
 Используйте <xref:System.Windows.Forms.MenuStrip> управления:  
  
-   Создание легко настраиваемых, стандартных меню, которые поддерживают дополнительные пользовательского интерфейса и макет функции, например текст и изображения упорядочение и выравнивание, операции перетаскивания и вставки, MDI, переполнение и альтернативные режимы доступа к пунктам меню.  
  
-   Поддерживает типичные внешний вид и поведение операционной системы.  
  
-   Обрабатывать события должен быть одинаковым для всех контейнеров и содержащихся элементов таким же образом обрабатывать события для других элементов управления.  
  
 В следующей таблице показаны некоторые особенно важные свойства <xref:System.Windows.Forms.MenuStrip> и связанных классов.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Возвращает или задает <xref:System.Windows.Forms.ToolStripMenuItem> , используемый для отображения списка дочерних MDI-форм.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Возвращает или задает способ слияния дочерних меню с родительскими меню в приложениях MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Возвращает или задает позицию элемента, объединенные в меню в приложениях MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Возвращает или задает значение, указывающее, является ли форма контейнером для дочерних MDI-форм.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Возвращает или задает значение, указывающее, отображаются ли всплывающие подсказки для <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.MenuStrip> область переполнения.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Возвращает или задает сочетания клавиш, связанных с <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Возвращает или задает значение, указывающее, будет ли сочетание клавиш, связанных с <xref:System.Windows.Forms.ToolStripMenuItem> отображаются рядом с <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 В следующей таблице показаны важные <xref:System.Windows.Forms.MenuStrip> сопутствующих классов.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Представляет отдельные пункты, отображаемые на <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Представляет контекстное меню.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь нажимает кнопку <xref:System.Windows.Forms.ToolStripDropDownButton> или пункта меню верхнего уровня.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Предоставляет базовые функциональные возможности для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem> , отображения элементов раскрывающегося списка при нажатии.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
