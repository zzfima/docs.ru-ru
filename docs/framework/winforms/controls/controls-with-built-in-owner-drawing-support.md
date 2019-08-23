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
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="c3601-102">Элементы управления Windows Forms со встроенной поддержки рисования владельцем</span><span class="sxs-lookup"><span data-stu-id="c3601-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="c3601-103">Рисование владельцем в Windows Forms, иначе называемое пользовательским рисованием, — это способ изменения внешнего вида определенных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3601-104">Слово «Control» в этом разделе используется для обозначения классов, производных от либо <xref:System.Windows.Forms.Control>. <xref:System.ComponentModel.Component></span><span class="sxs-lookup"><span data-stu-id="c3601-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="c3601-105">Как правило, Windows обрабатывает Рисование автоматически, используя параметры свойств, <xref:System.Windows.Forms.Control.BackColor%2A> такие как, для определения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="c3601-106">При рисовании владельцем можно перехватить процесс рисования, изменив элементы внешнего вида, которые недоступны при использовании свойств.</span><span class="sxs-lookup"><span data-stu-id="c3601-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="c3601-107">Например, многие элементы управления позволяют задавать цвет отображаемого текста, но вы ограничены одним цветом.</span><span class="sxs-lookup"><span data-stu-id="c3601-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="c3601-108">Рисование владельцем позволяет, например, отображать часть текста черным цветом, а другую часть — красным.</span><span class="sxs-lookup"><span data-stu-id="c3601-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="c3601-109">На практике рисование владельцем аналогично рисованию графических элементов в форме.</span><span class="sxs-lookup"><span data-stu-id="c3601-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="c3601-110">Например, можно использовать графические методы в обработчике <xref:System.Windows.Forms.Control.Paint> события формы для имитации `ListBox` элемента управления, но вам придется написать собственный код для обработки всех действий пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3601-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="c3601-111">При рисовании владельцем элемент управления использует ваш код для рисования своего содержимого, но в остальном сохраняет все свои внутренние возможности.</span><span class="sxs-lookup"><span data-stu-id="c3601-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="c3601-112">Графические методы можно использовать для рисования каждого элемента в элементе управления или для настройки некоторых аспектов каждого элемента при использовании внешнего вида по умолчанию для других аспектов каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="c3601-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="c3601-113">Рисование владельцем в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3601-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="c3601-114">Чтобы выполнить рисование владельцем в элементах управления, поддерживающих эту функцию, вы, как правило, задаете одно свойство и обрабатываете одно или несколько событий.</span><span class="sxs-lookup"><span data-stu-id="c3601-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="c3601-115">Большинство элементов управления, поддерживающих рисование владельцем, имеют свойство `OwnerDraw` или `DrawMode`, указывающее, будет ли элемент управления вызывать связанные с рисованием события при рисовании себя.</span><span class="sxs-lookup"><span data-stu-id="c3601-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="c3601-116">Элементы управления, которые не имеют свойства `OwnerDraw` или `DrawMode`, включают элемент управления `DataGridView`, предоставляющий происходящие автоматически события рисования, и элемент управления `ToolStrip`, рисуемый с помощью внешнего класса отрисовки, имеющего собственные события, связанные с рисованием.</span><span class="sxs-lookup"><span data-stu-id="c3601-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="c3601-117">Существует много различных типов событий рисования, однако типичное событие рисования возникает для рисования отдельного элемента внутри элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="c3601-118">Обработчик событий получает объект `EventArgs`, который содержит сведения о рисуемом элементе, и инструменты, которые можно использовать для рисования.</span><span class="sxs-lookup"><span data-stu-id="c3601-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="c3601-119">Например, этот объект обычно содержит порядковый номер элемента в родительской коллекции, <xref:System.Drawing.Rectangle> который указывает границы дисплея элемента, <xref:System.Drawing.Graphics> и объект для вызова методов рисования.</span><span class="sxs-lookup"><span data-stu-id="c3601-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="c3601-120">Для некоторых событий объект `EventArgs` предоставляет дополнительные сведения об элементе и методах, которые можно вызвать для рисования некоторых аспектов элемента по умолчанию, таких как фон или прямоугольник фокуса.</span><span class="sxs-lookup"><span data-stu-id="c3601-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="c3601-121">Чтобы создать элемент управления для повторного использования, содержащий настройки рисования владельцем, создайте новый класс, производный от класса элемента управления, который поддерживает рисование владельцем.</span><span class="sxs-lookup"><span data-stu-id="c3601-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="c3601-122">Вместо обработки событий рисования включите код рисования владельцем в переопределения для соответствующего метода или методов `On`*ИмяСобытия* в новом классе.</span><span class="sxs-lookup"><span data-stu-id="c3601-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="c3601-123">Убедитесь в том, что в этом случае вызывается метод или методы `On`*ИмяСобытия* базового класса, чтобы пользователи элемента управления могли обрабатывать события рисования владельцем и выполнять дополнительные настройки.</span><span class="sxs-lookup"><span data-stu-id="c3601-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="c3601-124">Следующие элементы управления Windows Forms поддерживают рисование владельцем во всех версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3601-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <span data-ttu-id="c3601-125"><xref:System.Windows.Forms.MenuItem>(используется <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="c3601-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
- <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="c3601-126">Следующие элементы управления поддерживают рисование владельцем только в .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="c3601-126">The following controls support owner drawing only in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="c3601-127">Следующие элементы управления поддерживают рисование владельцем и являются новыми в .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="c3601-127">The following controls support owner drawing and are new in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="c3601-128">В следующих разделах приводятся дополнительные сведения для каждого из этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="c3601-129">Элементы управления ListBox и ComboBox</span><span class="sxs-lookup"><span data-stu-id="c3601-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="c3601-130">Элементы управления <xref:System.Windows.Forms.ComboBox> и позволяют рисовать отдельные элементы в элементе управления либо в одном размере, либо в разных размерах. <xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="c3601-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3601-131">Хотя элемент управления является производным <xref:System.Windows.Forms.ListBox> от элемента управления, он не поддерживает рисование владельцем. <xref:System.Windows.Forms.CheckedListBox></span><span class="sxs-lookup"><span data-stu-id="c3601-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="c3601-132">Чтобы нарисовать каждый элемент того же размера, присвойте `DrawMode` <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> свойству значение и `DrawItem` обработайте событие.</span><span class="sxs-lookup"><span data-stu-id="c3601-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="c3601-133">Чтобы нарисовать каждый элемент, используя другой размер, установите `DrawMode` свойство в <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> значение и обработайте `DrawItem` оба `MeasureItem` события и.</span><span class="sxs-lookup"><span data-stu-id="c3601-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="c3601-134">Событие `MeasureItem` позволяет указать размер элемента, прежде чем возникнет событие `DrawItem` для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="c3601-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="c3601-135">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c3601-135">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [<span data-ttu-id="c3601-136">Практическое руководство. Создание переменного размера текста в элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="c3601-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="c3601-137">Компонент MenuItem</span><span class="sxs-lookup"><span data-stu-id="c3601-137">MenuItem Component</span></span>  
 <span data-ttu-id="c3601-138">Компонент представляет один пункт меню <xref:System.Windows.Forms.MainMenu> в компоненте или <xref:System.Windows.Forms.ContextMenu>. <xref:System.Windows.Forms.MenuItem></span><span class="sxs-lookup"><span data-stu-id="c3601-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="c3601-139">Чтобы нарисовать <xref:System.Windows.Forms.MenuItem>объект, установите `OwnerDraw` его свойство `true` в значение и `DrawItem` обработайте его событие.</span><span class="sxs-lookup"><span data-stu-id="c3601-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="c3601-140">Чтобы изменять размер элемента меню перед возникновением события `DrawItem`, требуется обработка события `MeasureItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="c3601-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="c3601-141">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="c3601-141">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="c3601-142">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="c3601-142">TabControl Control</span></span>  
 <span data-ttu-id="c3601-143"><xref:System.Windows.Forms.TabControl> Элемент управления позволяет рисовать отдельные вкладки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="c3601-144">Рисование владельцем влияет только на вкладки; <xref:System.Windows.Forms.TabPage> содержимое не изменяется.</span><span class="sxs-lookup"><span data-stu-id="c3601-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="c3601-145">Чтобы нарисовать каждую вкладку в <xref:System.Windows.Forms.TabControl>, `DrawMode` установите `DrawItem` свойство в <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> значение и обработайте событие.</span><span class="sxs-lookup"><span data-stu-id="c3601-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="c3601-146">Это событие возникает один раз для каждой вкладки, только если вкладка видна в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="c3601-147">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="c3601-147">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="c3601-148">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="c3601-148">ToolTip Component</span></span>  
 <span data-ttu-id="c3601-149"><xref:System.Windows.Forms.ToolTip> Компонент позволяет рисовать всю всплывающую подсказку при отображении.</span><span class="sxs-lookup"><span data-stu-id="c3601-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="c3601-150">Чтобы нарисовать <xref:System.Windows.Forms.ToolTip>объект, установите `OwnerDraw` его свойство `true` в значение и `Draw` обработайте его событие.</span><span class="sxs-lookup"><span data-stu-id="c3601-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="c3601-151"><xref:System.Windows.Forms.ToolTip> Чтобы настроить размер объекта `Draw` до возникновения `Popup` события, обработайте событие и задайте <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> свойство в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="c3601-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="c3601-152">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="c3601-152">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="c3601-153">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="c3601-153">ListView Control</span></span>  
 <span data-ttu-id="c3601-154"><xref:System.Windows.Forms.ListView> Элемент управления позволяет рисовать отдельные элементы, подэлементы и заголовки столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="c3601-155">Чтобы включить рисование владельцем в элементе управления, задайте для свойства `OwnerDraw` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c3601-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="c3601-156">Для рисования каждого пункта в элементе управления обработайте событие `DrawItem`.</span><span class="sxs-lookup"><span data-stu-id="c3601-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="c3601-157">Для рисования каждого подэлемента или заголовка <xref:System.Windows.Forms.ListView.View%2A> столбца в элементе управления <xref:System.Windows.Forms.View.Details>, если свойство имеет значение, обрабатывает `DrawSubItem` события и `DrawColumnHeader` .</span><span class="sxs-lookup"><span data-stu-id="c3601-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="c3601-158">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="c3601-158">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="c3601-159">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="c3601-159">TreeView Control</span></span>  
 <span data-ttu-id="c3601-160"><xref:System.Windows.Forms.TreeView> Элемент управления позволяет нарисовать отдельные узлы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="c3601-161">Чтобы нарисовать только текст, отображаемый в каждом узле, `DrawMode` установите свойство <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> в значение и `DrawNode` обработайте событие для отрисовки текста.</span><span class="sxs-lookup"><span data-stu-id="c3601-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="c3601-162">Чтобы нарисовать все элементы каждого узла, присвойте `DrawMode` <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> свойству значение и обработайте `DrawNode` событие для отрисовки необходимых элементов, таких как текст, значки, флажки, знаки плюса и минуса, а также линии, соединяющие узлы.</span><span class="sxs-lookup"><span data-stu-id="c3601-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="c3601-163">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="c3601-163">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="c3601-164">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="c3601-164">DataGridView Control</span></span>  
 <span data-ttu-id="c3601-165"><xref:System.Windows.Forms.DataGridView> Элемент управления позволяет рисовать отдельные ячейки и строки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="c3601-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="c3601-166">Для рисования отдельных ячеек обработайте событие `CellPainting`.</span><span class="sxs-lookup"><span data-stu-id="c3601-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="c3601-167">Для рисования отдельных строк или элементов строк обработайте одно или оба события `RowPrePaint` и `RowPostPaint`.</span><span class="sxs-lookup"><span data-stu-id="c3601-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="c3601-168">Событие `RowPrePaint` возникает до рисования ячеек в строке, а событие `RowPostPaint` — после их рисования.</span><span class="sxs-lookup"><span data-stu-id="c3601-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="c3601-169">Можно обрабатывать оба события и событие `CellPainting` для рисования фона строки, отдельных ячеек и переднего плана строки по отдельности. Кроме того, можно предоставить особые настройки в нужных местах и использовать отображение по умолчанию для других элементов строки.</span><span class="sxs-lookup"><span data-stu-id="c3601-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="c3601-170">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c3601-170">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [<span data-ttu-id="c3601-171">Практическое руководство. Настройка внешнего вида ячеек в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="c3601-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [<span data-ttu-id="c3601-172">Практическое руководство. Настройка внешнего вида строк в элементе управления Windows Forms DataGridView</span><span class="sxs-lookup"><span data-stu-id="c3601-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="c3601-173">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c3601-173">ToolStrip Control</span></span>  
 <span data-ttu-id="c3601-174"><xref:System.Windows.Forms.ToolStrip>и производные элементы управления позволяют настраивать любой аспект их внешнего вида.</span><span class="sxs-lookup"><span data-stu-id="c3601-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="c3601-175">Чтобы обеспечить <xref:System.Windows.Forms.ToolStrip> пользовательскую отрисовку для элементов управления, `Renderer` установите свойство <xref:System.Windows.Forms.ToolStrip> `ToolStripRenderer` объекта <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, или <xref:System.Windows.Forms.ToolStripContentPanel> в объект и обработайте одно или несколько событий рисования, предоставляемых `ToolStripRenderer` класс.</span><span class="sxs-lookup"><span data-stu-id="c3601-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="c3601-176">Кроме того, можно `Renderer` установить свойство в экземпляре вашего собственного класса, производного <xref:System.Windows.Forms.ToolStripProfessionalRenderer>от `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripSystemRenderer> или, который реализует или `On`переопределяет конкретные методы *EventName* .</span><span class="sxs-lookup"><span data-stu-id="c3601-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="c3601-177">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="c3601-177">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [<span data-ttu-id="c3601-178">Практическое руководство. Создание и настройка пользовательского модуля отрисовки для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3601-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [<span data-ttu-id="c3601-179">Практическое руководство. Пользовательское рисование элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c3601-179">How to: Custom Draw a ToolStrip Control</span></span>](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3601-180">См. также</span><span class="sxs-lookup"><span data-stu-id="c3601-180">See also</span></span>

- [<span data-ttu-id="c3601-181">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c3601-181">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
