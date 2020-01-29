---
title: Общие сведения об элементе управления MenuStrip
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734468"
---
# <a name="menustrip-control-overview-windows-forms"></a>Общие сведения об элементе управления MenuStrip (Windows Forms)
Меню предоставляют пользователям функциональные возможности, сохраняя команды, сгруппированные по общей теме.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> был представлен в версии 2,0 .NET Framework. С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно легко создавать меню, аналогичные тем, которые находятся в Microsoft Office.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает многодокументный интерфейс (MDI) и слияние меню, всплывающие подсказки и переполнение. Вы можете повысить удобство использования и удобочитаемость меню, добавив ключи доступа, сочетания клавиш, флажки, изображения и разделители.  
  
 Элемент управления <xref:System.Windows.Forms.MenuStrip> заменяет и расширяет функциональные возможности элемента управления <xref:System.Windows.Forms.MainMenu>; Однако элемент управления <xref:System.Windows.Forms.MainMenu> сохраняется для обеспечения обратной совместимости и использования в будущем при выборе.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Способы использования элемента управления MenuStrip  
 Используйте элемент управления <xref:System.Windows.Forms.MenuStrip> для:  
  
- Создание легко настраиваемых, часто используемых меню, поддерживающих расширенные функции пользовательского интерфейса и макета, таких как упорядочение текста и изображений и выравнивание, операции перетаскивания, MDI, переполнение и альтернативные режимы доступа к командам меню.  
  
- Поддержка типичного внешнего вида и поведения операционной системы.  
  
- Согласованность событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.  
  
 В следующей таблице приведены некоторые особо важные свойства <xref:System.Windows.Forms.MenuStrip> и связанных классов.  
  
|Идентификаторы|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Возвращает или задает <xref:System.Windows.Forms.ToolStripMenuItem>, используемый для вывода списка дочерних MDI-форм.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Возвращает или задает, как дочерние меню объединяются с родительскими меню в приложениях MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Возвращает или задает позицию объединенного элемента в меню в приложениях MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Возвращает или задает значение, указывающее, является ли форма контейнером для дочерних форм MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Возвращает или задает значение, указывающее, отображаются ли подсказки для <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.MenuStrip> область переполнения.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Возвращает или задает сочетания клавиш, связанные с <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Возвращает или задает значение, указывающее, отображаются ли сочетания клавиш, связанные с <xref:System.Windows.Forms.ToolStripMenuItem>, рядом с <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 В следующей таблице показаны важные <xref:System.Windows.Forms.MenuStrip> сопутствующие классы.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Представляет выбираемый параметр, отображаемый в <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Представляет контекстное меню.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или пункт меню более высокого уровня.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Предоставляет базовые функциональные возможности для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem>, которые отображают раскрывающиеся элементы при щелчке.|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
