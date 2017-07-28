---
title: "Элементы управления Windows Forms со встроенной поддержки рисования владельцем | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Рисование, владелец"
  - "Рисование пользовательского"
  - "Изменение внешнего вида элементов управления [Windows Forms]"
  - "пользовательское рисование"
  - "рисование владельцем"
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Элементы управления Windows Forms со встроенной поддержки рисования владельцем
Рисование владельцем в Windows Forms, который называется также пользовательское рисование, — это метод для изменения внешнего вида определенных элементов управления.  
  
> [!NOTE]
>  Слово «control» в этом разделе используется для обозначения классы, производные от <xref:System.Windows.Forms.Control> или <xref:System.ComponentModel.Component>.  
  
 Как правило, Windows, рисование обрабатывается автоматически при помощи параметров свойств, таких как <xref:System.Windows.Forms.Control.BackColor%2A> для определения внешнего вида элемента управления. При рисовании владельцем можно перехватить процесс рисования изменение элементы, которые недоступны с помощью свойств внешнего вида. Например многие элементы управления позволяют задавать цвет текста, который отображается, но вы ограничены одним цветом. Рисование владельцем позволяет отображаться часть текста черным и часть красным цветом.  
  
 На практике рисование владельцем аналогично рисованию изображений в форме. Например, можно использовать графические методы в обработчике для формы <xref:System.Windows.Forms.Control.Paint> событий для эмуляции `ListBox` элемента управления, но вам пришлось бы писать собственный код для обработки взаимодействия с пользователем. При рисовании владельцем элемент управления использует код пользователя для рисования своего содержимого, но в противном случае сохраняет все свои существующие возможности. Можно использовать графические методы для рисования каждого элемента в элементе управления или для настройки некоторых параметров каждого элемента при использовании внешний вид по умолчанию для других параметров каждого элемента.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Элементы управления рисования владельцем в Windows Forms  
 Для рисования элементов управления, поддерживающих его владельцем, вы обычно задается одно свойство и обрабатывать одно или несколько событий.  
  
 Большинство элементов управления, поддерживающих рисование пользователем имеют `OwnerDraw` или `DrawMode` свойство, указывающее, будет ли элемент управления вызывает его связанных с рисованием событий или событий при оформлении самого.  
  
 Элементы управления, которые не имеют `OwnerDraw` или `DrawMode` свойство включать `DataGridView` управления, предоставляющий происходящие автоматически события рисования и `ToolStrip` управления, рисуемый при помощи внешнего класса отрисовки, имеет свои собственные события, связанных с рисованием.  
  
 Существует много различных типов событий рисования, но типичное событие рисования происходит для рисования отдельного элемента внутри элемента управления. Обработчик событий получает `EventArgs` объект, который содержит сведения о изображаемый и инструментами, которые можно использовать для рисования. Например, этот объект обычно содержит порядковый номер элемента в его родительской коллекции <xref:System.Drawing.Rectangle> указывает отображения границ элемента и <xref:System.Drawing.Graphics> объекта для вызова методов рисования. Для некоторых событий `EventArgs` объект предоставляет дополнительные сведения об элементе и методах, которые можно вызвать для рисования некоторых частей элемента по умолчанию, таких как фона или прямоугольника фокуса.  
  
 Создание элемента управления для повторного использования, содержащий пользовательские настройки, создайте новый класс, производный от класса элемента управления, который поддерживает рисование владельцем. Вместо обработки событий рисования включите код рисования владельцем в переопределения для соответствующей `On` *EventName* метод или методы в новом классе. Убедитесь в том, что можно вызвать базовый класс `On` *EventName* метод или методы в этом случае, чтобы пользователи элемента управления могли обрабатывать события рисования владельцем и выполнять дополнительные настройки.  
  
 Следующие формы Windows управляет поддержка рисования владельцем в всех версий платформы .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem> (используемые <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 Следующие элементы управления поддерживают рисование владельцем только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 Следующие элементы управления поддерживают рисование владельцем и новые возможности являются [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Следующие разделы предоставляют дополнительные сведения для каждого из этих элементов управления.  
  
### <a name="listbox-and-combobox-controls"></a>Элементы управления ComboBox и ListBox  
 <xref:System.Windows.Forms.ListBox> и <xref:System.Windows.Forms.ComboBox> элементы управления позволяют рисовать отдельные элементы в элементе управления одного или разного размера.  
  
> [!NOTE]
>  Хотя <xref:System.Windows.Forms.CheckedListBox> управления является производным от <xref:System.Windows.Forms.ListBox> управления, он не поддерживает рисование владельцем.  
  
 Для рисования каждого элемента того же размера, `DrawMode` свойства <xref:System.Windows.Forms.DrawMode> и обрабатывать `DrawItem` события.  
  
 Для рисования элементов разного размера, установите `DrawMode` свойства <xref:System.Windows.Forms.DrawMode> и обработать `MeasureItem` и `DrawItem` события. `MeasureItem` Событий позволяет указать размер элемента, прежде чем `DrawItem` событие для этого элемента.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=fullName>  
  
-   [Практическое руководство: создание переменного размера текста в элементе управления ComboBox](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Компонент MenuItem  
 <xref:System.Windows.Forms.MenuItem> компонент представляет собой отдельный пункт меню в <xref:System.Windows.Forms.MainMenu> или <xref:System.Windows.Forms.ContextMenu> компонента.  
  
 Для рисования <xref:System.Windows.Forms.MenuItem>, задайте его `OwnerDraw` свойства `true` и обработать его `DrawItem` события. Чтобы изменить размер элемента меню перед `DrawItem` происходит событие, обрабатывать этот элемент `MeasureItem` события.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=fullName>  
  
### <a name="tabcontrol-control"></a>Элемент управления TabControl  
 <xref:System.Windows.Forms.TabControl> позволяет рисовать отдельные вкладки в элементе управления. Рисование владельцем влияет только на вкладки; <xref:System.Windows.Forms.TabPage> содержимое не затрагиваются.  
  
 Для рисования вкладки <xref:System.Windows.Forms.TabControl>, задайте `DrawMode` свойства <xref:System.Windows.Forms.TabDrawMode> и обрабатывать `DrawItem` события. Это событие происходит один раз для каждой вкладки, только в том случае, если вкладка видна в элементе управления.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=fullName>  
  
### <a name="tooltip-component"></a>Компонент ToolTip  
 <xref:System.Windows.Forms.ToolTip> компонент позволяет рисовать ToolTip целиком при его отображении.  
  
 Для рисования <xref:System.Windows.Forms.ToolTip>, задайте его `OwnerDraw` свойства `true` и обработать его `Draw` события. Чтобы настроить размер <xref:System.Windows.Forms.ToolTip> перед `Draw` происходит событие, обрабатывать `Popup` событий и набор <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> свойство в обработчике событий.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=fullName>  
  
### <a name="listview-control"></a>Элемент управления ListView  
 <xref:System.Windows.Forms.ListView> позволяет рисовать отдельные элементы, подпункты и заголовки столбцов в элементе управления.  
  
 Чтобы включить рисование владельцем в элементе управления, задайте `OwnerDraw` свойства `true`.  
  
 Для рисования каждого элемента в элементе управления обработайте `DrawItem` события.  
  
 Для рисования каждого вложенного элемента или столбца заголовка в элементе управления при <xref:System.Windows.Forms.ListView.View%2A> свойству <xref:System.Windows.Forms.View>, обрабатывать `DrawSubItem` и `DrawColumnHeader` события.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=fullName>  
  
### <a name="treeview-control"></a>Элемент управления TreeView  
 <xref:System.Windows.Forms.TreeView> позволяет рисовать отдельные узлы в элементе управления.  
  
 Чтобы нарисовать только текст, отображаемый в каждом узле, установите `DrawMode` свойства <xref:System.Windows.Forms.TreeViewDrawMode> и обрабатывать `DrawNode` событий для отрисовки текста.  
  
 Чтобы нарисовать все элементы каждого узла, установите `DrawMode` свойства <xref:System.Windows.Forms.TreeViewDrawMode> и обрабатывать `DrawNode` событий для рисования любых требуемых, такие как текст, значки, флажки, знаки плюс и минус и линии, соединяющие узлы элементов.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=fullName>  
  
### <a name="datagridview-control"></a>Элемент управления DataGridView  
 <xref:System.Windows.Forms.DataGridView> позволяет рисовать отдельные ячейки и строки в элементе управления.  
  
 Для рисования отдельных ячеек обработайте `CellPainting` события.  
  
 Для рисования отдельных строк или элементов строк обработайте одно или оба `RowPrePaint` и `RowPostPaint` события. `RowPrePaint` Событие происходит до рисуются ячеек в строке и `RowPostPaint` событие возникает после их построения. Можно обрабатывать события, как и `CellPainting` событий для рисования фона строки, отдельных ячеек и переднего плана отдельно, или можно предоставить особых настроек, где они нужны и использовать отображение по умолчанию для других элементов строки.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Практическое руководство: Настройка внешнего вида ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Практическое руководство: Настройка внешнего вида строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>Элемент управления ToolStrip  
 <xref:System.Windows.Forms.ToolStrip> и производные элементы управления позволяют настраивать все аспекты их внешний вид.  
  
 Для обеспечения пользовательской отрисовки для <xref:System.Windows.Forms.ToolStrip> набор элементов управления, `Renderer` свойство <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, или <xref:System.Windows.Forms.ToolStripContentPanel> для `ToolStripRenderer` и обработать один или несколько из большого числа событий рисования `ToolStripRenderer` класс. Можно также задать `Renderer` свойство для экземпляра собственный класс, производный от `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, или <xref:System.Windows.Forms.ToolStripSystemRenderer> , реализующего или переопределяющего определенные `On` *EventName* методы.  
  
 Дополнительные сведения, включая примеры кода см. в следующих разделах:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Практическое руководство: Создание и определение пользовательского средства отрисовки для элемента управления ToolStrip в Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Практическое руководство: пользовательская прорисовка элемента управления ToolStrip](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)