---
title: Создание элемента управления с настраиваемым внешним видом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: d9cf092cf47d4fb70b15033d039777d3279b633a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283563"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Создание элемента управления с настраиваемым внешним видом

<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] дает возможность создать элемент управления, внешний вид которого можно настроить. Например, можно изменить внешний вид <xref:System.Windows.Controls.CheckBox> помимо того, какие свойства будут доступны, создав новую <xref:System.Windows.Controls.ControlTemplate>. На следующем рисунке показана <xref:System.Windows.Controls.CheckBox>, использующая <xref:System.Windows.Controls.ControlTemplate> по умолчанию и <xref:System.Windows.Controls.CheckBox>, использующая настраиваемый <xref:System.Windows.Controls.ControlTemplate>.

![Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию

![Элемент управления CheckBox, использующий пользовательский шаблон элемента управления.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления

При использовании модели частей и состояний при создании элемента управления внешний вид элемента управления будет настраиваемым. Средства конструктора, такие как Blend для Visual Studio, поддерживают модель частей и состояний, поэтому при соблюдении этой модели элемент управления будет настраиваться в этих типах приложений.  В этом разделе рассматривается модель частей и состояний, а также объясняется, как это сделать при создании собственного элемента управления. В этом разделе используется пример пользовательского элемента управления, `NumericUpDown`, для иллюстрации философии этой модели.  Элемент управления `NumericUpDown` отображает числовое значение, которое пользователь может увеличить или уменьшить, нажав кнопки элемента управления.  На следующем рисунке показан элемент управления `NumericUpDown`, описанный в этом разделе.

![Пользовательский элемент управления NumericUpDown.](./media/ndp-numericupdown.png "NDP_NumericUPDown")
Пользовательский элемент управления NumericUpDown

В этом разделе содержатся следующие подразделы:

- [Предварительные требования](#prerequisites)

- [Модель частей и состояний](#parts_and_states_model)

- [Определение визуальной структуры и визуального поведения элемента управления в ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)

- [Использование частей ControlTemplate в коде](#using_parts_of_the_controltemplate_in_code)

- [Предоставление контракта элемента управления](#providing_the_control_contract)

- [Полный пример](#complete_example)

<a name="prerequisites"></a>

## <a name="prerequisites"></a>Предварительные требования

В этом разделе предполагается, что вы знаете, как создать новый <xref:System.Windows.Controls.ControlTemplate> для существующего элемента управления, знакомы с элементами в контракте элемента управления и понимаете концепции, обсуждаемые в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).

> [!NOTE]
> Чтобы создать элемент управления, для которого может быть настроен внешний вид, необходимо создать элемент управления, который наследует от класса <xref:System.Windows.Controls.Control> или одного из его подклассов, отличных от <xref:System.Windows.Controls.UserControl>.  Элемент управления, наследуемый от <xref:System.Windows.Controls.UserControl>, — это элемент управления, который можно быстро создать, но он не использует <xref:System.Windows.Controls.ControlTemplate> и не может настраивать внешний вид.

<a name="parts_and_states_model"></a>

## <a name="parts-and-states-model"></a>Модель частей и состояний

Модель частей и состояний определяет, как определить визуальную структуру и визуальное поведение элемента управления. Чтобы следовать модели частей и состояний, необходимо выполнить следующие действия.

- Определите визуальную структуру и визуальное поведение в <xref:System.Windows.Controls.ControlTemplate> элемента управления.

- Следуйте определенным рекомендациям, когда логика элемента управления взаимодействует с частями шаблона элемента управления.

- Предоставьте контракт элемента управления, чтобы указать, что следует включить в <xref:System.Windows.Controls.ControlTemplate>.

При определении визуальной структуры и визуального поведения в <xref:System.Windows.Controls.ControlTemplate> элемента управления авторы приложений могут изменять визуальную структуру и визуальное поведение элемента управления, создавая новую <xref:System.Windows.Controls.ControlTemplate> вместо написания кода.   Необходимо предоставить контракт элемента управления, который сообщает авторам приложений, <xref:System.Windows.FrameworkElement> какие объекты и состояния должны быть определены в <xref:System.Windows.Controls.ControlTemplate>. При взаимодействии с частями в <xref:System.Windows.Controls.ControlTemplate> следует соблюдать некоторые рекомендации, чтобы элемент управления правильно обрабатывал незавершенные <xref:System.Windows.Controls.ControlTemplate>.  Если следовать этим трем принципам, авторы приложений смогут создавать <xref:System.Windows.Controls.ControlTemplate> для элемента управления так же легко, как и для элементов управления, поставляемых с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В следующем разделе подробно описывается каждая из этих рекомендаций.

<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>

## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Определение визуальной структуры и визуального поведения элемента управления в ControlTemplate

При создании пользовательского элемента управления с помощью модели частей и состояний вы определяете визуальную структуру и визуальное поведение элемента управления в его <xref:System.Windows.Controls.ControlTemplate>, а не в логике.  Визуальная структура элемента управления является составной частью <xref:System.Windows.FrameworkElement> объектов, составляющих элемент управления.  Визуальное поведение — это способ отображения элемента управления, когда он находится в определенном состоянии.   Дополнительные сведения о создании <xref:System.Windows.Controls.ControlTemplate>, определяющего визуальную структуру и визуальное поведение элемента управления, см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).

В примере элемента управления `NumericUpDown` визуальная структура содержит два элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton> и <xref:System.Windows.Controls.TextBlock>.  Если добавить эти элементы управления в код элемента управления `NumericUpDown`--в конструкторе, например, позиции этих элементов управления будут неизменными.  Вместо того, чтобы определять визуальную структуру элемента управления и визуальное поведение в своем коде, необходимо определить ее в <xref:System.Windows.Controls.ControlTemplate>.  Затем разработчик приложения может настроить расположение кнопок и <xref:System.Windows.Controls.TextBlock> и указать, какое поведение происходит, когда `Value` отрицательно, поскольку <xref:System.Windows.Controls.ControlTemplate> можно заменить.

В следующем примере показана визуальная структура элемента управления `NumericUpDown`, которая включает <xref:System.Windows.Controls.Primitives.RepeatButton> для увеличения `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> для уменьшения `Value`и <xref:System.Windows.Controls.TextBlock> для отображения `Value`.

[!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]

Визуальное поведение элемента управления `NumericUpDown` заключается в том, что значение имеет красный шрифт, если оно отрицательное.  Если вы изменяете <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> в коде, если `Value` отрицательный, `NumericUpDown` всегда будет показывать красное отрицательное значение. Визуальное поведение элемента управления указывается в <xref:System.Windows.Controls.ControlTemplate> путем добавления <xref:System.Windows.VisualState> объектов в <xref:System.Windows.Controls.ControlTemplate>.  В следующем примере показаны объекты <xref:System.Windows.VisualState> для состояний `Positive` и `Negative`.  `Positive` и `Negative` являются взаимоисключающими (элемент управления всегда находится в точности один из двух), поэтому в примере объекты <xref:System.Windows.VisualState> помещаются в один <xref:System.Windows.VisualStateGroup>.  Когда элемент управления переходит в состояние `Negative`, <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> становится красным.  Когда элемент управления находится в состоянии `Positive`, <xref:System.Windows.Controls.TextBlock.Foreground%2A> возвращается к исходному значению.  Определение <xref:System.Windows.VisualState> объектов в <xref:System.Windows.Controls.ControlTemplate> обсуждается в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).

> [!NOTE]
> Не забудьте задать <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> присоединенное свойство в корневой <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

<a name="using_parts_of_the_controltemplate_in_code"></a>

## <a name="using-parts-of-the-controltemplate-in-code"></a>Использование частей ControlTemplate в коде

Автор <xref:System.Windows.Controls.ControlTemplate> может опустить <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState> объектов, либо намеренно, либо по ошибке, но логика элемента управления может потребовать, чтобы эти компоненты работали правильно. Модель "части и состояния" указывает, что элемент управления должен быть устойчивым к <xref:System.Windows.Controls.ControlTemplate>, на котором отсутствуют <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState> объекты.  Элемент управления не должен вызывать исключение или сообщать об ошибке, если в <xref:System.Windows.Controls.ControlTemplate>отсутствует <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>или <xref:System.Windows.VisualStateGroup>. В этом разделе описаны рекомендации по взаимодействию с <xref:System.Windows.FrameworkElement> объектами и управлением состояниями.

### <a name="anticipate-missing-frameworkelement-objects"></a>Ожидается отсутствие объектов FrameworkElement

При определении <xref:System.Windows.FrameworkElement> объектов в <xref:System.Windows.Controls.ControlTemplate>логике элемента управления может потребоваться взаимодействие с некоторыми из них.  Например, элемент управления `NumericUpDown` подписывается на событие кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> для увеличения или уменьшения `Value` и устанавливает для свойства <xref:System.Windows.Controls.TextBlock.Text%2A> <xref:System.Windows.Controls.TextBlock> значение `Value`. Если в пользовательском <xref:System.Windows.Controls.ControlTemplate> опущены <xref:System.Windows.Controls.TextBlock> или кнопки, то допустимо, чтобы элемент управления потерял некоторые его функции, но вы должны быть уверены, что элемент управления не вызывает ошибку. Например, если <xref:System.Windows.Controls.ControlTemplate> не содержит кнопки для изменения `Value`, `NumericUpDown` теряет эту функциональность, но приложение, использующее <xref:System.Windows.Controls.ControlTemplate>, будет продолжать работать.

Следующие рекомендации гарантируют, что элемент управления будет правильно реагировать на отсутствие <xref:System.Windows.FrameworkElement> объектов:

1. Задайте атрибут `x:Name` для каждой <xref:System.Windows.FrameworkElement>, на которую необходимо ссылаться в коде.

2. Определите частные свойства для каждого <xref:System.Windows.FrameworkElement>, с которым необходимо взаимодействовать.

3. Подпишитесь и отменяйте подписывание любых событий, обрабатываемых элементом управления в методе доступа set свойства <xref:System.Windows.FrameworkElement>.

4. Задайте свойства <xref:System.Windows.FrameworkElement>, определенные на шаге 2, в методе <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>. Это самое раннее, что <xref:System.Windows.FrameworkElement> в <xref:System.Windows.Controls.ControlTemplate> доступен элементу управления. Используйте `x:Name` <xref:System.Windows.FrameworkElement>, чтобы получить его из <xref:System.Windows.Controls.ControlTemplate>.

5. Убедитесь, что <xref:System.Windows.FrameworkElement> не `null` перед доступом к ее членам.  Если это `null`, не сообщайте об ошибке.

В следующих примерах показано, как элемент управления `NumericUpDown` взаимодействует с <xref:System.Windows.FrameworkElement>ными объектами в соответствии с рекомендациями из предыдущего списка.

В примере, который определяет визуальную структуру элемента управления `NumericUpDown` в <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton>, увеличивающее `Value`, имеет атрибут `x:Name`, установленный в `UpButton`.  В следующем примере объявляется свойство с именем `UpButtonElement`, которое представляет <xref:System.Windows.Controls.Primitives.RepeatButton>, объявленный в <xref:System.Windows.Controls.ControlTemplate>. Метод доступа `set` First отменяет подписывание на событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки, если `UpDownElement` не `null`, то задается свойство, а затем подписывается на событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>. Кроме того, имеется свойство, определенное, но не показанное здесь для других <xref:System.Windows.Controls.Primitives.RepeatButton>, именуемое `DownButtonElement`.

[!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
[!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]

В следующем примере показаны <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> для элемента управления `NumericUpDown`.  В примере используется метод <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> для получения объектов <xref:System.Windows.FrameworkElement> из <xref:System.Windows.Controls.ControlTemplate>.  Обратите внимание, что пример защищается от случаев, когда <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> находит <xref:System.Windows.FrameworkElement> с указанным именем, которое не относится к ожидаемому типу. Также рекомендуется пропускать элементы с указанным `x:Name`, но имеют неверный тип.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Следуя рекомендациям, приведенным в предыдущих примерах, вы убедитесь, что элемент управления продолжит работу, когда в <xref:System.Windows.Controls.ControlTemplate> отсутствует <xref:System.Windows.FrameworkElement>.

### <a name="use-the-visualstatemanager-to-manage-states"></a>Использование VisualStateManager для управления состояниями

<xref:System.Windows.VisualStateManager> отслеживает состояния элемента управления и выполняет логику, необходимую для перехода между состояниями. При добавлении <xref:System.Windows.VisualState> объектов в <xref:System.Windows.Controls.ControlTemplate>их необходимо добавить в <xref:System.Windows.VisualStateGroup> и добавить <xref:System.Windows.VisualStateGroup> в <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> присоединенное свойство, чтобы у <xref:System.Windows.VisualStateManager> был доступ к ним.

В следующем примере повторяется предыдущий пример, в котором показаны <xref:System.Windows.VisualState>ные объекты, соответствующие `Positive` и `Negative` состояниям элемента управления. <xref:System.Windows.Media.Animation.Storyboard> в `Negative`<xref:System.Windows.VisualState> превращает <xref:System.Windows.Controls.TextBlock.Foreground%2A> <xref:System.Windows.Controls.TextBlock> Red.   Когда `NumericUpDown` элемент управления находится в состоянии `Negative`, начинается раскадровка в `Negative`ном состоянии.  Затем <xref:System.Windows.Media.Animation.Storyboard> в `Negative` состояние останавливается, когда элемент управления возвращается в состояние `Positive`.  <xref:System.Windows.VisualState> `Positive`не обязательно должен содержать <xref:System.Windows.Media.Animation.Storyboard>, так как если <xref:System.Windows.Media.Animation.Storyboard> для `Negative` останавливается, <xref:System.Windows.Controls.TextBlock.Foreground%2A> возвращается к исходному цвету.

[!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]

Обратите внимание, что <xref:System.Windows.Controls.TextBlock> присваивается имя, но <xref:System.Windows.Controls.TextBlock> не находится в контракте элемента управления для `NumericUpDown`, так как логика элемента управления никогда не ссылается на <xref:System.Windows.Controls.TextBlock>.  Элементы, упоминаемые в <xref:System.Windows.Controls.ControlTemplate>, имеют имена, но не обязательно должны быть частью контракта элемента управления, <xref:System.Windows.Controls.ControlTemplate> поскольку для элемента управления может не потребоваться ссылка на этот элемент.  Например, кто-то, кто создает новый <xref:System.Windows.Controls.ControlTemplate> для `NumericUpDown`, может решить не указывать, что `Value` отрицательно, изменив <xref:System.Windows.Controls.Control.Foreground%2A>.  В этом случае ни код, ни <xref:System.Windows.Controls.ControlTemplate> не ссылаются на <xref:System.Windows.Controls.TextBlock> по имени.

Логика элемента управления отвечает за изменение состояния элемента управления. В следующем примере показано, что элемент управления `NumericUpDown` вызывает метод <xref:System.Windows.VisualStateManager.GoToState%2A>, чтобы переходить в состояние `Positive`, когда `Value` имеет значение 0 или больше, и состояние `Negative`, если `Value` меньше 0.

[!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
[!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]

Метод <xref:System.Windows.VisualStateManager.GoToState%2A> выполняет логику, необходимую для запуска и завершения раскадровки соответствующим образом. Когда элемент управления вызывает <xref:System.Windows.VisualStateManager.GoToState%2A> для изменения его состояния, <xref:System.Windows.VisualStateManager> выполняет следующие действия:

- Если <xref:System.Windows.VisualState>, что в элементе управления будет <xref:System.Windows.Media.Animation.Storyboard>, начинается раскадровка. Затем, если <xref:System.Windows.VisualState>, из которого поступает элемент управления, <xref:System.Windows.Media.Animation.Storyboard>, раскадровка заканчивается.

- Если элемент управления уже находится в указанном состоянии, <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий и возвращает `true`.

- Если указанное состояние не существует в <xref:System.Windows.Controls.ControlTemplate> `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий и возвращает `false`.

#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Рекомендации по работе с VisualStateManager

Для поддержания состояния элемента управления рекомендуется выполнить следующие действия.

- Используйте свойства для отслеживания состояния.

- Создайте вспомогательный метод для перехода между состояниями.

Элемент управления `NumericUpDown` использует свойство `Value` для отслеживания того, находится ли он в `Positive` или `Negative` состоянии.  Элемент управления `NumericUpDown` также определяет `Focused` и `UnFocused` состояния, которые отслеживают свойство <xref:System.Windows.UIElement.IsFocused%2A>. При использовании состояний, которые, естественно, не соответствуют свойству элемента управления, можно определить частное свойство для отслеживания состояния.

Один метод, который обновляет все состояния, централизует вызовы <xref:System.Windows.VisualStateManager> и обеспечивает управляемость кода. В следующем примере показан вспомогательный метод элемента управления `NumericUpDown` `UpdateStates`. Если `Value` больше или равно 0, <xref:System.Windows.Controls.Control> находится в состоянии `Positive`.  Если `Value` меньше 0, элемент управления находится в состоянии `Negative`.  Если <xref:System.Windows.UIElement.IsFocused%2A> `true`, элемент управления находится в `Focused` состоянии. в противном случае он находится в состоянии `Unfocused`.  Элемент управления может вызывать `UpdateStates` каждый раз, когда ему нужно изменить свое состояние, независимо от изменения состояния.

[!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
[!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]

Если имя состояния передается <xref:System.Windows.VisualStateManager.GoToState%2A>, когда элемент управления уже находится в этом состоянии, <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий, поэтому не нужно проверять текущее состояние элемента управления.  Например, если `Value` меняется от одного отрицательного числа к другому отрицательному, раскадровка для состояния `Negative` не прерывается и пользователь не увидит изменения в элементе управления.

<xref:System.Windows.VisualStateManager> использует <xref:System.Windows.VisualStateGroup> объекты, чтобы определить, какое состояние выйти при вызове <xref:System.Windows.VisualStateManager.GoToState%2A>. Элемент управления всегда находится в одном состоянии для каждого <xref:System.Windows.VisualStateGroup>, определенного в его <xref:System.Windows.Controls.ControlTemplate> и оставляет состояние только при переходе в другое состояние из того же <xref:System.Windows.VisualStateGroup>. Например, <xref:System.Windows.Controls.ControlTemplate> элемента управления `NumericUpDown` определяет `Positive` и `Negative`<xref:System.Windows.VisualState> объекты в одном <xref:System.Windows.VisualStateGroup>, а `Focused` и `Unfocused`<xref:System.Windows.VisualState> объекты в другом. (Вы видите `Focused` и `Unfocused`<xref:System.Windows.VisualState>, определенные в разделе " [полный пример](#complete_example) " в этом разделе, когда элемент управления переходит из состояния `Positive` в состояние `Negative` или наоборот, элемент управления остается в `Focused` или `Unfocused` состоянии.

Существует три типичных места, в которых состояние элемента управления может измениться:

- При применении <xref:System.Windows.Controls.ControlTemplate> к <xref:System.Windows.Controls.Control>.

- При изменении свойства.

- При возникновении события.

В следующих примерах показано обновление состояния элемента управления `NumericUpDown` в этих случаях.

Необходимо обновить состояние элемента управления в методе <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>, чтобы элемент управления выявлялся в правильном состоянии при применении <xref:System.Windows.Controls.ControlTemplate>. В следующем примере вызывается `UpdateStates` в <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>, чтобы гарантировать, что элемент управления находится в соответствующих состояниях.  Например, предположим, что вы создаете элемент управления `NumericUpDown`, а затем установите для его <xref:System.Windows.Controls.Control.Foreground%2A> значение зеленый, а `Value` — значение-5.  Если не вызвать `UpdateStates` при применении <xref:System.Windows.Controls.ControlTemplate> к элементу управления `NumericUpDown`, элемент управления находится не в состоянии `Negative`, а значение — зеленым вместо красного.  Чтобы перевести элемент управления в состояние `Negative`, необходимо вызвать метод `UpdateStates`.

[!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
[!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]

Часто требуется обновлять состояния элемента управления при изменении свойства. В следующем примере показан весь метод `ValueChangedCallback`. Поскольку `ValueChangedCallback` вызывается при изменении `Value`, метод вызывает `UpdateStates` на случай, если `Value` изменился с положительного на отрицательный или наоборот. Допускается вызов `UpdateStates`, когда `Value` изменяется, но остается положительным или отрицательным, поскольку в этом случае элемент управления не изменит состояние.

[!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
[!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]

Также может потребоваться обновить состояния при возникновении события. В следующем примере показано, что `NumericUpDown` вызывает `UpdateStates` в <xref:System.Windows.Controls.Control> для управления событием <xref:System.Windows.UIElement.GotFocus>.

[!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
[!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]

<xref:System.Windows.VisualStateManager> помогает управлять состояниями элемента управления. Используя <xref:System.Windows.VisualStateManager>, вы гарантируете, что элемент управления правильно переходит между состояниями.  Если следовать рекомендациям, описанным в этом разделе, для работы с <xref:System.Windows.VisualStateManager>, код элемента управления останется доступным для чтения и сопровождения.

<a name="providing_the_control_contract"></a>

## <a name="providing-the-control-contract"></a>Предоставление контракта элемента управления

Вы предоставляете контракт элемента управления, чтобы <xref:System.Windows.Controls.ControlTemplate> авторы узнают, что следует разместить в шаблоне. Контракт элемента управления имеет три элемента:

- визуальный элемент, используемый логикой элемента управления;

- состояния элемента управления и группа, к которой принадлежит каждое состояние;

- общие свойства, визуально воздействующие на элемент управления.

Кто-то, создающий новый <xref:System.Windows.Controls.ControlTemplate>, должен иметь представление об объектах <xref:System.Windows.FrameworkElement>, используемых логикой элемента управления, типе каждого объекта и его имени. Автору <xref:System.Windows.Controls.ControlTemplate> также необходимо иметь имя каждого возможного состояния, в котором может находиться элемент управления, а также указать, в каком <xref:System.Windows.VisualStateGroup> находится состояние.

При возврате к примеру `NumericUpDown` элемент управления ждет, что <xref:System.Windows.Controls.ControlTemplate> будет иметь следующие <xref:System.Windows.FrameworkElement> объекты:

- <xref:System.Windows.Controls.Primitives.RepeatButton> с именем `UpButton`.

- <xref:System.Windows.Controls.Primitives.RepeatButton> с именем `DownButton.`

 Элемент управления может находиться в следующих состояниях:

- В `ValueStates`<xref:System.Windows.VisualStateGroup>

  - `Positive`

  - `Negative`

- В `FocusStates`<xref:System.Windows.VisualStateGroup>

  - `Focused`

  - `Unfocused`

Чтобы указать, какие объекты <xref:System.Windows.FrameworkElement> ожидает элемент управления, используйте <xref:System.Windows.TemplatePartAttribute>, который указывает имя и тип ожидаемых элементов.  Чтобы указать возможные состояния элемента управления, используйте <xref:System.Windows.TemplateVisualStateAttribute>, который указывает имя состояния и <xref:System.Windows.VisualStateGroup> к нему.  Вставьте <xref:System.Windows.TemplatePartAttribute> и <xref:System.Windows.TemplateVisualStateAttribute> в определение класса элемента управления.

Любое открытое свойство, влияющее на внешний вид элемента управления, также является частью контракта элемента управления.

В следующем примере задается объект <xref:System.Windows.FrameworkElement> и состояния для элемента управления `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
[!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]

<a name="complete_example"></a>

## <a name="complete-example"></a>Полный пример

Ниже приведен пример всего <xref:System.Windows.Controls.ControlTemplate> для элемента управления `NumericUpDown`.

[!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]

В следующем примере показана логика для `NumericUpDown`.

[!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
[!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]

## <a name="see-also"></a>См. также

- [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md)
- [Настройка элементов управления](control-customization.md)
