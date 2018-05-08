---
title: Общие сведения о разработке управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: a6c2c796819924cdbd15d6eefffe10a607bad9bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="control-authoring-overview"></a>Общие сведения о разработке элементов управления
Расширяемость модели элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] значительно уменьшает необходимость создания новых элементов управления. Однако в некоторых случаях может потребоваться создать пользовательский элемент управления. В этом разделе обсуждаются функции, которые уменьшают необходимость создания пользовательских элементов управления, а также различные модели создания элементов управления в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Также здесь демонстрируется создание нового элемента управления.  
  
 
  
<a name="when_to_write_a_new_control"></a>   
## <a name="alternatives-to-writing-a-new-control"></a>Альтернативы написанию нового элемента управления  
 Исторически сложилось, что если нужно настроить вид существующего элемента управления, то ограничиваются изменением его стандартных свойств, таких как цвет фона, ширина границы и размер шрифта. Если необходимо расширить внешний вид или поведение элемента управления за пределы этих предопределенных параметров, то необходимо создать новый элемент управления, как правило, путем наследования от существующего элемента управления и переопределения метода, ответственного за отрисовку элемента управления.  Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет настраивать существующие элементы управления с помощью модели форматированного содержимого, стилей, шаблонов и триггеров. Ниже представлены примеры использования этих функций для создания настраиваемых и согласованных функциональных возможностей без необходимости создания нового элемента управления.  
  
-   **Форматированное содержимое.** Многие стандартные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают форматированное содержимое. Например, свойство содержимого <xref:System.Windows.Controls.Button> относится к типу <xref:System.Object>, теоретически ничего могут отображаться на <xref:System.Windows.Controls.Button>.  Чтобы отобразить изображение и текст кнопки, можно добавить изображение и <xref:System.Windows.Controls.TextBlock> для <xref:System.Windows.Controls.StackPanel> и назначить <xref:System.Windows.Controls.StackPanel> для <xref:System.Windows.Controls.ContentControl.Content%2A> свойства. Поскольку элементы управления могут отображать визуальные элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и произвольные данные, это уменьшает необходимость создания нового элемента управления или изменения существующего для поддержки сложной визуализации. Дополнительные сведения о модели содержимого для <xref:System.Windows.Controls.Button> и других моделях содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
-   **Стили.** Объект <xref:System.Windows.Style> — это совокупность значений, представляющих свойства для элемента управления. С помощью стилей можно создать повторно используемое представление нужного внешнего вида и поведения элемента управления без написания нового элемента управления. Например, предположим, что все вашей <xref:System.Windows.Controls.TextBlock> элементам управления иметь красный, сделанные шрифтом Arial с размером шрифта 14. Можно создать стиль как ресурс и задать соответствующие свойства. Каждый <xref:System.Windows.Controls.TextBlock> , добавьте в приложение будет иметь тот же внешний вид.  
  
-   **Шаблоны данных.** Объект <xref:System.Windows.DataTemplate> позволяет настроить способ отображения данных в элементе управления. Например <xref:System.Windows.DataTemplate> может использоваться для указания способа отображения данных в <xref:System.Windows.Controls.ListBox>.  Пример см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).  В дополнение к настройке внешнего вида данных, <xref:System.Windows.DataTemplate> может включать элементы пользовательского интерфейса, который обеспечивает большую гибкость в пользовательских интерфейсах пользователя.  Например, с помощью <xref:System.Windows.DataTemplate>, можно создать <xref:System.Windows.Controls.ComboBox> , в которой каждый элемент содержит флажок.  
  
-   **Шаблоны элементов управления.** Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использовать <xref:System.Windows.Controls.ControlTemplate> для определения структуры и внешнего вида, который отделяет внешний вид элемента управления от функциональные возможности элемента управления элемента управления. Можно значительно изменить внешний вид элемента управления путем переопределения его <xref:System.Windows.Controls.ControlTemplate>.  Предположим, что нужен элемент управления, который выглядит как светофор. Этот элемент управления имеет простой пользовательский интерфейс и функциональные возможности.  Элемент управления состоит из трех кругов, из которых одновременно загорается только один. После некоторого размышления становится понятно, <xref:System.Windows.Controls.RadioButton> предоставляют возможности выбора только один раз, но внешний вид по умолчанию <xref:System.Windows.Controls.RadioButton> похож на Светофор индикаторы.  Поскольку <xref:System.Windows.Controls.RadioButton> использует шаблон элемента управления для определения внешнего вида, легко переопределить <xref:System.Windows.Controls.ControlTemplate> требованиям элемента управления и использование переключателей для построения светофора.  
  
    > [!NOTE]
    >  Несмотря на то что <xref:System.Windows.Controls.RadioButton> можно использовать <xref:System.Windows.DataTemplate>, <xref:System.Windows.DataTemplate> не хватает в этом примере.  <xref:System.Windows.DataTemplate> Определяет внешний вид содержимого элемента управления. В случае использования <xref:System.Windows.Controls.RadioButton>, содержимое является все, что отображается справа от круг, указывающий ли <xref:System.Windows.Controls.RadioButton> выбран.  В примере светофора переключатель должен быть тем кругом, который может "загораться". Так как внешний вид требование Светофор таким образом отличается от внешнего вида элемента <xref:System.Windows.Controls.RadioButton>, необходимо переопределить <xref:System.Windows.Controls.ControlTemplate>.  В целом <xref:System.Windows.DataTemplate> используется для определения содержимого (или данных) элемента управления, а также <xref:System.Windows.Controls.ControlTemplate> используется для определения структуру элемента управления.  
  
-   **Триггеры.** Объект <xref:System.Windows.Trigger> позволяет динамически изменять внешний вид и поведение элемента управления без необходимости создания нового элемента. Например, предположим, имеется несколько <xref:System.Windows.Controls.ListBox> элементов управления в приложении и элементы в каждом <xref:System.Windows.Controls.ListBox> быть полужирным и красным при их выборе. Может быть очевидным, чтобы создать класс, наследующий от <xref:System.Windows.Controls.ListBox> и Переопределите <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> метод, чтобы изменить внешний вид выбранного элемента, но более удачным подходом является добавление триггера стиль <xref:System.Windows.Controls.ListBoxItem> , изменяется внешний вид Выбранный элемент. Триггер позволяет изменять значения свойств или выполнять действия в зависимости от значения свойства. <xref:System.Windows.EventTrigger> Позволяет предпринять действия при возникновении события.  
  
 Дополнительные сведения о стилях, шаблонах и триггерах см. в разделе [Использование стилей и шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 В целом, если элемент управления отражает функциональность существующего элемента управления, но должен выглядеть по-другому, сначала следует рассмотреть возможность использования какого-либо из методов, описанных в этом разделе, для изменения внешнего вида существующего элемента.  
  
<a name="models_for_control_authoring"></a>   
## <a name="models-for-control-authoring"></a>Модели для создания элементов управления  
 Модель форматированного содержимого, стили, шаблоны и триггеры уменьшают необходимость создания новых элементов управления. Тем не менее, если необходимо создать новый элемент управления, важно понимать различные модели создания элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет три общих модели для создания элемента управления, которые имеют различный набор функций и уровень гибкости. Основными классами для три модели <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>, и <xref:System.Windows.FrameworkElement>.  
  
### <a name="deriving-from-usercontrol"></a>Создание производных классов от UserControl  
 Самый простой способ создания элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является наследование от <xref:System.Windows.Controls.UserControl>. При создании элемента управления, который наследует от <xref:System.Windows.Controls.UserControl>, добавить существующие компоненты для <xref:System.Windows.Controls.UserControl>, назовите компоненты и ссылается на обработчики событий в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Затем можно ссылаться на именованные элементы и определять обработчики событий в коде. Эта модель разработки очень схожа с моделью, используемой для разработки приложений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Если сборка выполнена неправильно, <xref:System.Windows.Controls.UserControl> можно использовать преимущества сложных элементов, стили и триггеров. Тем не менее если элемент управления наследуется от <xref:System.Windows.Controls.UserControl>, людей, использующих элемент управления, не смогут использовать <xref:System.Windows.DataTemplate> или <xref:System.Windows.Controls.ControlTemplate> для настройки внешнего вида.  Это необходимо для наследования от <xref:System.Windows.Controls.Control> класс или один из его производных классов (отличного от <xref:System.Windows.Controls.UserControl>) для создания пользовательского элемента управления, поддерживающего шаблоны.  
  
#### <a name="benefits-of-deriving-from-usercontrol"></a>Преимущества использования производного класса от UserControl  
 Рассмотрите возможность наследования от <xref:System.Windows.Controls.UserControl> Если применяются все из следующих действий:  
  
-   Нужно создать элемент управления аналогично созданию приложения.  
  
-   Элемент управления состоит только из существующих компонентов.  
  
-   Не нужно поддерживать сложные настройки.  
  
### <a name="deriving-from-control"></a>Создание производного от элемента управления  
 Наследование от <xref:System.Windows.Controls.Control> класс — это модель, применяемые в большинстве существующих [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления. При создании элемента управления, который наследует от <xref:System.Windows.Controls.Control> класса, его внешний вид определяется с помощью шаблонов. Таким образом, можно отделить рабочую логику от визуального представления. Также можно обеспечить разделение пользовательского интерфейса и логики с помощью команд и привязок вместо событий и использования ссылок на элементы в <xref:System.Windows.Controls.ControlTemplate> по возможности.  Если пользовательский Интерфейс и логика элемента управления должным образом разделены, пользователи элемента управления могут переопределить элемента управления <xref:System.Windows.Controls.ControlTemplate> для настройки внешнего вида. Хотя создание пользовательского <xref:System.Windows.Controls.Control> не так прост, как построение <xref:System.Windows.Controls.UserControl>, настраиваемый <xref:System.Windows.Controls.Control> обеспечивает наибольшую гибкость.  
  
#### <a name="benefits-of-deriving-from-control"></a>Преимущества использования производного от элемента управления  
 Рассмотрите возможность наследования от <xref:System.Windows.Controls.Control> вместо использования <xref:System.Windows.Controls.UserControl> класса, если выполняется любое из следующих условий:  
  
-   Внешний элемент управления настраивается через <xref:System.Windows.Controls.ControlTemplate>.  
  
-   Элемент управления должен поддерживать различные темы.  
  
### <a name="deriving-from-frameworkelement"></a>Создание производного от FrameworkElement  
 Элементы управления, которые являются производными от <xref:System.Windows.Controls.UserControl> или <xref:System.Windows.Controls.Control> основываются на сочетании существующих элементов. Во многих сценариях это решение приемлемо, так как любой объект, наследуемый от <xref:System.Windows.FrameworkElement> может находиться в <xref:System.Windows.Controls.ControlTemplate>. Однако бывают случаи, когда для внешнего вида элемента управления требуется больше, чем функциональность простой композиции элементов. В этих сценариях, компонент создание на основе <xref:System.Windows.FrameworkElement> – правильный выбор.  
  
 Существует два стандартных методов для построения <xref:System.Windows.FrameworkElement>-компонентов, основанных на: прямая отрисовка и настраиваемое построение элемента. Прямая отрисовка включает переопределение <xref:System.Windows.UIElement.OnRender%2A> метод <xref:System.Windows.FrameworkElement> и предоставляя <xref:System.Windows.Media.DrawingContext> операций, которые явно определяют графические параметры компонента. Это метод, используемый для <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.Border>. Построение пользовательского элемента предполагает использование объектов типа <xref:System.Windows.Media.Visual> для построения внешнего компонента. Например, см. раздел [Использование объектов DrawingVisual](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track> Пример элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , используется сочетание настраиваемого элемента. Можно также комбинировать прямую отрисовку и пользовательскую композицию элемента в одном элементе управления.  
  
#### <a name="benefits-of-deriving-from-frameworkelement"></a>Преимущества использования производного от FrameworkElement  
 Рассмотрите возможность наследования от <xref:System.Windows.FrameworkElement> при выполнении одного из следующих условий:  
  
-   Требуется точный контроль над внешним видом элемента управления помимо того, который обеспечивается простой композицией элемента.  
  
-   Необходимо определить внешний вид элемента управления путем определения собственной логики отрисовки.  
  
-   Чтобы составить существующие элементы нестандартными способами, которые выходят за рамки возможностей с <xref:System.Windows.Controls.UserControl> и <xref:System.Windows.Controls.Control>.  
  
<a name="control_authoring_basics"></a>   
## <a name="control-authoring-basics"></a>Основы создания элементов управления  
 Как обсуждалось выше, одной из наиболее мощных функций [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является возможность выхода за пределы задания базовых свойств элемента управления, чтобы изменить его внешний вид и поведение, но без необходимости создания пользовательского элемента управления. Функции стилей, привязки данных и триггеров предоставляются системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и системой событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В следующих разделах описаны некоторые рекомендации, которым нужно следовать независимо от модели, используемой для создания пользовательского элемента управления. Это необходимо, чтобы пользователи вашего пользовательского элемента управления могли использовать эти функции точно так же, как для элемента управления, входящего в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="use-dependency-properties"></a>Использование свойств зависимостей  
 Если свойство является свойством зависимостей, то можно сделать следующее:  
  
-   Установить свойство в стиле.  
  
-   Привязать свойство к источнику данных.  
  
-   Использовать динамический ресурс в качестве значения свойства.  
  
-   Анимировать свойство.  
  
 Если свойство элемента управления должно поддерживать подобную функциональность, то следует реализовать его как свойство зависимостей. В следующем примере определяется свойство зависимостей с именем `Value` следующим способом:  
  
-   Определение <xref:System.Windows.DependencyProperty> идентификатор с именем `ValueProperty` как `public` `static` `readonly` поля.  
  
-   Зарегистрируйте имя свойства в системе свойств путем вызова <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>, чтобы указать следующее:  
  
    -   Имя свойства.  
  
    -   Тип свойства.  
  
    -   Тип, к которому принадлежит это свойство.  
  
    -   Метаданные для свойства. Метаданные содержат значение свойства по умолчанию, <xref:System.Windows.CoerceValueCallback> и <xref:System.Windows.PropertyChangedCallback>.  
  
-   Определите свойство программы-оболочки [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] с именем `Value`, которое используется для регистрации свойства зависимостей, путем реализации методов доступа `get` и `set` свойства. Обратите внимание, что `get` и `set` вызывать только методы доступа <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> соответственно. Рекомендуется, методы доступа для свойства зависимостей не содержали дополнительной логики, так как клиенты и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно обойти методы доступа и вызывать <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> напрямую. Например, если свойство привязано к источнику данных, то метод доступа `set` свойства не вызывается.  Вместо добавления дополнительную логику для получения и установки методов доступа, используйте <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>, и <xref:System.Windows.PropertyChangedCallback> ответить или проверьте значение, когда она изменяет делегаты.  Дополнительные сведения об этих обратных вызовах см. в разделе [Проверка и обратные вызовы свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Определите метод для <xref:System.Windows.CoerceValueCallback> с именем `CoerceValue`. `CoerceValue` гарантирует, что `Value` больше или равно `MinValue` и меньше или равно `MaxValue`.  
  
-   Определите метод для <xref:System.Windows.PropertyChangedCallback>с именем `OnValueChanged`. `OnValueChanged` Создает <xref:System.Windows.RoutedPropertyChangedEventArgs%601> объекта и подготавливает для вызова `ValueChanged` перенаправленного события. Перенаправляемые события рассматриваются в следующем разделе.  
  
 [!code-csharp[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
 [!code-vb[UserControlNumericUpDown#DependencyProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]  
  
 Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
### <a name="use-routed-events"></a>Использование перенаправляемых событий  
 Аналогично тому, как свойства зависимостей расширяют представление свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] дополнительной функциональностью, перенаправляемые события расширяют представление стандартных событий [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. При создании нового элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рекомендуется также реализовывать событие как перенаправляемое, так как такие события поддерживают следующее поведение:  
  
-   События могут обрабатываться в родительском элементе нескольких элементов управления. Если событие является событием восходящей маршрутизации, то один родительский элемент в дереве элементов может подписаться на это событие. Разработчики приложений могут использовать один обработчик для реагирования на событие нескольких элементов управления. Например, если элемент управления является частью каждого элемента в <xref:System.Windows.Controls.ListBox> (так как он включен в <xref:System.Windows.DataTemplate>), разработчик приложения может определить обработчик событий для события элемента управления на <xref:System.Windows.Controls.ListBox>. Обработчик событий вызывается при возникновении события в любом элементе управления.  
  
-   Перенаправленные события можно использовать в <xref:System.Windows.EventSetter>, который позволяет разработчикам приложений определить обработчик события в стиле.  
  
-   Перенаправленные события можно использовать в <xref:System.Windows.EventTrigger>, что полезно для анимации свойства с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Следующий пример определяет перенаправляемое событие:  
  
-   Определение <xref:System.Windows.RoutedEvent> идентификатор с именем `ValueChangedEvent` как `public` `static` `readonly` поля.  
  
-   Зарегистрируйте перенаправленное событие путем вызова <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> метод. В примере указывается следующие сведения при вызове <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>:  
  
    -   Имя события `ValueChanged`.  
  
    -   Стратегия маршрутизации является <xref:System.Windows.RoutingStrategy.Bubble>, это означает, что сначала вызывается обработчик событий в источнике (объект, который вызывает событие), а затем обработчики событий в родительских элементов источника, называются последовательно, начиная с обработчиком событий на ближайший родительский элемент.  
  
    -   Тип обработчика событий <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, созданный с <xref:System.Decimal> типа.  
  
    -   Тип — владелец события — `NumericUpDown`.  
  
-   Объявите общее событие с именем `ValueChanged`, которое включает объявления метода доступа к событию. В примере вызывается <xref:System.Windows.UIElement.AddHandler%2A> в `add` объявления метода доступа set и <xref:System.Windows.UIElement.RemoveHandler%2A> в `remove` объявление метода доступа для использования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] событий служб.  
  
-   Создайте защищенный виртуальный метод с именем `OnValueChanged`, вызывающий событие `ValueChanged`.  
  
 [!code-csharp[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
 [!code-vb[UserControlNumericUpDown#RoutedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]  
  
 Дополнительные сведения см. в разделах [Общие сведения о перенаправляемых событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md) и [Создание пользовательских перенаправляемых событий](../../../../docs/framework/wpf/advanced/how-to-create-a-custom-routed-event.md).  
  
### <a name="use-binding"></a>Использование привязки  
 Для отделения пользовательского интерфейса от логики элемента управления можно использовать привязку данных. Это особенно важно, если определить внешний вид элемента управления с помощью <xref:System.Windows.Controls.ControlTemplate>. При использовании привязки данных можно избавиться от необходимости ссылаться на определенные части пользовательского интерфейса из кода. Рекомендуется избегать ссылок на элементы, которые <xref:System.Windows.Controls.ControlTemplate> потому, что когда код ссылается на элементы, которые <xref:System.Windows.Controls.ControlTemplate> и <xref:System.Windows.Controls.ControlTemplate> изменяется указанный элемент должен быть включен в новом <xref:System.Windows.Controls.ControlTemplate>.  
  
 В следующем примере обновляется <xref:System.Windows.Controls.TextBlock> из `NumericUpDown` элемента управления, присвоение имени и ссылаясь на текстовое поле по имени в коде.  
  
 [!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]  
  
 [!code-csharp[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
 [!code-vb[UserControlNumericUpDownSimple#UIRefCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]  
  
 Следующий пример использует привязку для достижения такого же результата.  
  
 [!code-xaml[UserControlNumericUpDown#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]  
  
 Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
### <a name="design-for-designers"></a>Разработка для конструкторов  
 Чтобы получить поддержку пользовательских элементов управления WPF в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] (например, редактирование свойства с помощью окна "Свойства"), следуйте приведенным ниже рекомендациям.  Дополнительные сведения о разработке для [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] см. в разделе [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).  
  
#### <a name="dependency-properties"></a>Свойства зависимостей  
 Следует реализовать методы доступа [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] `get` и `set`, как описано ранее в разделе "Использование свойств зависимостей". Конструкторы могут использовать программы-оболочки для обнаружения свойства зависимостей, но им, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и клиентам элемента управления, не требуется вызывать методы доступа при получении или настройке свойства.  
  
#### <a name="attached-properties"></a>Вложенные свойства  
 При реализации вложенных свойств в пользовательских элементах управления учитывайте следующие рекомендации:  
  
-   У `public` `static` `readonly` <xref:System.Windows.DependencyProperty> формы *PropertyName* `Property` создании с помощью <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод. Имя свойства, которое передается <xref:System.Windows.DependencyProperty.RegisterAttached%2A> должно соответствовать *PropertyName*.  
  
-   Реализуйте пару методов CLR `public` `static` с именем `Set`*PropertyName* и `Get`*PropertyName*. Оба метода должны принимать класс, производный от <xref:System.Windows.DependencyProperty> качестве первого аргумента. Метод `Set`*PropertyName* также принимает аргумент, тип которого соответствует зарегистрированному типу данных для свойства. Метод `Get`*PropertyName* должен возвращать значение такого же типа. Если метод `Set` *PropertyName* отсутствует, свойство отмечается как "только для чтения".  
  
-   `Set` *PropertyName* и `Get` *PropertyName* должны перенаправляться непосредственно в <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> методы зависимостей целевого объекта, соответственно. Разработчики могут получить доступ к вложенному свойству, вызвав программу-оболочку метода или с помощью прямого вызова целевого объекта зависимостей.  
  
 Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
### <a name="define-and-use-shared-resources"></a>Определение и использование общих ресурсов  
 Можно включить элемент управления в ту же сборку, что и приложение, или упаковать его в отдельную сборку, которая может использоваться в нескольких приложениях. В большинстве случаев сведения, рассматриваемые в данном разделе, применяются независимо от используемого метода.  Однако есть одно отличие, о котором следует упомянуть.  При помещении элемента управления в ту же сборку, что и приложение, можно добавить глобальные ресурсы в файл App.xaml. Но не сборку, которая содержит только элементы управления <xref:System.Windows.Application> объект, связанный с ним, поэтому файл App.xaml недоступен.  
  
 Приложение выполняет поиск ресурса на трех уровнях в следующем порядке:  
  
1.  Уровень элемента.  
  
     Система начинает с элемента, который ссылается на ресурс, а затем ищет ресурсы логического родительского элемента и так далее, пока не будет достигнут корневой элемент.  
  
2.  Уровень приложения.  
  
     Ресурсов, выделяемых <xref:System.Windows.Application> объекта.  
  
3.  Уровень темы.  
  
     Словари уровня темы хранятся в подпапке "Темы".  Файлы в папке "Темы" соответствуют темам.  Например, могут присутствовать файлы Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml и т. д.  Также может присутствовать файл с именем generic.xaml.  Когда система ищет ресурс на уровне темы, она сначала ищет его в файле конкретной темы, а затем в файле generic.xaml.  
  
 Если элемент управления находится в сборке отдельно от приложения, глобальные ресурсы необходимо поместить на уровень элемента или на уровень темы. Оба метода имеют свои преимущества.  
  
#### <a name="defining-resources-at-the-element-level"></a>Определение ресурсов на уровне элемента  
 Общие ресурсы на уровне элемента можно определить путем создания пользовательского словаря ресурсов и его объединения со словарем ресурсов элемента управления.  При использовании этого метода можно присвоить файлу ресурсов любое имя и его можно поместить в одну папку с элементами управления. Ресурсы на уровне элемента также могут использовать простые строки как ключи. В следующем примере создается <xref:System.Windows.Media.LinearGradientBrush> файл ресурсов с именем Dictionary1.xaml.  
  
 [!code-xaml[SharedResources#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]  
  
 После определения словаря необходимо его объединить со словарем ресурсов элемента управления.  Это можно сделать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода.  
  
 Следующий пример объединяет словарь ресурса с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[SharedResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]  
  
 Недостаток этого подхода заключается в том, <xref:System.Windows.ResourceDictionary> создается каждый раз, ссылки на объект.  Например, если в библиотеке имеется 10 пользовательских элементов управления и выполняется объединение словарей общих ресурсов для каждого элемента управления с помощью XAML, будут созданы 10 идентичных <xref:System.Windows.ResourceDictionary> объектов.  Этого можно избежать, Создание статического класса, который объединяет ресурсы в коде и возвращает итоговое <xref:System.Windows.ResourceDictionary>.  
  
 В следующем примере создается класс, который возвращает общий <xref:System.Windows.ResourceDictionary>.  
  
 [!code-csharp[SharedResources#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]  
  
 В следующем примере общий ресурс объединяется с ресурсами пользовательского элемента управления в конструкторе элемента управления, прежде чем он вызывает `InitializeComponent`.  Поскольку `SharedDictionaryManager.SharedDictionary` является статическим свойством <xref:System.Windows.ResourceDictionary> создается только один раз. Поскольку словарь ресурсов был объединен до вызова `InitializeComponent`, ресурсы доступны для элемента управления в его файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-csharp[SharedResources#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]  
  
#### <a name="defining-resources-at-the-theme-level"></a>Определение ресурсов на уровне темы  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать ресурсы для разных тем Windows.  Как разработчик элемента управления, вы можете определить ресурс для определенной темы, чтобы изменить внешний вид элемента управления в зависимости от того, какая тема используется. Например, внешний вид <xref:System.Windows.Controls.Button> в классической темы (тема по умолчанию для Windows 2000) отличается от <xref:System.Windows.Controls.Button> в теме Windows Luna (тема по умолчанию для Windows XP) из-за <xref:System.Windows.Controls.Button> использует другой <xref:System.Windows.Controls.ControlTemplate> для каждой темы.  
  
 Ресурсы, относящиеся к теме, хранятся в словаре ресурсов с заданным именем файла. Эти файлы должны находиться в папке с именем `Themes`, которая является подпапкой папки, содержащей элемент управления. В следующей таблице перечислены файлы словаря ресурсов и темы, связанные с каждым файлом.  
  
|Имя файла словаря ресурсов|Тема Windows|  
|-----------------------------------|-------------------|  
|`Classic.xaml`|Классический вид Windows 9x/2000 для Windows XP|  
|`Luna.NormalColor.xaml`|Синяя тема по умолчанию в Windows XP|  
|`Luna.Homestead.xaml`|Оливковая тема в Windows XP|  
|`Luna.Metallic.xaml`|Серебристая тема в Windows XP|  
|`Royale.NormalColor.xaml`|Тема по умолчанию в Windows XP Media Center Edition|  
|`Aero.NormalColor.xaml`|Тема по умолчанию в Windows Vista|  
  
 Не нужно определять ресурс для каждой темы. Если ресурс не определен для конкретной темы, элемент управления проверяет `Classic.xaml` для ресурса. Если ресурс не определен в файле, соответствующем текущей теме, или в `Classic.xaml`, то элемент управления использует общий ресурс, который находится в файле словаря ресурса с именем `generic.xaml`.  Файл `generic.xaml` расположен в той же папке, что и файлы словаря ресурсов, связанные с темами. Хотя `generic.xaml` не соответствует конкретной теме Windows, он по-прежнему является словарем уровня темы.  
  
 [Пример пользовательского элемента управления NumericUpDown с темами и поддержкой автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025) содержит два словаря ресурсов для элемента управления `NumericUpDown`: один — в файле generic.xaml, а второй — в Luna.NormalColor.xaml.  Можно запустить приложение и переключаться между серебристой темой в Windows XP и другой темой, чтобы увидеть разницу между двумя шаблонами элемента управления. (Если вы используете Windows Vista, можно переименовать Luna.NormalColor.xaml в Aero.NormalColor.xaml и переключаться между двумя темами, например между классической и темой по умолчанию для Windows Vista.)  
  
 При переводе <xref:System.Windows.Controls.ControlTemplate> в одном файле словаря ресурсов отдельных тем, необходимо создать статический конструктор для элемента управления и вызвать <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> метод <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
 [!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]  
  
##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Определение и создание ссылок на ключи для ресурсов тем  
 При определении ресурса на уровне элемента можно назначить строку в качестве его ключа и получить доступ к ресурсу через эту строку. При определении ресурсов на уровне темы, необходимо использовать <xref:System.Windows.ComponentResourceKey> как ключ.  В следующем примере определяется ресурс в файле generic.xaml.  
  
 [!code-xaml[ThemeResourcesControlLibrary#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]  
  
 Следующий пример ссылается на ресурс, указав <xref:System.Windows.ComponentResourceKey> как ключ.  
  
 [!code-xaml[ThemeResourcesControlLibrary#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]  
  
##### <a name="specifying-the-location-of-theme-resources"></a>Определение местоположения ресурсов тем  
 Чтобы найти ресурсы для элемента управления, ведущее приложение должно знать, что сборка содержит ресурсы для элемента управления. Это можно сделать, добавив <xref:System.Windows.ThemeInfoAttribute> к сборке, содержащей элемент управления. <xref:System.Windows.ThemeInfoAttribute> Имеет <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> свойство, которое указывает местоположение универсальных ресурсов и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> свойство, определяющее расположение тематических ресурсов.  
  
 В следующем примере задается <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> свойства <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, чтобы указать, что универсальные и отдельные ресурсы находятся в той же сборке, что и элемент управления.  
  
 [!code-csharp[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
 [!code-vb[CustomControlNumericUpDown#ThemesSection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]  
  
## <a name="see-also"></a>См. также  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)
