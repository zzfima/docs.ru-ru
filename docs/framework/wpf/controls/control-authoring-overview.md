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
ms.openlocfilehash: 3ea5519259ba2ee31bfd6bc25f6bedf1f1250799
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401547"
---
# <a name="control-authoring-overview"></a>Общие сведения о разработке элементов управления

Расширяемость модели элементов управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] значительно уменьшает необходимость создания новых элементов управления. Однако в некоторых случаях может потребоваться создать пользовательский элемент управления. В этом разделе обсуждаются функции, которые уменьшают необходимость создания пользовательских элементов управления, а также различные модели создания элементов управления в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Также здесь демонстрируется создание нового элемента управления.

<a name="when_to_write_a_new_control"></a>

## <a name="alternatives-to-writing-a-new-control"></a>Альтернативы написанию нового элемента управления

Исторически сложилось, что если нужно настроить вид существующего элемента управления, то ограничиваются изменением его стандартных свойств, таких как цвет фона, ширина границы и размер шрифта. Если необходимо расширить внешний вид или поведение элемента управления за пределы этих предопределенных параметров, то необходимо создать новый элемент управления, как правило, путем наследования от существующего элемента управления и переопределения метода, ответственного за отрисовку элемента управления.  Кроме того, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет настраивать существующие элементы управления с помощью модели форматированного содержимого, стилей, шаблонов и триггеров. Ниже представлены примеры использования этих функций для создания настраиваемых и согласованных функциональных возможностей без необходимости создания нового элемента управления.

- **Форматированное содержимое.** Многие стандартные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживают форматированное содержимое. Например, свойство Content объекта <xref:System.Windows.Controls.Button> имеет тип <xref:System.Object>, поэтому теоретически все <xref:System.Windows.Controls.Button>может быть отображено в.  Чтобы кнопка <xref:System.Windows.Controls.TextBlock> отображала изображение и текст, можно добавить изображение и <xref:System.Windows.Controls.StackPanel> в <xref:System.Windows.Controls.ContentControl.Content%2A> и присвоить <xref:System.Windows.Controls.StackPanel> свойству значение. Поскольку элементы управления могут отображать визуальные элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и произвольные данные, это уменьшает необходимость создания нового элемента управления или изменения существующего для поддержки сложной визуализации. Дополнительные сведения о модели содержимого для <xref:System.Windows.Controls.Button> и других моделях содержимого в см. в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]разделе [модель содержимого WPF](wpf-content-model.md).

- **Стили.** <xref:System.Windows.Style> Представляет собой коллекцию значений, представляющих свойства элемента управления. С помощью стилей можно создать повторно используемое представление нужного внешнего вида и поведения элемента управления без написания нового элемента управления. Например, предположим, что все <xref:System.Windows.Controls.TextBlock> элементы управления должны иметь красный шрифт Arial с размером шрифта 14. Можно создать стиль как ресурс и задать соответствующие свойства. Затем каждое <xref:System.Windows.Controls.TextBlock> Добавление в приложение будет иметь одинаковый внешний вид.

- **Шаблоны данных.** А <xref:System.Windows.DataTemplate> позволяет настраивать способ отображения данных в элементе управления. Например, <xref:System.Windows.DataTemplate> можно использовать для указания способа отображения данных <xref:System.Windows.Controls.ListBox>в.  Пример см. в разделе [Общие сведения о шаблонах данных](../data/data-templating-overview.md).  Помимо настройки внешнего вида данных, <xref:System.Windows.DataTemplate> может включать элементы пользовательского интерфейса, что обеспечивает большую гибкость в пользовательских интерфейсах.  Например, с помощью <xref:System.Windows.DataTemplate>можно <xref:System.Windows.Controls.ComboBox> создать, в котором каждый элемент содержит флажок.

- **Шаблоны элементов управления.** Многие элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в <xref:System.Windows.Controls.ControlTemplate> используют для определения структуры и внешнего вида элемента управления, которые разделяют внешний вид элемента управления от функциональных возможностей элемента управления. Можно радикально изменить внешний вид элемента управления, переопределяя его <xref:System.Windows.Controls.ControlTemplate>.  Предположим, что нужен элемент управления, который выглядит как светофор. Этот элемент управления имеет простой пользовательский интерфейс и функциональные возможности.  Элемент управления состоит из трех кругов, из которых одновременно загорается только один. После какого- <xref:System.Windows.Controls.RadioButton> либо отражения можно подумать, что компонент предоставляет функции только одного выбранного за раз, но внешний вид <xref:System.Windows.Controls.RadioButton> по умолчанию не выглядит ничего вроде огней на светофоре.  Поскольку компонент использует шаблон элемента управления для определения его внешнего вида, легко <xref:System.Windows.Controls.ControlTemplate> переопределить в соответствии с требованиями элемента управления и использовать переключатели для создания светофора. <xref:System.Windows.Controls.RadioButton>

  > [!NOTE]
  > Несмотря на то <xref:System.Windows.DataTemplate>, что <xref:System.Windows.DataTemplate> может использовать, в этом примере недостаточно. <xref:System.Windows.Controls.RadioButton>  <xref:System.Windows.DataTemplate> Определяет внешний вид содержимого элемента управления. В случае <xref:System.Windows.Controls.RadioButton>, содержимое отображается справа от окружности, которое указывает, выбран ли объект <xref:System.Windows.Controls.RadioButton> .  В примере светофора переключатель должен быть тем кругом, который может "загораться". Так как требование внешнего вида для светофора отличается от внешнего вида <xref:System.Windows.Controls.RadioButton>по умолчанию, необходимо <xref:System.Windows.Controls.ControlTemplate>переопределить.  В целом, <xref:System.Windows.DataTemplate> используется для определения содержимого (или данных) элемента управления, <xref:System.Windows.Controls.ControlTemplate> а используется для определения структуры элемента управления.

- **Триггеры.** <xref:System.Windows.Trigger> Позволяет динамически изменять внешний вид и поведение элемента управления без создания нового элемента управления. Например, предположим, что в приложении <xref:System.Windows.Controls.ListBox> есть несколько элементов управления и при их выборе требуется, <xref:System.Windows.Controls.ListBox> чтобы элементы в каждом из них были полужирным и красным. Первым порывом может быть создание класса, который наследует от <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.Primitives.Selector.OnSelectionChanged%2A> переопределяет метод для изменения внешнего вида выбранного элемента, но лучшим подходом является добавление триггера <xref:System.Windows.Controls.ListBoxItem> к стилю, который изменяет внешний вид выбранный элемент. Триггер позволяет изменять значения свойств или выполнять действия в зависимости от значения свойства. <xref:System.Windows.EventTrigger> Позволяет выполнять действия при возникновении события.

Дополнительные сведения о стилях, шаблонах и триггерах см. в разделе [Использование стилей и шаблонов](styling-and-templating.md).

В целом, если элемент управления отражает функциональность существующего элемента управления, но должен выглядеть по-другому, сначала следует рассмотреть возможность использования какого-либо из методов, описанных в этом разделе, для изменения внешнего вида существующего элемента.

<a name="models_for_control_authoring"></a>

## <a name="models-for-control-authoring"></a>Модели для создания элементов управления

Модель форматированного содержимого, стили, шаблоны и триггеры уменьшают необходимость создания новых элементов управления. Тем не менее, если необходимо создать новый элемент управления, важно понимать различные модели создания элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет три общих модели для создания элемента управления, которые имеют различный набор функций и уровень гибкости. Базовыми классами для трех моделей являются <xref:System.Windows.Controls.UserControl>, <xref:System.Windows.Controls.Control>и <xref:System.Windows.FrameworkElement>.

### <a name="deriving-from-usercontrol"></a>Создание производных классов от UserControl

Самый простой способ создать элемент управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] заключается в наследовании от. <xref:System.Windows.Controls.UserControl> При построении элемента управления, наследуемого <xref:System.Windows.Controls.UserControl>от, добавляются существующие компоненты <xref:System.Windows.Controls.UserControl>, имена компонентов и ссылки на обработчики событий в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Затем можно ссылаться на именованные элементы и определять обработчики событий в коде. Эта модель разработки очень схожа с моделью, используемой для разработки приложений в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

При правильном <xref:System.Windows.Controls.UserControl> построении может воспользоваться преимуществами расширенного содержимого, стилей и триггеров. Однако если элемент управления наследуется от <xref:System.Windows.Controls.UserControl>, то пользователи, использующие ваш элемент управления, не смогут <xref:System.Windows.DataTemplate> использовать или <xref:System.Windows.Controls.ControlTemplate> для настройки внешнего вида.  Для создания пользовательского элемента управления, поддерживающего <xref:System.Windows.Controls.Control> шаблоны, необходимо получить от класса или одного из его <xref:System.Windows.Controls.UserControl>производных классов (кроме).

#### <a name="benefits-of-deriving-from-usercontrol"></a>Преимущества использования производного класса от UserControl

Рассмотрите возможность наследования от <xref:System.Windows.Controls.UserControl> , если применяются все следующие условия.

- Нужно создать элемент управления аналогично созданию приложения.

- Элемент управления состоит только из существующих компонентов.

- Не нужно поддерживать сложные настройки.

### <a name="deriving-from-control"></a>Создание производного от элемента управления

Наследование от <xref:System.Windows.Controls.Control> класса — это модель, используемая большинством существующих [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов управления. При создании элемента управления, который наследуется от <xref:System.Windows.Controls.Control> класса, его внешний вид определяется с помощью шаблонов. Таким образом, можно отделить рабочую логику от визуального представления. Кроме того, можно обеспечить разделение пользовательского интерфейса и логики с помощью команд и привязок вместо событий и избегать ссылок на элементы в, когда <xref:System.Windows.Controls.ControlTemplate> это возможно.  Если пользовательский интерфейс и логика элемента управления правильно отделены, пользователь элемента управления может переопределять внешний вид элемента управления <xref:System.Windows.Controls.ControlTemplate> . Хотя создание пользовательского <xref:System.Windows.Controls.Control> не так просто <xref:System.Windows.Controls.UserControl>, как создание, пользователь <xref:System.Windows.Controls.Control> предоставляет наибольшую гибкость.

#### <a name="benefits-of-deriving-from-control"></a>Преимущества использования производного от элемента управления

Рекомендуется использовать наследование <xref:System.Windows.Controls.Control> вместо класса, <xref:System.Windows.Controls.UserControl> если применяется одно из следующих условий:

- Необходимо настроить внешний вид элемента управления с помощью <xref:System.Windows.Controls.ControlTemplate>.

- Элемент управления должен поддерживать различные темы.

### <a name="deriving-from-frameworkelement"></a>Создание производного от FrameworkElement

Элементы управления, производные <xref:System.Windows.Controls.UserControl> от <xref:System.Windows.Controls.Control> или основанные на компоновке существующих элементов. Во многих сценариях это приемлемое решение, поскольку любой объект, наследующий от <xref:System.Windows.FrameworkElement> , может находиться <xref:System.Windows.Controls.ControlTemplate>в. Однако бывают случаи, когда для внешнего вида элемента управления требуется больше, чем функциональность простой композиции элементов. В этих сценариях необходимо выбрать компонент на <xref:System.Windows.FrameworkElement> основе правильного выбора.

Существует два стандартных метода для создания <xref:System.Windows.FrameworkElement>компонентов на основе: прямая отрисовка и настраиваемая композиция элементов. Прямая отрисовка включает переопределение <xref:System.Windows.UIElement.OnRender%2A> <xref:System.Windows.FrameworkElement> метода и предоставление <xref:System.Windows.Media.DrawingContext> операций, явно определяющих визуальные элементы компонента. Это метод, используемый <xref:System.Windows.Controls.Image> и. <xref:System.Windows.Controls.Border> Пользовательская композиция элементов включает использование объектов типа <xref:System.Windows.Media.Visual> для составления внешнего вида компонента. Например, см. раздел [Использование объектов DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md). <xref:System.Windows.Controls.Primitives.Track>— Это пример элемента управления в, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в котором используется пользовательская композиция элементов. Можно также комбинировать прямую отрисовку и пользовательскую композицию элемента в одном элементе управления.

#### <a name="benefits-of-deriving-from-frameworkelement"></a>Преимущества использования производного от FrameworkElement

Рассмотрите возможность наследования от <xref:System.Windows.FrameworkElement> , если применяется одно из следующих условий:

- Требуется точный контроль над внешним видом элемента управления помимо того, который обеспечивается простой композицией элемента.

- Необходимо определить внешний вид элемента управления путем определения собственной логики отрисовки.

- Необходимо составить существующие элементы нестандартными <xref:System.Windows.Controls.UserControl> способами, которые выходят за рамки возможностей и. <xref:System.Windows.Controls.Control>

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

- `ValueProperty` `public` Определите идентификатор с именем в виде`static` поля .`readonly` <xref:System.Windows.DependencyProperty>

- Зарегистрируйте имя свойства в системе свойств, вызвав <xref:System.Windows.DependencyProperty.Register%2A?displayProperty=nameWithType>метод, чтобы указать следующее:

  - Имя свойства.

  - Тип свойства.

  - Тип, к которому принадлежит это свойство.

  - Метаданные для свойства. Метаданные содержат значение свойства по умолчанию, <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.PropertyChangedCallback>и.

- Определите свойство оболочки CLR с именем `Value`, которое совпадает с именем, используемым для регистрации свойства зависимостей, путем реализации методов доступа `get` свойства и `set` . Обратите внимание `get` , `set` что методы доступа и <xref:System.Windows.DependencyObject.GetValue%2A> вызывают <xref:System.Windows.DependencyObject.SetValue%2A> только метод и соответственно. Рекомендуется, чтобы методы доступа свойств зависимостей не содержали дополнительной логики, так как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] клиенты и могут обходить методы доступа <xref:System.Windows.DependencyObject.GetValue%2A> , <xref:System.Windows.DependencyObject.SetValue%2A> а также вызывать и напрямую. Например, если свойство привязано к источнику данных, то метод доступа `set` свойства не вызывается.  Вместо того чтобы добавлять дополнительную логику в методы доступа get и Set, используйте <xref:System.Windows.ValidateValueCallback>делегаты, <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback>и для ответа или проверки значения при его изменении.  Дополнительные сведения об этих обратных вызовах см. в разделе [Проверка и обратные вызовы свойства зависимостей](../advanced/dependency-property-callbacks-and-validation.md).

- Определите метод для <xref:System.Windows.CoerceValueCallback> именованного `CoerceValue`метода. `CoerceValue` гарантирует, что `Value` больше или равно `MinValue` и меньше или равно `MaxValue`.

- Определите метод для <xref:System.Windows.PropertyChangedCallback>с именем `OnValueChanged`. `OnValueChanged`Создает объект и готовится к `ValueChanged` вызову перенаправленного события. <xref:System.Windows.RoutedPropertyChangedEventArgs%601> Перенаправляемые события рассматриваются в следующем разделе.

[!code-csharp[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#dependencyproperty)]
[!code-vb[UserControlNumericUpDown#DependencyProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#dependencyproperty)]

Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../advanced/custom-dependency-properties.md).

### <a name="use-routed-events"></a>Использование перенаправляемых событий

Так же как свойства зависимостей расширяют понятие свойств среды CLR с дополнительными функциональными возможностями, перенаправленные события расширяют понятие стандартных событий CLR. При создании нового элемента управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рекомендуется также реализовывать событие как перенаправляемое, так как такие события поддерживают следующее поведение:

- События могут обрабатываться в родительском элементе нескольких элементов управления. Если событие является событием восходящей маршрутизации, то один родительский элемент в дереве элементов может подписаться на это событие. Разработчики приложений могут использовать один обработчик для реагирования на событие нескольких элементов управления. Например, если элемент управления является частью каждого элемента в <xref:System.Windows.Controls.ListBox> (так как он включен <xref:System.Windows.DataTemplate>в), разработчик приложения может определить обработчик событий для события <xref:System.Windows.Controls.ListBox>элемента управления в. Обработчик событий вызывается при возникновении события в любом элементе управления.

- Перенаправленные события могут использоваться в <xref:System.Windows.EventSetter>, что позволяет разработчикам приложений указывать обработчик события в стиле.

- Перенаправленные события можно использовать в <xref:System.Windows.EventTrigger>, что удобно для анимации свойств с помощью. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md).

Следующий пример определяет перенаправляемое событие:

- `ValueChangedEvent` `public` Определите идентификатор с именем в виде`static` поля .`readonly` <xref:System.Windows.RoutedEvent>

- Зарегистрируйте перенаправленное событие, вызвав <xref:System.Windows.EventManager.RegisterRoutedEvent%2A?displayProperty=nameWithType> метод. В примере при вызове метода <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>указываются следующие сведения:

  - Имя события `ValueChanged`.

  - Стратегия маршрутизации — <xref:System.Windows.RoutingStrategy.Bubble>это, что означает, что обработчик событий в источнике (объект, вызывающий событие) вызывается первым, а затем обработчики событий в родительских элементах источника вызываются в случае успеха, начиная с обработчика событий в ближайшем родительский элемент.

  - Тип обработчика событий создается <xref:System.Windows.RoutedPropertyChangedEventHandler%601> <xref:System.Decimal> с помощью типа.

  - Тип — владелец события — `NumericUpDown`.

- Объявите общее событие с именем `ValueChanged`, которое включает объявления метода доступа к событию. В примере <xref:System.Windows.UIElement.AddHandler%2A> вызывается `remove` `add` в объявлении метода <xref:System.Windows.UIElement.RemoveHandler%2A> доступа и в объявлении метода доступа [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для использования служб событий.

- Создайте защищенный виртуальный метод с именем `OnValueChanged`, вызывающий событие `ValueChanged`.

[!code-csharp[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml.cs#routedevent)]
[!code-vb[UserControlNumericUpDown#RoutedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDown/visualbasic/numericupdown.xaml.vb#routedevent)]

Дополнительные сведения см. в разделах [Общие сведения о перенаправляемых событиях](../advanced/routed-events-overview.md) и [Создание пользовательских перенаправляемых событий](../advanced/how-to-create-a-custom-routed-event.md).

### <a name="use-binding"></a>Использование привязки

Для отделения пользовательского интерфейса от логики элемента управления можно использовать привязку данных. Это особенно важно, если вы определяете внешний вид элемента управления с помощью <xref:System.Windows.Controls.ControlTemplate>. При использовании привязки данных можно избавиться от необходимости ссылаться на определенные части пользовательского интерфейса из кода. Рекомендуется избегать ссылок <xref:System.Windows.Controls.ControlTemplate> на элементы, находящихся в, так как когда код ссылается на элементы, находящихся <xref:System.Windows.Controls.ControlTemplate> в, и <xref:System.Windows.Controls.ControlTemplate> изменяется, элемент, на который указывает ссылка, должен быть включен в <xref:System.Windows.Controls.ControlTemplate>новый.

В следующем примере выполняется обновление <xref:System.Windows.Controls.TextBlock> `NumericUpDown` элемента управления, присвоение ему имени и ссылки на текстовое поле по имени в коде.

[!code-xaml[UserControlNumericUpDownSimple#UIRefMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml#uirefmarkup)]

[!code-csharp[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDownSimple/CSharp/NumericUpDown.xaml.cs#uirefcode)]
[!code-vb[UserControlNumericUpDownSimple#UIRefCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UserControlNumericUpDownSimple/VisualBasic/NumericUpDown.xaml.vb#uirefcode)]

Следующий пример использует привязку для достижения такого же результата.

[!code-xaml[UserControlNumericUpDown#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/UserControlNumericUpDown/CSharp/NumericUpDown.xaml#binding)]

Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).

### <a name="design-for-designers"></a>Разработка для конструкторов

Чтобы получить поддержку пользовательских элементов управления WPF в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] (например, редактирование свойства с помощью окна "Свойства"), следуйте приведенным ниже рекомендациям.  Дополнительные сведения о разработке для [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]см. в разделе [Разработка XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).

#### <a name="dependency-properties"></a>Свойства зависимостей

Не забудьте реализовать CLR `get` и `set` методы доступа, как описано выше в разделе "использование свойств зависимостей". Конструкторы могут использовать программы-оболочки для обнаружения свойства зависимостей, но им, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и клиентам элемента управления, не требуется вызывать методы доступа при получении или настройке свойства.

#### <a name="attached-properties"></a>Вложенные свойства

При реализации вложенных свойств в пользовательских элементах управления учитывайте следующие рекомендации:

- `public` Имеетформу`Property` *PropertyName* , созданную с помощью метода<xref:System.Windows.DependencyProperty.RegisterAttached%2A> . `static` `readonly` <xref:System.Windows.DependencyProperty> Имя свойства, которое передается <xref:System.Windows.DependencyProperty.RegisterAttached%2A> в, должно соответствовать *PropertyName*.

- Реализуйте пару методов CLR `public` `static` с именем `Set`*PropertyName* и `Get`*PropertyName*. Оба метода должны принимать класс, производный <xref:System.Windows.DependencyProperty> от, в качестве первого аргумента. Метод `Set`*PropertyName* также принимает аргумент, тип которого соответствует зарегистрированному типу данных для свойства. Метод `Get`*PropertyName* должен возвращать значение такого же типа. Если метод `Set` *PropertyName* отсутствует, свойство отмечается как "только для чтения".

- `Set`*PropertyName* и `Get` *PropertyName* должны прямо маршрутизироваться к <xref:System.Windows.DependencyObject.GetValue%2A> методам и <xref:System.Windows.DependencyObject.SetValue%2A> в целевом объекте зависимости соответственно. Разработчики могут получить доступ к вложенному свойству, вызвав программу-оболочку метода или с помощью прямого вызова целевого объекта зависимостей.

Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).

### <a name="define-and-use-shared-resources"></a>Определение и использование общих ресурсов

Можно включить элемент управления в ту же сборку, что и приложение, или упаковать его в отдельную сборку, которая может использоваться в нескольких приложениях. В большинстве случаев сведения, рассматриваемые в данном разделе, применяются независимо от используемого метода.  Однако есть одно отличие, о котором следует упомянуть.  При помещении элемента управления в ту же сборку, что и приложение, можно добавить глобальные ресурсы в файл App.xaml. Но сборка, содержащая только элементы управления, не имеет <xref:System.Windows.Application> связанного с ней объекта, поэтому файл App. XAML недоступен.

Приложение выполняет поиск ресурса на трех уровнях в следующем порядке:

1. Уровень элемента.

   Система начинает с элемента, который ссылается на ресурс, а затем ищет ресурсы логического родительского элемента и так далее, пока не будет достигнут корневой элемент.

2. Уровень приложения.

   Ресурсы, определяемые <xref:System.Windows.Application> объектом.

3. Уровень темы.

   Словари уровня темы хранятся в подпапке "Темы".  Файлы в папке "Темы" соответствуют темам.  Например, могут присутствовать файлы Aero.NormalColor.xaml, Luna.NormalColor.xaml, Royale.NormalColor.xaml и т. д.  Также может присутствовать файл с именем generic.xaml.  Когда система ищет ресурс на уровне темы, она сначала ищет его в файле конкретной темы, а затем в файле generic.xaml.

Если элемент управления находится в сборке отдельно от приложения, глобальные ресурсы необходимо поместить на уровень элемента или на уровень темы. Оба метода имеют свои преимущества.

#### <a name="defining-resources-at-the-element-level"></a>Определение ресурсов на уровне элемента

Общие ресурсы на уровне элемента можно определить путем создания пользовательского словаря ресурсов и его объединения со словарем ресурсов элемента управления.  При использовании этого метода можно присвоить файлу ресурсов любое имя и его можно поместить в одну папку с элементами управления. Ресурсы на уровне элемента также могут использовать простые строки как ключи. В следующем примере создается <xref:System.Windows.Media.LinearGradientBrush> файл ресурсов с именем Dictionary1. XAML.

[!code-xaml[SharedResources#1](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/Dictionary1.xaml#1)]

После определения словаря необходимо его объединить со словарем ресурсов элемента управления.  Это можно сделать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода.

Следующий пример объединяет словарь ресурса с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-xaml[SharedResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml#2)]

Недостатком этого подхода является то, что <xref:System.Windows.ResourceDictionary> объект создается каждый раз при ссылке на него.  Например, если в библиотеке имеется 10 пользовательских элементов управления и объединены словари общих ресурсов для каждого элемента управления с помощью XAML, то создается 10 идентичных <xref:System.Windows.ResourceDictionary> объектов.  Это можно избежать, создав статический класс, который объединяет ресурсы в коде и возвращает полученный результат <xref:System.Windows.ResourceDictionary>.

В следующем примере создается класс, который возвращает общий <xref:System.Windows.ResourceDictionary>объект.

[!code-csharp[SharedResources#3](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/SharedDictionaryManager.cs#3)]

В следующем примере общий ресурс объединяется с ресурсами пользовательского элемента управления в конструкторе элемента управления, прежде чем он вызывает `InitializeComponent`.  Поскольку является статическим свойством, объект <xref:System.Windows.ResourceDictionary> создается только один раз. `SharedDictionaryManager.SharedDictionary` Поскольку словарь ресурсов был объединен до вызова `InitializeComponent`, ресурсы доступны для элемента управления в его файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

[!code-csharp[SharedResources#4](~/samples/snippets/csharp/VS_Snippets_Wpf/SharedResources/CS/ShapeResizer.xaml.cs#4)]

#### <a name="defining-resources-at-the-theme-level"></a>Определение ресурсов на уровне темы

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать ресурсы для разных тем Windows.  Как разработчик элемента управления, вы можете определить ресурс для определенной темы, чтобы изменить внешний вид элемента управления в зависимости от того, какая тема используется. <xref:System.Windows.Controls.Button> Например, внешний вид в классической теме Windows (тема по умолчанию для Windows 2000) отличается от элемента <xref:System.Windows.Controls.Button> в теме Windows Luna (тема по умолчанию для <xref:System.Windows.Controls.Button> Windows XP), так как использует другой <xref:System.Windows.Controls.ControlTemplate> для каждой темы.

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

[Пример пользовательского элемента управления NumericUpDown с темами и поддержкой автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=160025) содержит два словаря ресурсов для элемента управления `NumericUpDown`: один — в файле generic.xaml, а второй — в Luna.NormalColor.xaml.  Можно запустить приложение и переключаться между серебристой темой в Windows XP и другой темой, чтобы увидеть разницу между двумя шаблонами элемента управления. (Если вы используете Windows Vista, можно переименовать Luna.NormalColor.xaml в Aero.NormalColor.xaml и переключаться между двумя темами, например между классической и темой по умолчанию для Windows Vista.)

При помещении <xref:System.Windows.Controls.ControlTemplate> в любой из файлов словаря ресурсов для конкретной темы необходимо создать статический конструктор для элемента управления и <xref:System.Windows.DependencyProperty.OverrideMetadata%28System.Type%2CSystem.Windows.PropertyMetadata%29> вызвать метод в <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>, как показано в следующем примере.

[!code-csharp[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/CSharp/NumericUpDown.cs#staticconstructor)]
[!code-vb[CustomControlNumericUpDownOneProject#StaticConstructor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDownOneProject/visualbasic/numericupdown.vb#staticconstructor)]

##### <a name="defining-and-referencing-keys-for-theme-resources"></a>Определение и создание ссылок на ключи для ресурсов тем

При определении ресурса на уровне элемента можно назначить строку в качестве его ключа и получить доступ к ресурсу через эту строку. При определении ресурса на уровне темы необходимо использовать в <xref:System.Windows.ComponentResourceKey> качестве ключа.  В следующем примере определяется ресурс в файле generic.xaml.

[!code-xaml[ThemeResourcesControlLibrary#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/Themes/generic.xaml#5)]

В следующем примере ссылка на ресурс указывается в <xref:System.Windows.ComponentResourceKey> качестве ключа.

[!code-xaml[ThemeResourcesControlLibrary#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ThemeResourcesControlLibrary/CS/NumericUpDown.xaml#6)]

##### <a name="specifying-the-location-of-theme-resources"></a>Определение местоположения ресурсов тем

Чтобы найти ресурсы для элемента управления, ведущее приложение должно знать, что сборка содержит ресурсы для элемента управления. Это можно сделать, добавив <xref:System.Windows.ThemeInfoAttribute> в сборку, содержащую элемент управления. Имеет свойство, указывающее расположение <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> универсальных ресурсов и свойство, которое указывает расположение ресурсов, зависящих от темы. <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> <xref:System.Windows.ThemeInfoAttribute>

В следующем примере <xref:System.Windows.ThemeInfoAttribute.GenericDictionaryLocation%2A> свойству <xref:System.Windows.ResourceDictionaryLocation.SourceAssembly>и <xref:System.Windows.ThemeInfoAttribute.ThemeDictionaryLocation%2A> присваивается значение, чтобы указать, что универсальные и зависящие от темы ресурсы находятся в той же сборке, что и элемент управления.

[!code-csharp[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/Properties/AssemblyInfo.cs#themessection)]
[!code-vb[CustomControlNumericUpDown#ThemesSection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/my project/assemblyinfo.vb#themessection)]

## <a name="see-also"></a>См. также

- [Проектирование XAML в Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [URI типа "pack" в WPF](../app-development/pack-uris-in-wpf.md)
- [Настройка элементов управления](control-customization.md)
