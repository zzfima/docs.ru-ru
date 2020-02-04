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
# <a name="wpf-content-model"></a>Модель содержимого WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] — это презентационная платформа, которая предоставляет множество элементов и типов, схожих с элементами управления, основное предназначение которых — отображение различных типов содержимого. Чтобы определить, какой элемент управления использовать или от какого элемента управления выполнять наследование, вы должны понимать, какие виды объектов лучше всего может отображать конкретный элемент управления.  
  
 В этом разделе приводятся обобщенные сведения о модели содержимого для элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и типов, схожих с элементами управления. Модель содержимого описывает, какое содержимое может использоваться в элементе управления. Также в этом разделе перечисляются свойства содержимого для каждой модели содержимого. Свойство содержимого — это свойство, которое используется для хранения содержимого объекта.  

<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a>Классы с произвольным содержимым  
 Некоторые элементы управления могут содержать объект любого типа, например строку, объект <xref:System.DateTime> или <xref:System.Windows.UIElement>, который является контейнером для дополнительных элементов. Например, <xref:System.Windows.Controls.Button> может содержать изображение и некоторый текст; или <xref:System.Windows.Controls.CheckBox> может содержать значение <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется четыре класса, которые могут иметь произвольное содержимое. В следующей таблице перечислены классы, которые наследуются от <xref:System.Windows.Controls.Control>.  
  
|Класс с произвольным содержимым|Содержимое|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|Один произвольный объект.|  
|<xref:System.Windows.Controls.HeaderedContentControl>|Заголовок и один элемент, которые являются произвольными объектами.|  
|<xref:System.Windows.Controls.ItemsControl>|Коллекция произвольных объектов.|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|Заголовок и коллекция элементов, являющиеся произвольными объектами.|  
  
 Элементы управления, производные от этих классов, могут содержать тот же тип содержимого и обрабатывать содержимое аналогичным образом. На следующем рисунке показан один элемент управления из каждой модели содержимого, который содержит изображение и некоторый текст:  
  
 ![Снимок экрана, на котором показаны четыре различных элемента управления — по одному из каждой модели содержимого.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a>Элементы управления, содержащие один произвольный объект  
 Класс <xref:System.Windows.Controls.ContentControl> содержит один фрагмент произвольного содержимого. Его свойство содержимого — <xref:System.Windows.Controls.ContentControl.Content%2A>. Следующие элементы управления наследуются от <xref:System.Windows.Controls.ContentControl> и используют его модель содержимого:  
  
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
  
 На следующем рисунке показаны четыре кнопки, для которых <xref:System.Windows.Controls.ContentControl.Content%2A> задана строка, <xref:System.DateTime> объект, <xref:System.Windows.Shapes.Rectangle>и <xref:System.Windows.Controls.Panel>, содержащая <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>:  
  
 ![Снимок экрана, на котором показаны четыре кнопки с разными типами содержимого.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 Пример задания свойства <xref:System.Windows.Controls.ContentControl.Content%2A> см. в разделе <xref:System.Windows.Controls.ContentControl>.  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a>Элементы управления, содержащие заголовок и один произвольный объект  
 Класс <xref:System.Windows.Controls.HeaderedContentControl> наследует от <xref:System.Windows.Controls.ContentControl> и отображает содержимое с заголовком. Он наследует свойство содержимого <xref:System.Windows.Controls.ContentControl.Content%2A>от <xref:System.Windows.Controls.ContentControl> и определяет свойство <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>, которое имеет тип <xref:System.Object>. Таким образом, оба могут быть произвольным объектом.  
  
 Следующие элементы управления наследуются от <xref:System.Windows.Controls.HeaderedContentControl> и используют его модель содержимого:  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 На следующем рисунке показаны два объекта <xref:System.Windows.Controls.TabItem>. Первый <xref:System.Windows.Controls.TabItem> имеет <xref:System.Windows.UIElement> объектов в качестве <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>. Для <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> задается <xref:System.Windows.Controls.StackPanel>, содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>. Для <xref:System.Windows.Controls.ContentControl.Content%2A> задается <xref:System.Windows.Controls.StackPanel>, содержащий <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.Label>. Второй <xref:System.Windows.Controls.TabItem> содержит строку в <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.ContentControl.Content%2A>.  
  
 ![Элемент TabControl, использующий различные типы в свойстве Header.](./media/wpf-content-model/control-content-model-tab.png)  
  
 Пример создания объектов <xref:System.Windows.Controls.TabItem> см. в разделе <xref:System.Windows.Controls.HeaderedContentControl>.  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a>Элементы управления, содержащие коллекцию произвольных объектов  
 Класс <xref:System.Windows.Controls.ItemsControl> наследует от <xref:System.Windows.Controls.Control> и может содержать несколько элементов, таких как строки, объекты или другие элементы. Его свойства содержимого — <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> и <xref:System.Windows.Controls.ItemsControl.Items%2A>. <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> обычно используется для заполнения <xref:System.Windows.Controls.ItemsControl> коллекцией данных. Если вы не хотите использовать коллекцию для заполнения <xref:System.Windows.Controls.ItemsControl>, можно добавить элементы с помощью свойства <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 Следующие элементы управления наследуются от <xref:System.Windows.Controls.ItemsControl> и используют его модель содержимого:  
  
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
  
 На следующем рисунке показана <xref:System.Windows.Controls.ListBox>, содержащая следующие типы элементов:  
  
- Строка.  
  
- Объект <xref:System.DateTime> .  
  
- <xref:System.Windows.UIElement>.  
  
- <xref:System.Windows.Controls.Panel>, содержащий <xref:System.Windows.Shapes.Ellipse> и <xref:System.Windows.Controls.TextBlock>.  
  
 ![Снимок экрана, на котором показан элемент управления ListBox с четырьмя типами содержимого.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a>Элементы управления, содержащие заголовок и коллекцию произвольных объектов  
 Класс <xref:System.Windows.Controls.HeaderedItemsControl> наследует от <xref:System.Windows.Controls.ItemsControl> и может содержать несколько элементов, таких как строки, объекты или другие элементы, и заголовок. Он наследует свойства содержимого <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>и <xref:System.Windows.Controls.ItemsControl.Items%2A>, а также определяет свойство <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>, которое может быть произвольным объектом.  
  
 Следующие элементы управления наследуются от <xref:System.Windows.Controls.HeaderedItemsControl> и используют его модель содержимого:  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a>Классы, содержащие коллекцию объектов UIElement  
 Класс <xref:System.Windows.Controls.Panel> размещает и упорядочивает дочерние объекты <xref:System.Windows.UIElement>. Его свойство содержимого — <xref:System.Windows.Controls.Panel.Children%2A>.  
  
 Следующие классы наследуют от класса <xref:System.Windows.Controls.Panel> и используют его модель содержимого:  
  
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
  
 Дополнительные сведения см. в разделе [Общие сведения о панелях](panels-overview.md).  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a>Классы, влияющие на внешний вид объекта UIElement  
 Класс <xref:System.Windows.Controls.Decorator> применяет визуальные эффекты к одному дочернему <xref:System.Windows.UIElement>или вокруг него. Его свойство содержимого — <xref:System.Windows.Controls.Decorator.Child%2A>. Следующие классы наследуют от <xref:System.Windows.Controls.Decorator> и используют его модель содержимого:  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 На следующем рисунке показана <xref:System.Windows.Controls.TextBox> с раз<xref:System.Windows.Controls.Border> вокруг него.  
  
 ![Элемент управления TextBox с черной границей вокруг него](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")  
Элемент управления TextBlock с границей вокруг него  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a>Классы, предоставляющие визуальную обратную связь об объекте UIElement  
 Класс <xref:System.Windows.Documents.Adorner> предоставляет пользователю визуальные подсказки. Например, можно использовать <xref:System.Windows.Documents.Adorner> для добавления функциональных дескрипторов к элементам или предоставления сведений о состоянии элемента управления. Класс <xref:System.Windows.Documents.Adorner> предоставляет платформу, позволяющую создавать собственные графические элементы. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предоставляет никаких реализованных декоративных элементов. Дополнительные сведения см. в разделе [Общие сведения о декоративных элементах](adorners-overview.md).  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a>Классы, позволяющие пользователям вводить текст  
 WPF предоставляет три основных элемента управления, которые позволяют пользователям вводить текст. Каждый из этих элементов управления отображает текст по-разному. В следующей таблице приведены эти три элемента управления с поддержкой ввода текста, их возможности по отображению текста и свойства, которые содержат текст этого элемента управления.  
  
|Control|В каком виде отображается текст|Свойство содержимого|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|с обычным текстом;|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|Форматированный текст|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|Скрытый текст (символы скрыты)|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a>Классы, отображающие пользовательский текст  
 Некоторые классы могут использоваться для отображения простого или форматированного текста. Для вывода небольшого объема текста можно использовать <xref:System.Windows.Controls.TextBlock>. Если требуется отображать большие объемы текста, используйте элементы управления <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>или <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
 У <xref:System.Windows.Controls.TextBlock> есть два свойства содержимого: <xref:System.Windows.Controls.TextBlock.Text%2A> и <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Если требуется отображать текст, использующий единообразное форматирование, чаще всего используется свойство <xref:System.Windows.Controls.TextBlock.Text%2A>. Если вы планируете использовать разное форматирование во всем тексте, используйте свойство <xref:System.Windows.Controls.TextBlock.Inlines%2A>. Свойство <xref:System.Windows.Controls.TextBlock.Inlines%2A> — это коллекция объектов <xref:System.Windows.Documents.Inline>, которые определяют способ форматирования текста.  
  
 В следующей таблице перечислены свойства содержимого для классов <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>и <xref:System.Windows.Controls.FlowDocumentScrollViewer>.  
  
|Control|Свойство содержимого|Тип свойства содержимого|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|Документ|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|Документ|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|Документ|<xref:System.Windows.Documents.FlowDocument>|  
  
 <xref:System.Windows.Documents.FlowDocument> реализует интерфейс <xref:System.Windows.Documents.IDocumentPaginatorSource>; Таким образом, все три класса могут принимать <xref:System.Windows.Documents.FlowDocument> как содержимое.  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a>Классы, выполняющие форматирование пользовательского текста  
 <xref:System.Windows.Documents.TextElement> и связанные с ним классы позволяют форматировать текст. <xref:System.Windows.Documents.TextElement> объекты содержат и форматируют текст в <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Documents.FlowDocument>ных объектах. Двумя основными типами <xref:System.Windows.Documents.TextElement> объектов являются <xref:System.Windows.Documents.Block> элементы и элементы <xref:System.Windows.Documents.Inline>. Элемент <xref:System.Windows.Documents.Block> представляет блок текста, например абзац или список. Элемент <xref:System.Windows.Documents.Inline> представляет часть текста в блоке. Многие классы <xref:System.Windows.Documents.Inline> определяют форматирование текста, к которому они применяются. Каждая <xref:System.Windows.Documents.TextElement> имеет собственную модель содержимого. Подробнее см. в разделе [Общие сведения о модели содержимого TextElement](../advanced/textelement-content-model-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- [Дополнительно](../advanced/index.md)
