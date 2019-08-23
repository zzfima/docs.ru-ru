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
ms.openlocfilehash: 63a0b724b71c4a4901c2dedcf502045a75ec405c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933722"
---
# <a name="customizing-the-appearance-of-an-existing-control-by-creating-a-controltemplate"></a>Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate
<a name="introduction"></a>Объект <xref:System.Windows.Controls.ControlTemplate> задает визуальную структуру и визуальное поведение элемента управления. Внешний вид элемента управления можно настроить, присвоив ему новый <xref:System.Windows.Controls.ControlTemplate>. При создании <xref:System.Windows.Controls.ControlTemplate>вы заменяете внешний вид существующего элемента управления, не изменяя его функциональность. Например, можно сделать так, чтобы кнопки в приложении округлялись вместо квадратной фигуры по умолчанию, но кнопка по-прежнему будет <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывать событие.  
  
 В этом разделе объясняются различные части <xref:System.Windows.Controls.ControlTemplate>, демонстрируется создание простого <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button>, а также объясняется, как определить контракт элемента управления, чтобы можно было настроить его внешний вид. Поскольку вы создаете <xref:System.Windows.Controls.ControlTemplate> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], можно изменить внешний вид элемента управления без написания какого-либо кода. Можно также использовать конструктор, например Microsoft Expression Blend, чтобы создать шаблоны пользовательского элемента управления. В этом разделе приведены примеры в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , которые настраивают внешний вид <xref:System.Windows.Controls.Button> и перечислены полные примеры в конце раздела. Дополнительные сведения об использовании Expression Blend см. в статье [Настройка стиля элемента управления, поддерживающего шаблон](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
 На следующих иллюстрациях показан <xref:System.Windows.Controls.Button> объект, который <xref:System.Windows.Controls.ControlTemplate> использует объект, созданный в этом разделе.  
  
 ![Кнопка с пользовательским шаблоном элемента управления.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Кнопка, использующая пользовательский шаблон элемента управления  
  
 ![Кнопка с красной границей.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Кнопка, использующая пользовательский шаблон элемента управления, когда на ней находится указатель мыши  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что пользователь понимает процесс создания и использования элементов управления и стилей, который рассматривался в разделе [Элементы управления](index.md). Концепции, обсуждаемые в этом разделе, применяются к элементам, которые <xref:System.Windows.Controls.Control> наследуются от класса <xref:System.Windows.Controls.UserControl>, за исключением. <xref:System.Windows.Controls.ControlTemplate> К нельзя применять. <xref:System.Windows.Controls.UserControl>  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## <a name="when-you-should-create-a-controltemplate"></a>Когда следует создавать объект ControlTemplate  
 Элементы управления имеют много свойств, таких <xref:System.Windows.Controls.Border.Background%2A>как <xref:System.Windows.Controls.Control.Foreground%2A>, и <xref:System.Windows.Controls.Control.FontFamily%2A>, которые можно задать для задания различных аспектов внешнего вида элемента управления, но изменения, которые можно выполнить путем установки этих свойств, ограничены. Например, можно задать <xref:System.Windows.Controls.Control.Foreground%2A> для свойства синий цвет и <xref:System.Windows.Controls.Control.FontStyle%2A> курсив на <xref:System.Windows.Controls.CheckBox>.  
  
 Без возможности создания новых <xref:System.Windows.Controls.ControlTemplate> элементов управления для всех элементов управления в каждом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]приложении будет иметь одинаковый общий внешний вид, что ограничит возможность создания приложения с пользовательским внешним видом и поведением. По умолчанию каждый <xref:System.Windows.Controls.CheckBox> из них имеет похожие характеристики. Например, содержимое <xref:System.Windows.Controls.CheckBox> элемента всегда находится справа от индикатора выбора, а галочка всегда используется для указания того, что выбрано значение <xref:System.Windows.Controls.CheckBox> .  
  
 Вы создаете <xref:System.Windows.Controls.ControlTemplate> , когда нужно настроить внешний вид элемента управления, помимо того, что устанавливает другие свойства элемента управления. Предположим, что содержимое флажка находится над индикатором выделения, и необходимо, чтобы значение X указывало <xref:System.Windows.Controls.CheckBox> на выбранное значение. <xref:System.Windows.Controls.CheckBox> Эти изменения указываются в параметре <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>объекта.  
  
 На следующем рисунке показан объект <xref:System.Windows.Controls.CheckBox> , который использует значение <xref:System.Windows.Controls.ControlTemplate>по умолчанию.  
  
 ![Флажок с шаблоном элемента управления по умолчанию.](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию  
  
 На следующем рисунке показан объект <xref:System.Windows.Controls.CheckBox> , который использует пользовательский <xref:System.Windows.Controls.ControlTemplate> объект для <xref:System.Windows.Controls.CheckBox> размещения содержимого над индикатором <xref:System.Windows.Controls.CheckBox> выделения и отображает X при выборе.  
  
 ![Флажок с пользовательским шаблоном элемента управления.](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления  
  
 Для в этом примере относительно сложный, поэтому в этом разделе используется <xref:System.Windows.Controls.ControlTemplate> более простой пример создания для <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.CheckBox>  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## <a name="changing-the-visual-structure-of-a-control"></a>Изменение визуальной структуры элемента управления  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]элемент управления часто представляет собой составные <xref:System.Windows.FrameworkElement> объекты. При создании <xref:System.Windows.Controls.ControlTemplate>вы объединяете <xref:System.Windows.FrameworkElement> объекты для создания одного элемента управления. Элемент должен иметь только один <xref:System.Windows.FrameworkElement> в качестве корневого элемента. <xref:System.Windows.Controls.ControlTemplate> Корневой элемент обычно содержит другие <xref:System.Windows.FrameworkElement> объекты. Комбинация объектов составляет визуальную структуру элемента управления.  
  
 В следующем примере создается пользовательский <xref:System.Windows.Controls.ControlTemplate> объект <xref:System.Windows.Controls.Button>для. Создает визуальную структуру <xref:System.Windows.Controls.Button>. <xref:System.Windows.Controls.ControlTemplate> В этом примере не меняется внешний вид кнопки при перемещении на нее указателя мыши или при ее нажатии. Изменение внешнего вида кнопки при ее переходе в другое состояние рассматривается далее в этом разделе.  
  
 В данном примере визуальная структура состоит из следующих частей:  
  
- Имя, служащее корнем <xref:System.Windows.FrameworkElement>шаблона. <xref:System.Windows.Controls.Border> `RootElement`  
  
- Объект <xref:System.Windows.Controls.Grid> , являющийся `RootElement`дочерним элементом.  
  
- Объект <xref:System.Windows.Controls.ContentPresenter> , отображающий содержимое кнопки. <xref:System.Windows.Controls.ContentPresenter> Позволяет отображать любой тип объекта.  
  
 [!code-xaml[VSMButtonTemplate#BasicTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### <a name="preserving-the-functionality-of-a-controls-properties-by-using-templatebinding"></a>Сохранение функциональности свойств элемента управления с помощью TemplateBinding  
 При создании нового <xref:System.Windows.Controls.ControlTemplate>для изменения внешнего вида элемента управления может потребоваться использовать открытые свойства. Расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) привязывает свойство элемента, который находится в, <xref:System.Windows.Controls.ControlTemplate> к открытому свойству, определенному элементом управления. Использование расширения [TemplateBinding](../advanced/templatebinding-markup-extension.md) позволяет свойствам элемента управления действовать в качестве параметров шаблона. Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../advanced/templatebinding-markup-extension.md).  
  
 В следующем примере повторяется часть предыдущего примера, в которой используется расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) для привязки свойств элементов, которые находятся в, <xref:System.Windows.Controls.ControlTemplate> к общим свойствам, определенным кнопкой.  
  
 [!code-xaml[VSMButtonTemplate#TemplateBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 В этом примере <xref:System.Windows.Controls.Grid> шаблон <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> свойства имеет привязанный к <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType>. Так <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> как является привязанным шаблоном, можно создать несколько кнопок, которые <xref:System.Windows.Controls.ControlTemplate> используют один и <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> тот же параметр, и задать разные значения для каждой кнопки. Если <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> шаблон не привязан к свойству элемента <xref:System.Windows.Controls.ControlTemplate>в, установка <xref:System.Windows.Controls.Control.Background%2A?displayProperty=nameWithType> элемента кнопки не повлияет на внешний вид кнопки.  
  
 Следует отметить, что не требуется, чтобы имена этих двух свойств совпадали. В предыдущем примере <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> свойство <xref:System.Windows.Controls.Button> шаблона <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType> имеет значение, привязанное <xref:System.Windows.Controls.ContentPresenter>к свойству объекта. Это позволяет располагать содержимое кнопки горизонтально. <xref:System.Windows.Controls.ContentPresenter>не имеет свойства с именем `HorizontalContentAlignment`, но <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=nameWithType> может быть привязано к <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=nameWithType>. Перед привязкой свойства к шаблону следует убедиться, что целевое и исходное свойства имеют один и тот же тип.  
  
 <xref:System.Windows.Controls.Control> Класс определяет несколько свойств, которые должны использоваться шаблоном элемента управления для получения влияния на элемент управления, когда они заданы. <xref:System.Windows.Controls.ControlTemplate> Использование свойства зависит от свойства. Параметр <xref:System.Windows.Controls.ControlTemplate> должен использовать свойство одним из следующих способов:  
  
- Элемент в <xref:System.Windows.Controls.ControlTemplate> шаблоне привязывается к свойству.  
  
- Элемент в <xref:System.Windows.Controls.ControlTemplate> класса наследует свойство от родителя <xref:System.Windows.FrameworkElement>.  
  
 В следующей таблице перечислены визуальные свойства, наследуемые элементом управления <xref:System.Windows.Controls.Control> от класса. В таблице также указывается, использует ли шаблон элемента управления по умолчанию значение наследуемого свойства или оно должно быть привязано к шаблону.  
  
|Свойство.|Способ использования|  
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
  
 В таблице перечислены только визуальные свойства, унаследованные <xref:System.Windows.Controls.Control> от класса. Помимо свойств, перечисленных в таблице, элемент управления может также наследовать <xref:System.Windows.FrameworkElement.DataContext%2A>свойства, <xref:System.Windows.FrameworkElement.Language%2A>и <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> из родительского элемента Framework.  
  
 Кроме того, если <xref:System.Windows.Controls.ContentPresenter> находится <xref:System.Windows.Controls.ControlTemplate> в <xref:System.Windows.Controls.ContentControl>, то <xref:System.Windows.Controls.ContentPresenter> будет автоматически привязан к <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> свойствам и <xref:System.Windows.Controls.ContentControl.Content%2A> . Аналогично, <xref:System.Windows.Controls.ItemsPresenter> , который находится в <xref:System.Windows.Controls.ControlTemplate> , <xref:System.Windows.Controls.ItemsControl> будет автоматически привязан к <xref:System.Windows.Controls.ItemsControl.Items%2A> свойствам и <xref:System.Windows.Controls.ItemsPresenter> .  
  
 В следующем примере создаются две кнопки, которые используют <xref:System.Windows.Controls.ControlTemplate> объект, определенный в предыдущем примере. В примере <xref:System.Windows.Controls.Control.Background%2A>задаются <xref:System.Windows.Controls.Control.Foreground%2A>свойства, <xref:System.Windows.Controls.Control.FontSize%2A> и для каждой кнопки. Установка свойства оказывает воздействие, <xref:System.Windows.Controls.ControlTemplate>так как оно привязано к шаблону в. <xref:System.Windows.Controls.Control.Background%2A> Несмотря на то <xref:System.Windows.Controls.Control.Foreground%2A> , <xref:System.Windows.Controls.Control.FontSize%2A> что свойства и не привязаны к шаблону, их установка оказывает воздействие, поскольку их значения наследуются.  
  
 [!code-xaml[VSMButtonTemplate#ButtonDeclaration](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 В предыдущем примере получался результат, аналогичный показанному на следующем рисунке.  
  
 ![Две кнопки, одна синяя и одна фиолетовой.](./media/ndp-buttontwo.png "NDP_ButtonTwo")  
Две кнопки с различными цветами фона  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## <a name="changing-the-appearance-of-a-control-depending-on-its-state"></a>Изменение внешнего вида элемента управления в зависимости от его состояния  
 Разница между кнопкой с внешним видом по умолчанию и кнопкой из предыдущего примера состоит в том, что кнопка по умолчанию слегка изменяется при переходе в другое состояние. Например, внешний вид кнопки по умолчанию изменяется при нажатии этой кнопки или при наведении на нее указателя мыши. <xref:System.Windows.Controls.ControlTemplate> Хотя компонент не изменяет функциональные возможности элемента управления, он изменяет визуальное поведение элемента управления. Визуальное поведение описывает внешний вид элемента управления в определенных состояниях. Чтобы лучше понять разницу между функциональностью и визуальным поведением элемента управления, рассмотрим пример с кнопкой. Функциональность кнопки заключается в вызове <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события при его щелчке, но визуальное поведение кнопки заключается в том, чтобы изменить внешний вид, на который указывает или нажата кнопка.  
  
 Объекты используются <xref:System.Windows.VisualState> для задания внешнего вида элемента управления, если он находится в определенном состоянии. Объект <xref:System.Windows.VisualState> содержит объект <xref:System.Windows.Media.Animation.Storyboard> , который изменяет внешний вид <xref:System.Windows.Controls.ControlTemplate>элементов в. Для этого не нужно писать код, так как логика элемента управления меняет состояние с помощью <xref:System.Windows.VisualStateManager>. Когда элемент управления переходит в состояние, заданное <xref:System.Windows.VisualState.Name%2A?displayProperty=nameWithType> свойством <xref:System.Windows.Media.Animation.Storyboard> , начинается. Когда элемент управления выходит из состояния, <xref:System.Windows.Media.Animation.Storyboard> останавливается.  
  
 В следующем примере показано <xref:System.Windows.VisualState> , что изменяет внешний вид <xref:System.Windows.Controls.Button> объекта при наведении на него указателя мыши. Изменяет цвет границы кнопки, изменяя цвет `BorderBrush`. <xref:System.Windows.Media.Animation.Storyboard> Если вы ссылаетесь на <xref:System.Windows.Controls.ControlTemplate> пример в начале этого раздела, то помните, что `BorderBrush` <xref:System.Windows.Media.SolidColorBrush> это имя, назначенное для <xref:System.Windows.Controls.Border.Background%2A> объекта <xref:System.Windows.Controls.Border>.  
  
 [!code-xaml[VSMButtonTemplate#4](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Элемент управления отвечает за определение состояний как часть своего контракта, что подробно рассматривается в подразделе [Настройка других элементов управления через понимание контракта элемента управления](#customizing_other_controls_by_understanding_the_control_contract) далее в этом разделе. В следующей таблице перечислены состояния, указанные для <xref:System.Windows.Controls.Button>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|----------------------|---------------------------|-----------------|  
|Обычный|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Нажато|CommonStates|Элемент управления нажат.|  
|отключено|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Без фокуса ввода|FocusStates|Элемент управления не имеет фокуса.|  
  
 `CommonStates` `Normal` `MouseOver` `Pressed`Определяет две группы состояний: группа содержит состояния,, и `Disabled`. <xref:System.Windows.Controls.Button> Группа `FocusStates` содержит состояния `Focused` и `Unfocused`. Состояния, входящие в одну группу, являются взаимоисключающими. Элемент управления всегда находится строго в одном состоянии из каждой группы. <xref:System.Windows.Controls.Button> Например, элемент может иметь фокус, даже если указатель мыши не находится над ним, <xref:System.Windows.Controls.Button> поэтому в `Focused` состоянии может находиться `MouseOver`состояние, `Pressed`или `Normal` .  
  
 Объекты добавляются <xref:System.Windows.VisualState> в <xref:System.Windows.VisualStateGroup> объекты. Объекты добавляются <xref:System.Windows.VisualStateGroup> <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> в присоединенное свойство. В следующем примере определяются <xref:System.Windows.VisualState> объекты `Normal`для состояний, `MouseOver` `CommonStates` и `Pressed` , которые находятся в группе. Каждый из них <xref:System.Windows.VisualState> соответствует имени в предыдущей таблице. <xref:System.Windows.VisualState.Name%2A> Состояние `Disabled` и состояния из группы `FocusStates` опущены для сохранения краткости примера, но они включены в полный пример, приведенный в конце этого раздела.  
  
> [!NOTE]
> Обязательно задайте <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> присоединенное свойство в корне <xref:System.Windows.FrameworkElement> <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMButtonTemplate#VisualStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 В предыдущем примере получался результат, аналогичный показанному на следующих рисунках.  
  
 ![Кнопка с пользовательским шаблоном элемента управления.](./media/ndp-buttonnormal.png "NDP_ButtonNormal")  
Кнопка, использующая пользовательский шаблон элемента управления в нормальном состоянии  
  
 ![Кнопка с красной границей.](./media/ndp-buttonmouseover.png "NDP_ButtonMouseOver")  
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда указатель мыши находится над кнопкой  
  
 ![Граница прозрачна для нажатой кнопки.](./media/ndp-buttonpressed.png "NDP_ButtonPressed")  
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда она нажата  
  
 Визуальные состояния элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе [Стили и шаблоны элемента Control](control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## <a name="specifying-the-behavior-of-a-control-when-it-transitions-between-states"></a>Задание поведения элемента управления, когда он переходит между состояниями  
 В предыдущем примере внешний вид кнопки изменяется, когда пользователь нажимает ее, но если кнопка остается нажатой менее полной секунды, то пользователь не видит эффекта нажатия. По умолчанию для запуска анимации требуется одна секунда. Поскольку пользователи, скорее всего, щелкают и освобождают кнопку в гораздо меньше времени, визуальная обратная связь не будет действовать, если <xref:System.Windows.Controls.ControlTemplate> оставить ее в своем состоянии по умолчанию.  
  
 Можно указать время, затрачиваемое на выполнение анимации для плавного переноса элемента управления из одного состояния в другое путем добавления <xref:System.Windows.VisualTransition> объектов <xref:System.Windows.Controls.ControlTemplate>в. При создании <xref:System.Windows.VisualTransition>можно указать один или несколько из следующих элементов:  
  
- время, которое занимает переход между состояниями;  
  
- дополнительные изменения внешнего вида элемента управления, возникающие во время перехода;  
  
- Состояние, <xref:System.Windows.VisualTransition> к которому применяется.  
  
### <a name="specifying-the-duration-of-a-transition"></a>Задание продолжительности перехода  
 Можно указать, как долго выполняется переход, задав <xref:System.Windows.VisualTransition.GeneratedDuration%2A> свойство. В предыдущем примере имеется объект <xref:System.Windows.VisualState> , указывающий, что граница кнопки становится прозрачной при нажатии кнопки, но анимация занимает слишком много времени, чтобы быть заметной при быстром нажатии и отпускании кнопки. Можно использовать, <xref:System.Windows.VisualTransition> чтобы указать период времени, в течение которого элемент управления переходит в состояние нажатия. В следующем примере задается, что переход элемента управления в нажатое состояние занимает одну сотую секунды.  
  
 [!code-xaml[VSMButtonTemplate#PressedTransition](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### <a name="specifying-changes-to-the-controls-appearance-during-a-transition"></a>Задание изменений внешнего вида элемента управления во время перехода  
 <xref:System.Windows.VisualTransition> Содержит,которыйначинается,когдаэлементуправления<xref:System.Windows.Media.Animation.Storyboard> переходит между состояниями. Например, можно указать, что определенная анимация происходит при переходе элемента управления из состояния `MouseOver` в состояние `Normal`. В следующем примере создается объект <xref:System.Windows.VisualTransition> , указывающий, что когда пользователь перемещает указатель мыши за пределы кнопки, граница кнопки меняется на синий, затем на желтый, затем на черный через 1,5 секунд.  
  
 [!code-xaml[VSMButtonTemplate#8](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### <a name="specifying-when-a-visualtransition-is-applied"></a>Указание места применения VisualTransition  
 <xref:System.Windows.VisualTransition> Может быть ограничена только определенными состояниями или его можно применять при каждом переходе элемента управления между состояниями. В <xref:System.Windows.VisualTransition> предыдущем примере атрибут применяется, когда элемент управления переходит `Normal` `MouseOver` из состояния в состояние. в примере перед этим применяется, <xref:System.Windows.VisualTransition> когда элемент управления переходит `Pressed` в состояние. Вы ограничиваете <xref:System.Windows.VisualTransition> применение, <xref:System.Windows.VisualTransition.To%2A> устанавливая свойства и <xref:System.Windows.VisualTransition.From%2A> . В таблице ниже приведено описание уровней ограничений от наибольшего до наименьшего.  
  
|Тип ограничения|Состояние, из которого выполняется переход|Состояние, в которое выполняется переход|  
|-------------------------|-------------------|-----------------|  
|Из указанного состояния в другое указанное состояние|Имя<xref:System.Windows.VisualState>|Имя<xref:System.Windows.VisualState>|  
|Из любого состояния в указанное состояние|Не задано|Имя<xref:System.Windows.VisualState>|  
|Из указанного состояния в любое состояние|Имя<xref:System.Windows.VisualState>|Не задано|  
|Из любого состояния в любое другое состояние|Не задано|Не задано|  
  
 В можно иметь несколько <xref:System.Windows.VisualTransition> объектов ,ссылающихсянаодноитожесостояние,ноонибудутиспользоватьсявпорядке,указанномвпредыдущейтаблице.<xref:System.Windows.VisualStateGroup> В следующем примере есть два <xref:System.Windows.VisualTransition> объекта. Когда элемент управления переходит из `Pressed` состояния `MouseOver` в состояние, используется объект <xref:System.Windows.VisualTransition> , который имеет оба <xref:System.Windows.VisualTransition.From%2A> параметра <xref:System.Windows.VisualTransition.To%2A> и. Когда элемент управления переходит из состояния, отличного от `Pressed`, в состояние `MouseOver`, используется другой объект.  
  
 [!code-xaml[VSMButtonTemplate#7](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 <xref:System.Windows.VisualState> Содержитсвойство,<xref:System.Windows.VisualStateGroup>которое содержит <xref:System.Windows.VisualTransition> объекты, применяемые к объектам в. <xref:System.Windows.VisualStateGroup.Transitions%2A> <xref:System.Windows.VisualStateGroup> Как автор, вы можете включить все <xref:System.Windows.VisualTransition> необходимые. <xref:System.Windows.Controls.ControlTemplate> Однако если <xref:System.Windows.VisualTransition.To%2A> для свойств и <xref:System.Windows.VisualTransition.From%2A> заданы имена состояний <xref:System.Windows.VisualStateGroup>, которых нет в, то <xref:System.Windows.VisualTransition> игнорируется.  
  
 В следующем примере показана <xref:System.Windows.VisualStateGroup> `CommonStates`для. В примере определяется <xref:System.Windows.VisualTransition> для каждой из следующих переходов кнопки.  
  
- в состояние `Pressed`;  
  
- в состояние `MouseOver`;  
  
- из состояния `Pressed` в состояние `MouseOver`;  
  
- из состояния `MouseOver` в состояние `Normal`.  
  
 [!code-xaml[VSMButtonTemplate#VisualTransitions](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## <a name="customizing-other-controls-by-understanding-the-control-contract"></a>Настройка других элементов управления через понимание контракта элемента управления  
 Элемент управления, использующий <xref:System.Windows.Controls.ControlTemplate> для указания его визуальной структуры (с помощью <xref:System.Windows.FrameworkElement> объектов) и визуального поведения <xref:System.Windows.VisualState> (с помощью объектов), использует модель элемента управления Parts. Множество элементов управления, имеющихся в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4, используют эту модель. Части, которые <xref:System.Windows.Controls.ControlTemplate> необходимо учитывать автору, передаются через контракт управления. Поняв части контракта элемента управления, можно настроить внешний вид любого элемента управления, использующего модель частей элемента управления.  
  
 Контракт элемента управления имеет три элемента:  
  
- визуальный элемент, используемый логикой элемента управления;  
  
- состояния элемента управления и группа, к которой принадлежит каждое состояние;  
  
- общие свойства, визуально воздействующие на элемент управления.  
  
### <a name="visual-elements-in-the-control-contract"></a>Визуальные элементы в контракте элемента управления  
 Иногда логика элемента управления взаимодействует с элементом <xref:System.Windows.FrameworkElement> , который находится <xref:System.Windows.Controls.ControlTemplate>в. Например, элемент управления может обрабатывать событие одного из своих элементов. Когда элемент управления должен найти конкретный <xref:System.Windows.FrameworkElement> объект <xref:System.Windows.Controls.ControlTemplate>в, ему необходимо <xref:System.Windows.Controls.ControlTemplate> передать эту информацию автору. Элемент управления использует объект <xref:System.Windows.TemplatePartAttribute> для передачи ожидаемого типа элемента и имя элемента. Не содержит <xref:System.Windows.FrameworkElement> частей в контракте элемента управления, но другие <xref:System.Windows.Controls.ComboBox>элементы управления, такие как, делают. <xref:System.Windows.Controls.Button>  
  
 В следующем примере показаны <xref:System.Windows.TemplatePartAttribute> объекты, указанные <xref:System.Windows.Controls.ComboBox> в классе. <xref:System.Windows.Controls.ComboBox> Логика <xref:System.Windows.Controls.ControlTemplate>, которой требуется `PART_EditableTextBox` <xref:System.Windows.Controls.TextBox> найти именованный объект и <xref:System.Windows.Controls.Primitives.Popup> имя `PART_Popup` в нем.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 В следующем примере <xref:System.Windows.Controls.ControlTemplate> показана упрощенная <xref:System.Windows.Controls.ComboBox> для, включающая элементы <xref:System.Windows.TemplatePartAttribute> , заданные объектами <xref:System.Windows.Controls.ComboBox> класса.  
  
 [!code-xaml[VSMButtonTemplate#ComboBoxTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### <a name="states-in-the-control-contract"></a>Состояния в контракте элемента управления  
 Состояния элемента управления также являются частью контракта элемента управления. В примере создания <xref:System.Windows.Controls.ControlTemplate> для a <xref:System.Windows.Controls.Button> показано, как задать внешний вид объекта в <xref:System.Windows.Controls.Button> зависимости от его состояний. Вы создаете <xref:System.Windows.VisualState> для каждого заданного состояния и размещаете <xref:System.Windows.VisualState> все объекты, <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> <xref:System.Windows.VisualStateGroup>которые совместно используют в, как описано в разделе [Изменение внешнего вида элемента управления в зависимости от его состояния](#changing_the_appearance_of_a_control_depending_on_its_state) ранее в этой статье. Сторонние элементы управления должны указывать состояния с помощью <xref:System.Windows.TemplateVisualStateAttribute>, что позволяет средствам конструктора, таким как Expression Blend, предоставлять состояния элемента управления для создания шаблонов элементов управления.  
  
 Контракты элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Стили и шаблоны элемента Control](control-styles-and-templates.md).  
  
### <a name="properties-in-the-control-contract"></a>Свойства в контракте элемента управления  
 Общие свойства, визуально влияющие на элемент управления, также включаются в контракт элемента управления. Эти свойства можно задать, чтобы изменить внешний вид элемента управления без создания нового <xref:System.Windows.Controls.ControlTemplate>. Расширение разметки [TemplateBinding](../advanced/templatebinding-markup-extension.md) можно также использовать для привязки свойств элементов, которые находятся в, <xref:System.Windows.Controls.ControlTemplate> к общим свойствам, определенным <xref:System.Windows.Controls.Button>в.  
  
 В следующем примере показан контракт элемента управления "Кнопка".  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 При создании объект <xref:System.Windows.Controls.ControlTemplate>, как правило, проще всего начать с существующего <xref:System.Windows.Controls.ControlTemplate> и внести в него изменения. Можно выполнить одно из следующих действий, чтобы изменить существующий <xref:System.Windows.Controls.ControlTemplate>:  
  
- Воспользоваться конструктором, таким как Expression Blend, который предоставляет графический пользовательский интерфейс для создания шаблонов элементов управления. Дополнительные сведения см. в статье [Настройка стиля элемента управления, поддерживающего шаблон](https://go.microsoft.com/fwlink/?LinkId=161153).  
  
- Получите значение по <xref:System.Windows.Controls.ControlTemplate> умолчанию и измените его. Шаблоны элементов управления по умолчанию, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в документе [Default WPF Themes](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Полный пример  
 В следующем примере показан полный <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate> пример, рассмотренный в этом разделе.  
  
 [!code-xaml[VSMButtonTemplate#3](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## <a name="see-also"></a>См. также

- [Стилизация и использование шаблонов](styling-and-templating.md)
