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
ms.openlocfilehash: fba640ab71459407bfc7a62908021e509346c363
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197361"
---
# <a name="control-authoring-overview"></a>Общие сведения о разработке элементов управления

Расширяемость модели элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] значительно уменьшает необходимость создания новых элементов управления. Однако в некоторых случаях может потребоваться создать пользовательский элемент управления. В этом разделе обсуждаются функции, которые уменьшают необходимость создания пользовательских элементов управления, а также различные модели создания элементов управления в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Также здесь демонстрируется создание нового элемента управления.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Альтернативы написанию нового элемента управления

Исторически сложилось, что если нужно настроить вид существующего элемента управления, то ограничиваются изменением его стандартных свойств, таких как цвет фона, ширина границы и размер шрифта. Если необходимо расширить внешний вид или поведение элемента управления за пределы этих предопределенных параметров, то необходимо создать новый элемент управления, как правило, путем наследования от существующего элемента управления и переопределения метода, ответственного за отрисовку элемента управления.  Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет настраивать существующие элементы управления с помощью модели форматированного содержимого, стилей, шаблонов и триггеров. Ниже представлены примеры использования этих функций для создания настраиваемых и согласованных функциональных возможностей без необходимости создания нового элемента управления.

- **Форматированное содержимое.** Многие стандартные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают форматированное содержимое. Например, свойство Content объекта <xref:System.Windows.Controls.Button> имеет тип <xref:System.Object>, поэтому теоретически все может отображаться на <xref:System.Windows.Controls.Button>.  Чтобы кнопка отображала изображение и текст, можно добавить изображение и <xref:System.Windows.Controls.TextBlock> в <xref:System.Windows.Controls.StackPanel> и назначить <xref:System.Windows.Controls.StackPanel> свойству <xref:System.Windows.Controls.ContentControl.Content%2A>. Поскольку элементы управления могут отображать визуальные элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и произвольные данные, это уменьшает необходимость создания нового элемента управления или изменения существующего для поддержки сложной визуализации. Дополнительные сведения о модели содержимого для <xref:System.Windows.Controls.Button> и других моделей содержимого в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]см. в разделе [модель содержимого WPF](wpf-content-model.md).

- **Стили.** <xref:System.Windows.Style> — это коллекция значений, представляющих свойства элемента управления. С помощью стилей можно создать повторно используемое представление нужного внешнего вида и поведения элемента управления без написания нового элемента управления. Например, предположим, что все элементы управления <xref:System.Windows.Controls.TextBlock> должны иметь красный, Arial Font с размером шрифта 14. Можно создать стиль как ресурс и задать соответствующие свойства. Затем каждый <xref:System.Windows.Controls.TextBlock>, добавляемый в приложение, будет иметь одинаковый внешний вид.

- **Шаблоны данных.** <xref:System.Windows.DataTemplate> позволяет настроить отображение данных в элементе управления. Например, <xref:System.Windows.DataTemplate> можно использовать для указания способа отображения данных в <xref:System.Windows.Controls.ListBox>.  Пример см. в разделе [Общие сведения о шаблонах данных](../data/data-templating-overview.md).  В дополнение к настройке внешнего вида данных <xref:System.Windows.DataTemplate> может включать элементы пользовательского интерфейса, что обеспечивает большую гибкость в пользовательских интерфейсах.  Например, с помощью <xref:System.Windows.DataTemplate>можно создать <xref:System.Windows.Controls.ComboBox>, в котором каждый элемент содержит флажок.

- **Шаблоны элементов управления.** Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] используют <xref:System.Windows.Controls.ControlTemplate> для определения структуры и внешнего вида элемента управления, который отделяет внешний вид элемента управления от функциональных возможностей элемента управления. Можно радикально изменить внешний вид элемента управления, переопределяя его <xref:System.Windows.Controls.ControlTemplate>.  Предположим, что нужен элемент управления, который выглядит как светофор. Этот элемент управления имеет простой пользовательский интерфейс и функциональные возможности.  Элемент управления состоит из трех кругов, из которых одновременно загорается только один. После некоторого отражения можно подумать, что <xref:System.Windows.Controls.RadioButton> предлагает функции только одного выбранного элемента, но внешний вид по умолчанию <xref:System.Windows.Controls.RadioButton> ничего не выглядит как освещение на светофоре.  Поскольку <xref:System.Windows.Controls.RadioButton> использует шаблон элемента управления для определения его внешнего вида, легко Переопределите <xref:System.Windows.Controls.ControlTemplate> в соответствии с требованиями элемента управления и используйте переключатели для создания светофора.

  > [!NOTE]
  > Хотя <xref:System.Windows.Controls.RadioButton> может использовать <xref:System.Windows.DataTemplate>, в этом примере недостаточно <xref:System.Windows.DataTemplate>.  <xref:System.Windows.DataTemplate> определяет внешний вид содержимого элемента управления. В случае <xref:System.Windows.Controls.RadioButton>содержимое отображается справа от окружности, которое указывает, выбран ли <xref:System.Windows.Controls.RadioButton>.  В примере светофора переключатель должен быть тем кругом, который может "загораться". Так как требование внешнего вида для светофора отличается от стандартного вида <xref:System.Windows.Controls.RadioButton>, необходимо переопределить <xref:System.Windows.Controls.ControlTemplate>.  В целом <xref:System.Windows.DataTemplate> используется для определения содержимого (или данных) элемента управления, а <xref:System.Windows.Controls.ControlTemplate> используется для определения структуры элемента управления.

- **Триггеры.** <xref:System.Windows.Trigger> позволяет динамически изменять внешний вид и поведение элемента управления без создания нового элемента управления. Например, предположим, что в приложении имеется несколько элементов управления <xref:System.Windows.Controls.ListBox> и при их выборе требуется, чтобы элементы в каждой <xref:System.Windows.Controls.ListBox> были полужирным и красным. Первым порывом может быть создание класса, который наследует от <xref:System.Windows.Controls.ListBox> и переопределяет метод <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A>, чтобы изменить внешний вид выбранного элемента, но лучшим подходом является добавление триггера к стилю <xref:System.Windows.Controls.ListBoxItem>, который изменяет внешний вид выбранного элемента. . Триггер позволяет изменять значения свойств или выполнять действия в зависимости от значения свойства. <xref:System.Windows.EventTrigger> позволяет выполнять действия при возникновении события.

Дополнительные сведения о стилях, шаблонах и триггерах см. в разделе [Использование стилей и шаблонов](styling-and-templating.md).

В целом, если элемент управления отражает функциональность существующего элемента управления, но должен выглядеть по-другому, сначала следует рассмотреть возможность использования какого-либо из методов, описанных в этом разделе, для изменения внешнего вида существующего элемента.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Модели для создания элементов управления

Модель форматированного содержимого, стили, шаблоны и триггеры уменьшают необходимость создания новых элементов управления. Тем не менее, если необходимо создать новый элемент управления, важно понимать различные модели создания элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет три общих модели для создания элемента управления, которые имеют различный набор функций и уровень гибкости. Базовыми классами для трех моделей являются <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>и <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Создание производных классов от UserControl

Самым простым способом создания элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является наследование от <xref:System.Windows.Controls.UserControl>. При создании элемента управления, который наследуется от <xref:System.Windows.Controls.UserControl>, вы добавляете в <xref:System.Windows.Controls.UserControl>существующие компоненты, настраиваете компоненты и ссылается на обработчики событий в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Затем можно ссылаться на именованные элементы и определять обработчики событий в коде. Эта модель разработки очень схожа с моделью, используемой для разработки приложений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

При правильном построении <xref:System.Windows.Controls.UserControl> может воспользоваться преимуществами расширенного содержимого, стилей и триггеров. Однако если элемент управления наследуется от <xref:System.Windows.Controls.UserControl>, то пользователи, использующие ваш элемент управления, не смогут использовать <xref:System.Windows.DataTemplate> или <xref:System.Windows.Controls.ControlTemplate> для настройки внешнего вида.  Для создания пользовательского элемента управления, поддерживающего шаблоны, необходимо, чтобы производные от класса <xref:System.Windows.Controls.Control> или одного из его производных классов (кроме <xref:System.Windows.Controls.UserControl>).

#### <a name="benefits-of-deriving-from-usercontrol"></a>Преимущества использования производного класса от UserControl

Рассмотрите возможность наследования от <xref:System.Windows.Controls.UserControl>, если применяются все следующие условия:

- Нужно создать элемент управления аналогично созданию приложения.

- Элемент управления состоит только из существующих компонентов.

- Не нужно поддерживать сложные настройки.

### <a name="deriving-from-control"></a>Создание производного от элемента управления

Наследование от класса <xref:System.Windows.Controls.Control> — это модель, используемая большинством существующих элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. При создании элемента управления, который наследуется от класса <xref:System.Windows.Controls.Control>, его внешний вид определяется с помощью шаблонов. Таким образом, можно отделить рабочую логику от визуального представления. Можно также обеспечить разделение пользовательского интерфейса и логики с помощью команд и привязок вместо событий и избегать ссылок на элементы в <xref:System.Windows.Controls.ControlTemplate>, когда это возможно.  Если пользовательский интерфейс и логика элемента управления правильно привязаны, пользователь элемента управления может переопределить <xref:System.Windows.Controls.ControlTemplate> элемента управления, чтобы настроить его внешний вид. Несмотря на то, что создание пользовательского <xref:System.Windows.Controls.Control> не так просто, как создание <xref:System.Windows.Controls.UserControl>, настраиваемая <xref:System.Windows.Controls.Control> обеспечивает наибольшую гибкость.

#### <a name="benefits-of-deriving-from-control"></a>Преимущества использования производного от элемента управления

Рассмотрите возможность наследования от <xref:System.Windows.Controls.Control> вместо использования класса <xref:System.Windows.Controls.UserControl>, если применяется одно из следующих условий:

- Внешний вид элемента управления должен быть настраиваемым с помощью <xref:System.Windows.Controls.ControlTemplate>.

- Элемент управления должен поддерживать различные темы.

### <a name="deriving-from-frameworkelement"></a>Создание производного от FrameworkElement

Элементы управления, производные от <xref:System.Windows.Controls.UserControl> или <xref:System.Windows.Controls.Control>, зависят от составления существующих элементов. Во многих сценариях это приемлемое решение, поскольку любой объект, наследующий от <xref:System.Windows.FrameworkElement>, может находиться в <xref:System.Windows.Controls.ControlTemplate>. Однако бывают случаи, когда для внешнего вида элемента управления требуется больше, чем функциональность простой композиции элементов. В этих сценариях необходимо выбрать компонент на <xref:System.Windows.FrameworkElement>.

Существует два стандартных метода создания компонентов на основе <xref:System.Windows.FrameworkElement>: прямая отрисовка и настраиваемая композиция элементов. Прямая визуализация включает переопределение метода <xref:System.Windows.UIElement.OnRender%2A> <xref:System.Windows.FrameworkElement> и предоставление операций <xref:System.Windows.Media.DrawingContext>, которые явно определяют визуальные элементы компонента. Это метод, используемый <xref:System.Windows.Controls.Image> и <xref:System.Windows.Controls.Border>. В состав настраиваемого элемента входит использование объектов типа <xref:System.Windows.Media.Visual> для составления внешнего вида компонента. Например, см. раздел [Использование объектов DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track> является примером элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], использующего настраиваемую композицию элементов. Можно также комбинировать прямую отрисовку и пользовательскую композицию элемента в одном элементе управления.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Преимущества использования производного от FrameworkElement

Рассмотрите возможность наследования от <xref:System.Windows.FrameworkElement> при любом из следующих условий:

- Требуется точный контроль над внешним видом элемента управления помимо того, который обеспечивается простой композицией элемента.

- Необходимо определить внешний вид элемента управления путем определения собственной логики отрисовки.

- Необходимо составить существующие элементы нестандартными способами, которые выходят за рамки того, что возможно с <xref:System.Windows.Controls.UserControl> и <xref:System.Windows.Controls.Control>.

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

- Определите идентификатор <xref:System.Windows.DependencyProperty> с именем `ValueProperty` как поле `public` `static` `readonly`.

- Зарегистрируйте имя свойства в системе свойств, вызвав <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>, чтобы указать следующее:

  - Имя свойства.

  - Тип свойства.

  - Тип, к которому принадлежит это свойство.

  - Метаданные для свойства. Метаданные содержат значение свойства по умолчанию, <xref:System.Windows.CoerceValueCallback> и <xref:System.Windows.PropertyChangedCallback>.

- Определите свойство оболочки CLR с именем `Value`, которое совпадает с именем, используемым для регистрации свойства зависимостей, путем реализации методов доступа `get` и `set` свойства. Обратите внимание, что методы доступа `get` и `set` вызывают только <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> соответственно. Рекомендуется, чтобы методы доступа свойств зависимостей не содержали дополнительной логики, так как клиенты и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] могут обходить методы доступа, а также вызывать <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> напрямую. Например, если свойство привязано к источнику данных, то метод доступа `set` свойства не вызывается.  Вместо того, чтобы добавлять дополнительную логику в методы доступа get и Set, используйте делегаты <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.CoerceValueCallback>и <xref:System.Windows.PropertyChangedCallback> для ответа или проверки значения при его изменении.  Дополнительные сведения об этих обратных вызовах см. в разделе [Проверка и обратные вызовы свойства зависимостей](../advanced/dependency-property-callbacks-and-validation.md).

- Определите метод для <xref:System.Windows.CoerceValueCallback> с именем `CoerceValue`. `CoerceValue` гарантирует, что `Value` больше или равно `MinValue` и меньше или равно `MaxValue`.

- Определите метод для <xref:System.Windows.PropertyChangedCallback>с именем `OnValueChanged`. `OnValueChanged` создает объект <xref:System.Windows.RoutedPropertyChangedEventArgs%601> и готовится к вызову `ValueChanged` перенаправленного события. Перенаправляемые события рассматриваются в следующем разделе.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Использование перенаправляемых событий

Так же как свойства зависимостей расширяют понятие свойств среды CLR с дополнительными функциональными возможностями, перенаправленные события расширяют понятие стандартных событий CLR. При создании нового элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рекомендуется также реализовывать событие как перенаправляемое, так как такие события поддерживают следующее поведение:

- События могут обрабатываться в родительском элементе нескольких элементов управления. Если событие является событием восходящей маршрутизации, то один родительский элемент в дереве элементов может подписаться на это событие. Разработчики приложений могут использовать один обработчик для реагирования на событие нескольких элементов управления. Например, если элемент управления является частью каждого элемента в <xref:System.Windows.Controls.ListBox> (поскольку он включен в <xref:System.Windows.DataTemplate>), разработчик приложения может определить обработчик событий для события элемента управления в <xref:System.Windows.Controls.ListBox>. Обработчик событий вызывается при возникновении события в любом элементе управления.

- Перенаправленные события можно использовать в <xref:System.Windows.EventSetter>, что позволяет разработчикам приложений указывать обработчик события в стиле.

- Перенаправленные события можно использовать в <xref:System.Windows.EventTrigger>, что удобно для анимации свойств с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md).

Следующий пример определяет перенаправляемое событие:

- Определите идентификатор <xref:System.Windows.RoutedEvent> с именем `ValueChangedEvent` как поле `public` `static` `readonly`.

- Зарегистрируйте перенаправленное событие, вызвав метод <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType>. В примере указываются следующие сведения при вызове <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>.

  - Имя события `ValueChanged`.

  - Стратегия маршрутизации <xref:System.Windows.RoutingStrategy.Bubble>, что означает, что обработчик событий в источнике (объект, вызывающий событие) вызывается первым, а затем обработчики событий в родительских элементах источника вызываются в случае успеха, начиная с обработчика событий в ближайшем родительский элемент.

  - Тип обработчика событий <xref:System.Windows.RoutedPropertyChangedEventHandler%601>, созданный с типом <xref:System.Decimal>.

  - Тип — владелец события — `NumericUpDown`.

- Объявите общее событие с именем `ValueChanged`, которое включает объявления метода доступа к событию. В примере вызывается <xref:System.Windows.UIElement.AddHandler%2A> в объявлении метода доступа `add` и <xref:System.Windows.UIElement.RemoveHandler%2A> в объявлении метода доступа `remove` для использования [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] служб событий.

- Создайте защищенный виртуальный метод с именем `OnValueChanged`, вызывающий событие `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Дополнительные сведения см. в разделах [Общие сведения о перенаправляемых событиях](../advanced/routed-events-overview.md) и [Создание пользовательских перенаправляемых событий](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Использование привязки

Для отделения пользовательского интерфейса от логики элемента управления можно использовать привязку данных. Это особенно важно, если вы определяете внешний вид элемента управления с помощью <xref:System.Windows.Controls.ControlTemplate>. При использовании привязки данных можно избавиться от необходимости ссылаться на определенные части пользовательского интерфейса из кода. Рекомендуется избегать ссылок на элементы, находящихся в <xref:System.Windows.Controls.ControlTemplate>, так как когда код ссылается на элементы, находящихся в <xref:System.Windows.Controls.ControlTemplate> и <xref:System.Windows.Controls.ControlTemplate> изменяется, элемент, на который указывает ссылка, должен быть включен в новый <xref:System.Windows.Controls.ControlTemplate>.

В следующем примере выполняется обновление <xref:System.Windows.Controls.TextBlock> элемента управления `NumericUpDown`, присвоение ему имени и ссылки на текстовое поле по имени в коде.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Следующий пример использует привязку для достижения такого же результата.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).

### <a name="design-for-designers"></a>Разработка для конструкторов

Чтобы получить поддержку пользовательских элементов управления WPF в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] (например, редактирование свойства с помощью окна "Свойства"), следуйте приведенным ниже рекомендациям.  Дополнительные сведения о разработке для [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]см. в разделе [Разработка XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Свойства зависимостей

Не забудьте реализовать `get` CLR и методы доступа `set`, как описано выше, в разделе "использование свойств зависимостей". Конструкторы могут использовать программы-оболочки для обнаружения свойства зависимостей, но им, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и клиентам элемента управления, не требуется вызывать методы доступа при получении или настройке свойства.

#### <a name="attached-properties"></a>Вложенные свойства

При реализации вложенных свойств в пользовательских элементах управления учитывайте следующие рекомендации:

- Иметь `public` `static` `readonly` <xref:System.Windows.DependencyProperty> форме *PropertyName*`Property`, которая была создана с помощью метода <xref:System.Windows.DependencyProperty.RegisterAttached%2A>. Имя свойства, которое передается в <xref:System.Windows.DependencyProperty.RegisterAttached%2A>, должно соответствовать *PropertyName*.

- Реализуйте пару методов CLR `public` `static` с именем `Set`*PropertyName* и `Get`*PropertyName*. Оба метода должны принимать класс, производный от <xref:System.Windows.DependencyProperty> в качестве первого аргумента. Метод `Set`*PropertyName* также принимает аргумент, тип которого соответствует зарегистрированному типу данных для свойства. Метод `Get`*PropertyName* должен возвращать значение такого же типа. Если метод `Set` *PropertyName* отсутствует, свойство отмечается как "только для чтения".

- `Set` *PropertyName* и `Get`*PropertyName* должны напрямую маршрутизироваться к методам <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> в целевом объекте зависимости соответственно. Разработчики могут получить доступ к вложенному свойству, вызвав программу-оболочку метода или с помощью прямого вызова целевого объекта зависимостей.

Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Определение и использование общих ресурсов

Можно включить элемент управления в ту же сборку, что и приложение, или упаковать его в отдельную сборку, которая может использоваться в нескольких приложениях. В большинстве случаев сведения, рассматриваемые в данном разделе, применяются независимо от используемого метода.  Однако есть одно отличие, о котором следует упомянуть.  При помещении элемента управления в ту же сборку, что и приложение, можно добавить глобальные ресурсы в файл App.xaml. Но сборка, содержащая только элементы управления, не имеет связанного с ней объекта <xref:System.Windows.Application>, поэтому файл App. XAML недоступен.

Приложение выполняет поиск ресурса на трех уровнях в следующем порядке:

1. Уровень элемента.

   Система начинает с элемента, который ссылается на ресурс, а затем ищет ресурсы логического родительского элемента и так далее, пока не будет достигнут корневой элемент.

2. Уровень приложения.

   Ресурсы, определяемые объектом <xref:System.Windows.Application>.

3. Уровень темы.

   Словари уровня темы хранятся в подпапке "Темы".  Файлы в папке "Темы" соответствуют темам.  Например, могут присутствовать файлы Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml и т. д.  Также может присутствовать файл с именем generic.xaml.  Когда система ищет ресурс на уровне темы, она сначала ищет его в файле конкретной темы, а затем в файле generic.xaml.

Если элемент управления находится в сборке отдельно от приложения, глобальные ресурсы необходимо поместить на уровень элемента или на уровень темы. Оба метода имеют свои преимущества.

#### <a name="defining-resources-at-the-element-level"></a>Определение ресурсов на уровне элемента

Общие ресурсы на уровне элемента можно определить путем создания пользовательского словаря ресурсов и его объединения со словарем ресурсов элемента управления.  При использовании этого метода можно присвоить файлу ресурсов любое имя и его можно поместить в одну папку с элементами управления. Ресурсы на уровне элемента также могут использовать простые строки как ключи. В следующем примере создается файл ресурсов <xref:System.Windows.Media.LinearGradientBrush> с именем Dictionary1. XAML.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

После определения словаря необходимо его объединить со словарем ресурсов элемента управления.  Это можно сделать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода.

Следующий пример объединяет словарь ресурса с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Недостатком этого подхода является то, что объект <xref:System.Windows.ResourceDictionary> создается каждый раз при ссылке на него.  Например, если в библиотеке имеется 10 пользовательских элементов управления и объединены словари общих ресурсов для каждого элемента управления с помощью XAML, то создаются 10 идентичных <xref:System.Windows.ResourceDictionary> объектов.  Это можно избежать, создав статический класс, который объединяет ресурсы в коде и возвращает результирующий <xref:System.Windows.ResourceDictionary>.

В следующем примере создается класс, который возвращает общий <xref:System.Windows.ResourceDictionary>.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

В следующем примере общий ресурс объединяется с ресурсами пользовательского элемента управления в конструкторе элемента управления, прежде чем он вызывает `InitializeComponent`.  Поскольку `SharedDictionaryManager.SharedDictionary` является статическим свойством, <xref:System.Windows.ResourceDictionary> создается только один раз. Поскольку словарь ресурсов был объединен до вызова `InitializeComponent`, ресурсы доступны для элемента управления в его файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Определение ресурсов на уровне темы

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать ресурсы для разных тем Windows.  Как разработчик элемента управления, вы можете определить ресурс для определенной темы, чтобы изменить внешний вид элемента управления в зависимости от того, какая тема используется. Например, внешний вид <xref:System.Windows.Controls.Button> в классической теме Windows (тема по умолчанию для Windows 2000) отличается от <xref:System.Windows.Controls.Button> в теме Windows Luna (тема по умолчанию для Windows XP), так как <xref:System.Windows.Controls.Button> использует разные <xref:System.Windows.Controls.ControlTemplate> для каждой темы.

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

В [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) примере [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) пользовательского элемента управления NumericUpDown с темой и поддержкой автоматизации пользовательского интерфейса содержатся два словаря ресурсов для элемента управления `NumericUpDown`: один — в Generic. XAML, а другой — в Luna. NormalColor. XAML. 

При помещении <xref:System.Windows.Controls.ControlTemplate> в любой из файлов словаря ресурсов для конкретной темы необходимо создать статический конструктор для элемента управления и вызвать метод <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> в <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, как показано в следующем примере.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Определение и создание ссылок на ключи для ресурсов тем

При определении ресурса на уровне элемента можно назначить строку в качестве его ключа и получить доступ к ресурсу через эту строку. При определении ресурса на уровне темы необходимо использовать <xref:System.Windows.ComponentResourceKey> в качестве ключа.  В следующем примере определяется ресурс в файле generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

Следующий пример ссылается на ресурс, указывая <xref:System.Windows.ComponentResourceKey> в качестве ключа.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Определение местоположения ресурсов тем

Чтобы найти ресурсы для элемента управления, ведущее приложение должно знать, что сборка содержит ресурсы для элемента управления. Это можно сделать, добавив <xref:System.Windows.ThemeInfoAttribute> в сборку, содержащую элемент управления. <xref:System.Windows.ThemeInfoAttribute> имеет свойство <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A>, которое указывает расположение универсальных ресурсов, и свойство <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A>, указывающее расположение ресурсов, зависящих от темы.

В следующем примере свойства <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> задаются для <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>, чтобы указать, что универсальные и относящиеся к теме ресурсы находятся в той же сборке, что и элемент управления.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>См. также

- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [URI типа "pack" в WPF](../app-development/pack-uris-in-wpf.md)
- [Настройка элементов управления](control-customization.md)
