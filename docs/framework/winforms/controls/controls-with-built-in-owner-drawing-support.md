---
title: Элементы управления Windows Forms со встроенной поддержки рисования владельцем
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930191"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Элементы управления Windows Forms со встроенной поддержки рисования владельцем
Рисование владельцем в Windows Forms, иначе называемое пользовательским рисованием, — это способ изменения внешнего вида определенных элементов управления.  
  
> [!NOTE]
> Слово «Control» в этом разделе используется для обозначения классов, производных от либо <xref:System.Windows.Forms.Control>. <xref:System.ComponentModel.Component>  
  
 Как правило, Windows обрабатывает Рисование автоматически, используя параметры свойств, <xref:System.Windows.Forms.Control.BackColor%2A> такие как, для определения внешнего вида элемента управления. При рисовании владельцем можно перехватить процесс рисования, изменив элементы внешнего вида, которые недоступны при использовании свойств. Например, многие элементы управления позволяют задавать цвет отображаемого текста, но вы ограничены одним цветом. Рисование владельцем позволяет, например, отображать часть текста черным цветом, а другую часть — красным.  
  
 На практике рисование владельцем аналогично рисованию графических элементов в форме. Например, можно использовать графические методы в обработчике <xref:System.Windows.Forms.Control.Paint> события формы для имитации `ListBox` элемента управления, но вам придется написать собственный код для обработки всех действий пользователя. При рисовании владельцем элемент управления использует ваш код для рисования своего содержимого, но в остальном сохраняет все свои внутренние возможности. Графические методы можно использовать для рисования каждого элемента в элементе управления или для настройки некоторых аспектов каждого элемента при использовании внешнего вида по умолчанию для других аспектов каждого элемента.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Рисование владельцем в элементах управления Windows Forms  
 Чтобы выполнить рисование владельцем в элементах управления, поддерживающих эту функцию, вы, как правило, задаете одно свойство и обрабатываете одно или несколько событий.  
  
 Большинство элементов управления, поддерживающих рисование владельцем, имеют свойство `OwnerDraw` или `DrawMode`, указывающее, будет ли элемент управления вызывать связанные с рисованием события при рисовании себя.  
  
 Элементы управления, которые не имеют свойства `OwnerDraw` или `DrawMode`, включают элемент управления `DataGridView`, предоставляющий происходящие автоматически события рисования, и элемент управления `ToolStrip`, рисуемый с помощью внешнего класса отрисовки, имеющего собственные события, связанные с рисованием.  
  
 Существует много различных типов событий рисования, однако типичное событие рисования возникает для рисования отдельного элемента внутри элемента управления. Обработчик событий получает объект `EventArgs`, который содержит сведения о рисуемом элементе, и инструменты, которые можно использовать для рисования. Например, этот объект обычно содержит порядковый номер элемента в родительской коллекции, <xref:System.Drawing.Rectangle> который указывает границы дисплея элемента, <xref:System.Drawing.Graphics> и объект для вызова методов рисования. Для некоторых событий объект `EventArgs` предоставляет дополнительные сведения об элементе и методах, которые можно вызвать для рисования некоторых аспектов элемента по умолчанию, таких как фон или прямоугольник фокуса.  
  
 Чтобы создать элемент управления для повторного использования, содержащий настройки рисования владельцем, создайте новый класс, производный от класса элемента управления, который поддерживает рисование владельцем. Вместо обработки событий рисования включите код рисования владельцем в переопределения для соответствующего метода или методов `On`*ИмяСобытия* в новом классе. Убедитесь в том, что в этом случае вызывается метод или методы `On`*ИмяСобытия* базового класса, чтобы пользователи элемента управления могли обрабатывать события рисования владельцем и выполнять дополнительные настройки.  
  
 Следующие элементы управления Windows Forms поддерживают рисование владельцем во всех версиях .NET Framework.  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem>(используется <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu>)  
  
- <xref:System.Windows.Forms.TabControl>  
  
 Следующие элементы управления поддерживают рисование владельцем только в .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 Следующие элементы управления поддерживают рисование владельцем и являются новыми в .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 В следующих разделах приводятся дополнительные сведения для каждого из этих элементов управления.  
  
### <a name="listbox-and-combobox-controls"></a>Элементы управления ListBox и ComboBox  
 Элементы управления <xref:System.Windows.Forms.ComboBox> и позволяют рисовать отдельные элементы в элементе управления либо в одном размере, либо в разных размерах. <xref:System.Windows.Forms.ListBox>  
  
> [!NOTE]
> Хотя элемент управления является производным <xref:System.Windows.Forms.ListBox> от элемента управления, он не поддерживает рисование владельцем. <xref:System.Windows.Forms.CheckedListBox>  
  
 Чтобы нарисовать каждый элемент того же размера, присвойте `DrawMode` <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> свойству значение и `DrawItem` обработайте событие.  
  
 Чтобы нарисовать каждый элемент, используя другой размер, установите `DrawMode` свойство в <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> значение и обработайте `DrawItem` оба `MeasureItem` события и. Событие `MeasureItem` позволяет указать размер элемента, прежде чем возникнет событие `DrawItem` для этого элемента.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах.  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [Практическое руководство. Создание переменного размера текста в элементе управления ComboBox](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Компонент MenuItem  
 Компонент представляет один пункт меню <xref:System.Windows.Forms.MainMenu> в компоненте или <xref:System.Windows.Forms.ContextMenu>. <xref:System.Windows.Forms.MenuItem>  
  
 Чтобы нарисовать <xref:System.Windows.Forms.MenuItem>объект, установите `OwnerDraw` его свойство `true` в значение и `DrawItem` обработайте его событие. Чтобы изменять размер элемента меню перед возникновением события `DrawItem`, требуется обработка события `MeasureItem` элемента.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>Элемент управления TabControl  
 <xref:System.Windows.Forms.TabControl> Элемент управления позволяет рисовать отдельные вкладки в элементе управления. Рисование владельцем влияет только на вкладки; <xref:System.Windows.Forms.TabPage> содержимое не изменяется.  
  
 Чтобы нарисовать каждую вкладку в <xref:System.Windows.Forms.TabControl>, `DrawMode` установите `DrawItem` свойство в <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> значение и обработайте событие. Это событие возникает один раз для каждой вкладки, только если вкладка видна в элементе управления.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>Компонент ToolTip  
 <xref:System.Windows.Forms.ToolTip> Компонент позволяет рисовать всю всплывающую подсказку при отображении.  
  
 Чтобы нарисовать <xref:System.Windows.Forms.ToolTip>объект, установите `OwnerDraw` его свойство `true` в значение и `Draw` обработайте его событие. <xref:System.Windows.Forms.ToolTip> Чтобы настроить размер объекта `Draw` до возникновения `Popup` события, обработайте событие и задайте <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> свойство в обработчике событий.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>Элемент управления ListView  
 <xref:System.Windows.Forms.ListView> Элемент управления позволяет рисовать отдельные элементы, подэлементы и заголовки столбцов в элементе управления.  
  
 Чтобы включить рисование владельцем в элементе управления, задайте для свойства `OwnerDraw` значение `true`.  
  
 Для рисования каждого пункта в элементе управления обработайте событие `DrawItem`.  
  
 Для рисования каждого подэлемента или заголовка <xref:System.Windows.Forms.ListView.View%2A> столбца в элементе управления <xref:System.Windows.Forms.View.Details>, если свойство имеет значение, обрабатывает `DrawSubItem` события и `DrawColumnHeader` .  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>Элемент управления TreeView  
 <xref:System.Windows.Forms.TreeView> Элемент управления позволяет нарисовать отдельные узлы в элементе управления.  
  
 Чтобы нарисовать только текст, отображаемый в каждом узле, `DrawMode` установите свойство <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> в значение и `DrawNode` обработайте событие для отрисовки текста.  
  
 Чтобы нарисовать все элементы каждого узла, присвойте `DrawMode` <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> свойству значение и обработайте `DrawNode` событие для отрисовки необходимых элементов, таких как текст, значки, флажки, знаки плюса и минуса, а также линии, соединяющие узлы.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>Элемент управления DataGridView  
 <xref:System.Windows.Forms.DataGridView> Элемент управления позволяет рисовать отдельные ячейки и строки в элементе управления.  
  
 Для рисования отдельных ячеек обработайте событие `CellPainting`.  
  
 Для рисования отдельных строк или элементов строк обработайте одно или оба события `RowPrePaint` и `RowPostPaint`. Событие `RowPrePaint` возникает до рисования ячеек в строке, а событие `RowPostPaint` — после их рисования. Можно обрабатывать оба события и событие `CellPainting` для рисования фона строки, отдельных ячеек и переднего плана строки по отдельности. Кроме того, можно предоставить особые настройки в нужных местах и использовать отображение по умолчанию для других элементов строки.  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах.  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [Практическое руководство. Настройка внешнего вида ячеек в элементе управления Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [Практическое руководство. Настройка внешнего вида строк в элементе управления Windows Forms DataGridView](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>Элемент управления ToolStrip  
 <xref:System.Windows.Forms.ToolStrip>и производные элементы управления позволяют настраивать любой аспект их внешнего вида.  
  
 Чтобы обеспечить <xref:System.Windows.Forms.ToolStrip> пользовательскую отрисовку для элементов управления, `Renderer` установите свойство <xref:System.Windows.Forms.ToolStrip> `ToolStripRenderer` объекта <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, или <xref:System.Windows.Forms.ToolStripContentPanel> в объект и обработайте одно или несколько событий рисования, предоставляемых `ToolStripRenderer` класс. Кроме того, можно `Renderer` установить свойство в экземпляре вашего собственного класса, производного <xref:System.Windows.Forms.ToolStripProfessionalRenderer>от `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripSystemRenderer> или, который реализует или `On`переопределяет конкретные методы *EventName* .  
  
 Дополнительные сведения, включая примеры кода, см. в следующих разделах.  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [Практическое руководство. Создание и настройка пользовательского модуля отрисовки для элемента управления ToolStrip в Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [Практическое руководство. Пользовательское рисование элемента управления ToolStrip](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>См. также

- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
