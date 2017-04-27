---
title: "Общие сведения о шаблонах данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязки данных, шаблонов"
  - "связывание данных, шаблоны"
  - "шаблоны данных"
  - "данные - шаблоны"
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Общие сведения о шаблонах данных
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Модель шаблонов данных предоставляет большую гибкость при определении представления данных. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]элементы управления имеют встроенные функции для поддержки настройки представления данных. В этом разделе сначала демонстрируется определение <xref:System.Windows.DataTemplate> и затем представлены другие возможности шаблонов данных, такие как выбор шаблона на основе пользовательской логики и поддержка отображения иерархических данных.  
  
   
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе рассматриваются функций шаблонов данных и не общие сведения о понятиях привязки данных. Сведения о базовых концепциях привязки данных содержатся [Обзор привязки данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> является представлением данных и является одним из многих средств, предоставляемых [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модель стилей и шаблонов. Введение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модель стилей и шаблонов, таких как использование <xref:System.Windows.Style> для задания свойств элементов управления, в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md) раздела.  
  
 Кроме того, важно понимать `Resources`, по сути, что включение объектов, таких как <xref:System.Windows.Style> и <xref:System.Windows.DataTemplate> для повторного использования. Дополнительные сведения о ресурсах см. в разделе [ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Основы шаблонов данных  
   
  
 Чтобы продемонстрировать важность <xref:System.Windows.DataTemplate> важно, давайте разберем пример привязки данных. В этом примере у нас есть <xref:System.Windows.Controls.ListBox> , привязанный к списку `Task` объектов. Каждый `Task` объект имеет `TaskName` (строка), `Description` (строка), `Priority` (int) и свойство типа `TaskType`, который является `Enum` значениями `Home` и `Work`.  
  
 [!code-xml[DataTemplatingIntro_snip#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xml[DataTemplatingIntro_snip#UI1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xml[DataTemplatingIntro_snip#UI2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Без DataTemplate  
 Без <xref:System.Windows.DataTemplate>наш <xref:System.Windows.Controls.ListBox> в данный момент выглядит следующим образом:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Это время, без любые конкретные инструкции <xref:System.Windows.Controls.ListBox> , по умолчанию вызывает `ToString` при попытке отображения объектов в коллекции. Таким образом Если `Task` переопределяет метод `ToString` метода, а затем <xref:System.Windows.Controls.ListBox> отображает строковое представление каждого исходного объекта в коллекции.  
  
 Например если `Task` класса переопределения `ToString` метод таким образом, где `name` — поле для `TaskName` свойства:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Затем <xref:System.Windows.Controls.ListBox> выглядит следующим образом:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Тем не менее это ограничение и жесткие. Кроме того Если выполняется привязка к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных, невозможно переопределить `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Определение простой DataTemplate  
 Решением является определение <xref:System.Windows.DataTemplate>. Один из способов сделать это является установка <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство <xref:System.Windows.Controls.ListBox> для <xref:System.Windows.DataTemplate>. Укажите в своей <xref:System.Windows.DataTemplate> становится визуальную структуру объекта данных. Следующие <xref:System.Windows.DataTemplate> довольно прост. Мы зададим инструкции, каждый элемент отображается в виде трех <xref:System.Windows.Controls.TextBlock> элементы <xref:System.Windows.Controls.StackPanel>. Каждый <xref:System.Windows.Controls.TextBlock> элемент привязывается к свойству `Task` класса.  
  
 [!code-xml[DataTemplatingIntro_snip#Inline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 Базовые данные в примерах этого раздела — это совокупность [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] объектов. Если выполнить привязку к [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данным, основные понятия схожи, но есть незначительные синтаксические различия. Например, вместо `Path=TaskName`, необходимо установить <xref:System.Windows.Data.Binding.XPath%2A> для `@TaskName` (если `TaskName` является атрибутом вашей [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] узла).  
  
 Теперь наши <xref:System.Windows.Controls.ListBox> выглядит следующим образом:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Создание DataTemplate как ресурс  
 В приведенном выше примере мы определили <xref:System.Windows.DataTemplate> встроенный. Очень часто его определения в разделе ресурсов, поэтому он может быть повторно используемым объектом, как в следующем примере:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#AsResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Теперь вы можете использовать `myTaskTemplate` в качестве ресурса, как показано в следующем примере:  
  
 [!code-xml[DataTemplatingIntro_snip#MyTaskTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Поскольку `myTaskTemplate` является ресурсом, теперь можно использовать его для других элементов управления, которые имеют свойства, которое принимает <xref:System.Windows.DataTemplate> типа. Как показано выше, для <xref:System.Windows.Controls.ItemsControl> объекты, такие как <xref:System.Windows.Controls.ListBox>, это <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> свойство. Для <xref:System.Windows.Controls.ContentControl> объектов, это <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойство.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Свойство DataType  
 <xref:System.Windows.DataTemplate> класс имеет <xref:System.Windows.DataTemplate.DataType%2A> свойство, которое очень похоже на <xref:System.Windows.Style.TargetType%2A> свойство <xref:System.Windows.Style> класса. Таким образом, вместо указания `x:Key` для <xref:System.Windows.DataTemplate> в приведенном выше примере можно сделать следующее:  
  
 [!code-xml[DataTemplatingIntro_snip#DataType](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Это <xref:System.Windows.DataTemplate> автоматически применяется ко всем `Task` объектов. Обратите внимание, что в этом случае `x:Key` устанавливается неявно. Таким образом при назначении этого <xref:System.Windows.DataTemplate> `x:Key` значение, то неявное переопределение `x:Key` и <xref:System.Windows.DataTemplate> не будут применяться автоматически.  
  
 При связывании <xref:System.Windows.Controls.ContentControl> в коллекцию `Task` объектов, <xref:System.Windows.Controls.ContentControl> не использует выше <xref:System.Windows.DataTemplate> автоматически. Это обусловлено привязки на <xref:System.Windows.Controls.ContentControl> требуется больше информации для различения ли вы хотите выполнить привязку для всей коллекции или к отдельным объектам. Если ваш <xref:System.Windows.Controls.ContentControl> отслеживает выбор <xref:System.Windows.Controls.ItemsControl> тип, можно задать <xref:System.Windows.Data.Binding.Path%2A> свойство <xref:System.Windows.Controls.ContentControl> привязка к «`/`» для указания, что вы заинтересованы в текущем элементе. Например, в разделе [привязки для сбора и отображения информации на основе выбора](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md). В противном случае, необходимо указать <xref:System.Windows.DataTemplate> явным образом задав <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойство.  
  
 <xref:System.Windows.DataTemplate.DataType%2A> свойство особенно полезно, если у вас есть <xref:System.Windows.Data.CompositeCollection> различных типов объектов данных. Например, в разделе [реализовать CompositeCollection](../../../../docs/framework/wpf/data/how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Добавление более DataTemplate  
 В настоящее время данные отображают необходимую информацию, но есть возможность для улучшения. Давайте улучшим представление, добавив <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Grid>и некоторые <xref:System.Windows.Controls.TextBlock> элементы, описывающие данные, отображается.  
  
 [!code-xml[DataTemplatingIntro#AddingMore](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 На следующем снимке экрана показано <xref:System.Windows.Controls.ListBox> с этим измененным <xref:System.Windows.DataTemplate>:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 Можно установить <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> для <xref:System.Windows.HorizontalAlignment> на <xref:System.Windows.Controls.ListBox> чтобы убедиться, что ширина элементов занимает все место:  
  
 [!code-xml[DataTemplatingIntro_snip#Stretch](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 С <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> свойству <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.ListBox> теперь выглядит следующим образом:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Использование триггеров данных для применения значений свойств  
 В текущей презентации не говорится ли `Task` домашней задачей или офисной. Помните, что `Task` объект имеет `TaskType` свойство типа `TaskType`, который является перечислением со значениями `Home` и `Work`.  
  
 В следующем примере <xref:System.Windows.DataTrigger> задает <xref:System.Windows.Controls.Border.BorderBrush%2A> элемента с именем `border` для `Yellow` Если `TaskType` свойство `TaskType.Home`.  
  
 [!code-xml[DataTemplatingIntro#DT](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xml[DataTemplatingIntro#DataTrigger](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xml[DataTemplatingIntro#AddingMore2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Теперь приложение выглядит следующим образом. Домашние задачи отображаются с желтой границей, а офисные отображаются с синей границей:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 В этом примере <xref:System.Windows.DataTrigger> использует <xref:System.Windows.Setter> можно задать значение свойства. Классы триггера также имеют <xref:System.Windows.TriggerBase.EnterActions%2A> и <xref:System.Windows.TriggerBase.ExitActions%2A> свойства, позволяющие запускать ряд действий, например анимацию. Кроме того, имеется также <xref:System.Windows.MultiDataTrigger> , позволяющий применять изменения на основе значений нескольких свойств с привязкой к данным.  
  
 Альтернативным способом достижения такого же эффекта является привязка <xref:System.Windows.Controls.Border.BorderBrush%2A> свойства `TaskType` свойство и использование преобразователя значения для возврата цвета на основе `TaskType` значение. Создание вышеупомянутого эффекта с помощью преобразователя является немного более эффективным с точки зрения производительности. Кроме того Создание собственных преобразователей обеспечивает большую гибкость, поскольку применяется свою собственную логику. В конечном счете Выбор метода зависит от сценария и предпочтений. Сведения о том, как написать преобразователь в разделе <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Что входит в DataTemplate?  
 В предыдущем примере мы разместили внутри триггера <xref:System.Windows.DataTemplate> с помощью <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> свойство. <xref:System.Windows.Setter> триггера задает значение свойства элемента ( <xref:System.Windows.Controls.Border> элемент), находится в пределах <xref:System.Windows.DataTemplate>. Тем не менее если свойства, вашей `Setters` интересует не являются свойствами элементов, которые находятся в пределах текущего <xref:System.Windows.DataTemplate>, возможно, более подходит задание свойств с помощью <xref:System.Windows.Style> для <xref:System.Windows.Controls.ListBoxItem> класса (при привязке элемента управления <xref:System.Windows.Controls.ListBox>). Например, если вы хотите вашей <xref:System.Windows.Trigger> для анимации <xref:System.Windows.UIElement.Opacity%2A> значения элемента при наведении указателя мыши на элемент, определите триггеры в <xref:System.Windows.Controls.ListBoxItem> стиль. Например, в разделе [введение в стили и шаблоны образец](http://go.microsoft.com/fwlink/?LinkID=160010).  
  
 В целом, помните, что <xref:System.Windows.DataTemplate> применяется для каждого созданного <xref:System.Windows.Controls.ListBoxItem> (Дополнительные сведения о том, как и где он применен фактически см. в разделе <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> страницы.). Ваш <xref:System.Windows.DataTemplate> отвечает только за презентацию и внешний вид объектов данных. В большинстве случаев, все другие аспекты презентации, такие как элемент выглядит при его выборе или как <xref:System.Windows.Controls.ListBox> размещает элементы, не входящие в определение <xref:System.Windows.DataTemplate>. Например, в разделе [стиля и шаблона ItemsControl](#DataTemplating_ItemsControl) раздел.  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Выбор на основе свойств объекта данных DataTemplate  
 В [свойство типа данных](#Styling_DataType) разделе мы говорили, что можно определить различные шаблоны данных для различных объектов данных. Это особенно полезно при наличии <xref:System.Windows.Data.CompositeCollection> различных типов или коллекций с элементами различных типов. В [использование триггеров данных для применения значений свойств](#DataTrigger_to_Apply_Property_Values) разделе было показано, что если имеется коллекция одинаковых типов объектов данных можно создать <xref:System.Windows.DataTemplate> и затем использовать триггеры для применения изменений на основании значений свойств каждого объекта данных. Однако триггеры позволяют применить значения свойств или запустить анимацию, однако они не предоставляют гибкость при реконструкции структуры объектов данных. Некоторые сценарии могут потребовать создания различных <xref:System.Windows.DataTemplate> для данных объектов, которые имеют тот же тип, но различные свойства.  
  
 Например, если `Task` объект имеет `Priority` значение `1`, вы можете отказаться от нее в качестве оповещения для себя совершенно другой вид. В этом случае можно создать <xref:System.Windows.DataTemplate> для отображения с высоким приоритетом `Task` объектов. Давайте добавим следующий <xref:System.Windows.DataTemplate> в раздела ресурсов:  
  
 [!code-xml[DataTemplatingIntro_snip#ImportantTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Обратите внимание, в этом примере используется <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> свойство. Ресурсы, определенные в этом разделе, являются общими для элементов внутри <xref:System.Windows.DataTemplate>.  
  
 Чтобы предоставить логику, чтобы определить, какие <xref:System.Windows.DataTemplate> для использования на основе `Priority` значение объекта данных, создать подкласс <xref:System.Windows.Controls.DataTemplateSelector> и Переопределите <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод. В следующем примере <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод предоставляет логику для возвращения соответствующего шаблона, основанного на значение `Priority` свойства. Шаблон для возврата находится в ресурсах <xref:System.Windows.Window> элемента.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 Затем можно объявить `TaskListDataTemplateSelector` как ресурс:  
  
 [!code-xml[DataTemplatingIntro_snip#R1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xml[DataTemplatingIntro_snip#DTS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xml[DataTemplatingIntro_snip#R2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Для использования ресурса выбора шаблона, назначьте его <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> свойство <xref:System.Windows.Controls.ListBox>. <xref:System.Windows.Controls.ListBox> вызовов <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> метод `TaskListDataTemplateSelector` для каждого элемента в коллекции. Вызов передает объект данных в качестве параметра элемента. <xref:System.Windows.DataTemplate> , возвращаемый метод затем применяется к объекту данных.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemTemplateSelector](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 С помощью выбора шаблона на месте <xref:System.Windows.Controls.ListBox> теперь выглядит следующим образом:  
  
 ![Снимок экрана примера шаблона данных](../../../../docs/framework/wpf/data/media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  
  
 Это заключительный шаг нашего обсуждения данного примера. Полный пример см. [введение в шаблоны данных](http://go.microsoft.com/fwlink/?LinkID=160009).  
  
<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Стилизация и использование шаблонов ItemsControl  
 Несмотря на то что <xref:System.Windows.Controls.ItemsControl> не только типом элемента управления, который можно использовать <xref:System.Windows.DataTemplate> , это очень распространенный сценарий для привязки <xref:System.Windows.Controls.ItemsControl> в коллекцию. В [именно входит в DataTemplate](#what_belongs_in_datatemplate) разделе мы обсуждали, определение вашего <xref:System.Windows.DataTemplate> должен быть озабочена представления данных. Чтобы узнать, когда это не подходит для использования <xref:System.Windows.DataTemplate> важно понимать различные свойства стилей и шаблонов, предоставляемых <xref:System.Windows.Controls.ItemsControl>. Следующий пример предназначен для демонстрации функции каждого из этих свойств. <xref:System.Windows.Controls.ItemsControl> в этом примере, привязанного к тому же `Tasks` коллекции, как показано в предыдущем примере. Для демонстрационных целей стили и шаблоны в этом примере являются все объявленные встроенными.  
  
 [!code-xml[DataTemplatingIntro_snip#ItemsControlProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Ниже приведен снимок экрана примера при его отображении.  
  
 ![Снимок экрана примера ItemsControl](../../../../docs/framework/wpf/data/media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Обратите внимание, что вместо <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, можно использовать <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. См. в предыдущем разделе в качестве примера. Аналогичным образом, вместо <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, вы можете использовать <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Два других относящихся к стилю свойства <xref:System.Windows.Controls.ItemsControl> , не показанные здесь, <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> и <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Поддержка иерархических данных  
 Пока мы только рассматривали как для привязки и отображения одной коллекции. Иногда имеется коллекция, содержащая другие коллекции. <xref:System.Windows.HierarchicalDataTemplate> класс предназначен для использования с <xref:System.Windows.Controls.HeaderedItemsControl> типы для отображения таких данных. В следующем примере `ListLeagueList` является списком `League` объектов. Каждый `League` объект имеет `Name` и коллекцию `Division` объектов. Каждый `Division` имеет `Name` и коллекцию `Team` объектов и каждая `Team` объект имеет `Name`.  
  
 [!code-xml[HierarchicalDataTemplateSnippet#HDT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Пример показывает, что с помощью <xref:System.Windows.HierarchicalDataTemplate>, можно отобразить данные списка, содержащего другие списки. Ниже приведен снимок экрана примера.  
  
 ![Снимок экрана примера HierarchicalDataTemplate](../../../../docs/framework/wpf/data/media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>См. также  
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Поиск элементов, созданных DataTemplate](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Обзор шаблонов и стилях заголовков столбцов GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)