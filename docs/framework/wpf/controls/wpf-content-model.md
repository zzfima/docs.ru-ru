---
title: "Модель содержимого WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d708674682ffd7b0d13c9cbe828e28bbc26e260
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-content-model"></a><span data-ttu-id="7893e-102">Модель содержимого WPF</span><span class="sxs-lookup"><span data-stu-id="7893e-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="7893e-103"> — это презентационная платформа, которая предоставляет множество элементов и типов, схожих с элементами управления, основное предназначение которых — отображение различных типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="7893e-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="7893e-104">Чтобы определить, какой элемент управления использовать или от какого элемента управления выполнять наследование, вы должны понимать, какие виды объектов лучше всего может отображать конкретный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="7893e-105">В этом разделе приводятся обобщенные сведения о модели содержимого для элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и типов, схожих с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="7893e-106">Модель содержимого описывает, какое содержимое может использоваться в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="7893e-107">Также в этом разделе перечисляются свойства содержимого для каждой модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="7893e-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="7893e-108">Свойство содержимого — это свойство, которое используется для хранения содержимого объекта.</span><span class="sxs-lookup"><span data-stu-id="7893e-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="7893e-109">Классы с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="7893e-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="7893e-110">Некоторые элементы управления могут содержать объекты любого типа, например, строка <xref:System.DateTime> объекта, или <xref:System.Windows.UIElement> который является контейнером для дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="7893e-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="7893e-111">Например <xref:System.Windows.Controls.Button> могут содержать изображения и текст; или <xref:System.Windows.Controls.CheckBox> может содержать значение <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7893e-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="7893e-112">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется четыре класса, которые могут иметь произвольное содержимое.</span><span class="sxs-lookup"><span data-stu-id="7893e-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="7893e-113">В следующей таблице перечислены классы, производные от <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="7893e-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="7893e-114">Класс с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="7893e-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="7893e-115">Content</span><span class="sxs-lookup"><span data-stu-id="7893e-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="7893e-116">Один произвольный объект.</span><span class="sxs-lookup"><span data-stu-id="7893e-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="7893e-117">Заголовок и один элемент, которые являются произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="7893e-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="7893e-118">Коллекция произвольных объектов.</span><span class="sxs-lookup"><span data-stu-id="7893e-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="7893e-119">Заголовок и коллекция элементов, являющиеся произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="7893e-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="7893e-120">Элементы управления, производные от этих классов, могут содержать тот же тип содержимого и обрабатывать содержимое аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="7893e-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="7893e-121">На рисунке ниже показаны элементы управления из каждой модели содержимого, содержащие изображение и некоторый текст.</span><span class="sxs-lookup"><span data-stu-id="7893e-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="7893e-122">![Button, GroupBox, Listbox, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="7893e-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="7893e-123">Элементы управления, содержащие один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="7893e-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="7893e-124"><xref:System.Windows.Controls.ContentControl> Класса содержит один элемент произвольного содержимого.</span><span class="sxs-lookup"><span data-stu-id="7893e-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="7893e-125">Свойство содержимого является <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="7893e-126">Следующие элементы управления наследуют от <xref:System.Windows.Controls.ContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="7893e-127">На следующем рисунке показано четыре кнопки, <xref:System.Windows.Controls.ContentControl.Content%2A> строка <xref:System.DateTime> объекта, <xref:System.Windows.Shapes.Rectangle>и <xref:System.Windows.Controls.Panel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7893e-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="7893e-128">![Четыре кнопки](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="7893e-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="7893e-129">Четыре кнопки с различными типами содержимого</span><span class="sxs-lookup"><span data-stu-id="7893e-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="7893e-130">Пример настройки <xref:System.Windows.Controls.ContentControl.Content%2A> свойство, в разделе <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="7893e-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="7893e-131">Элементы управления, содержащие заголовок и один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="7893e-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="7893e-132"><xref:System.Windows.Controls.HeaderedContentControl> Класс наследует от <xref:System.Windows.Controls.ContentControl> и отображает содержимое с заголовком.</span><span class="sxs-lookup"><span data-stu-id="7893e-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="7893e-133">Он наследует свойство содержимого <xref:System.Windows.Controls.ContentControl.Content%2A>, из <xref:System.Windows.Controls.ContentControl> и определяет <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> свойство, которое относится к типу <xref:System.Object>; таким образом, могут иметь любой объект.</span><span class="sxs-lookup"><span data-stu-id="7893e-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="7893e-134">Следующие элементы управления наследуют от <xref:System.Windows.Controls.HeaderedContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="7893e-135">На следующем рисунке показано два <xref:System.Windows.Controls.TabItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="7893e-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="7893e-136">Первый <xref:System.Windows.Controls.TabItem> имеет <xref:System.Windows.UIElement> объектов <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="7893e-137"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Равно <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7893e-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="7893e-138"><xref:System.Windows.Controls.ContentControl.Content%2A> Равно <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="7893e-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="7893e-139">Второй <xref:System.Windows.Controls.TabItem> имеет строку <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="7893e-140">![Элемент управления TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="7893e-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="7893e-141">Элемент управления TabControl, который использует различные типы в свойстве Header</span><span class="sxs-lookup"><span data-stu-id="7893e-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="7893e-142">Пример создания <xref:System.Windows.Controls.TabItem> объектов, в разделе <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="7893e-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="7893e-143">Элементы управления, содержащие коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="7893e-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="7893e-144"><xref:System.Windows.Controls.ItemsControl> Класс наследует от <xref:System.Windows.Controls.Control> и может содержать несколько элементов, таких как строки, объектов или других элементов.</span><span class="sxs-lookup"><span data-stu-id="7893e-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="7893e-145">Его свойства содержимого – <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="7893e-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>обычно используется для заполнения <xref:System.Windows.Controls.ItemsControl> сбора данных.</span><span class="sxs-lookup"><span data-stu-id="7893e-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="7893e-147">Если не хотите использовать коллекцию для заполнения <xref:System.Windows.Controls.ItemsControl>, можно добавить элементы с помощью <xref:System.Windows.Controls.ItemsControl.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7893e-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="7893e-148">Следующие элементы управления наследуют от <xref:System.Windows.Controls.ItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="7893e-149">На следующем рисунке показана <xref:System.Windows.Controls.ListBox> , содержащий эти типы элементов:</span><span class="sxs-lookup"><span data-stu-id="7893e-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="7893e-150">Строка.</span><span class="sxs-lookup"><span data-stu-id="7893e-150">A string.</span></span>  
  
-   <span data-ttu-id="7893e-151">Объект <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="7893e-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="7893e-152">Объект <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="7893e-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="7893e-153">Объект <xref:System.Windows.Controls.Panel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="7893e-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="7893e-154">![ListBox с четырьмя типами содержимого](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="7893e-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="7893e-155">Элемент управления ListBox, содержащий несколько типов объектов</span><span class="sxs-lookup"><span data-stu-id="7893e-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="7893e-156">Элементы управления, содержащие заголовок и коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="7893e-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="7893e-157"><xref:System.Windows.Controls.HeaderedItemsControl> Класс наследует от <xref:System.Windows.Controls.ItemsControl> и может содержать несколько элементов, такие как строки, объекты, или другие элементы и заголовок.</span><span class="sxs-lookup"><span data-stu-id="7893e-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="7893e-158">Он наследует <xref:System.Windows.Controls.ItemsControl> свойства, содержимого <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, и <xref:System.Windows.Controls.ItemsControl.Items%2A>, и он определяет <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> свойство, которое может быть любой объект.</span><span class="sxs-lookup"><span data-stu-id="7893e-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="7893e-159">Следующие элементы управления наследуют от <xref:System.Windows.Controls.HeaderedItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="7893e-160">Классы, содержащие коллекцию объектов UIElement</span><span class="sxs-lookup"><span data-stu-id="7893e-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="7893e-161"><xref:System.Windows.Controls.Panel> Класс размещает и размещает дочерние <xref:System.Windows.UIElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="7893e-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="7893e-162">Свойство содержимого является <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="7893e-163">Следующие классы наследуют от <xref:System.Windows.Controls.Panel> класса и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="7893e-164">Дополнительные сведения см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7893e-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="7893e-165">Классы, влияющие на внешний вид объекта UIElement</span><span class="sxs-lookup"><span data-stu-id="7893e-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="7893e-166"><xref:System.Windows.Controls.Decorator> Класс применяется визуальные эффекты или вокруг один дочерний <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="7893e-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="7893e-167">Свойство содержимого является <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="7893e-168">Следующие классы наследуют от <xref:System.Windows.Controls.Decorator> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="7893e-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="7893e-169">На следующем рисунке показана <xref:System.Windows.Controls.TextBox> с (снабжен) <xref:System.Windows.Controls.Border> вокруг нее.</span><span class="sxs-lookup"><span data-stu-id="7893e-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="7893e-170">![TextBox с черной границей](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="7893e-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="7893e-171">Элемент управления TextBlock с границей вокруг него</span><span class="sxs-lookup"><span data-stu-id="7893e-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="7893e-172">Классы, предоставляющие визуальную обратную связь об объекте UIElement</span><span class="sxs-lookup"><span data-stu-id="7893e-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="7893e-173"><xref:System.Windows.Documents.Adorner> Класс предоставляет визуальные подсказки для пользователя.</span><span class="sxs-lookup"><span data-stu-id="7893e-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="7893e-174">Например, использовать <xref:System.Windows.Documents.Adorner> добавить в элементы функциональные обработчики или предоставить сведения о состоянии управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="7893e-175"><xref:System.Windows.Documents.Adorner> Класс предоставляет платформу, чтобы при создании собственных графических элементов.</span><span class="sxs-lookup"><span data-stu-id="7893e-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="7893e-176"> не предоставляет никаких реализованных декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="7893e-176"> does not provide any implemented adorners.</span></span> <span data-ttu-id="7893e-177">Дополнительные сведения см. в разделе [Общие сведения о декоративных элементах](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7893e-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="7893e-178">Классы, позволяющие пользователям вводить текст</span><span class="sxs-lookup"><span data-stu-id="7893e-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="7893e-179">WPF предоставляет три основных элемента управления, которые позволяют пользователям вводить текст.</span><span class="sxs-lookup"><span data-stu-id="7893e-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="7893e-180">Каждый из этих элементов управления отображает текст по-разному.</span><span class="sxs-lookup"><span data-stu-id="7893e-180">Each control displays the text differently.</span></span> <span data-ttu-id="7893e-181">В следующей таблице приведены эти три элемента управления с поддержкой ввода текста, их возможности по отображению текста и свойства, которые содержат текст этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="7893e-182">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="7893e-182">Control</span></span>|<span data-ttu-id="7893e-183">В каком виде отображается текст</span><span class="sxs-lookup"><span data-stu-id="7893e-183">Text is displayed as</span></span>|<span data-ttu-id="7893e-184">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="7893e-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="7893e-185">Обычный текст</span><span class="sxs-lookup"><span data-stu-id="7893e-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="7893e-186">Форматированный текст</span><span class="sxs-lookup"><span data-stu-id="7893e-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="7893e-187">Скрытый текст (символы скрыты)</span><span class="sxs-lookup"><span data-stu-id="7893e-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="7893e-188">Классы, отображающие пользовательский текст</span><span class="sxs-lookup"><span data-stu-id="7893e-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="7893e-189">Некоторые классы могут использоваться для отображения простого или форматированного текста.</span><span class="sxs-lookup"><span data-stu-id="7893e-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="7893e-190">Можно использовать <xref:System.Windows.Controls.TextBlock> для отображения небольших объемов текста.</span><span class="sxs-lookup"><span data-stu-id="7893e-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="7893e-191">Если вы хотите отображать большие объемы текста, используйте <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, или <xref:System.Windows.Controls.FlowDocumentScrollViewer> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7893e-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="7893e-192"><xref:System.Windows.Controls.TextBlock> Имеет два свойства содержимого: <xref:System.Windows.Controls.TextBlock.Text%2A> и <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="7893e-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="7893e-193">Если вы хотите отображать текст, использующий последовательное форматирование <xref:System.Windows.Controls.TextBlock.Text%2A> свойство часто является оптимальным решением.</span><span class="sxs-lookup"><span data-stu-id="7893e-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="7893e-194">Если вы планируете использовать разное форматирование текста, используйте <xref:System.Windows.Controls.TextBlock.Inlines%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7893e-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="7893e-195"><xref:System.Windows.Controls.TextBlock.Inlines%2A> Свойство — это коллекция <xref:System.Windows.Documents.Inline> объектами, указывающих способ форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="7893e-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="7893e-196">В следующей таблице перечислены свойства содержимого для <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, и <xref:System.Windows.Controls.FlowDocumentScrollViewer> классы.</span><span class="sxs-lookup"><span data-stu-id="7893e-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="7893e-197">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="7893e-197">Control</span></span>|<span data-ttu-id="7893e-198">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="7893e-198">Content property</span></span>|<span data-ttu-id="7893e-199">Тип свойства содержимого</span><span class="sxs-lookup"><span data-stu-id="7893e-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="7893e-200">Document</span><span class="sxs-lookup"><span data-stu-id="7893e-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="7893e-201">Document</span><span class="sxs-lookup"><span data-stu-id="7893e-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="7893e-202">Document</span><span class="sxs-lookup"><span data-stu-id="7893e-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="7893e-203"><xref:System.Windows.Documents.FlowDocument> Реализует <xref:System.Windows.Documents.IDocumentPaginatorSource> интерфейс; таким образом, может потребоваться все три класса <xref:System.Windows.Documents.FlowDocument> как содержимое.</span><span class="sxs-lookup"><span data-stu-id="7893e-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="7893e-204">Классы, выполняющие форматирование пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="7893e-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="7893e-205"><xref:System.Windows.Documents.TextElement>и его связанные классы позволяют форматировать текст.</span><span class="sxs-lookup"><span data-stu-id="7893e-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="7893e-206"><xref:System.Windows.Documents.TextElement>объекты содержат и форматирование текста в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов.</span><span class="sxs-lookup"><span data-stu-id="7893e-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="7893e-207">Два основных типа <xref:System.Windows.Documents.TextElement> объектов <xref:System.Windows.Documents.Block> элементы и <xref:System.Windows.Documents.Inline> элементы.</span><span class="sxs-lookup"><span data-stu-id="7893e-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="7893e-208">Объект <xref:System.Windows.Documents.Block> представляет блок текста, например абзаца или список.</span><span class="sxs-lookup"><span data-stu-id="7893e-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="7893e-209"><xref:System.Windows.Documents.Inline> Элемент представляет часть текста в блоке.</span><span class="sxs-lookup"><span data-stu-id="7893e-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="7893e-210">Многие <xref:System.Windows.Documents.Inline> классы указать форматирование для текста, к которому они применяются.</span><span class="sxs-lookup"><span data-stu-id="7893e-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="7893e-211">Каждый <xref:System.Windows.Documents.TextElement> имеет свою собственную модель содержимого.</span><span class="sxs-lookup"><span data-stu-id="7893e-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="7893e-212">Подробнее см. в разделе [Общие сведения о модели содержимого TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7893e-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7893e-213">См. также</span><span class="sxs-lookup"><span data-stu-id="7893e-213">See Also</span></span>  
 [<span data-ttu-id="7893e-214">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="7893e-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
