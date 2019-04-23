---
title: Модель содержимого WPF
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
ms.openlocfilehash: 4f866e0366a7781c287b3ebae7b668c2b296a5cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134612"
---
# <a name="wpf-content-model"></a><span data-ttu-id="1e7ce-102">Модель содержимого WPF</span><span class="sxs-lookup"><span data-stu-id="1e7ce-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="1e7ce-103">— это презентационная платформа, которая предоставляет множество элементов и типов, схожих с элементами управления, основное предназначение которых — отображение различных типов содержимого.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="1e7ce-104">Чтобы определить, какой элемент управления использовать или от какого элемента управления выполнять наследование, вы должны понимать, какие виды объектов лучше всего может отображать конкретный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="1e7ce-105">В этом разделе приводятся обобщенные сведения о модели содержимого для элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и типов, схожих с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="1e7ce-106">Модель содержимого описывает, какое содержимое может использоваться в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="1e7ce-107">Также в этом разделе перечисляются свойства содержимого для каждой модели содержимого.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="1e7ce-108">Свойство содержимого — это свойство, которое используется для хранения содержимого объекта.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="1e7ce-109">Классы с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="1e7ce-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="1e7ce-110">Некоторые элементы управления могут содержать объекты любого типа, например строку, <xref:System.DateTime> объекта, или <xref:System.Windows.UIElement> являющийся контейнером для дополнительных элементов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="1e7ce-111">Например <xref:System.Windows.Controls.Button> может содержать изображение и некоторый текст; или <xref:System.Windows.Controls.CheckBox> может содержать значение <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1e7ce-112">В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется четыре класса, которые могут иметь произвольное содержимое.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-112">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="1e7ce-113">В следующей таблице перечислены классы, которые наследуют от <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="1e7ce-114">Класс с произвольным содержимым</span><span class="sxs-lookup"><span data-stu-id="1e7ce-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="1e7ce-115">Content</span><span class="sxs-lookup"><span data-stu-id="1e7ce-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="1e7ce-116">Один произвольный объект.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="1e7ce-117">Заголовок и один элемент, которые являются произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="1e7ce-118">Коллекция произвольных объектов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="1e7ce-119">Заголовок и коллекция элементов, являющиеся произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="1e7ce-120">Элементы управления, производные от этих классов, могут содержать тот же тип содержимого и обрабатывать содержимое аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="1e7ce-121">На следующем рисунке показан один элемент управления из каждой модели содержимого, который содержит изображение и некоторый текст:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![Снимок экрана, показывающий четыре различных элементов управления, один из каждой модели содержимого.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="1e7ce-123">Элементы управления, содержащие один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="1e7ce-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="1e7ce-124"><xref:System.Windows.Controls.ContentControl> Класса содержит один элемент произвольного содержимого.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="1e7ce-125">Его свойство содержимого — <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="1e7ce-126">Следующие элементы управления наследуют <xref:System.Windows.Controls.ContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="1e7ce-127">На следующем рисунке показано четыре кнопки, <xref:System.Windows.Controls.ContentControl.Content%2A> присваивается строка <xref:System.DateTime> объекта, <xref:System.Windows.Shapes.Rectangle>и <xref:System.Windows.Controls.Panel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Снимок экрана, показаны четыре кнопки с различными типами содержимого.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="1e7ce-129">Например, как задать <xref:System.Windows.Controls.ContentControl.Content%2A> свойство, см. в разделе <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="1e7ce-130">Элементы управления, содержащие заголовок и один произвольный объект</span><span class="sxs-lookup"><span data-stu-id="1e7ce-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="1e7ce-131"><xref:System.Windows.Controls.HeaderedContentControl> Класс наследует от <xref:System.Windows.Controls.ContentControl> и отображает содержимое с заголовком.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="1e7ce-132">Он наследует свойство content <xref:System.Windows.Controls.ContentControl.Content%2A>, из <xref:System.Windows.Controls.ContentControl> и определяет <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> свойство, имеющее тип <xref:System.Object>; таким образом, оба могут быть произвольными объектами.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="1e7ce-133">Следующие элементы управления наследуют <xref:System.Windows.Controls.HeaderedContentControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="1e7ce-134">На следующем рисунке показаны два <xref:System.Windows.Controls.TabItem> объектов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="1e7ce-135">Первый <xref:System.Windows.Controls.TabItem> имеет <xref:System.Windows.UIElement> объектов как <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="1e7ce-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Присваивается <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="1e7ce-137"><xref:System.Windows.Controls.ContentControl.Content%2A> Присваивается <xref:System.Windows.Controls.StackPanel> , содержащий <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="1e7ce-138">Второй <xref:System.Windows.Controls.TabItem> имеет строку в <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![TabControl, который использует различные типы в свойстве Header.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="1e7ce-140">Пример создания <xref:System.Windows.Controls.TabItem> объектов, см. в разделе <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="1e7ce-141">Элементы управления, содержащие коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="1e7ce-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="1e7ce-142"><xref:System.Windows.Controls.ItemsControl> Класс наследует от <xref:System.Windows.Controls.Control> и может содержать несколько элементов, таких как строки, объекты или другие элементы.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="1e7ce-143">Его свойства содержимого — <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="1e7ce-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> обычно используется для заполнения <xref:System.Windows.Controls.ItemsControl> со сбором данных.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="1e7ce-145">Если вы не хотите использовать коллекцию для заполнения <xref:System.Windows.Controls.ItemsControl>, можно добавить элементы с помощью <xref:System.Windows.Controls.ItemsControl.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="1e7ce-146">Следующие элементы управления наследуют <xref:System.Windows.Controls.ItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="1e7ce-147">На следующем рисунке показано <xref:System.Windows.Controls.ListBox> , содержащий следующие типы элементов:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="1e7ce-148">Строка.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-148">A string.</span></span>  
  
-   <span data-ttu-id="1e7ce-149">Объект <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-149">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="1e7ce-150">Объект <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-150">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="1e7ce-151">Объект <xref:System.Windows.Controls.Panel> , содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Снимок экрана с ListBox с четырьмя типами содержимого.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="1e7ce-153">Элементы управления, содержащие заголовок и коллекцию произвольных объектов</span><span class="sxs-lookup"><span data-stu-id="1e7ce-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="1e7ce-154"><xref:System.Windows.Controls.HeaderedItemsControl> Класс наследует от <xref:System.Windows.Controls.ItemsControl> и может содержать несколько элементов, таких как строки, объекты, или другие элементы и заголовок.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="1e7ce-155">Он наследует <xref:System.Windows.Controls.ItemsControl> свойства, содержимого <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, и <xref:System.Windows.Controls.ItemsControl.Items%2A>, и он определяет <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> свойство, которое может быть произвольный объект.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="1e7ce-156">Следующие элементы управления наследуют <xref:System.Windows.Controls.HeaderedItemsControl> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="1e7ce-157">Классы, содержащие коллекцию объектов UIElement</span><span class="sxs-lookup"><span data-stu-id="1e7ce-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="1e7ce-158"><xref:System.Windows.Controls.Panel> Класс размещение и упорядочивание дочерних <xref:System.Windows.UIElement> объектов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="1e7ce-159">Его свойство содержимого — <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="1e7ce-160">Следующие классы наследуют от <xref:System.Windows.Controls.Panel> класса и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="1e7ce-161">Дополнительные сведения см. в разделе [Общие сведения о панелях](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ce-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="1e7ce-162">Классы, влияющие на внешний вид объекта UIElement</span><span class="sxs-lookup"><span data-stu-id="1e7ce-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="1e7ce-163"><xref:System.Windows.Controls.Decorator> Класс применяет визуальные эффекты или вокруг один дочерний элемент <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="1e7ce-164">Его свойство содержимого — <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="1e7ce-165">Следующие классы наследуют от <xref:System.Windows.Controls.Decorator> и используют его модель содержимого:</span><span class="sxs-lookup"><span data-stu-id="1e7ce-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="1e7ce-166">На следующем рисунке показано <xref:System.Windows.Controls.TextBox> с (снабжен) <xref:System.Windows.Controls.Border> вокруг него.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="1e7ce-167">![TextBox с черной границей](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="1e7ce-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="1e7ce-168">Элемент управления TextBlock с границей вокруг него</span><span class="sxs-lookup"><span data-stu-id="1e7ce-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="1e7ce-169">Классы, предоставляющие визуальную обратную связь об объекте UIElement</span><span class="sxs-lookup"><span data-stu-id="1e7ce-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="1e7ce-170"><xref:System.Windows.Documents.Adorner> Предоставляет пользователю визуальные подсказки.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="1e7ce-171">Например, использовать <xref:System.Windows.Documents.Adorner> для добавления функциональных обработчиков к элементам или предоставления сведения о состоянии об элементе управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="1e7ce-172"><xref:System.Windows.Documents.Adorner> Класс предоставляет платформу, которые можно создавать собственные декоративные элементы.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="1e7ce-173">не предоставляет никаких реализованных декоративных элементов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-173">does not provide any implemented adorners.</span></span> <span data-ttu-id="1e7ce-174">Дополнительные сведения см. в разделе [Общие сведения о декоративных элементах](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ce-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="1e7ce-175">Классы, позволяющие пользователям вводить текст</span><span class="sxs-lookup"><span data-stu-id="1e7ce-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="1e7ce-176">WPF предоставляет три основных элемента управления, которые позволяют пользователям вводить текст.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="1e7ce-177">Каждый из этих элементов управления отображает текст по-разному.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-177">Each control displays the text differently.</span></span> <span data-ttu-id="1e7ce-178">В следующей таблице приведены эти три элемента управления с поддержкой ввода текста, их возможности по отображению текста и свойства, которые содержат текст этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="1e7ce-179">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="1e7ce-179">Control</span></span>|<span data-ttu-id="1e7ce-180">В каком виде отображается текст</span><span class="sxs-lookup"><span data-stu-id="1e7ce-180">Text is displayed as</span></span>|<span data-ttu-id="1e7ce-181">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="1e7ce-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="1e7ce-182">Обычный текст</span><span class="sxs-lookup"><span data-stu-id="1e7ce-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="1e7ce-183">Форматированный текст</span><span class="sxs-lookup"><span data-stu-id="1e7ce-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="1e7ce-184">Скрытый текст (символы скрыты)</span><span class="sxs-lookup"><span data-stu-id="1e7ce-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="1e7ce-185">Классы, отображающие пользовательский текст</span><span class="sxs-lookup"><span data-stu-id="1e7ce-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="1e7ce-186">Некоторые классы могут использоваться для отображения простого или форматированного текста.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="1e7ce-187">Можно использовать <xref:System.Windows.Controls.TextBlock> для отображения текста небольшого объема.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="1e7ce-188">Если вы хотите отображать большие объемы текста, используйте <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, или <xref:System.Windows.Controls.FlowDocumentScrollViewer> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="1e7ce-189"><xref:System.Windows.Controls.TextBlock> Имеет два свойства содержимого: <xref:System.Windows.Controls.TextBlock.Text%2A> и <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="1e7ce-190">Если вы хотите отображать текст с единообразным форматированием <xref:System.Windows.Controls.TextBlock.Text%2A> свойство является оптимальным решением.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="1e7ce-191">Если вы планируете использовать разное форматирование текста, используйте <xref:System.Windows.Controls.TextBlock.Inlines%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="1e7ce-192"><xref:System.Windows.Controls.TextBlock.Inlines%2A> Свойство — это коллекция <xref:System.Windows.Documents.Inline> объекты, которые определяют способ форматирования текста.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="1e7ce-193">В следующей таблице перечислены свойства содержимого для <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, и <xref:System.Windows.Controls.FlowDocumentScrollViewer> классы.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="1e7ce-194">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="1e7ce-194">Control</span></span>|<span data-ttu-id="1e7ce-195">Свойство содержимого</span><span class="sxs-lookup"><span data-stu-id="1e7ce-195">Content property</span></span>|<span data-ttu-id="1e7ce-196">Тип свойства содержимого</span><span class="sxs-lookup"><span data-stu-id="1e7ce-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="1e7ce-197">Document</span><span class="sxs-lookup"><span data-stu-id="1e7ce-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="1e7ce-198">Document</span><span class="sxs-lookup"><span data-stu-id="1e7ce-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="1e7ce-199">Document</span><span class="sxs-lookup"><span data-stu-id="1e7ce-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="1e7ce-200"><xref:System.Windows.Documents.FlowDocument> Реализует <xref:System.Windows.Documents.IDocumentPaginatorSource> интерфейс; таким образом, все три класса могут принимать <xref:System.Windows.Documents.FlowDocument> как содержимое.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="1e7ce-201">Классы, выполняющие форматирование пользовательского текста</span><span class="sxs-lookup"><span data-stu-id="1e7ce-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="1e7ce-202"><xref:System.Windows.Documents.TextElement> и связанные с ним классы позволяют вам форматировать текст.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="1e7ce-203"><xref:System.Windows.Documents.TextElement> объекты содержат и форматируют текст в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument> объектов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="1e7ce-204">Два основных типа <xref:System.Windows.Documents.TextElement> объекты являются <xref:System.Windows.Documents.Block> элементов и <xref:System.Windows.Documents.Inline> элементов.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="1e7ce-205">Объект <xref:System.Windows.Documents.Block> представляет блок текста, например, абзац или список.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="1e7ce-206"><xref:System.Windows.Documents.Inline> Элемент представляет собой часть текста в блоке.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="1e7ce-207">Многие <xref:System.Windows.Documents.Inline> классы задают форматирование текста, к которому они применяются.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="1e7ce-208">Каждый <xref:System.Windows.Documents.TextElement> имеет собственную модель содержимого.</span><span class="sxs-lookup"><span data-stu-id="1e7ce-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="1e7ce-209">Подробнее см. в разделе [Общие сведения о модели содержимого TextElement](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1e7ce-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7ce-210">См. также</span><span class="sxs-lookup"><span data-stu-id="1e7ce-210">See also</span></span>

- [<span data-ttu-id="1e7ce-211">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="1e7ce-211">Advanced</span></span>](../advanced/index.md)
