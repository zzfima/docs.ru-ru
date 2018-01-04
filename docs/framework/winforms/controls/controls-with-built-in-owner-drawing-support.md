---
title: "Элементы управления Windows Forms со встроенной поддержки рисования владельцем"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efd297dcc11005d6b6d47bb9ce3853a757046e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="b011c-102">Элементы управления Windows Forms со встроенной поддержки рисования владельцем</span><span class="sxs-lookup"><span data-stu-id="b011c-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="b011c-103">Рисование владельцем в Windows Forms, иначе называемое пользовательским рисованием, — это способ изменения внешнего вида определенных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b011c-104">Слово «элемент управления» этого раздела используется для обозначения классов, которые являются производными либо от <xref:System.Windows.Forms.Control> или <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="b011c-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="b011c-105">Как правило, Windows, рисование обрабатывается автоматически при помощи параметров свойств, таких как <xref:System.Windows.Forms.Control.BackColor%2A> для определения внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="b011c-106">При рисовании владельцем можно перехватить процесс рисования, изменив элементы внешнего вида, которые недоступны при использовании свойств.</span><span class="sxs-lookup"><span data-stu-id="b011c-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="b011c-107">Например, многие элементы управления позволяют задавать цвет отображаемого текста, но вы ограничены одним цветом.</span><span class="sxs-lookup"><span data-stu-id="b011c-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="b011c-108">Рисование владельцем позволяет, например, отображать часть текста черным цветом, а другую часть — красным.</span><span class="sxs-lookup"><span data-stu-id="b011c-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="b011c-109">На практике рисование владельцем аналогично рисованию графических элементов в форме.</span><span class="sxs-lookup"><span data-stu-id="b011c-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="b011c-110">Например, можно использовать графические методы в обработчике для формы <xref:System.Windows.Forms.Control.Paint> событий для эмуляции `ListBox` контроль, но вам потребуется написать собственный код для управления взаимодействием с пользователем.</span><span class="sxs-lookup"><span data-stu-id="b011c-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="b011c-111">При рисовании владельцем элемент управления использует ваш код для рисования своего содержимого, но в остальном сохраняет все свои внутренние возможности.</span><span class="sxs-lookup"><span data-stu-id="b011c-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="b011c-112">Графические методы можно использовать для рисования каждого элемента в элементе управления или для настройки некоторых аспектов каждого элемента при использовании внешнего вида по умолчанию для других аспектов каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="b011c-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="b011c-113">Рисование владельцем в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b011c-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="b011c-114">Чтобы выполнить рисование владельцем в элементах управления, поддерживающих эту функцию, вы, как правило, задаете одно свойство и обрабатываете одно или несколько событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="b011c-115">Большинство элементов управления, поддерживающих рисование владельцем, имеют свойство `OwnerDraw` или `DrawMode`, указывающее, будет ли элемент управления вызывать связанные с рисованием события при рисовании себя.</span><span class="sxs-lookup"><span data-stu-id="b011c-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="b011c-116">Элементы управления, которые не имеют свойства `OwnerDraw` или `DrawMode`, включают элемент управления `DataGridView`, предоставляющий происходящие автоматически события рисования, и элемент управления `ToolStrip`, рисуемый с помощью внешнего класса отрисовки, имеющего собственные события, связанные с рисованием.</span><span class="sxs-lookup"><span data-stu-id="b011c-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="b011c-117">Существует много различных типов событий рисования, однако типичное событие рисования возникает для рисования отдельного элемента внутри элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="b011c-118">Обработчик событий получает объект `EventArgs`, который содержит сведения о рисуемом элементе, и инструменты, которые можно использовать для рисования.</span><span class="sxs-lookup"><span data-stu-id="b011c-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="b011c-119">Например, этот объект обычно содержит порядковый номер элемента в его родительской коллекции <xref:System.Drawing.Rectangle> указывает отображения границ элемента и <xref:System.Drawing.Graphics> объекта для вызова методов рисования.</span><span class="sxs-lookup"><span data-stu-id="b011c-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="b011c-120">Для некоторых событий объект `EventArgs` предоставляет дополнительные сведения об элементе и методах, которые можно вызвать для рисования некоторых аспектов элемента по умолчанию, таких как фон или прямоугольник фокуса.</span><span class="sxs-lookup"><span data-stu-id="b011c-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="b011c-121">Чтобы создать элемент управления для повторного использования, содержащий настройки рисования владельцем, создайте новый класс, производный от класса элемента управления, который поддерживает рисование владельцем.</span><span class="sxs-lookup"><span data-stu-id="b011c-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="b011c-122">Вместо обработки событий рисования включите код рисования владельцем в переопределения для соответствующего метода или методов `On`*ИмяСобытия* в новом классе.</span><span class="sxs-lookup"><span data-stu-id="b011c-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="b011c-123">Убедитесь в том, что в этом случае вызывается метод или методы `On`*ИмяСобытия* базового класса, чтобы пользователи элемента управления могли обрабатывать события рисования владельцем и выполнять дополнительные настройки.</span><span class="sxs-lookup"><span data-stu-id="b011c-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="b011c-124">Следующие элементы управления Windows Forms поддерживают рисование владельцем во всех версиях .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b011c-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <span data-ttu-id="b011c-125"><xref:System.Windows.Forms.MenuItem>(используемые <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="b011c-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="b011c-126">Следующие элементы управления поддерживают рисование владельцем только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b011c-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="b011c-127">Следующие элементы управления поддерживают рисование владельцем и являются новыми в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b011c-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="b011c-128">В следующих разделах приводятся дополнительные сведения для каждого из этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="b011c-129">Элементы управления ListBox и ComboBox</span><span class="sxs-lookup"><span data-stu-id="b011c-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="b011c-130"><xref:System.Windows.Forms.ListBox> И <xref:System.Windows.Forms.ComboBox> элементы управления позволяют рисовать отдельные элементы в элементе управления одного или разного размера.</span><span class="sxs-lookup"><span data-stu-id="b011c-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b011c-131">Несмотря на то что <xref:System.Windows.Forms.CheckedListBox> управления является производным от <xref:System.Windows.Forms.ListBox> элемента управления, он не поддерживает рисование владельцем.</span><span class="sxs-lookup"><span data-stu-id="b011c-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="b011c-132">Для рисования каждого элемента тот же размер, `DrawMode` свойства <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> и обрабатывать `DrawItem` событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="b011c-133">Для рисования элементов разного размера, задайте `DrawMode` свойства <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> и обработать `MeasureItem` и `DrawItem` события.</span><span class="sxs-lookup"><span data-stu-id="b011c-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="b011c-134">Событие `MeasureItem` позволяет указать размер элемента, прежде чем возникнет событие `DrawItem` для этого элемента.</span><span class="sxs-lookup"><span data-stu-id="b011c-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="b011c-135">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b011c-135">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [<span data-ttu-id="b011c-136">Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="b011c-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="b011c-137">Компонент MenuItem</span><span class="sxs-lookup"><span data-stu-id="b011c-137">MenuItem Component</span></span>  
 <span data-ttu-id="b011c-138"><xref:System.Windows.Forms.MenuItem> Компонент представляет собой отдельный пункт меню в <xref:System.Windows.Forms.MainMenu> или <xref:System.Windows.Forms.ContextMenu> компонента.</span><span class="sxs-lookup"><span data-stu-id="b011c-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="b011c-139">Для рисования <xref:System.Windows.Forms.MenuItem>, задайте его `OwnerDraw` свойства `true` и обработать его `DrawItem` событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="b011c-140">Чтобы изменять размер элемента меню перед возникновением события `DrawItem`, требуется обработка события `MeasureItem` элемента.</span><span class="sxs-lookup"><span data-stu-id="b011c-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="b011c-141">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="b011c-141">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="b011c-142">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="b011c-142">TabControl Control</span></span>  
 <span data-ttu-id="b011c-143"><xref:System.Windows.Forms.TabControl> Позволяет рисовать отдельные вкладки в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="b011c-144">Рисование владельцем влияет только на вкладки; <xref:System.Windows.Forms.TabPage> содержимое не затрагиваются.</span><span class="sxs-lookup"><span data-stu-id="b011c-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="b011c-145">Для рисования вкладки <xref:System.Windows.Forms.TabControl>, задайте `DrawMode` свойства <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> и обрабатывать `DrawItem` событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="b011c-146">Это событие возникает один раз для каждой вкладки, только если вкладка видна в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="b011c-147">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="b011c-147">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="b011c-148">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="b011c-148">ToolTip Component</span></span>  
 <span data-ttu-id="b011c-149"><xref:System.Windows.Forms.ToolTip> Компонент позволяет рисовать ToolTip целиком при его отображении.</span><span class="sxs-lookup"><span data-stu-id="b011c-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="b011c-150">Для рисования <xref:System.Windows.Forms.ToolTip>, задайте его `OwnerDraw` свойства `true` и обработать его `Draw` событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="b011c-151">Чтобы настроить размер <xref:System.Windows.Forms.ToolTip> перед `Draw` происходит событие, обрабатывать `Popup` событий и набор <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> свойство в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="b011c-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="b011c-152">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="b011c-152">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="b011c-153">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="b011c-153">ListView Control</span></span>  
 <span data-ttu-id="b011c-154"><xref:System.Windows.Forms.ListView> Позволяет рисовать отдельные элементы, подпункты и заголовки столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="b011c-155">Чтобы включить рисование владельцем в элементе управления, задайте для свойства `OwnerDraw` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="b011c-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="b011c-156">Для рисования каждого пункта в элементе управления обработайте событие `DrawItem`.</span><span class="sxs-lookup"><span data-stu-id="b011c-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="b011c-157">Чтобы нарисовать Заголовок каждого вложенного элемента или столбца в элементе управления при <xref:System.Windows.Forms.ListView.View%2A> свойству <xref:System.Windows.Forms.View.Details>, обрабатывать `DrawSubItem` и `DrawColumnHeader` события.</span><span class="sxs-lookup"><span data-stu-id="b011c-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="b011c-158">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="b011c-158">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="b011c-159">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="b011c-159">TreeView Control</span></span>  
 <span data-ttu-id="b011c-160"><xref:System.Windows.Forms.TreeView> Позволяет рисовать отдельные узлы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="b011c-161">Чтобы нарисовать только текст, отображаемый в каждом узле, установите `DrawMode` свойства <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> и обрабатывать `DrawNode` событий для рисования текста.</span><span class="sxs-lookup"><span data-stu-id="b011c-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="b011c-162">Чтобы нарисовать все элементы каждого узла, установите `DrawMode` свойства <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> и обрабатывать `DrawNode` событий для рисования любых требуемых, такие как текста, значков, установите флажки, плюса и минуса, а также линии, соединяющие узлы элементов.</span><span class="sxs-lookup"><span data-stu-id="b011c-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="b011c-163">Дополнительные сведения, включая примеры кода, см. в следующих разделах справочника.</span><span class="sxs-lookup"><span data-stu-id="b011c-163">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="b011c-164">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="b011c-164">DataGridView Control</span></span>  
 <span data-ttu-id="b011c-165"><xref:System.Windows.Forms.DataGridView> Позволяет рисовать отдельных ячеек и строк в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b011c-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="b011c-166">Для рисования отдельных ячеек обработайте событие `CellPainting`.</span><span class="sxs-lookup"><span data-stu-id="b011c-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="b011c-167">Для рисования отдельных строк или элементов строк обработайте одно или оба события `RowPrePaint` и `RowPostPaint`.</span><span class="sxs-lookup"><span data-stu-id="b011c-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="b011c-168">Событие `RowPrePaint` возникает до рисования ячеек в строке, а событие `RowPostPaint` — после их рисования.</span><span class="sxs-lookup"><span data-stu-id="b011c-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="b011c-169">Можно обрабатывать оба события и событие `CellPainting` для рисования фона строки, отдельных ячеек и переднего плана строки по отдельности. Кроме того, можно предоставить особые настройки в нужных местах и использовать отображение по умолчанию для других элементов строки.</span><span class="sxs-lookup"><span data-stu-id="b011c-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="b011c-170">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b011c-170">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [<span data-ttu-id="b011c-171">Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b011c-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [<span data-ttu-id="b011c-172">Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b011c-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="b011c-173">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b011c-173">ToolStrip Control</span></span>  
 <span data-ttu-id="b011c-174"><xref:System.Windows.Forms.ToolStrip>и производные элементы управления дают возможность настраивать все аспекты их внешний вид.</span><span class="sxs-lookup"><span data-stu-id="b011c-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="b011c-175">Чтобы предоставить пользовательскую отрисовку для <xref:System.Windows.Forms.ToolStrip> элементов управления `Renderer` свойство <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, или <xref:System.Windows.Forms.ToolStripContentPanel> для `ToolStripRenderer` и обработать один или несколько из большого числа событий рисования по `ToolStripRenderer` класса.</span><span class="sxs-lookup"><span data-stu-id="b011c-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="b011c-176">Можно также задать `Renderer` свойство для экземпляра собственный класс, производный от `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, или <xref:System.Windows.Forms.ToolStripSystemRenderer> , реализующего или переопределяющего определенные `On` *EventName* методы.</span><span class="sxs-lookup"><span data-stu-id="b011c-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="b011c-177">Дополнительные сведения, включая примеры кода, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b011c-177">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [<span data-ttu-id="b011c-178">Практическое руководство. Создание и определение пользовательского средства визуализации для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b011c-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [<span data-ttu-id="b011c-179">Практическое руководство. Пользовательская прорисовка элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="b011c-179">How to: Custom Draw a ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="b011c-180">См. также</span><span class="sxs-lookup"><span data-stu-id="b011c-180">See Also</span></span>  
 [<span data-ttu-id="b011c-181">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b011c-181">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
