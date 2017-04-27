---
title: "Стилизация и использование шаблонов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "триггеры"
  - "стили, создание ссылок на"
  - "триггеры событий"
  - "стили, предварительные требования"
  - "стили, объявление"
  - "стили, общие сведения"
  - "стили, расширение"
  - "стили, триггеры"
  - "стили, триггеры событий"
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Стилизация и использование шаблонов
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Стилизация и использование шаблонов относятся к набору возможностей (стили, шаблоны, триггеры и раскадровки), позволяющих разработчикам и дизайнерам создавать визуально привлекательные эффекты, а также для создания согласованного внешнего вида своих продуктов. Несмотря на то, что разработчики и дизайнеры могут настроить внешний вид в основе приложений по, надежный модель стилей и шаблонов необходима для поддержки и общего использования внешнего вида внутри приложений и между ними. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет такую модель.  
  
 Еще одна возможность [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модели стилизации является разделение представления и логики. Это означает, что дизайнеры могут создавать внешний вид приложения только с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в то же время, когда разработчики работают над логикой программы, используя C# или Visual Basic.  
  
 В этом обзоре основное внимание уделяется аспектам Стилизация и использование шаблонов приложения и не затрагивает все концепции привязки данных. Сведения о привязке данных см. в разделе [Обзор привязки данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Кроме того важно понимать ресурсы, которые позволяют стили и шаблоны для повторного использования. Дополнительные сведения о ресурсах см. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
   
  
<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>Пример шаблонов и стилей  
 Примеры кода, используемые в данном обзоре основаны на образце простой фото показано на следующем рисунке:  
  
 ![Стиль ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 В этом примере простой photo использует Стилизация и использование шаблонов для создания привлекательного интерфейса. Образец содержит два <xref:System.Windows.Controls.TextBlock> элементы и <xref:System.Windows.Controls.ListBox> элемента управления, к которому привязан список образов. Полный пример см. [введение в стили и шаблоны образец](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>Основы стиля  
 Можно представить себе <xref:System.Windows.Style> как удобный способ для применения набора значений свойств к более одного элемента. Например, рассмотрим следующие <xref:System.Windows.Controls.TextBlock> элементов и их внешний вид по умолчанию:  
  
 [!code-xml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![Снимок экрана примера стилизации](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")  
  
 Внешний вид по умолчанию можно изменить путем задания свойств, таких как <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>, на каждом <xref:System.Windows.Controls.TextBlock> напрямую. Тем не менее если требуется вашей <xref:System.Windows.Controls.TextBlock> элементы совместно использовать некоторые свойства, можно создать <xref:System.Windows.Style> в `Resources` части вашего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла, как показано ниже:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 При задании <xref:System.Windows.Style.TargetType%2A> стиля <xref:System.Windows.Controls.TextBlock> тип, стиль будет применен ко всем <xref:System.Windows.Controls.TextBlock> элементов в окне.  
  
 Теперь <xref:System.Windows.Controls.TextBlock> элементы отображаются следующим образом:  
  
 ![Снимок экрана примера стилизации](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>Расширяемые стили  
 Возможно, вам необходимо два <xref:System.Windows.Controls.TextBlock> элементы совместно использовать некоторые свойства, такие как <xref:System.Windows.Controls.Control.FontFamily%2A> и выравнивается по центру <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, и при этом требуется текст «Мои рисунки» имеют ряд дополнительных свойств. Что можно сделать, создав новый стиль, основанный на основе первого стиля, как показано ниже:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Обратите внимание, что предыдущему стилю присваивается `x:Key`. Чтобы применить стиль, установите <xref:System.Windows.FrameworkElement.Style%2A> свойство вашей <xref:System.Windows.Controls.TextBlock> для `x:Key` значение, как показано ниже:  
  
 [!code-xml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 Это <xref:System.Windows.Controls.TextBlock> теперь имеет стиль <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> значение `Comic Sans MS`, <xref:System.Windows.Controls.TextBlock.FontSize%2A> равное 26 и <xref:System.Windows.Controls.TextBlock.Foreground%2A> значение <xref:System.Windows.Media.LinearGradientBrush> показано в примере. Обратите внимание, что он переопределяет <xref:System.Windows.Controls.Control.FontSize%2A> значение базового стиля. Если имеется более одного <xref:System.Windows.Setter> одного свойства <xref:System.Windows.Style>, <xref:System.Windows.Setter> именно объявленный последнее имеет приоритет.  
  
 Ниже показано, что <xref:System.Windows.Controls.TextBlock> элементов будет выглядеть так:  
  
 ![Стиль TextBlock с](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 Это `TitleText` стиль расширяет стиль, который был создан для <xref:System.Windows.Controls.TextBlock> типа. Можно также расширить стиль, имеющий `x:Key` с помощью `x:Key` значение. Например, см. пример для <xref:System.Windows.Style.BasedOn%2A> свойство.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>Связь свойства TargetType и атрибут x: Key  
 Как показано в первом примере задание <xref:System.Windows.Style.TargetType%2A> свойства `TextBlock` без присвоения стиля `x:Key` вызывает стиль, который будет применяться ко всем <xref:System.Windows.Controls.TextBlock> элементы. В этом случае `x:Key` неявно устанавливается значение `{x:Type TextBlock}`. Это означает, что если явно задать `x:Key` значений на что-либо, кроме `{x:Type TextBlock}`, <xref:System.Windows.Style> не применяется ко всем <xref:System.Windows.Controls.TextBlock> элементы автоматически. Вместо этого необходимо применить стиль (с помощью `x:Key` значение) для <xref:System.Windows.Controls.TextBlock> элементы явным образом. Если стиль находится в разделе «ресурсы» и не устанавливайте <xref:System.Windows.Style.TargetType%2A> свойства на стиль, то должен быть `x:Key`.  
  
 Помимо значения по умолчанию для `x:Key`, <xref:System.Windows.Style.TargetType%2A> свойство определяет тип, к которому применяются свойства установщика. Если вы не укажете <xref:System.Windows.Style.TargetType%2A>, необходимо уточнить свойства в вашей <xref:System.Windows.Setter> объектов с именем класса, используя синтаксис `Property="ClassName.Property"`. Например, вместо параметра `Property="FontSize"`, необходимо задать <xref:System.Windows.Setter.Property%2A> для `"TextBlock.FontSize"` или `"Control.FontSize"`.  
  
 Также Обратите внимание, что многие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы управления состоят из комбинации других [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления. Если создать стиль, применяемый ко всем элементам управления типа можно получить непредвиденные результаты. Например, если создать стиль, предназначенное <xref:System.Windows.Controls.TextBlock> введите в <xref:System.Windows.Window>, стиль применяется ко всем <xref:System.Windows.Controls.TextBlock> элементов управления в окне, даже если <xref:System.Windows.Controls.TextBlock> является частью другого элемента управления, таких как <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>Стили и ресурсы  
 Стиль может использоваться для любого элемента, производного от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>. — Наиболее распространенный способ объявления стиля в качестве ресурса в `Resources` статьи [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла, как показано в предыдущих примерах. Так как стили являются ресурсами, они подчиняются тем же правилам области, которые применяются ко всем ресурсам; место объявления стиля влияет на применения стиля. Например, если объявить стиль в корневом элементе определения приложения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл, стиль может использоваться в любом месте приложения. Если создается приложение переходов и объявить стиль в одном из приложения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы, стиль может использоваться только в том, что [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла. Дополнительные сведения о правилах видимости ресурсов см. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Кроме того, можно найти дополнительные сведения о стилях и ресурсах в [совместно используемые ресурсы и темы](#styling_themes) далее в этом обзоре.  
  
### <a name="setting-styles-programmatically"></a>Программная установка стилей  
 Для присвоения именованного стиля к элементу программными средствами получите стиль из коллекции ресурсов и назначить его свойству элемента <xref:System.Windows.FrameworkElement.Style%2A> свойство. Обратите внимание, что элементы в коллекции ресурсов имеют тип <xref:System.Object>. Таким образом, необходимо привести извлеченный стиль к <xref:System.Windows.Style> перед назначением их <xref:System.Windows.FrameworkElement.Style%2A> свойство. Например, чтобы задать определенный `TitleText` стиля на <xref:System.Windows.Controls.TextBlock> с именем `textblock1`, выполните следующие действия:  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Обратите внимание, что после применения стиля он запечатан и не может быть изменено. Если необходимо динамически изменить стиль, который уже был применен, необходимо создать новый стиль для замены существующего. Дополнительные сведения см. в разделе <xref:System.Windows.Style.IsSealed%2A> свойство.  
  
 Можно создать объект, который выбирает стиль для применения на основе пользовательской логики. Например, см. пример для <xref:System.Windows.Controls.StyleSelector> класса.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>Привязки, динамические ресурсы и обработчики событий  
 Обратите внимание, что можно использовать `Setter.Value` для указания [расширения разметки привязки](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) или [расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Дополнительные сведения см. в примерах, приведенных для <xref:System.Windows.Setter.Value%2A?displayProperty=fullName> свойство.  
  
 На данный момент этот обзор касается только использования установщиков для установки значения свойства. Можно также указать обработчики событий в стиле. Дополнительные сведения см. в разделе <xref:System.Windows.EventSetter>.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>Шаблоны данных  
 В этом образце приложения — <xref:System.Windows.Controls.ListBox> управления, связанный со списком фотографий:  
  
 [!code-xml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 Это <xref:System.Windows.Controls.ListBox> в данный момент выглядит следующим образом:  
  
 ![ListBox до применения шаблона](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 Большинство элементов управления имеют некоторый тип содержимого, и это содержимое часто извлекается из привязанных данных. В этом образце данных является список фотографий. В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], можно использовать <xref:System.Windows.DataTemplate> для определения визуального представления данных. По сути, что будет помещено в <xref:System.Windows.DataTemplate> определяет вид данных в отображаемом приложении.  
  
 В приложении образца каждый пользовательский `Photo` объект имеет `Source` свойство типа String, которое указывает путь к файлу изображения. В настоящее время объекты фотографий отображаются как пути к файлам.  
  
 Для фотографий, отображаются в виде изображений, создания <xref:System.Windows.DataTemplate> как ресурс:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 Обратите внимание, что <xref:System.Windows.DataTemplate.DataType%2A> очень похоже на свойство <xref:System.Windows.Style.TargetType%2A> свойство <xref:System.Windows.Style>. Если ваш <xref:System.Windows.DataTemplate> находится в разделе ресурсов, при указании <xref:System.Windows.DataTemplate.DataType%2A> свойство с типом и не назначайте ее `x:Key`, <xref:System.Windows.DataTemplate> будет применяться при каждом отображении этого типа. У вас всегда есть возможность назначать <xref:System.Windows.DataTemplate> с `x:Key` и установите в качестве `StaticResource` для свойств, которые принимают <xref:System.Windows.DataTemplate> типы, такие как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство или <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойство.  
  
 По существу <xref:System.Windows.DataTemplate> в приведенном выше примере, определяет, при наличии `Photo` объекта, он должен быть <xref:System.Windows.Controls.Image> в <xref:System.Windows.Controls.Border>. С этим <xref:System.Windows.DataTemplate>, наше приложение теперь выглядит следующим образом:  
  
 ![Фотография](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 Модель шаблонов данных предоставляет другие возможности. Например, при отображении данных коллекции, которая содержит другие коллекции с помощью <xref:System.Windows.Controls.HeaderedItemsControl> типов, такие как <xref:System.Windows.Controls.Menu> или <xref:System.Windows.Controls.TreeView>, существует <xref:System.Windows.HierarchicalDataTemplate>. Другой возможностью шаблонов данных является <xref:System.Windows.Controls.DataTemplateSelector>, который позволяет выбрать <xref:System.Windows.DataTemplate> для использования на основе пользовательской логики. Дополнительные сведения см. в разделе [сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md), который предоставляет более подробное рассмотрение различных функций шаблонов данных.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>Шаблоны элементов управления  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> элемента управления определяет внешний вид элемента управления. Можно изменить структуру и внешний вид элемента управления, определив новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления. Во многих случаях это позволяет достаточную гибкость, не придется написать собственные пользовательские элементы управления. Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>Триггеры  
 Триггер задает свойства или начинает действия, такие как анимация, при изменении значения свойства или при возникновении события. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, и <xref:System.Windows.DataTemplate> имеют `Triggers` свойство, которое может содержать набор триггеров. Существуют разные типы триггеров.  
  
### <a name="property-triggers"></a>Триггеры свойств  
 Объект <xref:System.Windows.Trigger> , задает значения свойств или запускает действия на основе значения свойства, называется триггером свойства.  
  
 Чтобы продемонстрировать использование триггеров свойств, вы можете сделать каждую <xref:System.Windows.Controls.ListBoxItem> частично прозрачным, если он не является выбранным. Следующий стиль устанавливает <xref:System.Windows.UIElement.Opacity%2A> значение <xref:System.Windows.Controls.ListBoxItem> в `0.5`. Когда <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> свойство `true`, однако <xref:System.Windows.UIElement.Opacity%2A> задано значение `1.0`:  
  
 [!code-xml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 В этом примере используется <xref:System.Windows.Trigger> для задания значения свойства, но Обратите внимание, что <xref:System.Windows.Trigger> класс также содержит <xref:System.Windows.TriggerBase.EnterActions%2A> и <xref:System.Windows.TriggerBase.ExitActions%2A> свойства, которые позволяют выполнять действия триггера.  
  
 Обратите внимание, что <xref:System.Windows.FrameworkElement.MaxHeight%2A> свойство <xref:System.Windows.Controls.ListBoxItem> равен `75`. На следующем рисунке третий элемент является выбранным элементом:  
  
 ![Стиль ListView](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>EventTriggers и раскадровки  
 Другим типом триггера является <xref:System.Windows.EventTrigger>, которая запускает набор действий на основе вхождения события. Например, следующая <xref:System.Windows.EventTrigger> объектов указать, что при наведении указателя мыши <xref:System.Windows.Controls.ListBoxItem>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> свойство анимируется значение `90` над `0.2` второй период. Когда указатель мыши перемещается из элемента, свойство возвращает исходное значение в течение `1` второй. Обратите внимание, как не обязательно указывать <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> значение <xref:System.Windows.ContentElement.MouseLeave> анимации. Это, поскольку анимация может для отслеживания исходного значения.  
  
 [!code-xml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 На следующем рисунке мышь указывает на третий элемент:  
  
 ![Снимок экрана примера стилизации](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTriggers триггеров данных и MultiDataTriggers  
 В дополнение к <xref:System.Windows.Trigger> и <xref:System.Windows.EventTrigger>, существуют другие типы триггеров. <xref:System.Windows.MultiTrigger> позволяет задавать значения свойств на основе нескольких условий. Использовать <xref:System.Windows.DataTrigger> и <xref:System.Windows.MultiDataTrigger> когда свойство условия с привязкой к данным.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>Общие ресурсы и темы  
 Типичный [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] приложение может иметь несколько ресурсов пользовательского интерфейса (UI), которые применяются во всем приложении. В совокупности этот набор ресурсов может рассматриваться темы для приложения. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]обеспечивает поддержку для упаковки ресурсов пользовательского интерфейса в качестве темы с помощью словаря ресурсов, который инкапсулируется в качестве <xref:System.Windows.ResourceDictionary> класса.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]Темы определяются с помощью механизмов стилизации и шаблонов, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет для настройки отображения любого элемента.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]ресурсы темы хранятся в словарях внедренных ресурсов. Эти словари ресурсов должны быть внедрены в подписанной сборки и либо внедрить в той же сборке, как и сам код в сборке side-by-side. В случае с PresentationFramework.dll сборки, содержащей [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] элементы управления, ресурсы тем находятся в ряде параллельно существующих сборок.  
  
 Тема становится последним местом поиска стиля элемента. Как правило поиск будет начинается с прохода вверх по дереву элементов, поиск соответствующего ресурса, а затем искать в коллекции ресурсов приложений и наконец запрос к системе. Это дает разработчикам приложения возможность переопределить стиль для любого объекта на уровне дерева или приложения до достижения темы.  
  
 Словари ресурсов можно определить как отдельные файлы, которые позволяют повторно использовать тему для нескольких приложений. Также можно создать изменяемые темы, определив несколько словарей ресурсов, которые предоставляют те же типы ресурсов, но с разными значениями. Переопределение этих стилей или других ресурсы на уровне приложения является рекомендуемым методом смены тем приложения.  
  
 Для совместного использования набора ресурсов, включая стили и шаблоны в приложениях, можно создать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и укажите <xref:System.Windows.ResourceDictionary>. Например, взгляните на следующей иллюстрации показана часть [данный пример](http://go.microsoft.com/fwlink/?LinkID=160041):  
  
 ![Примерами шаблонов элементов управления](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 Если взглянуть на [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы в образце, можно заметить, что все файлы имеют следующие:  
  
 [!code-xml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 Он представляет собой `shared.xaml`, который определяет <xref:System.Windows.ResourceDictionary> , содержащий набор стилей и ресурсов кисти, что позволяет элементам управления в образце иметь согласованный внешний вид.  
  
 Дополнительные сведения см. в разделе [слияние словари ресурсов](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).  
  
 При создании темы для вас пользовательского элемента управления, ознакомьтесь с разделом внешняя библиотека элементов управления [управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
## <a name="see-also"></a>См. также  
 [URI упаковок в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Практическое руководство: поиск элементов, созданных ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [Поиск элементов, созданных DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)