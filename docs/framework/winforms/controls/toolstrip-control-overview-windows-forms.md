---
title: Общие сведения об элементе управления ToolStrip (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 3927f180e738541f2f2f8af6d03d281f6a601167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="toolstrip-control-overview-windows-forms"></a>Общие сведения об элементе управления ToolStrip (Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolStrip> управления и связанные с ним классы предоставляют общую инфраструктуру для объединения элементов пользовательского интерфейса в панели инструментов, строк состояния и меню. <xref:System.Windows.Forms.ToolStrip> элементы управления обладают богатые возможности разработки, включающий активации на месте и редактирования, пользовательский макет и нависания, которая обеспечивает совместное использование горизонтального или вертикального пространства панели инструментов.  
  
 Несмотря на то что <xref:System.Windows.Forms.ToolStrip> заменяет и расширяет его функциональные возможности для управления в предыдущих версиях <xref:System.Windows.Forms.ToolBar> при необходимости можно сохранить для обратной совместимости и использования в будущем.  
  
## <a name="features-of-the-toolstrip-controls"></a>Возможности элементов управления ToolStrip  
 Используйте <xref:System.Windows.Forms.ToolStrip> управления:  
  
-   Предоставляют единый пользовательский интерфейс для контейнеров.  
  
-   Создание легко настраиваемых, стандартных панелей инструментов, которые поддерживают дополнительные возможности пользовательского интерфейса и макет, такими как кнопки закрепления, нависание, текст и изображения, кнопки раскрывающегося списка и элементов управления, переполнение кнопки и изменение порядка выполнения <xref:System.Windows.Forms.ToolStrip> элементы.  
  
-   Поддерживает переполнение и реорганизацию элементов во время выполнения. Функция переполнения перемещает элементы в раскрывающееся меню, если не хватает места для их отображения в <xref:System.Windows.Forms.ToolStrip>.  
  
-   Поддерживает типичные вид и поведение операционной системы через общую модель подготовки к просмотру.  
  
-   Обрабатывать события должен быть одинаковым для всех контейнеров и содержащихся элементов таким же образом обрабатывать события для других элементов управления.  
  
-   Перетащите элементы из одной <xref:System.Windows.Forms.ToolStrip> в другую или в <xref:System.Windows.Forms.ToolStrip>.  
  
-   Создать раскрывающийся список элементов управления и редакторов типов интерфейса с расширенными <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Используйте <xref:System.Windows.Forms.ToolStripControlHost> класс для использования других элементов управления на <xref:System.Windows.Forms.ToolStrip> и получить <xref:System.Windows.Forms.ToolStrip> функциональные возможности для них.  
  
 Можно расширить функциональные возможности и изменения внешнего вида и поведения с помощью <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, и <xref:System.Windows.Forms.ToolStripManager> вместе с <xref:System.Windows.Forms.ToolStripRenderMode> и <xref:System.Windows.Forms.ToolStripManagerRenderMode> перечисления.  
  
 <xref:System.Windows.Forms.ToolStrip> Управления высокой настраиваемыми и возможности расширения, а также многие свойства, методы и события для настройки внешнего вида и поведения. Ниже приведены некоторые значимые члены.  
  
### <a name="important-toolstrip-members"></a>ToolStrip важные члены  
  
|name|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Возвращает или задает край родительского контейнера <xref:System.Windows.Forms.ToolStrip> прикрепляется к.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Возвращает или задает значение, указывающее, будут ли операции перетаскивания и переупорядочения элементов обрабатываться классом <xref:System.Windows.Forms.ToolStrip> в закрытом режиме.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Возвращает или задает значение, указывающее, как <xref:System.Windows.Forms.ToolStrip> располагает его элементов.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Возвращает или задает ли <xref:System.Windows.Forms.ToolStripItem> присоединяется к <xref:System.Windows.Forms.ToolStrip> или <xref:System.Windows.Forms.ToolStripOverflowButton> или могут перемещаться между ними.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Возвращает значение, указывающее, ли <xref:System.Windows.Forms.ToolStripItem> отображает другие элементы в раскрывающемся списке перечислены при <xref:System.Windows.Forms.ToolStripItem> нажатии.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Возвращает значение элемента <xref:System.Windows.Forms.ToolStripItem>, который является кнопкой переполнения для элемента управления <xref:System.Windows.Forms.ToolStrip> с включенной функцией переполнения.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Возвращает или задает <xref:System.Windows.Forms.ToolStripRenderer> позволяет настраивать внешний вид и поведение (Вид) <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Возвращает или задает стили рисования для применения к <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Возникает, когда <xref:System.Windows.Forms.ToolStrip.Renderer%2A> изменения свойств.|  
  
 <xref:System.Windows.Forms.ToolStrip> Элемента управления гибкость достигается за счет использования ряд сопутствующих классов. Ниже перечислены некоторые из наиболее значимых:  
  
### <a name="important-toolstrip-companion-classes"></a>Важные сопутствующие ToolStrip классы  
  
|name|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.MainMenu> класса.|  
|<xref:System.Windows.Forms.StatusStrip>|Заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.StatusBar> класса.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.ContextMenu> класса.|  
|<xref:System.Windows.Forms.ToolStripItem>|Абстрактный базовый класс, который управляет события и макет для всех элементов, <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, или <xref:System.Windows.Forms.ToolStripDropDown> может содержать.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Предоставляет контейнер с панелями на каждой стороне формы, в которой можно упорядочивать элементы управления в различные способы.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Обрабатывает функцию окрашивания для <xref:System.Windows.Forms.ToolStrip> объектов.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Предоставляет внешний вид в стиле Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Элементы управления <xref:System.Windows.Forms.ToolStrip> отрисовки и нависания и слияния <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, и <xref:System.Windows.Forms.ToolStripMenuItem> объектов.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Задает стиль рисования (custom, Windows XP или Microsoft Office профессиональный), применяется к нескольким <xref:System.Windows.Forms.ToolStrip> объектов, содержащихся в форме.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Задает стиль рисования (custom, Windows XP или Microsoft Office профессиональный), применяемая к <xref:System.Windows.Forms.ToolStrip> объектов, содержащихся в форме.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Размещает другие элементы управления, которые не являются <xref:System.Windows.Forms.ToolStrip> элементов управления, но для которого необходимо <xref:System.Windows.Forms.ToolStrip> функциональные возможности.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Указывает ли <xref:System.Windows.Forms.ToolStripItem> будет располагаться в главном <xref:System.Windows.Forms.ToolStrip>, в случае переполнения <xref:System.Windows.Forms.ToolStrip>, и ни одного.|  
  
 Дополнительные сведения см. в разделе [ToolStrip Сводка по технологиям](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) и [архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
