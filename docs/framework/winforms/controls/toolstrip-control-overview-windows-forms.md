---
title: "Общие сведения об элементе управления ToolStrip (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Toolstrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "панели инструментов [Windows Forms]"
  - "панели инструментов [Windows Forms], новые возможности Windows Forms"
  - "ToolStrip - элемент управления [Windows Forms], сведения об элементе управления ToolStrip"
  - "новые возможности [Windows Forms], панели инструментов"
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Общие сведения об элементе управления ToolStrip (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.ToolStrip> и связанные с ним классы образуют общую структуру, объединяющую элементы пользовательского интерфейса в панели инструментов, строки состояния и меню.  Элементы управления <xref:System.Windows.Forms.ToolStrip> предлагают множество функций, используемых в процессе проектирования, включающих активацию и редактирование "на месте", создание пользовательской структуры, а также функцию нависания, которая обеспечивает совместное использование горизонтального или вертикального пространства в области панели инструментов.  
  
 Хотя элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления предыдущих версий и расширяет его функциональные возможности, при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.  
  
## Функции элементов управления ToolStrip  
 Используйте элемент управления <xref:System.Windows.Forms.ToolStrip> для выполнения следующих действий:  
  
-   Создание общего пользовательского интерфейса в различных контейнерах.  
  
-   Создание легко настраиваемых панелей инструментов с одинаковыми функциями, поддерживающих расширенный пользовательский интерфейс и дополнительные средства работы со структурами, например: закрепление, нависание, кнопки с текстом и изображениями, кнопки и элементы управления со стрелками раскрывающегося списка, кнопки переполнения и переупорядочение элементов <xref:System.Windows.Forms.ToolStrip> при выполнении.  
  
-   Поддержка переполнения и переупорядочения элементов при выполнении.  Функция переполнения перемещает элементы в раскрывающееся меню, если не хватает места для их отображения в элементе управления <xref:System.Windows.Forms.ToolStrip>.  
  
-   Поддержка типового вида и поведения операционной системы в обычной модели отрисовки.  
  
-   Согласованная обработка событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.  
  
-   Перетаскивание элементов из одного элемента управления <xref:System.Windows.Forms.ToolStrip> в другой или в пределах одного элемента управления <xref:System.Windows.Forms.ToolStrip>.  
  
-   Создание в элементе управления <xref:System.Windows.Forms.ToolStripDropDown> раскрывающихся элементов управления и редакторов типов пользовательского интерфейса с расширенными функциями работы со структурами.  
  
 Использование класса <xref:System.Windows.Forms.ToolStripControlHost> для применения в элементе управления <xref:System.Windows.Forms.ToolStrip> других элементов управления и использования для них функций элемента <xref:System.Windows.Forms.ToolStrip>.  
  
 Можно расширить функциональные возможности и изменить внешний вид и поведение системы, используя перечисления <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer> и <xref:System.Windows.Forms.ToolStripManager> совместно с <xref:System.Windows.Forms.ToolStripRenderMode> и <xref:System.Windows.Forms.ToolStripManagerRenderMode>.  
  
 Элемент управления <xref:System.Windows.Forms.ToolStrip> можно легко настроить и расширить. Кроме того, он имеет множество свойств, методов и событий, что позволяет настроить внешний вид и поведение системы.  Ниже приведены некоторые значимые члены:  
  
### Важные члены элемента управления ToolStrip  
  
|Имя|Описание|  
|---------|--------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Возвращает или задает край родительского контейнера, к которому прикрепляется элемент управления <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Возвращает или задает значение, указывающее, будут ли операции перетаскивания и переупорядочения элементов обрабатываться классом <xref:System.Windows.Forms.ToolStrip> в закрытом режиме.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Возвращает или задает значение, указывающее, как элемент управления <xref:System.Windows.Forms.ToolStrip> выполняет размещение своих элементов.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Возвращает или задает значение, указывающее, вложен ли элемент управления <xref:System.Windows.Forms.ToolStripItem> к элементу управления <xref:System.Windows.Forms.ToolStrip> или <xref:System.Windows.Forms.ToolStripOverflowButton> или он может перемещаться между ними.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Возвращает значение, указывающее, отображает ли элемент управления <xref:System.Windows.Forms.ToolStripItem> другие элементы в раскрывающемся списке при выборе элемента управления <xref:System.Windows.Forms.ToolStripItem>.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Возвращает значение элемента <xref:System.Windows.Forms.ToolStripItem>, который является кнопкой переполнения для элемента управления <xref:System.Windows.Forms.ToolStrip> с включенной функцией переполнения.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Возвращает или задает значение для элемента управления <xref:System.Windows.Forms.ToolStripRenderer>, используемого для настройки внешнего вида и поведения элемента управления <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Возвращает или задает стили оформления для элемента управления <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Используется при изменении свойства <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.|  
  
 Гибкость элемента управления <xref:System.Windows.Forms.ToolStrip> достигается за счет использования нескольких сопутствующих классов.  Ниже приведены некоторые наиболее значимые из них:  
  
### Важные сопутствующие классы элемента управления ToolStrip  
  
|Имя|Описание|  
|---------|--------------|  
|<xref:System.Windows.Forms.MenuStrip>|Заменяет класс <xref:System.Windows.Forms.MainMenu> и расширяет его функциональные возможности.|  
|<xref:System.Windows.Forms.StatusStrip>|Заменяет класс <xref:System.Windows.Forms.StatusBar> и расширяет его функциональные возможности.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Заменяет класс <xref:System.Windows.Forms.ContextMenu> и расширяет его функциональные возможности.|  
|<xref:System.Windows.Forms.ToolStripItem>|Абстрактный базовый класс, который управляет событиями и структурой всех элементов, которые могут содержаться в элементах управления <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost> или <xref:System.Windows.Forms.ToolStripDropDown>.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Предоставляет контейнер с панелями на каждой стороне формы, в которых можно по\-разному расположить элементы управления.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Выполняет функции рисования для объектов <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Обеспечивает внешний вид, аналогичный Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Управляет отрисовкой и нависанием элемента управления <xref:System.Windows.Forms.ToolStrip>, а также слиянием объектов <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> и <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Определяет стиль оформления \(настраиваемый, Windows XP или Microsoft Office Professional\), который применяется к нескольким содержащимся в форме объектам <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Определяет стиль оформления \(настраиваемый, Windows XP или Microsoft Office Professional\), который применяется к одному содержащемуся в форме объекту <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Размещает другие элементы управления, которые не входят в состав элемента управления <xref:System.Windows.Forms.ToolStrip>, но для которых необходимо использовать функции элемента управления <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Указывает расположение элемента <xref:System.Windows.Forms.ToolStripItem>: на главном элементе управления <xref:System.Windows.Forms.ToolStrip>, на переполнении <xref:System.Windows.Forms.ToolStrip> или ни один из этих вариантов.|  
  
 Дополнительные сведения см. в разделах [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) и [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>