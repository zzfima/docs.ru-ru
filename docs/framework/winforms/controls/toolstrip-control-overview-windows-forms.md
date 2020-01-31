---
title: Общие сведения об элементе управления ToolStrip
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741074"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Общие сведения об элементе управления ToolStrip (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.ToolStrip> и связанные с ним классы предоставляют общую платформу для объединения элементов пользовательского интерфейса в панели инструментов, строки состояния и меню. <xref:System.Windows.Forms.ToolStrip> элементы управления предлагают широкие возможности во время разработки, включая встроенную активацию и редактирование, Пользовательский макет и нависания, что позволяет панелям инструментов совместно использовать горизонтальное или вертикальное пространство.  
  
 Хотя <xref:System.Windows.Forms.ToolStrip> заменяет и добавляет функциональные возможности в элемент управления в предыдущих версиях, <xref:System.Windows.Forms.ToolBar> сохраняется как для обратной совместимости, так и для будущего использования при необходимости.  
  
## <a name="features-of-the-toolstrip-controls"></a>Функции элементов управления ToolStrip  
 Используйте элемент управления <xref:System.Windows.Forms.ToolStrip> для:  
  
- Представьте общий пользовательский интерфейс в контейнерах.  
  
- Создание легко настраиваемых, часто используемых панелей инструментов, поддерживающих расширенные функции пользовательского интерфейса и макета, таких как закрепление, нависания, кнопки с текстом и изображениями, кнопки с раскрывающимся списком и элементы управления, кнопки переполнения и изменение порядка элементов <xref:System.Windows.Forms.ToolStrip>.  
  
- Поддержка переполнения и переупорядочивания элементов во время выполнения. Функция переполнения перемещает элементы в раскрывающееся меню, если недостаточно места для их вывода в <xref:System.Windows.Forms.ToolStrip>.  
  
- Поддержка типичного внешнего вида и поведения операционной системы с помощью общей модели отрисовки.  
  
- Согласованность событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.  
  
- Перетащите элементы из одного <xref:System.Windows.Forms.ToolStrip> в другой или в <xref:System.Windows.Forms.ToolStrip>.  
  
- Создание раскрывающихся элементов управления и редакторов типов пользовательского интерфейса с расширенными макетами в <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Используйте класс <xref:System.Windows.Forms.ToolStripControlHost>, чтобы использовать другие элементы управления в <xref:System.Windows.Forms.ToolStrip> и получить для них функции <xref:System.Windows.Forms.ToolStrip>.  
  
 Вы можете расширить функциональные возможности и изменить внешний вид и поведение, используя <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>и <xref:System.Windows.Forms.ToolStripManager> вместе с перечислениями <xref:System.Windows.Forms.ToolStripRenderMode> и <xref:System.Windows.Forms.ToolStripManagerRenderMode>.  
  
 Элемент управления <xref:System.Windows.Forms.ToolStrip> легко настраивается и расширяется, и он предоставляет множество свойств, методов и событий для настройки внешнего вида и поведения. Ниже приведены некоторые значимые члены:  
  
### <a name="important-toolstrip-members"></a>Важные элементы ToolStrip  
  
|Name|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Возвращает или задает границу родительского контейнера, к которому прикреплена <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Возвращает или задает значение, указывающее, будут ли операции перетаскивания и переупорядочения элементов обрабатываться классом <xref:System.Windows.Forms.ToolStrip> в закрытом режиме.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Возвращает или задает значение, указывающее, как <xref:System.Windows.Forms.ToolStrip> размещает свои элементы.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Возвращает или задает значение, указывающее, присоединен ли <xref:System.Windows.Forms.ToolStripItem> к <xref:System.Windows.Forms.ToolStrip> или <xref:System.Windows.Forms.ToolStripOverflowButton> или может перемещаться между ними.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Возвращает значение, указывающее, отображает ли <xref:System.Windows.Forms.ToolStripItem> другие элементы в раскрывающемся списке при нажатии <xref:System.Windows.Forms.ToolStripItem>.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Возвращает значение элемента <xref:System.Windows.Forms.ToolStripItem>, который является кнопкой переполнения для элемента управления <xref:System.Windows.Forms.ToolStrip> с включенной функцией переполнения.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Возвращает или задает <xref:System.Windows.Forms.ToolStripRenderer>, используемую для настройки внешнего вида и поведения (внешнего вида) <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Возвращает или задает стили рисования, применяемые к <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Возникает при изменении свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.|  
  
 Гибкость элемента управления <xref:System.Windows.Forms.ToolStrip> достигается за счет использования нескольких сопутствующих классов. Ниже приведены некоторые из наиболее значимых.  
  
### <a name="important-toolstrip-companion-classes"></a>Важные сопутствующие классы ToolStrip  
  
|Name|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Заменяет и добавляет функциональные возможности в класс <xref:System.Windows.Forms.MainMenu>.|  
|<xref:System.Windows.Forms.StatusStrip>|Заменяет и добавляет функциональные возможности в класс <xref:System.Windows.Forms.StatusBar>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Заменяет и добавляет функциональные возможности в класс <xref:System.Windows.Forms.ContextMenu>.|  
|<xref:System.Windows.Forms.ToolStripItem>|Абстрактный базовый класс, который управляет событиями и макетом для всех элементов, которые могут содержаться в <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>или <xref:System.Windows.Forms.ToolStripDropDown>.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Предоставляет контейнер с панелью на каждой стороне формы, в которой элементы управления могут быть упорядочены различными способами.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Обрабатывает функциональные возможности рисования для <xref:System.Windows.Forms.ToolStrip> объектов.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Обеспечивает внешний вид в стиле Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Элементы управления <xref:System.Windows.Forms.ToolStrip> отрисовку и нависания, а также слияние <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>и объектов <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Задает стиль рисования (настраиваемый, Windows XP или Microsoft Office Professional), применяемый к нескольким <xref:System.Windows.Forms.ToolStrip> объектам в форме.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Задает стиль рисования (настраиваемый, Windows XP или Microsoft Office Professional), применяемый к одному <xref:System.Windows.Forms.ToolStrip> объекту в форме.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Содержит другие элементы управления, не <xref:System.Windows.Forms.ToolStrip> элементы управления, для которых требуется <xref:System.Windows.Forms.ToolStrip> функциональность.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Указывает, должен ли <xref:System.Windows.Forms.ToolStripItem> быть размещен на основном <xref:System.Windows.Forms.ToolStrip>, на <xref:System.Windows.Forms.ToolStrip>переполнения или ни в каком другом.|  
  
 Дополнительные сведения см. в разделе Структура [технологии ToolStrip](toolstrip-technology-summary.md) и [архитектура элемента управления ToolStrip](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
