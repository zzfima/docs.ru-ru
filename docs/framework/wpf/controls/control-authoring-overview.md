---
title: Общие сведения о разработке элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], authoring overview
- authoring overview for controls [WPF]
ms.assetid: 3d864748-cff0-4e63-9b23-d8e5a635b28f
ms.openlocfilehash: d5dd2d962c554b860fb6f68110945d56c4ee03ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401031"
---
# <a name="control-authoring-overview"></a>Общие сведения о разработке элементов управления

Расширяемость модели элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] значительно уменьшает необходимость создания новых элементов управления. Однако в некоторых случаях может потребоваться создать пользовательский элемент управления. В этом разделе обсуждаются функции, которые уменьшают необходимость создания пользовательских элементов управления, а также различные модели создания элементов управления в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Также здесь демонстрируется создание нового элемента управления.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Альтернативы написанию нового элемента управления

Исторически сложилось, что если нужно настроить вид существующего элемента управления, то ограничиваются изменением его стандартных свойств, таких как цвет фона, ширина границы и размер шрифта. Если необходимо расширить внешний вид или поведение элемента управления за пределы этих предопределенных параметров, то необходимо создать новый элемент управления, как правило, путем наследования от существующего элемента управления и переопределения метода, ответственного за отрисовку элемента управления.  Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет настраивать существующие элементы управления с помощью модели форматированного содержимого, стилей, шаблонов и триггеров. Ниже представлены примеры использования этих функций для создания настраиваемых и согласованных функциональных возможностей без необходимости создания нового элемента управления.

- **Форматированное содержимое.** Многие стандартные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают форматированное содержимое. Например, свойство содержимого <xref:System.Windows.Controls.Button> a <xref:System.Object>тип, поэтому теоретически все может <xref:System.Windows.Controls.Button>отображаться на .  Чтобы кнопка отобразила изображение и текст, <xref:System.Windows.Controls.TextBlock> можно <xref:System.Windows.Controls.StackPanel> добавить изображение <xref:System.Windows.Controls.StackPanel> и <xref:System.Windows.Controls.ContentControl.Content%2A> а и назначить свойство. Поскольку элементы управления могут отображать визуальные элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и произвольные данные, это уменьшает необходимость создания нового элемента управления или изменения существующего для поддержки сложной визуализации. Для получения дополнительной информации <xref:System.Windows.Controls.Button> о модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]контента для и других моделей контента в , см. [WPF Content Model](wpf-content-model.md)

- **Стили.** A <xref:System.Windows.Style> — это набор значений, представляющих свойства для элемента управления. С помощью стилей можно создать повторно используемое представление нужного внешнего вида и поведения элемента управления без написания нового элемента управления. Например, предположим, что <xref:System.Windows.Controls.TextBlock> вы хотите, чтобы все элементы управления имели красный шрифт Arial с размером шрифта 14. Можно создать стиль как ресурс и задать соответствующие свойства. После <xref:System.Windows.Controls.TextBlock> этого каждое которое вы добавляете к вашему применению будет иметь такой же возникновение.

- **Шаблоны данных.** A <xref:System.Windows.DataTemplate> позволяет настроить способ отображения данных на элементе управления. Например, <xref:System.Windows.DataTemplate> можно использовать a для указания того, <xref:System.Windows.Controls.ListBox>как данные отображаются в .  Пример см. в разделе [Общие сведения о шаблонах данных](../data/data-templating-overview.md).  В дополнение к настройке внешнего <xref:System.Windows.DataTemplate> вида данных, может включать элементы пользовательского или, который дает вам большую гибкость в пользовательских пользовательских пользовательских пользовательских ими.  Например, с <xref:System.Windows.DataTemplate>помощью , <xref:System.Windows.Controls.ComboBox> вы можете создать, в котором каждый элемент содержит флажок.

- **Шаблоны управления.** Многие элементы <xref:System.Windows.Controls.ControlTemplate> управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используются для определения структуры и внешнего вида элемента управления, что отделяет внешний вид элемента управления от функциональности элемента управления. Вы можете кардинально изменить внешний вид элемента управления, переопределив его. <xref:System.Windows.Controls.ControlTemplate>  Предположим, что нужен элемент управления, который выглядит как светофор. Этот элемент управления имеет простой пользовательский интерфейс и функциональные возможности.  Элемент управления состоит из трех кругов, из которых одновременно загорается только один. После некоторого размышления, <xref:System.Windows.Controls.RadioButton> вы можете понять, что предлагает функциональность только один выбирается в то время, но по умолчанию внешний вид <xref:System.Windows.Controls.RadioButton> выглядит ничего подобного огни на стоп-сигнале.  Поскольку <xref:System.Windows.Controls.RadioButton> шаблон управления использует шаблон управления для определения его <xref:System.Windows.Controls.ControlTemplate> внешнего вида, легко переопределить, чтобы соответствовать требованиям управления, и использовать радио кнопки, чтобы сделать ваш стоп-сигнал.

  > [!NOTE]
  > Хотя <xref:System.Windows.Controls.RadioButton> может <xref:System.Windows.DataTemplate>использовать, <xref:System.Windows.DataTemplate> a не достаточно в этом примере.  Определяет <xref:System.Windows.DataTemplate> внешний вид содержимого элемента управления. В <xref:System.Windows.Controls.RadioButton>случае, содержание все, что появляется справа от круга, <xref:System.Windows.Controls.RadioButton> который указывает, является ли выбран.  В примере светофора переключатель должен быть тем кругом, который может "загораться". Потому что требование внешнего вида для стоп-лайта <xref:System.Windows.Controls.RadioButton>настолько отличается от <xref:System.Windows.Controls.ControlTemplate>внешнего вида по умолчанию, необходимо переопределить .  В целом <xref:System.Windows.DataTemplate> используется для определения содержимого (или данных) <xref:System.Windows.Controls.ControlTemplate> элемента управления, а для определения структуры элемента управления используется.

- **Триггеры.** A <xref:System.Windows.Trigger> позволяет динамически изменять внешний вид и поведение элемента управления без создания нового элемента управления. Например, предположим, <xref:System.Windows.Controls.ListBox> что у вас есть несколько элементов управления в приложении и хотите, чтобы элементы в каждом из них <xref:System.Windows.Controls.ListBox> были смелыми и красными, когда они выбраны. Ваш первый инстинкт может заключаться в <xref:System.Windows.Controls.ListBox> создании класса, который наследует и переопределить <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> метод, чтобы изменить внешний вид выбранного элемента, но лучший подход заключается в том, чтобы добавить триггер в стиль, <xref:System.Windows.Controls.ListBoxItem> который изменяет внешний вид выбранного элемента. Триггер позволяет изменять значения свойств или выполнять действия в зависимости от значения свойства. An <xref:System.Windows.EventTrigger> позволяет выполнять действия в случае события.

Дополнительные сведения о стилях, шаблонах и триггерах см. в разделе [Использование стилей и шаблонов](styling-and-templating.md).

В целом, если элемент управления отражает функциональность существующего элемента управления, но должен выглядеть по-другому, сначала следует рассмотреть возможность использования какого-либо из методов, описанных в этом разделе, для изменения внешнего вида существующего элемента.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Модели для создания элементов управления

Модель форматированного содержимого, стили, шаблоны и триггеры уменьшают необходимость создания новых элементов управления. Тем не менее, если необходимо создать новый элемент управления, важно понимать различные модели создания элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет три общих модели для создания элемента управления, которые имеют различный набор функций и уровень гибкости. Базовые классы для <xref:System.Windows.Controls.UserControl>трех <xref:System.Windows.Controls.Control>моделей, и <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Создание производных классов от UserControl

Самый простой способ создать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] контроль в <xref:System.Windows.Controls.UserControl>том, чтобы извлечь из . При создании элемента управления, <xref:System.Windows.Controls.UserControl>наследуемого из, <xref:System.Windows.Controls.UserControl>вы добавляете существующие компоненты [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]в, назовите компоненты и обработчики событий в. Затем можно ссылаться на именованные элементы и определять обработчики событий в коде. Эта модель разработки очень схожа с моделью, используемой для разработки приложений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

Если построен правильно, <xref:System.Windows.Controls.UserControl> может воспользоваться преимуществами богатого контента, стилей и триггеров. Однако, если ваш <xref:System.Windows.Controls.UserControl>контроль наследует от, люди, которые <xref:System.Windows.DataTemplate> используют <xref:System.Windows.Controls.ControlTemplate> ваш контроль не сможет использовать или настроить его внешний вид.  Необходимо извлечь из <xref:System.Windows.Controls.Control> класса или одного из его производных классов <xref:System.Windows.Controls.UserControl>(кроме) создать пользовательский элемент управления, поддерживающий шаблоны.

#### <a name="benefits-of-deriving-from-usercontrol"></a>Преимущества использования производного класса от UserControl

Рассмотрите возможность <xref:System.Windows.Controls.UserControl> вытекающих из, если все следующие применяются:

- Нужно создать элемент управления аналогично созданию приложения.

- Элемент управления состоит только из существующих компонентов.

- Не нужно поддерживать сложные настройки.

### <a name="deriving-from-control"></a>Создание производного от элемента управления

Выдвижение из <xref:System.Windows.Controls.Control> класса — это модель, используемая большинством существующих [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления. При создании элемента управления, <xref:System.Windows.Controls.Control> наследуетшего из класса, вы определяете его внешний вид с помощью шаблонов. Таким образом, можно отделить рабочую логику от визуального представления. Вы также можете обеспечить разъединение uI и логики, используя команды и привязки вместо событий и избегая ссылок элементов в по <xref:System.Windows.Controls.ControlTemplate> возможности.  Если пользовательский интерфейс и логика управления должным образом отделены, пользователь элемента <xref:System.Windows.Controls.ControlTemplate> управления может переопределить элемент управления, чтобы настроить его внешний вид. Хотя создание <xref:System.Windows.Controls.Control> обычая не так <xref:System.Windows.Controls.UserControl>просто, <xref:System.Windows.Controls.Control> как создание, пользовательский обеспечивает максимальную гибкость.

#### <a name="benefits-of-deriving-from-control"></a>Преимущества использования производного от элемента управления

Рассмотрите возможность <xref:System.Windows.Controls.Control> использования <xref:System.Windows.Controls.UserControl> класса вместо использования класса, если какой-либо из следующих применим:

- Вы хотите, чтобы внешний вид вашего элемента управления, чтобы быть настраиваемым <xref:System.Windows.Controls.ControlTemplate>через .

- Элемент управления должен поддерживать различные темы.

### <a name="deriving-from-frameworkelement"></a>Создание производного от FrameworkElement

Элементы управления, которые вытекают из <xref:System.Windows.Controls.UserControl> существующих элементов или <xref:System.Windows.Controls.Control> полагаются на него. Для многих сценариев это приемлемое решение, поскольку <xref:System.Windows.FrameworkElement> любой <xref:System.Windows.Controls.ControlTemplate>объект, который наследует сядец, может находиться в . Однако бывают случаи, когда для внешнего вида элемента управления требуется больше, чем функциональность простой композиции элементов. Для этих сценариев, <xref:System.Windows.FrameworkElement> основывая компонент на правильный выбор.

Существуют два стандартных <xref:System.Windows.FrameworkElement>метода для компонентов на основе построения: прямая визуализация и пользовательский состав элемента. Прямая визуализация включает <xref:System.Windows.UIElement.OnRender%2A> в <xref:System.Windows.FrameworkElement> себя <xref:System.Windows.Media.DrawingContext> переопределение метода и предоставление операций, которые явно определяют визуальные компоненты. Это метод, <xref:System.Windows.Controls.Image> используемый <xref:System.Windows.Controls.Border>и . Пользовательский состав элементов включает <xref:System.Windows.Media.Visual> в себя использование объектов типа для составления внешнего вида компонента. Например, см. раздел [Использование объектов DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>является примером элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления, в который используется пользовательская композиция элемента. Можно также комбинировать прямую отрисовку и пользовательскую композицию элемента в одном элементе управления.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Преимущества использования производного от FrameworkElement

Рассмотрите возможность <xref:System.Windows.FrameworkElement> выражая, если какой-либо из следующих применяются:

- Требуется точный контроль над внешним видом элемента управления помимо того, который обеспечивается простой композицией элемента.

- Необходимо определить внешний вид элемента управления путем определения собственной логики отрисовки.

- Вы хотите составить существующие элементы в новых <xref:System.Windows.Controls.UserControl> способов, которые выходят за рамки того, что возможно с и <xref:System.Windows.Controls.Control>.

<a name="control_authoring_basics"></a>

## <a name="control-authoring-basics"></a>Основы создания элементов управления

Как обсуждалось выше, одной из наиболее мощных функций [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является возможность выхода за пределы задания базовых свойств элемента управления, чтобы изменить его внешний вид и поведение, но без необходимости создания пользовательского элемента управления. Функции стилей, привязки данных и триггеров предоставляются системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и системой событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В следующих разделах описаны некоторые рекомендации, которым нужно следовать независимо от модели, используемой для создания пользовательского элемента управления. Это необходимо, чтобы пользователи вашего пользовательского элемента управления могли использовать эти функции точно так же, как для элемента управления, входящего в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

### <a name="use-dependency-properties"></a>Использование свойств зависимостей

Если свойство является свойством зависимостей, то можно сделать следующее:

- Установить свойство в стиле.

- Привязать свойство к источнику данных.

- Использовать динамический ресурс в качестве значения свойства.

- Анимировать свойство.

Если свойство элемента управления должно поддерживать подобную функциональность, то следует реализовать его как свойство зависимостей. В следующем примере определяется свойство зависимостей с именем `Value` следующим способом:

- Определите <xref:System.Windows.DependencyProperty> идентификатор, названный `ValueProperty` полем. `public` `static` `readonly`

- Зарегистрируйте имя недвижимости в системе <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>недвижимости, позвонив, чтобы указать следующее:

  - Имя свойства.

  - Тип свойства.

  - Тип, к которому принадлежит это свойство.

  - Метаданные для свойства. Метаданные содержат значение значения по умолчанию свойства, a <xref:System.Windows.CoerceValueCallback> и <xref:System.Windows.PropertyChangedCallback>a .

- Определите свойство обертки CLR названо `Value`, которое является тем же именем, `get` `set` которое используется для регистрации свойства зависимости, путем реализации собственности и аксессуаров. Обратите `get` внимание, `set` что и <xref:System.Windows.DependencyObject.GetValue%2A> аксессуары только вызов и <xref:System.Windows.DependencyObject.SetValue%2A> соответственно. Рекомендуется, чтобы аксессуары свойств зависимости не содержат дополнительной [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] логики, поскольку клиенты <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> могут обходить доступы и вызовы и напрямую. Например, если свойство привязано к источнику данных, то метод доступа `set` свойства не вызывается.  Вместо добавления дополнительной логики в get и <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.CoerceValueCallback>set <xref:System.Windows.PropertyChangedCallback> accessors, используйте , и делегаты, чтобы ответить или проверить значение, когда он изменяется.  Дополнительные сведения об этих обратных вызовах см. в разделе [Проверка и обратные вызовы свойства зависимостей](../advanced/dependency-property-callbacks-and-validation.md).

- Определите метод <xref:System.Windows.CoerceValueCallback> для `CoerceValue`названного . `CoerceValue` гарантирует, что `Value` больше или равно `MinValue` и меньше или равно `MaxValue`.

- Определите метод <xref:System.Windows.PropertyChangedCallback>для `OnValueChanged`, названного . `OnValueChanged`создает <xref:System.Windows.RoutedPropertyChangedEventArgs%601> объект и готовится `ValueChanged` поднять маршрутизированный событие. Перенаправляемые события рассматриваются в следующем разделе.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Использование перенаправляемых событий

Подобно тем, что свойства зависимости расширяют понятие свойств CLR с дополнительной функциональностью, маршрутные события расширяют понятие стандартных событий CLR. При создании нового элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рекомендуется также реализовывать событие как перенаправляемое, так как такие события поддерживают следующее поведение:

- События могут обрабатываться в родительском элементе нескольких элементов управления. Если событие является событием восходящей маршрутизации, то один родительский элемент в дереве элементов может подписаться на это событие. Разработчики приложений могут использовать один обработчик для реагирования на событие нескольких элементов управления. Например, если элемент управления является частью <xref:System.Windows.Controls.ListBox> каждого элемента в <xref:System.Windows.DataTemplate>(поскольку он включен в), разработчик приложения может <xref:System.Windows.Controls.ListBox>определить обработчик событий для события элемента на . Обработчик событий вызывается при возникновении события в любом элементе управления.

- Маршрутные события могут быть <xref:System.Windows.EventSetter>использованы в , что позволяет разработчикам приложений указать обработчик события в стиле.

- Маршрутные события могут быть <xref:System.Windows.EventTrigger>использованы в, который полезен [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]для анимирования свойств с помощью. Для получения дополнительной информации [см.](../graphics-multimedia/animation-overview.md)

Следующий пример определяет перенаправляемое событие:

- Определите <xref:System.Windows.RoutedEvent> идентификатор, названный `ValueChangedEvent` полем. `public` `static` `readonly`

- Зарегистрируйте маршрутное <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> событие, позвонив по методу. В примере указывается следующая информация при вызове: <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>

  - Имя события `ValueChanged`.

  - Стратегия трассировки <xref:System.Windows.RoutingStrategy.Bubble>— это означает, что обработчик события на источнике (объект, поднимающий событие) сначала вызывается, а затем обработчики событий на родительских элементах источника вызываются последовательно, начиная с обработчика событий на ближайшем родительском элементе.

  - Тип обработчика <xref:System.Windows.RoutedPropertyChangedEventHandler%601>событий построен с <xref:System.Decimal> типом.

  - Тип — владелец события — `NumericUpDown`.

- Объявите общее событие с именем `ValueChanged`, которое включает объявления метода доступа к событию. Пример вызывает <xref:System.Windows.UIElement.AddHandler%2A> в `add` декларации <xref:System.Windows.UIElement.RemoveHandler%2A> аксессуаров `remove` и в декларации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] аксессуаров для использования служб событий.

- Создайте защищенный виртуальный метод с именем `OnValueChanged`, вызывающий событие `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Дополнительные сведения см. в разделах [Общие сведения о перенаправляемых событиях](../advanced/routed-events-overview.md) и [Создание пользовательских перенаправляемых событий](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Использование привязки

Для отделения пользовательского интерфейса от логики элемента управления можно использовать привязку данных. Это особенно важно, если вы определяете внешний вид вашего контроля с помощью <xref:System.Windows.Controls.ControlTemplate>. При использовании привязки данных можно избавиться от необходимости ссылаться на определенные части пользовательского интерфейса из кода. Рекомендуется избегать ссылок на элементы, которые <xref:System.Windows.Controls.ControlTemplate> находятся в том, что, <xref:System.Windows.Controls.ControlTemplate> когда <xref:System.Windows.Controls.ControlTemplate> код ссылается на элементы, которые находятся в и изменен, ссылки элемент должен быть включен в новый <xref:System.Windows.Controls.ControlTemplate>.

Следующий пример <xref:System.Windows.Controls.TextBlock> обновляет `NumericUpDown` элемент управления, присваивая ему имя и ссылаясь на текстовый ящик по имени в коде.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Следующий пример использует привязку для достижения такого же результата.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Для получения дополнительной информации [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md)о привязке данных см.

### <a name="design-for-designers"></a>Разработка для конструкторов

Чтобы получить поддержку пользовательских элементов управления WPF в WPF Designer for Visual Studio (например, редактирование недвижимости с помощью окна Properties), следуйте этим рекомендациям.  Для получения дополнительной информации о разработке для WPF Designer, [см. Дизайн XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Свойства зависимостей

Обязательно внедрить CLR `get` и `set` аксессуары, как описано ранее, в "Использование свойств зависимости". Конструкторы могут использовать программы-оболочки для обнаружения свойства зависимостей, но им, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и клиентам элемента управления, не требуется вызывать методы доступа при получении или настройке свойства.

#### <a name="attached-properties"></a>Вложенные свойства

При реализации вложенных свойств в пользовательских элементах управления учитывайте следующие рекомендации:

- `public` `Property` <xref:System.Windows.DependencyProperty.RegisterAttached%2A> Исесть форму *PropertyName,* которая создавалась с помощью метода. `static` `readonly` <xref:System.Windows.DependencyProperty> Имя свойства, которое <xref:System.Windows.DependencyProperty.RegisterAttached%2A> передается, должно соответствовать *PropertyName.*

- Реализуйте пару методов CLR `public` `static` с именем `Set`*PropertyName* и `Get`*PropertyName*. Оба метода должны принять класс, полученный из <xref:System.Windows.DependencyProperty> их первого аргумента. Метод `Set`*PropertyName* также принимает аргумент, тип которого соответствует зарегистрированному типу данных для свойства. Метод `Get`*PropertyName* должен возвращать значение такого же типа. Если метод `Set`*PropertyName* отсутствует, свойство отмечается как "только для чтения".

- `Set`*Name* и `Get` *PropertyName* должны направляться непосредственно к <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A> и методам на объекте целевой зависимости, соответственно. Разработчики могут получить доступ к вложенному свойству, вызвав программу-оболочку метода или с помощью прямого вызова целевого объекта зависимостей.

Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Определение и использование общих ресурсов

Можно включить элемент управления в ту же сборку, что и приложение, или упаковать его в отдельную сборку, которая может использоваться в нескольких приложениях. В большинстве случаев сведения, рассматриваемые в данном разделе, применяются независимо от используемого метода.  Однако есть одно отличие, о котором следует упомянуть.  При помещении элемента управления в ту же сборку, что и приложение, можно добавить глобальные ресурсы в файл App.xaml. Но сборка, содержащая только <xref:System.Windows.Application> элементы управления, не имеет объекта, связанного с ней, поэтому файл App.xaml недоступен.

Приложение выполняет поиск ресурса на трех уровнях в следующем порядке:

1. Уровень элемента.

   Система начинает с элемента, который ссылается на ресурс, а затем ищет ресурсы логического родительского элемента и так далее, пока не будет достигнут корневой элемент.

2. Уровень приложения.

   Ресурсы, <xref:System.Windows.Application> определяемые объектом.

3. Уровень темы.

   Словари уровня темы хранятся в подпапке "Темы".  Файлы в папке "Темы" соответствуют темам.  Например, могут присутствовать файлы Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml и т. д.  Также может присутствовать файл с именем generic.xaml.  Когда система ищет ресурс на уровне темы, она сначала ищет его в файле конкретной темы, а затем в файле generic.xaml.

Если элемент управления находится в сборке отдельно от приложения, глобальные ресурсы необходимо поместить на уровень элемента или на уровень темы. Оба метода имеют свои преимущества.

#### <a name="defining-resources-at-the-element-level"></a>Определение ресурсов на уровне элемента

Общие ресурсы на уровне элемента можно определить путем создания пользовательского словаря ресурсов и его объединения со словарем ресурсов элемента управления.  При использовании этого метода можно присвоить файлу ресурсов любое имя и его можно поместить в одну папку с элементами управления. Ресурсы на уровне элемента также могут использовать простые строки как ключи. В следующем примере создается <xref:System.Windows.Media.LinearGradientBrush> файл ресурсов под названием Dictionary1.xaml.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

После определения словаря необходимо его объединить со словарем ресурсов элемента управления.  Это можно сделать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода.

Следующий пример объединяет словарь ресурса с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Недостатком этого подхода является <xref:System.Windows.ResourceDictionary> то, что объект создается каждый раз, когда вы ссылаетесь на него.  Например, если в библиотеке есть 10 пользовательских элементов управления и объединяются словари общих <xref:System.Windows.ResourceDictionary> ресурсов для каждого элемента управления с помощью XAML, вы создаете 10 одинаковых объектов.  Этого можно избежать, создав статический класс, который объединяет <xref:System.Windows.ResourceDictionary>ресурсы в коде и возвращает полученный.

Следующий пример создает класс, <xref:System.Windows.ResourceDictionary>который возвращает общий .

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

В следующем примере общий ресурс объединяется с ресурсами пользовательского элемента управления в конструкторе элемента управления, прежде чем он вызывает `InitializeComponent`.  Поскольку `SharedDictionaryManager.SharedDictionary` это статическое <xref:System.Windows.ResourceDictionary> свойство, создается только один раз. Поскольку словарь ресурсов был объединен до вызова `InitializeComponent`, ресурсы доступны для элемента управления в его файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Определение ресурсов на уровне темы

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать ресурсы для разных тем Windows.  Как разработчик элемента управления, вы можете определить ресурс для определенной темы, чтобы изменить внешний вид элемента управления в зависимости от того, какая тема используется. Например, появление <xref:System.Windows.Controls.Button> темы Windows Classic (тема по умолчанию для Windows 2000) отличается от темы <xref:System.Windows.Controls.Button> Windows Luna (тема по <xref:System.Windows.Controls.Button> умолчанию <xref:System.Windows.Controls.ControlTemplate> для Windows XP), потому что используется различные для каждой темы.

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

Пользовательский контроль [c'](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) или [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) NumericUpDown с тепозами и `NumericUpDown` образцом поддержки автоматизации пользовательского или прим.

При покладывании в любой <xref:System.Windows.Controls.ControlTemplate> из файлов словаря ресурсов, специфичных для <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> конкретной <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>темы, необходимо создать статический конструктор для управления и вызвать метод на , как показано в следующем примере.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Определение и создание ссылок на ключи для ресурсов тем

При определении ресурса на уровне элемента можно назначить строку в качестве его ключа и получить доступ к ресурсу через эту строку. При определении ресурса на уровне темы <xref:System.Windows.ComponentResourceKey> необходимо использовать ключ.  В следующем примере определяется ресурс в файле generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Следующий пример ссылается на ресурс, указывая в <xref:System.Windows.ComponentResourceKey> качестве ключа.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Определение местоположения ресурсов тем

Чтобы найти ресурсы для элемента управления, ведущее приложение должно знать, что сборка содержит ресурсы для элемента управления. Вы можете достичь этого, добавив в <xref:System.Windows.ThemeInfoAttribute> сборку, содержащую элемент управления. Свойство <xref:System.Windows.ThemeInfoAttribute> <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> имеет свойство, которое определяет расположение общих ресурсов, и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> свойство, которое определяет расположение тематических ресурсов.

В следующем примере приводится <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> свойства, <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>чтобы указать, что общие и тематические ресурсы находятся в той же сборке, что и элемент управления.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>См. также раздел

- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [URI типа "pack" в WPF](../app-development/pack-uris-in-wpf.md)
- [Настройка элементов управления](control-customization.md)
