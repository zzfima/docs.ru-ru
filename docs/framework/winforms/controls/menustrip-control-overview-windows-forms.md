---
title: Общие сведения об элементе управления MenuStrip (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 46a3a25415db77ee261f5fb1c3bf114b2275a2d4
ms.sourcegitcommit: 8c6426a3d2adff5fbcbe1fed0f28eda718c15351
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2019
ms.locfileid: "68733459"
---
# <a name="menustrip-control-overview-windows-forms"></a>Общие сведения об элементе управления MenuStrip (Windows Forms)
Меню предоставляют пользователям функциональные возможности, сохраняя команды, сгруппированные по общей теме.  
  
 Этот <xref:System.Windows.Forms.MenuStrip> элемент управления появился в версии 2,0 .NET Framework. С помощью <xref:System.Windows.Forms.MenuStrip> этого элемента управления можно легко создавать меню, аналогичные тем, которые находятся в Microsoft Office.  
  
 <xref:System.Windows.Forms.MenuStrip> Элемент управления поддерживает многодокументный интерфейс (MDI) и слияние меню, всплывающие подсказки и переполнение. Вы можете повысить удобство использования и удобочитаемость меню, добавив ключи доступа, сочетания клавиш, флажки, изображения и разделители.  
  
 Элемент управления заменяет и расширяет функциональные возможности <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> элемента управления, однако он сохраняется для обеспечения обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.MenuStrip>  
  
## <a name="ways-to-use-the-menustrip-control"></a>Способы использования элемента управления MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> Используйте элемент управления для:  
  
- Создание легко настраиваемых, часто используемых меню, поддерживающих расширенные функции пользовательского интерфейса и макета, таких как упорядочение текста и изображений и выравнивание, операции перетаскивания, MDI, переполнение и альтернативные режимы доступа к командам меню.  
  
- Поддержка типичного внешнего вида и поведения операционной системы.  
  
- Согласованность событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.  
  
 В следующей таблице приведены некоторые особо важные свойства <xref:System.Windows.Forms.MenuStrip> и связанные классы.  
  
|Свойство.|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Возвращает или задает объект <xref:System.Windows.Forms.ToolStripMenuItem> , используемый для вывода списка дочерних MDI-форм.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Возвращает или задает, как дочерние меню объединяются с родительскими меню в приложениях MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Возвращает или задает позицию объединенного элемента в меню в приложениях MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Возвращает или задает значение, указывающее, является ли форма контейнером для дочерних форм MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Возвращает или задает значение, указывающее, отображаются ли подсказки для <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.MenuStrip> область переполнения.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Возвращает или задает сочетания клавиш, <xref:System.Windows.Forms.ToolStripMenuItem>связанные с.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Возвращает или задает значение, указывающее, отображаются ли сочетания клавиш, связанные с, <xref:System.Windows.Forms.ToolStripMenuItem> рядом <xref:System.Windows.Forms.ToolStripMenuItem>с.|  
  
 В следующей таблице показаны важные <xref:System.Windows.Forms.MenuStrip> сопутствующие классы.  
  
|Класс|Описание|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Представляет выбираемый параметр, отображаемый в <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Представляет контекстное меню.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или элемент меню более высокого уровня.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Предоставляет базовые функциональные возможности для элементов управления <xref:System.Windows.Forms.ToolStripItem> , производных от элементов с раскрывающимися списками при щелчке.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
