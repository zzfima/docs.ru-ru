---
title: Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
ms.openlocfilehash: 0c79ba3dd42f2e65eb241409946e921577ced5f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920056"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate
<a name="introduction"></a><xref:System.Windows.Controls.ControlTemplate> задает визуальную структуру и визуальное поведение элемента управления. Внешний вид элемента управления можно настроить, присвоив ему новый <xref:System.Windows.Controls.ControlTemplate>. При создании <xref:System.Windows.Controls.ControlTemplate>вы заменяете внешний вид существующего элемента управления, не изменяя его функциональность. Например, можно сделать так, чтобы кнопки в приложении округлялись вместо квадратной фигуры по умолчанию, но кнопка по-прежнему будет вызывать событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.

 В этом разделе объясняются различные части <xref:System.Windows.Controls.ControlTemplate>, демонстрируется создание простого <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>и объясняется, как определить контракт элемента управления, чтобы можно было настроить его внешний вид. Поскольку вы создаете <xref:System.Windows.Controls.ControlTemplate> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно изменить внешний вид элемента управления без написания кода. Для создания пользовательских шаблонов элементов управления можно также использовать конструктор, например Blend для Visual Studio. В этом разделе приведены примеры в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые настраивают внешний вид <xref:System.Windows.Controls.Button> и список полных примеров в конце раздела. Дополнительные сведения об использовании Blend для Visual Studio см. [в разделе Стилизация элемента управления, поддерживающего шаблоны](https://go.microsoft.com/fwlink/?LinkId=161153).

 На следующих иллюстрациях показан <xref:System.Windows.Controls.Button>, использующий <xref:System.Windows.Controls.ControlTemplate>, созданный в этом разделе.

 ![Кнопка, использующая пользовательский шаблон элемента управления.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Кнопка, использующая пользовательский шаблон элемента управления

 ![Кнопка с красной границей.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Кнопка, использующая пользовательский шаблон элемента управления, когда на ней находится указатель мыши

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Необходимые компоненты
 В этом разделе предполагается, что пользователь понимает процесс создания и использования элементов управления и стилей, который рассматривался в разделе [Элементы управления](index.md). Концепции, обсуждаемые в этом разделе, применяются к элементам, которые наследуются от класса <xref:System.Windows.Controls.Control>, за исключением <xref:System.Windows.Controls.UserControl>. К <xref:System.Windows.Controls.UserControl>нельзя применить <xref:System.Windows.Controls.ControlTemplate>.

<a name="when_you_should_create_a_controltemplate"></a>
## <a name="when-you-should-create-a-controltemplate"></a>Когда следует создавать объект ControlTemplate
 Элементы управления имеют множество свойств, таких как <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>и <xref:System.Windows.Controls.Control.FontFamily%2A>, которые можно задать, чтобы указать различные аспекты внешнего вида элемента управления, но изменения, которые можно выполнить путем установки этих свойств, ограничены. Например, можно задать для свойства <xref:System.Windows.Controls.Control.Foreground%2A> значение Blue, а <xref:System.Windows.Controls.Control.FontStyle%2A> курсивом на <xref:System.Windows.Controls.CheckBox>.

 Без возможности создания новых <xref:System.Windows.Controls.ControlTemplate> для элементов управления все элементы управления в каждом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ном приложении будут иметь одинаковый общий внешний вид, что ограничит возможность создания приложения с пользовательским видом и поведением. По умолчанию каждый <xref:System.Windows.Controls.CheckBox> имеет аналогичные характеристики. Например, содержимое <xref:System.Windows.Controls.CheckBox> всегда находится справа от индикатора выбора, а галочка всегда используется для указания того, что <xref:System.Windows.Controls.CheckBox> выбрано.

 Вы создаете <xref:System.Windows.Controls.ControlTemplate>, если хотите настроить внешний вид элемента управления, помимо того, что устанавливает другие свойства элемента управления. В примере <xref:System.Windows.Controls.CheckBox>Предположим, что содержимое флажка должно располагаться над индикатором выбора, и необходимо указать X, чтобы показать, что <xref:System.Windows.Controls.CheckBox> выбрано. Эти изменения указываются в <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>.

 На следующем рисунке показана <xref:System.Windows.Controls.CheckBox>, использующая <xref:System.Windows.Controls.ControlTemplate>по умолчанию.

 ![Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию

 На следующем рисунке показана <xref:System.Windows.Controls.CheckBox>, использующая пользовательский <xref:System.Windows.Controls.ControlTemplate> для размещения содержимого <xref:System.Windows.Controls.CheckBox> над индикатором выбора и отображения X при выборе <xref:System.Windows.Controls.CheckBox>.

 ![Элемент управления CheckBox, использующий пользовательский шаблон элемента управления.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления

 <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.CheckBox> в этом образце относительно сложны, поэтому в этом разделе используется более простой пример создания <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>.

<a name="changing_the_visual_structure_of_a_control"></a>
## <a name="changing-the-visual-structure-of-a-control"></a>Изменение визуальной структуры элемента управления
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]элемент управления часто является составным <xref:System.Windows.FrameworkElement> объектами. При создании <xref:System.Windows.Controls.ControlTemplate>вы объединяете <xref:System.Windows.FrameworkElement> объекты для создания одного элемента управления. У <xref:System.Windows.Controls.ControlTemplate> должен быть только один <xref:System.Windows.FrameworkElement> в качестве корневого элемента. Корневой элемент обычно содержит другие объекты <xref:System.Windows.FrameworkElement>. Комбинация объектов составляет визуальную структуру элемента управления.

 В следующем примере создается настраиваемый <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.ControlTemplate> создает визуальную структуру <xref:System.Windows.Controls.Button>. В этом примере не меняется внешний вид кнопки при перемещении на нее указателя мыши или при ее нажатии. Изменение внешнего вида кнопки при ее переходе в другое состояние рассматривается далее в этом разделе.

 В данном примере визуальная структура состоит из следующих частей:

- <xref:System.Windows.Controls.Border> с именем `RootElement`, который служит корневым <xref:System.Windows.FrameworkElement>шаблона.

- <xref:System.Windows.Controls.Grid>, являющийся дочерним элементом `RootElement`.

- <xref:System.Windows.Controls.ContentPresenter>, отображающая содержимое кнопки. <xref:System.Windows.Controls.ContentPresenter> позволяет отображать любой тип объекта.

 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]

### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Сохранение функциональности свойств элемента управления с помощью TemplateBinding
 При создании нового <xref:System.Windows.Controls.ControlTemplate>может потребоваться использовать открытые свойства для изменения внешнего вида элемента управления. Расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) привязывает свойство элемента, который находится в <xref:System.Windows.Controls.ControlTemplate>, к открытому свойству, определенному элементом управления. Использование расширения [TemplateBinding](../advanced/templatebinding-markup-extension.md) позволяет свойствам элемента управления действовать в качестве параметров шаблона. Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../advanced/templatebinding-markup-extension.md).

 В следующем примере повторяется часть предыдущего примера, в которой используется расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) для привязки свойств элементов, которые находятся в <xref:System.Windows.Controls.ControlTemplate>, к общим свойствам, определенным кнопкой.

 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]

 В этом примере <xref:System.Windows.Controls.Grid> имеет шаблон свойства <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType>, привязанный к <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Поскольку <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> является привязанным шаблоном, можно создать несколько кнопок, использующих один и тот же <xref:System.Windows.Controls.ControlTemplate>, и задать для <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> различные значения для каждой кнопки. Если <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> не был привязан к свойству элемента в <xref:System.Windows.Controls.ControlTemplate>, установка <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> кнопки не повлияет на внешний вид кнопки.

 Следует отметить, что не требуется, чтобы имена этих двух свойств совпадали. В предыдущем примере свойство <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Button> является шаблоном, привязанным к свойству <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.ContentPresenter>. Это позволяет располагать содержимое кнопки горизонтально. <xref:System.Windows.Controls.ContentPresenter> не имеет свойства с именем `HorizontalContentAlignment`, но <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> можно привязать к <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Перед привязкой свойства к шаблону следует убедиться, что целевое и исходное свойства имеют один и тот же тип.

 Класс <xref:System.Windows.Controls.Control> определяет несколько свойств, которые должны использоваться шаблоном элемента управления для получения влияния на элемент управления, когда они заданы. То, как <xref:System.Windows.Controls.ControlTemplate> использует свойство, зависит от свойства. <xref:System.Windows.Controls.ControlTemplate> должен использовать свойство одним из следующих способов:

- Элемент в шаблоне <xref:System.Windows.Controls.ControlTemplate> привязывается к свойству.

- Элемент в <xref:System.Windows.Controls.ControlTemplate> наследует свойство от родительского <xref:System.Windows.FrameworkElement>.

 В следующей таблице перечислены визуальные свойства, наследуемые элементом управления от класса <xref:System.Windows.Controls.Control>. В таблице также указывается, использует ли шаблон элемента управления по умолчанию значение наследуемого свойства или оно должно быть привязано к шаблону.

|свойство;|Способ использования|
|--------------|------------------|
|<xref:System.Windows.Controls.Control.Background%2A>|Привязка к шаблону|
|<xref:System.Windows.Controls.Control.BorderThickness%2A>|Привязка к шаблону|
|<xref:System.Windows.Controls.Control.BorderBrush%2A>|Привязка к шаблону|
|<xref:System.Windows.Controls.Control.FontFamily%2A>|Наследование свойства или привязка к шаблону|
|<xref:System.Windows.Controls.Control.FontSize%2A>|Наследование свойства или привязка к шаблону|
|<xref:System.Windows.Controls.Control.FontStretch%2A>|Наследование свойства или привязка к шаблону|
|<xref:System.Windows.Controls.Control.FontWeight%2A>|Наследование свойства или привязка к шаблону|
|<xref:System.Windows.Controls.Control.Foreground%2A>|Наследование свойства или привязка к шаблону|
|<xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>|Привязка к шаблону|
|<xref:System.Windows.Controls.Control.Padding%2A>|Привязка к шаблону|
|<xref:System.Windows.Controls.Control.VerticalContentAlignment%2A>|Привязка к шаблону|

 В таблице перечислены только визуальные свойства, унаследованные от класса <xref:System.Windows.Controls.Control>. Помимо свойств, перечисленных в таблице, элемент управления может также наследовать свойства <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A>и <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> из родительского элемента Framework.

 Кроме того, если <xref:System.Windows.Controls.ContentPresenter> находится в <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ContentControl>, <xref:System.Windows.Controls.ContentPresenter> будет автоматически привязан к свойствам <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>. Аналогичным образом <xref:System.Windows.Controls.ItemsPresenter>, который находится в <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.ItemsControl>, автоматически привязывается к свойствам <xref:System.Windows.Controls.ItemsControl.Items%2A> и <xref:System.Windows.Controls.ItemsPresenter>.

 В следующем примере создаются две кнопки, использующие <xref:System.Windows.Controls.ControlTemplate>, определенные в предыдущем примере. В примере задаются свойства <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>и <xref:System.Windows.Controls.Control.FontSize%2A> для каждой кнопки. Установка свойства <xref:System.Windows.Controls.Control.Background%2A> оказывает воздействие, так как оно привязано к шаблону в <xref:System.Windows.Controls.ControlTemplate>. Несмотря на то, что свойства <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontSize%2A> не привязаны к шаблону, их установка оказывает воздействие, поскольку их значения наследуются.

 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]

 В предыдущем примере получался результат, аналогичный показанному на следующем рисунке.

 ![Две кнопки, одна синяя, а другая — фиолетовая.](./media/ndp-buttontwo.png "NDP_ButtonTwo")
Две кнопки с различными цветами фона

<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Изменение внешнего вида элемента управления в зависимости от его состояния
 Разница между кнопкой с внешним видом по умолчанию и кнопкой из предыдущего примера состоит в том, что кнопка по умолчанию слегка изменяется при переходе в другое состояние. Например, внешний вид кнопки по умолчанию изменяется при нажатии этой кнопки или при наведении на нее указателя мыши. Хотя <xref:System.Windows.Controls.ControlTemplate> не изменяет функциональность элемента управления, он изменяет визуальное поведение элемента управления. Визуальное поведение описывает внешний вид элемента управления в определенных состояниях. Чтобы лучше понять разницу между функциональностью и визуальным поведением элемента управления, рассмотрим пример с кнопкой. Функциональность кнопки заключается в вызове события <xref:System.Windows.Controls.Primitives.ButtonBase.Click> при щелчке, но визуальное поведение кнопки заключается в том, чтобы изменить внешний вид, на который указывает или нажата кнопка.

 Чтобы задать внешний вид элемента управления, когда он находится в определенном состоянии, используются <xref:System.Windows.VisualState> объекты. <xref:System.Windows.VisualState> содержит <xref:System.Windows.Media.Animation.Storyboard>, который изменяет внешний вид элементов в <xref:System.Windows.Controls.ControlTemplate>. Для этого не нужно писать код, так как логика элемента управления меняет состояние с помощью <xref:System.Windows.VisualStateManager>. Когда элемент управления переходит в состояние, заданное свойством <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType>, начинается <xref:System.Windows.Media.Animation.Storyboard>. Когда элемент управления выходит из состояния, <xref:System.Windows.Media.Animation.Storyboard> останавливается.

 В следующем примере показаны <xref:System.Windows.VisualState>, которые изменяют внешний вид <xref:System.Windows.Controls.Button> при наведении на нее указателя мыши. <xref:System.Windows.Media.Animation.Storyboard> изменяет цвет границы кнопки, изменяя цвет `BorderBrush`. Если вы ссылаетесь на <xref:System.Windows.Controls.ControlTemplate> пример в начале этого раздела, вы помните, что `BorderBrush` является именем <xref:System.Windows.Media.SolidColorBrush>, назначенного <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Border>.

 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]

 Элемент управления отвечает за определение состояний как часть своего контракта, что подробно рассматривается в подразделе [Настройка других элементов управления через понимание контракта элемента управления](#customizing_other_controls_by_understanding_the_control_contract) далее в этом разделе. В следующей таблице перечислены состояния, указанные для <xref:System.Windows.Controls.Button>.

|Имя VisualState|Имя VisualStateGroup|Описание|
|----------------------|---------------------------|-----------------|
|Норм.|CommonStates|Состояние по умолчанию.|
|MouseOver|CommonStates|Указатель мыши расположен над элементом управления.|
|Нажато|CommonStates|Элемент управления нажат.|
|Отключено.|CommonStates|Элемент управления отключен.|
|Focused|FocusStates|Элемент управления имеет фокус.|
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|

 <xref:System.Windows.Controls.Button> определяет две группы состояний: Группа `CommonStates` содержит `Normal`, `MouseOver`, `Pressed`и `Disabled` состояния. Группа `FocusStates` содержит состояния `Focused` и `Unfocused`. Состояния, входящие в одну группу, являются взаимоисключающими. Элемент управления всегда находится строго в одном состоянии из каждой группы. Например, <xref:System.Windows.Controls.Button> может иметь фокус, даже если указатель мыши находится не над ним, так что <xref:System.Windows.Controls.Button> в `Focused` состоянии может находиться в `MouseOver`, `Pressed`или `Normal`.

 <xref:System.Windows.VisualState> объекты добавляются к <xref:System.Windows.VisualStateGroup> объектам. <xref:System.Windows.VisualStateGroup> объекты добавляются в присоединенное к <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> свойство. В следующем примере определяются объекты <xref:System.Windows.VisualState> для состояний `Normal`, `MouseOver`и `Pressed`, которые находятся в группе `CommonStates`. <xref:System.Windows.VisualState.Name%2A> каждого <xref:System.Windows.VisualState> совпадает с именем в предыдущей таблице. Состояние `Disabled` и состояния из группы `FocusStates` опущены для сохранения краткости примера, но они включены в полный пример, приведенный в конце этого раздела.

> [!NOTE]
> Не забудьте задать <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> присоединенное свойство в корневой <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>.

 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]

 В предыдущем примере получался результат, аналогичный показанному на следующих рисунках.

 ![Кнопка, использующая пользовательский шаблон элемента управления.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")
Кнопка, использующая пользовательский шаблон элемента управления в нормальном состоянии

 ![Кнопка с красной границей.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда указатель мыши находится над кнопкой

 ![Граница прозрачна на нажатой кнопке.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда она нажата

 Визуальные состояния элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе [Стили и шаблоны элемента Control](control-styles-and-templates.md).

<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Задание поведения элемента управления, когда он переходит между состояниями
 В предыдущем примере внешний вид кнопки изменяется, когда пользователь нажимает ее, но если кнопка остается нажатой менее полной секунды, то пользователь не видит эффекта нажатия. По умолчанию для запуска анимации требуется одна секунда. Поскольку пользователи, скорее всего, щелкают и освобождают кнопку в гораздо меньше времени, визуальная обратная связь не будет действовать, если вы оставите <xref:System.Windows.Controls.ControlTemplate> в своем состоянии по умолчанию.

 Можно указать время, затрачиваемое на выполнение анимации, чтобы плавно перевести элемент управления из одного состояния в другое, добавив <xref:System.Windows.VisualTransition> объекты в <xref:System.Windows.Controls.ControlTemplate>. При создании <xref:System.Windows.VisualTransition>необходимо указать один или несколько из следующих элементов:

- время, которое занимает переход между состояниями;

- дополнительные изменения внешнего вида элемента управления, возникающие во время перехода;

- Состояние, к которому применяется <xref:System.Windows.VisualTransition>.

### <a name="specifying-the-duration-of-a-transition"></a>Задание продолжительности перехода
 Можно указать, как долго выполняется переход, установив свойство <xref:System.Windows.VisualTransition.GeneratedDuration%2A>. В предыдущем примере имеется <xref:System.Windows.VisualState>, указывающий, что граница кнопки становится прозрачной при нажатии кнопки, но анимация занимает слишком много времени, чтобы быть заметной при быстром нажатии и отпускании кнопки. Можно использовать <xref:System.Windows.VisualTransition>, чтобы указать период времени, в течение которого элемент управления переходит в состояние нажатия. В следующем примере задается, что переход элемента управления в нажатое состояние занимает одну сотую секунды.

 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]

### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Задание изменений внешнего вида элемента управления во время перехода
 <xref:System.Windows.VisualTransition> содержит <xref:System.Windows.Media.Animation.Storyboard>, который начинается при переходе элемента управления между состояниями. Например, можно указать, что определенная анимация происходит при переходе элемента управления из состояния `MouseOver` в состояние `Normal`. В следующем примере создается <xref:System.Windows.VisualTransition>, указывающий, что когда пользователь перемещает указатель мыши за пределы кнопки, граница кнопки меняется на синий, затем на желтый, затем на черный через 1,5 секунд.

 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]

### <a name="specifying-when-a-visualtransition-is-applied"></a>Указание места применения VisualTransition
 <xref:System.Windows.VisualTransition> может быть ограничена только определенными состояниями, или его можно применять при каждом переходе элемента управления между состояниями. В предыдущем примере <xref:System.Windows.VisualTransition> применяется при переходе элемента управления из состояния `MouseOver` в состояние `Normal`; в приведенном выше примере <xref:System.Windows.VisualTransition> применяется при переходе элемента управления в состояние `Pressed`. Вы ограничиваете применение <xref:System.Windows.VisualTransition>, устанавливая свойства <xref:System.Windows.VisualTransition.To%2A> и <xref:System.Windows.VisualTransition.From%2A>. В таблице ниже приведено описание уровней ограничений от наибольшего до наименьшего.

|Тип ограничения|Состояние, из которого выполняется переход|Состояние, в которое выполняется переход|
|-------------------------|-------------------|-----------------|
|Из указанного состояния в другое указанное состояние|Имя <xref:System.Windows.VisualState>|Имя <xref:System.Windows.VisualState>|
|Из любого состояния в указанное состояние|Не задано|Имя <xref:System.Windows.VisualState>|
|Из указанного состояния в любое состояние|Имя <xref:System.Windows.VisualState>|Не задано|
|Из любого состояния в любое другое состояние|Не задано|Не задано|

 В <xref:System.Windows.VisualStateGroup>, которые ссылаются на одно и то же состояние, можно использовать несколько <xref:System.Windows.VisualTransition> объектов, но они будут использоваться в порядке, указанном в предыдущей таблице. В следующем примере имеется два <xref:System.Windows.VisualTransition> объектов. Когда элемент управления переходит из состояния `Pressed` в состояние `MouseOver`, используется <xref:System.Windows.VisualTransition>, в котором заданы как <xref:System.Windows.VisualTransition.From%2A>, так и <xref:System.Windows.VisualTransition.To%2A>. Когда элемент управления переходит из состояния, отличного от `Pressed`, в состояние `MouseOver`, используется другой объект.

 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]

 <xref:System.Windows.VisualStateGroup> имеет свойство <xref:System.Windows.VisualStateGroup.Transitions%2A>, содержащее объекты <xref:System.Windows.VisualTransition>, которые применяются к <xref:System.Windows.VisualState> объектам в <xref:System.Windows.VisualStateGroup>. Как автор <xref:System.Windows.Controls.ControlTemplate>, вы можете включать любые <xref:System.Windows.VisualTransition>. Однако если для свойств <xref:System.Windows.VisualTransition.To%2A> и <xref:System.Windows.VisualTransition.From%2A> заданы имена состояний, которые не находятся в <xref:System.Windows.VisualStateGroup>, <xref:System.Windows.VisualTransition> игнорируется.

 В следующем примере показаны <xref:System.Windows.VisualStateGroup> для `CommonStates`. В примере определяется <xref:System.Windows.VisualTransition> для каждого из следующих переходов кнопки.

- в состояние `Pressed`;

- в состояние `MouseOver`;

- из состояния `Pressed` в состояние `MouseOver`;

- из состояния `MouseOver` в состояние `Normal`;

 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]

<a name="customizing_other_controls_by_understanding_the_control_contract"></a>
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Настройка других элементов управления через понимание контракта элемента управления
 Элемент управления, использующий <xref:System.Windows.Controls.ControlTemplate> для указания его визуальной структуры (с помощью <xref:System.Windows.FrameworkElement> объектов) и визуального поведения (с помощью <xref:System.Windows.VisualState> объектов) использует модель управления частями. Множество элементов управления, имеющихся в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4, используют эту модель. Части, которые необходимо учитывать автору <xref:System.Windows.Controls.ControlTemplate>, взаимодействуют через контракт управления. Поняв части контракта элемента управления, можно настроить внешний вид любого элемента управления, использующего модель частей элемента управления.

 Контракт элемента управления имеет три элемента:

- визуальный элемент, используемый логикой элемента управления;

- состояния элемента управления и группа, к которой принадлежит каждое состояние;

- общие свойства, визуально воздействующие на элемент управления.

### <a name="visual-elements-in-the-control-contract"></a>Визуальные элементы в контракте элемента управления
 Иногда логика элемента управления взаимодействует с <xref:System.Windows.FrameworkElement>, который находится в <xref:System.Windows.Controls.ControlTemplate>. Например, элемент управления может обрабатывать событие одного из своих элементов. Когда элемент управления планирует найти определенный <xref:System.Windows.FrameworkElement> в <xref:System.Windows.Controls.ControlTemplate>, он должен передать эту информацию автору <xref:System.Windows.Controls.ControlTemplate>. Элемент управления использует <xref:System.Windows.TemplatePartAttribute>, чтобы передать ожидаемый тип элемента и имя элемента. <xref:System.Windows.Controls.Button> не содержит <xref:System.Windows.FrameworkElement> частей в контракте элемента управления, но другие элементы управления, такие как <xref:System.Windows.Controls.ComboBox>, делают.

 В следующем примере показаны объекты <xref:System.Windows.TemplatePartAttribute>, указанные в классе <xref:System.Windows.Controls.ComboBox>. Логика <xref:System.Windows.Controls.ComboBox> планирует найти в `PART_Popup`е <xref:System.Windows.Controls.TextBox> с именем `PART_EditableTextBox` и <xref:System.Windows.Controls.Primitives.Popup> с именем <xref:System.Windows.Controls.ControlTemplate>.

 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]

 В следующем примере показано упрощенное <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ComboBox>, включающего элементы, заданные <xref:System.Windows.TemplatePartAttribute>ными объектами в классе <xref:System.Windows.Controls.ComboBox>.

 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]

### <a name="states-in-the-control-contract"></a>Состояния в контракте элемента управления
 Состояния элемента управления также являются частью контракта элемента управления. Пример создания <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> показывает, как задать внешний вид <xref:System.Windows.Controls.Button> в зависимости от его состояний. Можно создать <xref:System.Windows.VisualState> для каждого заданного состояния и разместить все <xref:System.Windows.VisualState> объекты, совместно использующие <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A>, в <xref:System.Windows.VisualStateGroup>, как описано в разделе [Изменение внешнего вида элемента управления в зависимости от его состояния](#changing_the_appearance_of_a_control_depending_on_its_state) ранее в этой статье. Сторонние элементы управления должны указывать состояния с помощью <xref:System.Windows.TemplateVisualStateAttribute>, что позволяет средствам конструктора, таким как [конструктор XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio) в Visual Studio и Blend для Visual Studio, предоставлять состояния элемента управления для создания шаблонов элементов управления.

 Контракты элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Стили и шаблоны элемента Control](control-styles-and-templates.md).

### <a name="properties-in-the-control-contract"></a>Свойства в контракте элемента управления
 Общие свойства, визуально влияющие на элемент управления, также включаются в контракт элемента управления. Эти свойства можно задать, чтобы изменить внешний вид элемента управления без создания нового <xref:System.Windows.Controls.ControlTemplate>. Расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) также можно использовать для привязки свойств элементов, которые находятся в <xref:System.Windows.Controls.ControlTemplate>, к общим свойствам, определенным <xref:System.Windows.Controls.Button>.

 В следующем примере показан контракт элемента управления "Кнопка".

 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]

 При создании <xref:System.Windows.Controls.ControlTemplate>проще всего начать с существующего <xref:System.Windows.Controls.ControlTemplate> и внести в него изменения. Для изменения существующего <xref:System.Windows.Controls.ControlTemplate>можно выполнить одно из следующих действий.

- Используйте конструктор, например Blend для Visual Studio, который предоставляет графический пользовательский интерфейс для создания шаблонов элементов управления. Дополнительные сведения см. в статье [Настройка стиля элемента управления, поддерживающего шаблон](https://go.microsoft.com/fwlink/?LinkId=161153).

- Получите <xref:System.Windows.Controls.ControlTemplate> по умолчанию и измените его. Шаблоны элементов управления по умолчанию, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в документе [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252).

<a name="complete_example"></a>
## <a name="complete-example"></a>Полный пример
 В следующем примере показан полный <xref:System.Windows.Controls.Button><xref:System.Windows.Controls.ControlTemplate>, который рассматривается в этом разделе.

 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]

## <a name="see-also"></a>См. также

- [Стилизация и использование шаблонов](styling-and-templating.md)
