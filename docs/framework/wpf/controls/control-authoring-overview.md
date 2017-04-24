---
title: "Общие сведения о разработке управления | Microsoft Docs"
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
  - "общие сведения о разработке элементов управления"
  - "элементы управления, общие сведения о разработке"
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Общие сведения о разработке управления
Расширяемость модели элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] значительно уменьшает необходимость создания новых элементов управления.  Однако в некоторых случаях разработчику по\-прежнему может понадобиться создать пользовательский элемент управления.  В этом разделе обсуждаются средства, которые уменьшают необходимость создавать пользовательские управления и различные модели разработки в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Этот раздел также демонстрирует способ создания нового элемента управления.  
  
   
  
<a name="when_to_write_a_new_control"></a>   
## Альтернативы написанию новых элементов управления  
 Ранее, когда разработчикам требовалось настроить специальное отображение существующего элемента управления, они были ограничены в изменениях стандартных свойств элемента управления — цвета фона, ширины границы и размеров шрифта.  Чтобы расширить возможности внешнего вида элемента управления, используя не только предопределенные параметры, разработчикам приходилось создавать новый элемент управления путем наследования от существующего элемента и переопределения метода, ответственного за отрисовку элемента.  Хотя это возможно и сейчас, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] теперь позволяет настраивать существующие элементы управления с помощью модели расширенного содержимого, стилей, шаблонов и триггеров.  В следующем списке перечислены способы использования этих средств для создания пользовательских единообразных отображений, не прибегая к созданию новых элементов управления.  
  
-   **Расширенное содержимое.** Многие стандартные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают расширенное содержимое.  Например, свойство содержимого <xref:System.Windows.Controls.Button> имеет тип <xref:System.Object>, поэтому на <xref:System.Windows.Controls.Button> в теории может отображаться все что угодно.  Чтобы кнопка отображала изображение и текст, можно добавить изображение и <xref:System.Windows.Controls.TextBlock> к <xref:System.Windows.Controls.StackPanel>, а затем присвоить <xref:System.Windows.Controls.StackPanel> к свойству <xref:System.Windows.Controls.ContentControl.Content%2A>.  Так как элементы управления могут отображать визуальные элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и произвольные данные, это уменьшает потребность в создании новых элементов управления или изменения существующего элемента управления для поддержки сложной визуализации.  Дополнительные сведения о модели содержимого для <xref:System.Windows.Controls.Button> и других моделях содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
-   **Стили.** <xref:System.Windows.Style> представляет собой набор значений, представляющих свойства для элемента управления.  С помощью стилей разработчик может создать повторно используемое представление нужного внешнего вида и поведения элемента управления без написания нового элемента управления.  В качестве примера предположим, что все элементы управления <xref:System.Windows.Controls.TextBlock> должны иметь красные надписи, сделанные шрифтом Arial размером 14.  Стиль можно создать как ресурс, задав соответствующие параметры.  Это приведет к тому, что каждый добавляемый в приложение <xref:System.Windows.Controls.TextBlock> будет выглядеть одинаково.  
  
-   **Шаблоны данных** <xref:System.Windows.DataTemplate> позволяет настраивать отображение данных на элементе управления.  Например, с помощью <xref:System.Windows.DataTemplate> можно определять формат отображения данных в <xref:System.Windows.Controls.ListBox>.  Пример см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).  В дополнение к настройке внешнего вида данных <xref:System.Windows.DataTemplate> может включать в себя элементы пользовательского интерфейса, что дает разработчикам больше возможностей при создании специальных интерфейсов.  Например, при помощи <xref:System.Windows.DataTemplate> можно создать <xref:System.Windows.Controls.ComboBox>, каждый элемент, в котором содержит флажок.  
  
-   **Шаблоны элементов управления.** Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют шаблон <xref:System.Windows.Controls.ControlTemplate> для определения структуры и внешнего вида элемента управления, который отделяет внешний вид элемента управления от его функциональных возможностей. Переопределив шаблон <xref:System.Windows.Controls.ControlTemplate>, можно существенно изменить внешний вид элемента управления.  Предположим, требуется элемент управления, который представляет собой светофор.  Этот элемент имеет простой пользовательский интерфейс и функциональность.  Он состоит из трех кругов, при этом в каждый момент времени может быть зажжен только один из них.  После некоторого размышления становится понятно, что <xref:System.Windows.Controls.RadioButton> обеспечивает функциональность для одновременного выделения только одного из них, но внешний вид <xref:System.Windows.Controls.RadioButton> по умолчанию мало похож на светофор.  Так как <xref:System.Windows.Controls.RadioButton> использует шаблон элемента управления для определения своего внешнего вида, проще всего переопределить <xref:System.Windows.Controls.ControlTemplate>, подстроив его под требования элемента управления, а затем воспользоваться переключателями для построения светофора.  
  
    > [!NOTE]
    >  Хотя <xref:System.Windows.Controls.RadioButton> может использовать <xref:System.Windows.DataTemplate>, в этом случае <xref:System.Windows.DataTemplate> недостаточно.  <xref:System.Windows.DataTemplate> определяет внешний вид содержимого элемента управления.  В случае с <xref:System.Windows.Controls.RadioButton> содержимым является все то, что отображается справа от круга, который указывает, выбран ли <xref:System.Windows.Controls.RadioButton>.  В примере со светофором переключатель должен быть просто кругом, который может "зажечься". Так как требования к внешнему виду светофора отличаются от внешнего вида <xref:System.Windows.Controls.RadioButton> по умолчанию, необходимо переопределить <xref:System.Windows.Controls.ControlTemplate>.  В общем случае <xref:System.Windows.DataTemplate> используется для определения содержимого \(или данных\) элемента управления, а <xref:System.Windows.Controls.ControlTemplate> применяется для построения структуры элемента управления.  
  
-   **Триггеры.** <xref:System.Windows.Trigger> позволяет динамически изменять внешний вид и поведение элемента управления без необходимости создания нового элемента.  Например, предположим, что в приложении существует несколько элементов управления <xref:System.Windows.Controls.ListBox>. При этом элементы каждого <xref:System.Windows.Controls.ListBox> должны отображаться красным цветом в жирном начертании при их выделении.  Самым очевидным способом выполнения этой задачи является создание класса, наследующего от <xref:System.Windows.Controls.ListBox>, и переопределение метода <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> для изменения внешнего вида выбранного элемента. Однако лучшим решением будет добавить к стилю <xref:System.Windows.Controls.ListBoxItem> триггер, изменяющий внешний вид выделенного элемента.  Триггер позволяет изменять значения свойств или совершать действия на основе значения свойства.  <xref:System.Windows.EventTrigger> позволяет выполнять действия при возникновении события.  
  
 Дополнительные сведения о стилях, шаблонах и триггерах см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 В общем случае, если элемент управления по функциональности соответствует существующему элементу, но должен выглядеть по\-другому, вначале стоит подумать, можно ли использовать какой\-либо из описанных в этом разделе методов для изменения существующего внешнего вида элементов.  
  
<a name="models_for_control_authoring"></a>   
## Модели для создания элемента управления  
 Модель расширенного содержимого, стили, шаблоны и триггеры уменьшают необходимость создания новых элементов.  Тем не менее, если новый элемент управления необходим, важно понимать различные модели разработки элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет три общих модели для создания элементов управления, каждая из которых имеет собственный набор функций и уровень гибкости.  Основными классами для этих моделей являются <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control> и <xref:System.Windows.FrameworkElement>.  
  
### Производные от UserControl  
 Самым простым способом создания элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является создание производной от <xref:System.Windows.Controls.UserControl>.  При построении элемента управления, наследующего от <xref:System.Windows.Controls.UserControl>, разработчик добавляет существующие компоненты к <xref:System.Windows.Controls.UserControl>, называет их и ссылается на обработчики событий в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Это позволяет впоследствии ссылаться на именованные элементы и определять обработчики событий в коде.  Эта модель разработки очень схожа с моделью, используемой для разработки приложений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
 Будучи построен правильно, <xref:System.Windows.Controls.UserControl> может пользоваться преимуществами расширенного содержимого, стилями и триггерами.  В то же самое время, если элемент управления наследует от <xref:System.Windows.Controls.UserControl>, то пользователи элемента управления не смогут применить <xref:System.Windows.DataTemplate> или <xref:System.Windows.Controls.ControlTemplate> для настройки его внешнего вида.  Для создания пользовательского элемента управления, поддерживающего шаблоны, необходимо создать производную от класса <xref:System.Windows.Controls.Control> или от одной из его производных \(отличной от <xref:System.Windows.Controls.UserControl>\).  
  
#### Преимущества создания производной UserControl  
 Попробуйте создать производную от <xref:System.Windows.Controls.UserControl>, если соблюдены все нижеперечисленные условия:  
  
-   Необходимо построить элемент управления так же, как строится приложение.  
  
-   Элемент управления состоит только из существующих компонентов.  
  
-   Поддержка сложной настройки не требуется.  
  
### Производные от элемента управления  
 Модель, порождаемая от класса <xref:System.Windows.Controls.Control>, используется большинством существующих элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Когда создается элемент управления, наследующий от класса <xref:System.Windows.Controls.Control>, то его внешний вид определяется при помощи шаблонов.  Это позволяет отделить рабочую логику от визуального представления.  Разделение пользовательского интерфейса и логики также достигается путем применения команд и привязок вместо событий, а также сокращением использования ссылок на элементы в <xref:System.Windows.Controls.ControlTemplate>. Если пользовательский интерфейс и логика элемента управления должным образом разделены, пользователи элемента управления могут переопределить его шаблон <xref:System.Windows.Controls.ControlTemplate> для изменения внешнего вида элемента управления. Хотя создание пользовательского элемента управления <xref:System.Windows.Controls.Control> не является такой же простой процедурой, как построение элемента управления <xref:System.Windows.Controls.UserControl>, пользовательский элемент управления <xref:System.Windows.Controls.Control> предоставляет наибольшую гибкость.  
  
#### Преимущества производной от элемента управления  
 Попробуйте создать производную от <xref:System.Windows.Controls.Control> вместо использования класса <xref:System.Windows.Controls.UserControl>, если выполняется одно из следующих условий:  
  
-   Внешний вид элемента управления должен настраиваться через <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Элемент управления должен поддерживать различные темы.  
  
### Производная от FrameworkElement  
 Элементы управления, производные от <xref:System.Windows.Controls.UserControl> или от <xref:System.Windows.Controls.Control>, основываются на сочетании существующих элементов.  Для многих скриптов это решение приемлемо, так как любой объект, наследующий от <xref:System.Windows.FrameworkElement>, может быть в <xref:System.Windows.Controls.ControlTemplate>.  В то же время бывают случаи, когда для внешнего вида элемента управления требуется функциональность, превосходящая возможности построения простого элемента.  В подобных скриптах необходимо строить компоненты на основе <xref:System.Windows.FrameworkElement>.  
  
 Существует два стандартных метода для построения компонентов, основанных на <xref:System.Windows.FrameworkElement>: прямая отрисовка и настраиваемое построение элемента.  Прямая отрисовка включает переопределение метода <xref:System.Windows.UIElement.OnRender%2A> из <xref:System.Windows.FrameworkElement> и предоставление операций <xref:System.Windows.Media.DrawingContext>, которые явно определяют графические параметры компонента.  Этот метод используется <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.Border>.  Пользовательское построение элемента включает в себя создание экземпляров и использование объектов типа <xref:System.Windows.Media.Visual> для построения внешнего вида компонента.  Пример см. в разделе [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md).  <xref:System.Windows.Controls.Primitives.Track> является примером элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], который использует пользовательское построение элемента.  Также в одном элементе можно комбинировать прямую отрисовку и настраиваемое построение.  
  
#### Преимущества производной от FrameworkElement  
 Попробуйте создать производную от <xref:System.Windows.FrameworkElement>, если соблюдено одно из следующих условий:  
  
-   Необходим тонкий контроль внешнего вида элемента управления, что не обеспечивается простым построением элемента.  
  
-   Необходимо определить внешний вид элемента управления путем определения собственной логики отображения.  
  
-   Требуется составить существующие элементы нестандартными способами, выходящими за рамки возможностей <xref:System.Windows.Controls.UserControl> и <xref:System.Windows.Controls.Control>.  
  
<a name="control_authoring_basics"></a>   
## Основы разработки элементов управления  
 Как указано выше, одной из наиболее мощных функций [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является возможность выхода за пределы задания базовых свойств элемента управления для изменения его внешнего вида и поведения без необходимости создания нового пользовательского элемента управления. Системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и системой событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляются такие возможности, как стили, привязка к данным и триггеры. В следующих разделах даются некоторые практические рекомендации, которым необходимо следовать независимо от модели, используемой для создания пользовательского элемента управления, чтобы пользователи этого элемента управления могли использовать данные возможности точно так же, как в случае любого другого элемента управления, входящего в состав [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Использование свойств зависимостей  
 Если свойство является свойством зависимостей, разработчик может выполнить следующие действия:  
  
-   Задать свойство в стиле.  
  
-   Привязать свойство к источнику данных.  
  
-   Использовать динамический ресурс в качестве значения свойства.  
  
-   Анимировать свойство.  
  
 Если свойство элемента управления должно поддерживать одну из перечисленных функций, необходимо реализовать его как свойство зависимостей.  В следующем примере для определения свойства зависимостей с именем `Value` необходимо выполнить приведенные ниже действия.  
  
-   Определите идентификатор <xref:System.Windows.DependencyProperty> с именем `ValueProperty` в качестве поля `public` `static` `readonly`.  
  
-   Зарегистрируйте имя свойства в системе свойств путем вызова <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=fullName>, указывая следующие данные:  
  
    -   Имя свойства.  
  
    -   Тип свойства.  
  
    -   Тип владельца свойства.  
  
    -   Метаданные для свойства.  Метаданные содержат значение свойства по умолчанию, <xref:System.Windows.CoerceValueCallback> и <xref:System.Windows.PropertyChangedCallback>.  
  
-   Определите свойство программы\-оболочки [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с именем `Value` \(это имя совпадает с именем, используемым для регистрации свойства зависимостей\) путем реализации методов доступа `get` и `set` этого свойства.  Обратите внимание, что методы доступа `get` и `set` вызывают только <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> соответственно.  Рекомендуется, чтобы методы доступа к свойствам зависимостей не содержали дополнительной логики, так как клиенты и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] могут пропускать методы доступа и вызывать <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> напрямую.  Например, если свойство привязано к источнику данных, то метод доступа свойства `set` не вызывается.  Вместо добавления дополнительной логики к методам доступа получения и установки следует использовать делегаты <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>, и <xref:System.Windows.PropertyChangedCallback> для ответа на значения или их проверки при изменении.  Дополнительные сведения об этих обратных вызовах см. в разделе [Проверка и обратные вызовы свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Определите метод для <xref:System.Windows.CoerceValueCallback> с именем `CoerceValue`.  Метод `CoerceValue` гарантирует, что значение `Value` больше или равно `MinValue` и меньше или равно `MaxValue`.  
  
-   Определите метод для <xref:System.Windows.PropertyChangedCallback> с именем `OnValueChanged`.  Метод `OnValueChanged` создает объект <xref:System.Windows.RoutedPropertyChangedEventArgs%601> и подготавливает создание перенаправленного события `ValueChanged`.  Перенаправленные события рассматриваются в следующем разделе.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### Использование перенаправленных событий  
 Аналогично [свойствам зависимостей](GTMT), которые расширяют свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] дополнительными функциональными возможностями, [перенаправленные события](GTMT) расширяют понятие стандартных событий [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  При создании нового элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рекомендуется также реализовывать событие как перенаправленное, так как перенаправленные события поддерживают следующее поведение:  
  
-   События могут обрабатываться в родительском элементе нескольких элементов управления.  Если событие является пузырьковым, на него может подписаться один родительский элемент в дереве элементов.  Затем разработчики приложения могут использовать один обработчик для реакции на событие нескольких элементов управления.  Например, если элемент управления является частью каждого элемента в <xref:System.Windows.Controls.ListBox> \(так как он включен в <xref:System.Windows.DataTemplate>\), разработчики приложения могут определить обработчик событий для события элемента управления в <xref:System.Windows.Controls.ListBox>.  Обработчик событий вызывается при возникновении события на любом элементе управления.  
  
-   Перенаправленные события можно использовать в <xref:System.Windows.EventSetter>. Это позволяет разработчикам указывать обработчик события внутри стиля.  
  
-   Перенаправленные события можно использовать в <xref:System.Windows.EventTrigger>, что может пригодиться для анимации свойств при помощи [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 В следующем примере определяется перенаправленное событие с помощью следующих действий:  
  
-   Определите идентификатор <xref:System.Windows.RoutedEvent> с именем `ValueChangedEvent` в качестве поля `public` `static` `readonly`.  
  
-   Зарегистрируйте перенаправленное событие путем вызова метода <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=fullName>.  При вызове <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> в примере указывается следующая информация:  
  
    -   Событие имеет имя `ValueChanged`.  
  
    -   Стратегией маршрутизации является <xref:System.Windows.RoutingStrategy>, то есть вначале вызывается обработчик событий в источнике \(объекте, вызывающем событие\), а затем поочередно вызываются обработчики событий родительских элементов источника, начиная с обработчика событий ближайшего родительского элемента.  
  
    -   Обработчик событий имеет тип <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, созданный с помощью типа <xref:System.Decimal>.  
  
    -   Типом владельца события является `NumericUpDown`.  
  
-   Объявите открытое событие, называемое `ValueChanged` и включающее объявления метода доступа к событию.  В этом примере вызывается <xref:System.Windows.UIElement.AddHandler%2A> в объявлении метода доступа `add` и <xref:System.Windows.UIElement.RemoveHandler%2A> в объявлении метода доступа `remove` для использования служб событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Создайте защищенный виртуальный метод с именем `OnValueChanged`, создающий событие `ValueChanged`.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 Дополнительные сведения см. в разделах [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md) и [Создание пользовательских перенаправленных событий](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md).  
  
### Использование привязки  
 Для отделения пользовательского интерфейса элемента управления от логики попробуйте использовать привязку данных.  Это особенно важно, если внешний вид элемента управления определяется при помощи <xref:System.Windows.Controls.ControlTemplate>.  Использование привязки данных может избавить разработчика от необходимости ссылаться на определенные части пользовательского интерфейса из кода.  Рекомендуется избегать ссылающихся элементов, находящихся в <xref:System.Windows.Controls.ControlTemplate>, потому что когда код ссылается на элементы в <xref:System.Windows.Controls.ControlTemplate>, а объект <xref:System.Windows.Controls.ControlTemplate> изменен, ссылочный элемент должен быть включен в новый <xref:System.Windows.Controls.ControlTemplate>.  
  
 Следующий пример обновляет <xref:System.Windows.Controls.TextBlock> элемента управления `NumericUpDown`, присваивая ему имя и ссылаясь на текстовое поле в коде по имени.  
  
 [!code-xml[UserControlNumericUpDownSimple#UIRefMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 В следующем примере для выполнения тех же действий используется привязка.  
  
 [!code-xml[UserControlNumericUpDown#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 Дополнительные сведения о привязке данных см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
### Разработка для конструкторов  
 Чтобы получить поддержку пользовательских элементов управления WPF в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)], необходимо воспользоваться этими правилами.  Дополнительные сведения по разработке для [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] см. в разделе [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26).  
  
#### Свойства зависимостей  
 Реализуйте методы доступа [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` and `set`, как описано ранее в разделе "Использование свойств зависимостей". Конструкторы могут использовать программу\-оболочку для обнаружения присутствия свойств зависимости, но, подобно [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и клиентам элемента управления, не обязаны вызывать методы доступа при получении или установке свойств.  
  
#### Вложенные свойства зависимостей  
 Вложенные свойства зависимостей на пользовательских элементах управления следует реализовывать с помощью следующих правил:  
  
-   Воспользуйтесь `public` `static` `readonly` <xref:System.Windows.DependencyProperty> из формы *PropertyName*`Property`, которая производила создание с помощью метода <xref:System.Windows.DependencyProperty.RegisterAttached%2A>.  Имя свойства, которое передается <xref:System.Windows.DependencyProperty.RegisterAttached%2A> должно соответствовать *PropertyName*.  
  
-   Реализуйте пару `public` `static` методов CLR с именами `Set`*PropertyName* и `Get`*PropertyName*.  Оба метода должны принимать производный класс от <xref:System.Windows.DependencyProperty> в качестве первого аргумента.  Метод `Set`*PropertyName* также принимает аргумент, тип которого соответствует зарегистрированному типу данных для свойства.  Метод `Get`*PropertyName* должен возвращать значение того же типа.  Если метод `Set`*PropertyName* отсутствует, свойство будет отмечено как свойство только для чтения.  
  
-   Методы `Set`*имя\_свойства* и `Get`*имя\_свойства* должны перенаправляться непосредственно в методы <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> целевого объекта зависимостей, соответственно.  Конструкторы могут обращаться к вложенному свойству зависимостей с помощью вызова через программу\-оболочку метода или с помощью прямого вызова целевого объекта зависимостей.  
  
 Дополнительные сведения о вложенных свойствах зависимостей см. в разделе [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
### Определение и использование общих ресурсов  
 Элемент управления можно включить в ту же сборку, что и приложение, или можно пакетировать его в отдельной сборке, которая может использоваться в нескольких приложениях.  В большинстве своем, сведения, обсуждаемые в этом разделе, применимы независимо от используемого метода.  Однако одно отличие требует упоминания.  При помещении элемента управления в одну сборку с приложением можно свободно добавить глобальные ресурсы в файл app.xaml.  Однако сборка, содержащая только элементы управления, не имеет связанного с ней объекта <xref:System.Windows.Application>, поэтому файл app.xaml недоступен.  
  
 Когда приложение выполняет поиск ресурса, оно использует три уровня в следующем порядке:  
  
1.  Уровень элемента.  
  
     Система начинает работу с элементом, ссылающимся на ресурс, и затем ищет ресурсы логического родительского элемента и так далее, пока не будет достигнут корневой элемент.  
  
2.  Уровень приложения.  
  
     Ресурсы, определенные объектом <xref:System.Windows.Application>.  
  
3.  Уровень темы.  
  
     Словари уровня темы сохраняются во вложенной папке с именем Themes.  Файлы в папке Themes соответствуют темам.  Например, могут быть файлы Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml и т.д.  Также может иметься файл с именем generic.xaml.  Когда система ищет ресурс на уровне темы, сначала она выполняет поиск в файле отдельной темы и затем — в файле generic.xaml.  
  
 Если элемент управления находится в сборке отдельно от приложения, глобальные ресурсы необходимо поместить на уровне элемента или темы.  Оба метода имеют свои преимущества.  
  
#### Определение ресурсов на уровне элемента  
 Общие ресурсы можно определить на уровне элемента созданием пользовательского словаря ресурсов и его объединением со словарем ресурсов элемента управления.  При использовании этого метода файл ресурса можно назвать любым способом, и он может находиться в той же папке, что и элементы управления.  Ресурсы на уровне элемента также могут использовать простые строки как ключи.  В следующем примере создается файл ресурса <xref:System.Windows.Media.LinearGradientBrush> с именем Dictionary1.xaml.  
  
 [!code-xml[SharedResources#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 После определения ресурса его необходимо объединить со словарем ресурсов элемента управления.  Это можно сделать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода.  
  
 В следующем примере выполняется объединение словаря ресурсов с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[SharedResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 Недостатком этого метода является то, что объект <xref:System.Windows.ResourceDictionary> создается при каждой ссылке на него.  Например, если в библиотеке имеется 10 пользовательских элементов управления и выполняется объединение словарей общих ресурсов для каждого элемента управления с использованием файла XAML, будут созданы 10 идентичных объектов <xref:System.Windows.ResourceDictionary>.  Этого можно избежать созданием статического класса, который объединяет ресурсы в коде и возвращает итоговый объект <xref:System.Windows.ResourceDictionary>.  
  
 В следующем примере создается класс, который возвращает общий объект <xref:System.Windows.ResourceDictionary>.  
  
 [!code-csharp[SharedResources#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 В следующем примере выполняется объединение общего ресурса с ресурсами пользовательского элемента управления в конструкторе элемента управления до того, как он вызывает `InitilizeComponent`.  Так как `SharedDictionaryManager.SharedDictionary` является статическим свойством, <xref:System.Windows.ResourceDictionary> создается только один раз.  Так как словарь ресурсов был объединен до того, как был вызван `InitializeComponent`, эти ресурсы доступны элементу управления в его файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[SharedResources#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### Определение ресурсов на уровне темы  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать ресурсы для разных тем Windows.  Автор элемента управления может определить ресурс для отдельной темы, чтобы изменять внешний вид элемента управления в зависимости от используемой темы.  Например, внешний вид элемента управления <xref:System.Windows.Controls.Button> в теме Windows Classic \(тема по умолчанию для Windows 2000\) отличается от внешнего вида элемента управления <xref:System.Windows.Controls.Button> в теме Windows Luna \(тема по умолчанию для Windows XP\), так как <xref:System.Windows.Controls.Button> использует отдельный шаблон <xref:System.Windows.Controls.ControlTemplate> для каждой темы.  
  
 Ресурсы, указанные для темы, хранятся в словаре ресурсов с отдельным именем файла.  Эти файлы должны находиться в папке с именем `Themes`, которая является вложенной в папке, содержащей элемент управления.  В следующей таблице перечислены файлы словарей ресурсов и схемы, с которыми они связаны в каждом файле:  
  
|Имя файла словаря ресурсов|Тема Windows|  
|--------------------------------|------------------|  
|`Classic.xaml`|Классический внешний вид Windows 9x\/2000 для Windows XP|  
|`Luna.NormalColor.xaml`|Синяя тема по умолчанию для Windows XP|  
|`Luna.Homestead.xaml`|Оливковая тема для Windows XP|  
|`Luna.Metallic.xaml`|Серебристая тема для Windows XP|  
|`Royale.NormalColor.xaml`|Тема по умолчанию для Windows XP Media Center Edition|  
|`Aero.NormalColor.xaml`|Тема по умолчанию для Windows Vista|  
  
 Не требуется определять ресурс для каждой темы.  Если ресурс не определен для конкретной темы, элемент управления выполняет поиск ресурса в файле `Classic.xaml`.  Если ресурс не определен ни в файле, соответствующем конкретной теме, ни в файле `Classic.xaml`, элемент управления использует универсальный ресурс из файла словаря ресурсов `generic.xaml`.  Файл `generic.xaml` расположен в одной папке с файлами словаря ресурсов для конкретных тем.  Хотя файл `generic.xaml` не соответствует отдельной теме Windows, он является словарем уровня схемы.  
  
 [В примере пользовательского элемента управления NumericUpDown с темой и поддержкой модели автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025) содержатся два словаря ресурсов для элемента управления `NumericUpDown`: generic.xaml и Luna.NormalColor.xaml.  Можно запустить приложение и переключаться между серебристой темой в Windows XP и другой темой, чтобы увидеть разницу между двумя шаблонами элемента управления.  \(При работе в Windows Vista можно переименовать Luna.NormalColor.xaml в Aero.NormalColor.xaml и переключаться между двумя темами, например классической Windows и темой по умолчанию для Windows Vista.\)  
  
 При помещении <xref:System.Windows.Controls.ControlTemplate> в другие файлы словарей ресурсов отдельных тем необходимо создать статический конструктор для элемента управления и вызвать метод <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> в <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### Определяющие и ссылочные ключи для ресурсов тем  
 При определении ресурса на уровне элемента можно назначить строку в качестве его ключа и обращаться к ресурсу через эту строку.  При определении ресурса на уровне темы необходимо в качестве ключа использовать <xref:System.Windows.ComponentResourceKey>.  В следующем примере определяется ресурс в файле generic.xaml.  
  
  
  
 В следующем примере выполняется ссылка на ресурс определением в качестве ключа <xref:System.Windows.ComponentResourceKey>.  
  
  
  
##### Определение местоположения ресурсов тем  
 Чтобы найти ресурсы для элемента управления, ведущее приложение должно знать, что сборка содержит ресурсы отдельного элемента управления.  Для этого можно добавить <xref:System.Windows.ThemeInfoAttribute> в сборку, которая содержит элемент управления.  <xref:System.Windows.ThemeInfoAttribute> имеет свойство <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>, которое указывает местоположение универсальных ресурсов, и свойство <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>, указывающее местоположение ресурсов отдельной схемы.  
  
 В следующем примере для свойств <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> задается значение <xref:System.Windows.ResourceDictionaryLocation>, чтобы указать, что универсальные и отдельные ресурсы схем находятся в одной сборке с элементом управления.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## См. также  
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)