---
title: Модель содержимого
ms.date: 03/30/2017
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
ms.openlocfilehash: a84ab2e66b4e373591fc9365b1c17d0bb0c66713
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738281"
---
# <a name="wpf-content-model"></a><span data-ttu-id="79770-102">Модель содержимого WPF</span><span class="sxs-lookup"><span data-stu-id="79770-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="79770-103">— это презентационная платформа, которая предоставляет множество элементов и типов, схожих с элементами управления, основное предназначение которых — отображение различных типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="79770-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="79770-104">Чтобы определить, какой элемент управления использовать или от какого элемента управления выполнять наследование, вы должны понимать, какие виды объектов лучше всего может отображать конкретный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="79770-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="79770-105">В этом разделе приводятся обобщенные сведения о модели содержимого для элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и типов, схожих с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="79770-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="79770-106">Модель содержимого описывает, какое содержимое может использоваться в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="79770-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="79770-107">Также в этом разделе перечисляются свойства содержимого для каждой модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="79770-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="79770-108">Свойство содержимого — это свойство, которое используется для хранения содержимого объекта.</span><span class="sxs-lookup"><span data-stu-id="79770-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="79770-109">Классы с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="79770-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="79770-110">Некоторые элементы управления могут содержать объект любого типа, например строку, объект <xref:System.DateTime> или <xref:System.Windows.UIElement>, который является контейнером для дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="79770-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="79770-111">Например, <xref:System.Windows.Controls.Button> может содержать изображение и некоторый текст; или <xref:System.Windows.Controls.CheckBox> может содержать значение <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79770-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="79770-112">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется четыре класса, которые могут иметь произвольное содержимое.</span><span class="sxs-lookup"><span data-stu-id="79770-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="79770-113">В следующей таблице перечислены классы, которые наследуются от <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="79770-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="79770-114">Класс с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="79770-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="79770-115">Content</span><span class="sxs-lookup"><span data-stu-id="79770-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="79770-116">Один произвольный объект.</span><span class="sxs-lookup"><span data-stu-id="79770-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="79770-117">Заголовок и один элемент, которые являются произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="79770-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="79770-118">Коллекция произвольных объектов.</span><span class="sxs-lookup"><span data-stu-id="79770-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="79770-119">Заголовок и коллекция элементов, являющиеся произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="79770-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="79770-120">Элементы управления, производные от этих классов, могут содержать тот же тип содержимого и обрабатывать содержимое аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="79770-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="79770-121">На следующем рисунке показан один элемент управления из каждой модели содержимого, который содержит изображение и некоторый текст:</span><span class="sxs-lookup"><span data-stu-id="79770-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![Снимок экрана, на котором показаны четыре различных элемента управления — по одному из каждой модели содержимого.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="79770-123">Элементы управления, содержащие один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="79770-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="79770-124">Класс <xref:System.Windows.Controls.ContentControl> содержит один фрагмент произвольного содержимого.</span><span class="sxs-lookup"><span data-stu-id="79770-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="79770-125">Его свойство содержимого — <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="79770-126">Следующие элементы управления наследуются от <xref:System.Windows.Controls.ContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="79770-127">На следующем рисунке показаны четыре кнопки, для которых <xref:System.Windows.Controls.ContentControl.Content%2A> задана строка, <xref:System.DateTime> объект, <xref:System.Windows.Shapes.Rectangle>и <xref:System.Windows.Controls.Panel>, содержащая <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>:</span><span class="sxs-lookup"><span data-stu-id="79770-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Снимок экрана, на котором показаны четыре кнопки с разными типами содержимого.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="79770-129">Пример задания свойства <xref:System.Windows.Controls.ContentControl.Content%2A> см. в разделе <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="79770-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="79770-130">Элементы управления, содержащие заголовок и один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="79770-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="79770-131">Класс <xref:System.Windows.Controls.HeaderedContentControl> наследует от <xref:System.Windows.Controls.ContentControl> и отображает содержимое с заголовком.</span><span class="sxs-lookup"><span data-stu-id="79770-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="79770-132">Он наследует свойство содержимого <xref:System.Windows.Controls.ContentControl.Content%2A>от <xref:System.Windows.Controls.ContentControl> и определяет свойство <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>, которое имеет тип <xref:System.Object>. Таким образом, оба могут быть произвольным объектом.</span><span class="sxs-lookup"><span data-stu-id="79770-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="79770-133">Следующие элементы управления наследуются от <xref:System.Windows.Controls.HeaderedContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="79770-134">На следующем рисунке показаны два объекта <xref:System.Windows.Controls.TabItem>.</span><span class="sxs-lookup"><span data-stu-id="79770-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="79770-135">Первый <xref:System.Windows.Controls.TabItem> имеет <xref:System.Windows.UIElement> объектов в качестве <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="79770-136">Для <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> задается <xref:System.Windows.Controls.StackPanel>, содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="79770-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="79770-137">Для <xref:System.Windows.Controls.ContentControl.Content%2A> задается <xref:System.Windows.Controls.StackPanel>, содержащий <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="79770-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="79770-138">Второй <xref:System.Windows.Controls.TabItem> содержит строку в <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![Элемент TabControl, использующий различные типы в свойстве Header.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="79770-140">Пример создания объектов <xref:System.Windows.Controls.TabItem> см. в разделе <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="79770-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="79770-141">Элементы управления, содержащие коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="79770-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="79770-142">Класс <xref:System.Windows.Controls.ItemsControl> наследует от <xref:System.Windows.Controls.Control> и может содержать несколько элементов, таких как строки, объекты или другие элементы.</span><span class="sxs-lookup"><span data-stu-id="79770-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="79770-143">Его свойства содержимого — <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="79770-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> обычно используется для заполнения <xref:System.Windows.Controls.ItemsControl> коллекцией данных.</span><span class="sxs-lookup"><span data-stu-id="79770-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="79770-145">Если вы не хотите использовать коллекцию для заполнения <xref:System.Windows.Controls.ItemsControl>, можно добавить элементы с помощью свойства <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="79770-146">Следующие элементы управления наследуются от <xref:System.Windows.Controls.ItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="79770-147">На следующем рисунке показана <xref:System.Windows.Controls.ListBox>, содержащая следующие типы элементов:</span><span class="sxs-lookup"><span data-stu-id="79770-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="79770-148">Строка.</span><span class="sxs-lookup"><span data-stu-id="79770-148">A string.</span></span>  
  
- <span data-ttu-id="79770-149">Объект <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="79770-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="79770-150">Объект <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="79770-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="79770-151"><xref:System.Windows.Controls.Panel>, содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="79770-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Снимок экрана, на котором показан элемент управления ListBox с четырьмя типами содержимого.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="79770-153">Элементы управления, содержащие заголовок и коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="79770-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="79770-154">Класс <xref:System.Windows.Controls.HeaderedItemsControl> наследует от <xref:System.Windows.Controls.ItemsControl> и может содержать несколько элементов, таких как строки, объекты или другие элементы, и заголовок.</span><span class="sxs-lookup"><span data-stu-id="79770-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="79770-155">Он наследует свойства содержимого <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>и <xref:System.Windows.Controls.ItemsControl.Items%2A>, а также определяет свойство <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>, которое может быть произвольным объектом.</span><span class="sxs-lookup"><span data-stu-id="79770-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="79770-156">Следующие элементы управления наследуются от <xref:System.Windows.Controls.HeaderedItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="79770-157">Классы, содержащие коллекцию объектов UIElement</span><span class="sxs-lookup"><span data-stu-id="79770-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="79770-158">Класс <xref:System.Windows.Controls.Panel> размещает и упорядочивает дочерние объекты <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="79770-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="79770-159">Его свойство содержимого — <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="79770-160">Следующие классы наследуют от класса <xref:System.Windows.Controls.Panel> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="79770-161">Дополнительные сведения см. в разделе [Общие сведения о панелях](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79770-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="79770-162">Классы, влияющие на внешний вид объекта UIElement</span><span class="sxs-lookup"><span data-stu-id="79770-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="79770-163">Класс <xref:System.Windows.Controls.Decorator> применяет визуальные эффекты к одному дочернему <xref:System.Windows.UIElement>или вокруг него.</span><span class="sxs-lookup"><span data-stu-id="79770-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="79770-164">Его свойство содержимого — <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="79770-165">Следующие классы наследуют от <xref:System.Windows.Controls.Decorator> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="79770-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="79770-166">На следующем рисунке показана <xref:System.Windows.Controls.TextBox> с раз<xref:System.Windows.Controls.Border> вокруг него.</span><span class="sxs-lookup"><span data-stu-id="79770-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="79770-167">![Элемент управления TextBox с черной границей вокруг него](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="79770-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="79770-168">Элемент управления TextBlock с границей вокруг него</span><span class="sxs-lookup"><span data-stu-id="79770-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="79770-169">Классы, предоставляющие визуальную обратную связь об объекте UIElement</span><span class="sxs-lookup"><span data-stu-id="79770-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="79770-170">Класс <xref:System.Windows.Documents.Adorner> предоставляет пользователю визуальные подсказки.</span><span class="sxs-lookup"><span data-stu-id="79770-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="79770-171">Например, можно использовать <xref:System.Windows.Documents.Adorner> для добавления функциональных дескрипторов к элементам или предоставления сведений о состоянии элемента управления.</span><span class="sxs-lookup"><span data-stu-id="79770-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="79770-172">Класс <xref:System.Windows.Documents.Adorner> предоставляет платформу, позволяющую создавать собственные графические элементы.</span><span class="sxs-lookup"><span data-stu-id="79770-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="79770-173">не предоставляет никаких реализованных декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="79770-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="79770-174">Дополнительные сведения см. в разделе [Общие сведения о декоративных элементах](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79770-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="79770-175">Классы, позволяющие пользователям вводить текст</span><span class="sxs-lookup"><span data-stu-id="79770-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="79770-176">WPF предоставляет три основных элемента управления, которые позволяют пользователям вводить текст.</span><span class="sxs-lookup"><span data-stu-id="79770-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="79770-177">Каждый из этих элементов управления отображает текст по-разному.</span><span class="sxs-lookup"><span data-stu-id="79770-177">Each control displays the text differently.</span></span> <span data-ttu-id="79770-178">В следующей таблице приведены эти три элемента управления с поддержкой ввода текста, их возможности по отображению текста и свойства, которые содержат текст этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="79770-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="79770-179">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="79770-179">Control</span></span>|<span data-ttu-id="79770-180">В каком виде отображается текст</span><span class="sxs-lookup"><span data-stu-id="79770-180">Text is displayed as</span></span>|<span data-ttu-id="79770-181">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="79770-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="79770-182">Обычный текст</span><span class="sxs-lookup"><span data-stu-id="79770-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="79770-183">Форматированный текст</span><span class="sxs-lookup"><span data-stu-id="79770-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="79770-184">Скрытый текст (символы скрыты)</span><span class="sxs-lookup"><span data-stu-id="79770-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="79770-185">Классы, отображающие пользовательский текст</span><span class="sxs-lookup"><span data-stu-id="79770-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="79770-186">Некоторые классы могут использоваться для отображения простого или форматированного текста.</span><span class="sxs-lookup"><span data-stu-id="79770-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="79770-187">Для вывода небольшого объема текста можно использовать <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="79770-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="79770-188">Если требуется отображать большие объемы текста, используйте элементы управления <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79770-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="79770-189">У <xref:System.Windows.Controls.TextBlock> есть два свойства содержимого: <xref:System.Windows.Controls.TextBlock.Text%2A> и <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="79770-190">Если требуется отображать текст, использующий единообразное форматирование, чаще всего используется свойство <xref:System.Windows.Controls.TextBlock.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="79770-191">Если вы планируете использовать разное форматирование во всем тексте, используйте свойство <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="79770-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="79770-192">Свойство <xref:System.Windows.Controls.TextBlock.Inlines%2A> — это коллекция объектов <xref:System.Windows.Documents.Inline>, которые определяют способ форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="79770-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="79770-193">В следующей таблице перечислены свойства содержимого для классов <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>и <xref:System.Windows.Controls.FlowDocumentScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="79770-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="79770-194">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="79770-194">Control</span></span>|<span data-ttu-id="79770-195">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="79770-195">Content property</span></span>|<span data-ttu-id="79770-196">Тип свойства содержимого</span><span class="sxs-lookup"><span data-stu-id="79770-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="79770-197">Document</span><span class="sxs-lookup"><span data-stu-id="79770-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="79770-198">Document</span><span class="sxs-lookup"><span data-stu-id="79770-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="79770-199">Document</span><span class="sxs-lookup"><span data-stu-id="79770-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="79770-200"><xref:System.Windows.Documents.FlowDocument> реализует интерфейс <xref:System.Windows.Documents.IDocumentPaginatorSource>; Таким образом, все три класса могут принимать <xref:System.Windows.Documents.FlowDocument> как содержимое.</span><span class="sxs-lookup"><span data-stu-id="79770-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="79770-201">Классы, выполняющие форматирование пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="79770-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="79770-202"><xref:System.Windows.Documents.TextElement> и связанные с ним классы позволяют форматировать текст.</span><span class="sxs-lookup"><span data-stu-id="79770-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="79770-203"><xref:System.Windows.Documents.TextElement> объекты содержат и форматируют текст в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>ных объектах.</span><span class="sxs-lookup"><span data-stu-id="79770-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="79770-204">Двумя основными типами <xref:System.Windows.Documents.TextElement> объектов являются <xref:System.Windows.Documents.Block> элементы и элементы <xref:System.Windows.Documents.Inline>.</span><span class="sxs-lookup"><span data-stu-id="79770-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="79770-205">Элемент <xref:System.Windows.Documents.Block> представляет блок текста, например абзац или список.</span><span class="sxs-lookup"><span data-stu-id="79770-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="79770-206">Элемент <xref:System.Windows.Documents.Inline> представляет часть текста в блоке.</span><span class="sxs-lookup"><span data-stu-id="79770-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="79770-207">Многие классы <xref:System.Windows.Documents.Inline> определяют форматирование текста, к которому они применяются.</span><span class="sxs-lookup"><span data-stu-id="79770-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="79770-208">Каждая <xref:System.Windows.Documents.TextElement> имеет собственную модель содержимого.</span><span class="sxs-lookup"><span data-stu-id="79770-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="79770-209">Подробнее см. в разделе [Общие сведения о модели содержимого TextElement](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79770-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79770-210">См. также:</span><span class="sxs-lookup"><span data-stu-id="79770-210">See also</span></span>

- [<span data-ttu-id="79770-211">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="79770-211">Advanced</span></span>](../advanced/index.md)
