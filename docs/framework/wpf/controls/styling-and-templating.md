---
title: Стилизация и использование шаблонов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- triggers [WPF]
- styles [WPF], referencing
- event triggers [WPF]
- styles [WPF], prerequisites
- styles [WPF], declaring
- styles [WPF], overview
- styles [WPF], extending
- styles [WPF], triggers
- styles [WPF], event triggers
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
ms.openlocfilehash: 9c2c38020bb57a008d0948a360a5b2cbe401089d
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457762"
---
# <a name="styling-and-templating"></a>Стилизация и использование шаблонов
Стилизация и использование шаблонов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] относятся к набору возможностей (стили, шаблоны, триггеры и раскадровки), которые позволяют разработчикам и дизайнерам создавать визуально привлекательные эффекты, а также создавать согласованный внешний вид своих продуктов. Несмотря на то что разработчики и дизайнеры могут создавать внешний вид отдельно для каждого приложения, надежная модель стилизации и использования шаблонов необходима для поддержки и совместного использования внешнего вида как внутри одного приложения, так и в ряде приложений. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет такую модель.  
  
 Еще одной возможностью модели стилизации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является разделение представления и логики. Это означает, что дизайнеры могут создавать внешний вид приложения только с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в то же самое время, когда разработчики работают над логикой программы, используя языки C# или Visual Basic.  
  
 В этом обзоре основное внимание уделяется аспектам стилизации и использования шаблонов приложения и не рассматриваются концепции привязки данных. Подробнее о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Также важно иметь представление о ресурсах, которые позволяют повторно использовать стили и шаблоны. Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).

<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Пример стилизации и использования шаблонов  
 В примерах кода, приведенных в этом обзоре, используется простой пример фото, показанный ниже:  
  
 ![Стилизированный ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 В этом простом примере фото стилизация и шаблоны применяются для создания привлекательного интерфейса. Образец содержит два <xref:System.Windows.Controls.TextBlock> элементы и <xref:System.Windows.Controls.ListBox> элемента управления, к которому привязан список образов. Полный пример см. в разделе [Вводная часть примера стилизации и использования шаблонов](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Основы стилей  
 Можно представить <xref:System.Windows.Style> — удобный способ применения набора значений свойств к более одного элемента. Например, рассмотрим следующие <xref:System.Windows.Controls.TextBlock> элементы и их внешний вид по умолчанию:  
  
 [!code-xaml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Пример стилизации (снимок экрана)](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.PNG "StylingIntro_TextBlocksBefore")  
  
 Внешний вид по умолчанию можно изменить путем задания свойств, таких как <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>, на каждом <xref:System.Windows.Controls.TextBlock> напрямую. Тем не менее если требуется вашей <xref:System.Windows.Controls.TextBlock> элементы совместно использовать некоторые свойства, можно создать <xref:System.Windows.Style> в `Resources` части вашего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла, как показано ниже:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 При задании <xref:System.Windows.Style.TargetType%2A> стиля <xref:System.Windows.Controls.TextBlock> тип, стиль будет применен ко всем <xref:System.Windows.Controls.TextBlock> элементам в окне.  
  
 Теперь <xref:System.Windows.Controls.TextBlock> элементы отображаются следующим образом:  
  
 ![Пример стилизации (снимок экрана)](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.PNG "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Расширение стилей  
 Возможно, вам необходимо два <xref:System.Windows.Controls.TextBlock> элементов, совместно использовать некоторые свойства, такие как <xref:System.Windows.Controls.Control.FontFamily%2A> и выравнивается по центру <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, и требуется текст «Мои рисунки», чтобы иметь дополнительные свойства. Это можно сделать, создав новый стиль на основе первого стиля, как показано ниже:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Обратите внимание, что предыдущий стиль получил атрибут `x:Key`. Чтобы применить стиль, задайте <xref:System.Windows.FrameworkElement.Style%2A> свойство вашей <xref:System.Windows.Controls.TextBlock> для `x:Key` значение, как показано ниже:  
  
 [!code-xaml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Это <xref:System.Windows.Controls.TextBlock> теперь имеет стиль <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение <xref:System.Windows.HorizontalAlignment.Center>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> значение `Comic Sans MS`, <xref:System.Windows.Controls.TextBlock.FontSize%2A> значение 26 и <xref:System.Windows.Controls.TextBlock.Foreground%2A> значение <xref:System.Windows.Media.LinearGradientBrush> показано в примере. Обратите внимание, что он переопределяет <xref:System.Windows.Controls.Control.FontSize%2A> значение базового стиля. Если имеется более одного <xref:System.Windows.Setter> одного свойства <xref:System.Windows.Style>, <xref:System.Windows.Setter> , объявленный последнего имеет приоритет.  
  
 В следующем примере показаны новые <xref:System.Windows.Controls.TextBlock> элементов будет выглядеть так:  
  
 ![Стилизированный TextBlocks](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Это `TitleText` стиль расширяет стиль, который был создан для <xref:System.Windows.Controls.TextBlock> типа. Можно также расширить стиль, имеющий атрибут `x:Key`, используя значение атрибута `x:Key`. Пример см. в разделе примера для <xref:System.Windows.Style.BasedOn%2A> свойства.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Связь свойства TargetType и атрибута x:Key  
 Как показано в первом примере задание <xref:System.Windows.Style.TargetType%2A> свойства `TextBlock` без присвоения стиля `x:Key` вызывает стиль, применяемый ко всем <xref:System.Windows.Controls.TextBlock> элементов. В этом случае для `x:Key` неявно устанавливается значение `{x:Type TextBlock}`. Это означает, что если явно задать `x:Key` значений к чему-либо, кроме `{x:Type TextBlock}`, <xref:System.Windows.Style> не применяется ко всем <xref:System.Windows.Controls.TextBlock> элементы автоматически. Вместо этого необходимо применить стиль (с помощью `x:Key` значение) для <xref:System.Windows.Controls.TextBlock> элементов явным образом. Если стиль находится в разделе "ресурсы" и не устанавливайте <xref:System.Windows.Style.TargetType%2A> свойства стилей, то необходимо предоставить `x:Key`.  
  
 Помимо значение по умолчанию для `x:Key`, <xref:System.Windows.Style.TargetType%2A> свойство задает тип, к которому применяются свойства установщика. Если вы не укажете <xref:System.Windows.Style.TargetType%2A>, необходимо уточнить свойства в вашей <xref:System.Windows.Setter> объектов с именем класса, используя синтаксис `Property="ClassName.Property"`. Например, вместо параметра `Property="FontSize"`, необходимо задать <xref:System.Windows.Setter.Property%2A> для `"TextBlock.FontSize"` или `"Control.FontSize"`.  
  
 Также обратите внимание, что многие элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются сочетанием других элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Если создать стиль, который применяется ко всем элементам управления типа, можно получить непредвиденные результаты. Например, если создать стиль, предназначенное <xref:System.Windows.Controls.TextBlock> введите в <xref:System.Windows.Window>, стиль будет применен ко всем <xref:System.Windows.Controls.TextBlock> элементов управления в окне, даже если <xref:System.Windows.Controls.TextBlock> является частью другого элемента управления, такие как <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Стили и ресурсы  
 Стиль может использоваться для любого элемента, производного от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>. Наиболее распространенный способ объявления стиля — это его объявление в качестве ресурса в разделе `Resources` файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], как было показано в предыдущих примерах. Так как стили являются ресурсами, для них действуют те же правила области видимости, которые применяются ко всем ресурсам. Область, в которой объявлен стиль, влияет на область применения стиля. Например, если объявить стиль в корневом элементе файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] определения приложения, стиль может использоваться в любом месте приложения. Если вы создаете приложение навигации и объявляете стиль в одном из файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] приложения, стиль можно будет использовать только в этом файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Подробнее о правилах видимости ресурсов см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Кроме того, дополнительные сведения о стилях и ресурсах можно найти в разделе [Совместно используемые ресурсы и темы](#styling_themes) данного обзора.  
  
### <a name="setting-styles-programmatically"></a>Программная установка стилей  
 Для присвоения именованного стиля к элементу программными средствами получите стиль из коллекции ресурсов и назначьте его на элемент <xref:System.Windows.FrameworkElement.Style%2A> свойство. Обратите внимание, что элементы в коллекции ресурсов имеют тип <xref:System.Object>. Таким образом, необходимо привести извлеченный стиль к <xref:System.Windows.Style> перед назначением их <xref:System.Windows.FrameworkElement.Style%2A> свойство. Например, чтобы задать определенный `TitleText` стиля на <xref:System.Windows.Controls.TextBlock> с именем `textblock1`, выполните следующие действия:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Обратите внимание, что после применения стиля он фиксируется и не может быть изменен. Если необходимо динамически изменить стиль, который уже был применен, нужно создать новый стиль для замены существующего. Дополнительные сведения см. в описании свойства <xref:System.Windows.Style.IsSealed%2A>.  
  
 Можно создать объект, который выбирает стиль, который нужно применить, основываясь на собственной логике. Пример см. в разделе примера для <xref:System.Windows.Controls.StyleSelector> класса.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Привязки, динамические ресурсы и обработчики событий  
 Обратите внимание, что свойство `Setter.Value` можно использовать для задания [привязки расширения разметки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) или [расширения разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Дополнительные сведения см. в разделе примеры, приведенные для <xref:System.Windows.Setter.Value%2A?displayProperty=nameWithType> свойства.  
  
 На данный момент этот обзор касается только использования методов задания для установки значений свойств. В стиле также можно задать обработчики событий. Дополнительные сведения см. в разделе <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Шаблоны данных  
 В этом образце приложения нет <xref:System.Windows.Controls.ListBox> элемент управления, который связан со списком фотографий:  
  
 [!code-xaml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Это <xref:System.Windows.Controls.ListBox> в данный момент выглядит следующим образом:  
  
 ![ListBox до применения шаблона](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 Большинство элементов управления имеют некое содержимое, и это содержимое часто поступает из данных, к которым осуществляется привязка. В этом примере такими данными является список фотографий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], используется <xref:System.Windows.DataTemplate> для определения визуального представления данных. По сути, что будет помещено в <xref:System.Windows.DataTemplate> определяет вид данных в отображаемом приложении.  
  
 В нашем примере приложения каждый пользовательский объект `Photo` имеет свойство `Source` строкового типа, которое задает путь к файлу изображения. Сейчас объекты фотографий отображаются как пути к файлам.  
  
 Для фотографий, отображаются в виде изображений, можно создавать <xref:System.Windows.DataTemplate> как ресурс:  
  
 [!code-xaml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xaml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xaml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Обратите внимание, что <xref:System.Windows.DataTemplate.DataType%2A> свойство очень похож на <xref:System.Windows.Style.TargetType%2A> свойство <xref:System.Windows.Style>. Если ваш <xref:System.Windows.DataTemplate> находится в разделе ресурсов, при указании <xref:System.Windows.DataTemplate.DataType%2A> свойство с типом и не назначить `x:Key`, <xref:System.Windows.DataTemplate> применяется при каждом появлении этого типа. Вы всегда можете присвоить <xref:System.Windows.DataTemplate> с `x:Key` и задайте его как `StaticResource` для свойств, которые принимают <xref:System.Windows.DataTemplate> типы, такие как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство или <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойства.  
  
 По существу <xref:System.Windows.DataTemplate> в приведенном выше примере, определяет, при каждом запуске `Photo` объекта, он должен быть <xref:System.Windows.Controls.Image> в <xref:System.Windows.Controls.Border>. С этим <xref:System.Windows.DataTemplate>, теперь приложение выглядит следующим образом:  
  
 ![Фотоизображение](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 Модель использования шаблонов данных предоставляет и другие возможности. Например, при отображении данных коллекции, которая содержит другие коллекции с помощью <xref:System.Windows.Controls.HeaderedItemsControl> типов, такие как <xref:System.Windows.Controls.Menu> или <xref:System.Windows.Controls.TreeView>, имеется <xref:System.Windows.HierarchicalDataTemplate>. Другой возможностью шаблонов данных является <xref:System.Windows.Controls.DataTemplateSelector>, который позволяет выбрать <xref:System.Windows.DataTemplate> для использования на основе пользовательской логики. Дополнительные сведения см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md), в котором более подробно рассматриваются различные возможности использования шаблонов данных.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Шаблоны элементов управления  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> элемента управления определяет внешний вид элемента управления. Можно изменить структуру и внешний вид элемента управления, определив новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления. Во многих случаях это является достаточно гибким средством, и вам не придется писать собственные пользовательские элементы управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Триггеры  
 Триггер задает значения свойств или активирует различные действия (например, анимацию) при изменении значения свойства или при возникновении какого-либо события. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, и <xref:System.Windows.DataTemplate> имеют `Triggers` свойство, которое может содержать набор триггеров. Существуют различные типы триггеров.  
  
### <a name="property-triggers"></a>Триггеры свойств  
 Объект <xref:System.Windows.Trigger> , задает значения свойств или запускает действия на основе значения свойства, называется триггером свойства.  
  
 Чтобы продемонстрировать использование триггеров свойств, можно сделать каждый <xref:System.Windows.Controls.ListBoxItem> частично прозрачным, если он установлен. Следующий стиль устанавливает <xref:System.Windows.UIElement.Opacity%2A> значение <xref:System.Windows.Controls.ListBoxItem> для `0.5`. Когда <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> свойство `true`, но при этом <xref:System.Windows.UIElement.Opacity%2A> равно `1.0`:  
  
 [!code-xaml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xaml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 В этом примере используется <xref:System.Windows.Trigger> для задания значения свойства, но Обратите внимание, что <xref:System.Windows.Trigger> класс также содержит <xref:System.Windows.TriggerBase.EnterActions%2A> и <xref:System.Windows.TriggerBase.ExitActions%2A> свойства, позволяющие выполнять действия триггера.  
  
 Обратите внимание, что <xref:System.Windows.FrameworkElement.MaxHeight%2A> свойство <xref:System.Windows.Controls.ListBoxItem> равно `75`. На следующем рисунке третий элемент является выбранным:  
  
 ![Стилизированный ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>Объекты EventTrigger и раскадровки  
 Другой тип триггера — <xref:System.Windows.EventTrigger>, которая запускает набор действий на основе вхождения события. Например, следующая <xref:System.Windows.EventTrigger> объектов указать, что при наведении указателя мыши <xref:System.Windows.Controls.ListBoxItem>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> анимирует свойство в значение `90` над `0.2` второй период. Когда указатель мыши перемещается за пределы этого элемента, свойство возвращается к исходному значению в течение `1` сек. Обратите внимание, каким образом не требуется указывать <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> значение для <xref:System.Windows.ContentElement.MouseLeave> анимации. Анимация сама может отслеживать исходное значение.  
  
 [!code-xaml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Подробнее см. в разделе [Общие сведения о раскадровках](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 На следующем рисунке указатель мыши указывает на третий элемент:  
  
 ![Пример стилизации (снимок экрана)](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>Объекты MultiTrigger, DataTrigger и MultiDataTrigger  
 В дополнение к <xref:System.Windows.Trigger> и <xref:System.Windows.EventTrigger>, существуют другие типы триггеров. <xref:System.Windows.MultiTrigger> позволяет задавать значения свойств на основе нескольких условий. Вы используете <xref:System.Windows.DataTrigger> и <xref:System.Windows.MultiDataTrigger> при свойство условия с привязкой к данным.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Общие ресурсы и темы  
 Типичное приложение Windows Presentation Foundation (WPF) может иметь несколько ресурсов пользовательского интерфейса (UI), которые применяются во всем приложении. В совокупности этот набор ресурсов можно рассматривать как тему приложения. Windows Presentation Foundation (WPF) предоставляет поддержку для упаковки ресурсов пользовательского интерфейса как тему с помощью словаря ресурсов, который инкапсулируется в качестве <xref:System.Windows.ResourceDictionary> класса.  
  
 Темы Windows Presentation Foundation (WPF) определяются с помощью механизмов стилизации и шаблонов, предоставляющую Windows Presentation Foundation (WPF) для настройки отображения любого элемента.  
  
 Ресурсы темы Windows Presentation Foundation (WPF), хранятся в словарях внедренных ресурсов. Эти словари ресурсов должны быть внедрены в подписанную сборку и могут быть внедрены либо в ту же сборку, что и сам код, либо в параллельную сборку. В случае PresentationFramework.dll сборку, которая содержит элементы управления Windows Presentation Foundation (WPF), ресурсы тем находятся в ряд side-by-side сборки.  
  
 Тема становится последним местом поиска стиля элемента. Как правило, процесс поиска начинается с прохода вверх по дереву элементов в поисках соответствующего ресурса, затем выполняется поиск в коллекции ресурсов приложения и, наконец, в последнюю очередь осуществляется запрос к системе. Это дает разработчикам приложений возможность переопределить стиль для любого объекта на уровне дерева или приложения до достижения темы.  
  
 Словари ресурсов, оформленные в виде отдельных файлов, позволяют повторно использовать тему в нескольких приложениях. Также можно создать изменяемые темы, определив несколько словарей ресурсов, которые обеспечивают одни и те же типы ресурсов, но с разными значениями. Переопределение этих стилей или других ресурсов на уровне приложения является рекомендуемым способом смены тем приложения.  
  
 Чтобы совместно используют набор ресурсов, включая стили и шаблоны в приложениях, можно создать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и укажите <xref:System.Windows.ResourceDictionary>. Например, посмотрите на следующую иллюстрацию — часть [примера "Стилизация с помощью ControlTemplate"](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating):

![Примеры шаблонов элементов управления](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Если взглянуть на файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в примере, можно заметить, что все файлы имеют следующий код:  
  
 [!code-xaml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Он представляет собой `shared.xaml`, который определяет <xref:System.Windows.ResourceDictionary> , содержащий набор стилей и ресурсов кисти, который включает элементы управления в образце иметь согласованный внешний вид.  
  
 Подробнее см. в разделе [Объединенные словари ресурсов](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 Если вы создаете тему для пользовательского элемента управления, ознакомьтесь с разделом "Внешняя библиотека элементов управления" в материале [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
## <a name="see-also"></a>См. также  
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Поиск элемента, созданного шаблоном ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Поиск элементов, созданных с использованием шаблона DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)
