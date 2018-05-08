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
ms.openlocfilehash: 9f539e7dbb105591375857122d738fddd87f6776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Создание элемента управления с настраиваемым внешним видом
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет возможность создания элемента управления, можно настроить, вид. Например, можно изменить внешний вид <xref:System.Windows.Controls.CheckBox> Кроме какие настройки свойств выполняется путем создания нового <xref:System.Windows.Controls.ControlTemplate>. На следующем рисунке показана <xref:System.Windows.Controls.CheckBox> , используется значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> и <xref:System.Windows.Controls.CheckBox> , использующий пользовательский <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Флажок с шаблоном элемента управления по умолчанию. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию  
  
 ![Флажок с пользовательским шаблоном элемента управления. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления  
  
 Если при создании элемента управления модели частей и состояний, внешний вид элемента управления будет настраиваемым. Средства конструктора, таких как Microsoft Expression Blend поддерживает модели частей и состояний, поэтому при следовании этой модели элемент управления будет настраиваемым в таких типах приложений.  Здесь описывается модель частей и состояний и порядок его при создании собственного элемента управления. В этом разделе используется пример пользовательского элемента управления, `NumericUpDown`для иллюстрации философии этой модели.  `NumericUpDown` Элемент управления отображает числовое значение, которое пользователь может увеличить или уменьшить, нажимая кнопки элемента управления.  На следующем рисунке показана `NumericUpDown` элемента управления, описанный в этом разделе.  
  
 ![Пользовательский элемент управления NumericUpDown. ] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
Пользовательский элемент управления NumericUpDown  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Необходимые компоненты](#prerequisites)  
  
-   [Модель частей и состояний](#parts_and_states_model)  
  
-   [Определение визуальную структуру и визуальное поведение элемента управления в шаблоне ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [С помощью частей шаблона элемента управления в коде](#using_parts_of_the_controltemplate_in_code)  
  
-   [Предоставление контракта элемента управления](#providing_the_control_contract)  
  
-   [Полный пример](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что вы знаете, как для создания нового <xref:System.Windows.Controls.ControlTemplate> для существующего элемента управления, знакомых с каковы элементы в контракт элемента управления и понять концепции, описанные в [Настройка внешнего вида существующего элемента управления, Создание шаблона элемента управления](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Чтобы создать элемент управления, который может быть настраиваемым внешним видом, необходимо создать элемент управления, который наследует от <xref:System.Windows.Controls.Control> класс или один из его подклассов, кроме <xref:System.Windows.Controls.UserControl>.  Элемент управления, который наследует от <xref:System.Windows.Controls.UserControl> — это элемент управления, которую можно быстро создать, но он не использует <xref:System.Windows.Controls.ControlTemplate> и изменить его внешний вид невозможно.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Модель частей и состояний  
 Модель частей и состояний указывает способ определения визуальную структуру и визуальное поведение элемента управления. Следовать модели частей и состояний, делать следующее:  
  
-   Определение визуальную структуру и визуальное поведение в <xref:System.Windows.Controls.ControlTemplate> элемента управления.  
  
-   Выполняйте определенные рекомендации, когда логика элемента управления взаимодействует с частями шаблона элемента управления.  
  
-   Укажите контракт элемента управления, чтобы указать, что должны быть включены в <xref:System.Windows.Controls.ControlTemplate>.  
  
 При определении визуальную структуру и визуальное поведение в <xref:System.Windows.Controls.ControlTemplate> элемента управления, разработчики приложения могут изменять визуальную структуру и визуальное поведение элемента управления, создав новую <xref:System.Windows.Controls.ControlTemplate> вместо написания кода.   Необходимо предоставить разработчикам контракт элемента управления, который сообщает приложению, какие <xref:System.Windows.FrameworkElement> объекты и состояния должен быть определен в <xref:System.Windows.Controls.ControlTemplate>. Некоторые рекомендации следовать при взаимодействии с частями в <xref:System.Windows.Controls.ControlTemplate> , чтобы элемент управления обрабатывал незавершенный <xref:System.Windows.Controls.ControlTemplate>.  Если следовать этим трем принципам разработчики приложений будут иметь возможность создавать <xref:System.Windows.Controls.ControlTemplate> для элемента управления точно так же, так же просто, как они могут для элементов управления, поставляемые с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В следующем разделе описываются каждой из этих рекомендаций подробно.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Определение визуальную структуру и визуальное поведение элемента управления в шаблоне ControlTemplate  
 При создании пользовательского элемента управления с помощью модели частей и состояний определяется визуальную структуру и визуальное поведение элемента управления его <xref:System.Windows.Controls.ControlTemplate> вместо в своей логике.  Визуальная структура элемента управления состоит из <xref:System.Windows.FrameworkElement> объекты, составляющие элемента управления.  Визуальное поведение имеет внешний вид элемента управления, когда он находится в определенном состоянии.   Дополнительные сведения о создании <xref:System.Windows.Controls.ControlTemplate> , указывающий визуальную структуру и визуальное поведение элемента управления см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 В качестве примера `NumericUpDown` управления визуальная структура содержит две <xref:System.Windows.Controls.Primitives.RepeatButton> элементов управления и <xref:System.Windows.Controls.TextBlock>.  При добавлении этих элементов управления в коде `NumericUpDown` управления--в конструкторе, например положение этих элементов управления может быть неизменяемым.  Вместо того чтобы определять visual структуру и поведение элемента управления в его код, его следует определить в <xref:System.Windows.Controls.ControlTemplate>.  Затем разработчик приложения может настроить положение кнопок и <xref:System.Windows.Controls.TextBlock> и указать поведение при `Value` отрицательное поскольку <xref:System.Windows.Controls.ControlTemplate> можно заменить.  
  
 Следующий пример показывает структуру visual `NumericUpDown` управления, который включает в себя <xref:System.Windows.Controls.Primitives.RepeatButton> увеличить `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> для уменьшения `Value`и <xref:System.Windows.Controls.TextBlock> для отображения `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Визуальное поведение `NumericUpDown` управления состоит в том, что значение отображается красным цветом отрицательное.  При изменении <xref:System.Windows.Controls.TextBlock.Foreground%2A> из <xref:System.Windows.Controls.TextBlock> в код при `Value` отрицательное, `NumericUpDown` всегда будет отображаться красный отрицательное значение. Укажите визуальное поведение элемента управления в <xref:System.Windows.Controls.ControlTemplate> путем добавления <xref:System.Windows.VisualState> объектов <xref:System.Windows.Controls.ControlTemplate>.  В следующем примере показан <xref:System.Windows.VisualState> объектов для `Positive` и `Negative` состояния.  `Positive` и `Negative` являются взаимоисключающими (элемент управления всегда находится в одном из двух), поэтому в примере <xref:System.Windows.VisualState> объектов в единую <xref:System.Windows.VisualStateGroup>.  Когда элемент управления переходит в `Negative` состояние, <xref:System.Windows.Controls.TextBlock.Foreground%2A> из <xref:System.Windows.Controls.TextBlock> становится красным.  Если элемент управления находится в `Positive` состояние, <xref:System.Windows.Controls.TextBlock.Foreground%2A> он возвращает исходное значение.  Определение <xref:System.Windows.VisualState> объекты в <xref:System.Windows.Controls.ControlTemplate> обсуждается ниже в [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Не забудьте задать <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> вложенное свойство в корне <xref:System.Windows.FrameworkElement> из <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>С помощью частей шаблона элемента управления в коде  
 A <xref:System.Windows.Controls.ControlTemplate> автор опустили <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState> объектов намеренно или по ошибке, но логика элемента управления может потребоваться тех частей, для правильной работы функций. Модель частей и состояний указывает, что элемент управления должен быть устойчив к <xref:System.Windows.Controls.ControlTemplate> , где отсутствует <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState> объектов.  Элемент управления не должно создавать новый отчет или исключение ошибку если <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, или <xref:System.Windows.VisualStateGroup> отсутствует <xref:System.Windows.Controls.ControlTemplate>. В этом разделе описываются рекомендации по взаимодействию с <xref:System.Windows.FrameworkElement> объектов и управление ими состояния.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Ожидается отсутствие FrameworkElement объектов  
 При определении <xref:System.Windows.FrameworkElement> объекты в <xref:System.Windows.Controls.ControlTemplate>, логика элемента управления может потребоваться взаимодействовать с некоторыми из них.  Например `NumericUpDown` управления подписывается кнопок <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий для увеличения или уменьшения `Value` и задает <xref:System.Windows.Controls.TextBlock.Text%2A> свойство <xref:System.Windows.Controls.TextBlock> для `Value`. Если в настраиваемом <xref:System.Windows.Controls.ControlTemplate> опускает <xref:System.Windows.Controls.TextBlock> или кнопки, это приемлемо, что элемент управления теряет часть ее функциональных возможностей, но следует убедиться, что элемент управления не вызывает ошибку. Например если <xref:System.Windows.Controls.ControlTemplate> не содержит кнопки для смены `Value`, `NumericUpDown` теряет свою функциональность, но приложение, использующее <xref:System.Windows.Controls.ControlTemplate> будет продолжать выполняться.  
  
 Следующие рекомендации убедитесь, что элемент управления правильно реагирует на отсутствует <xref:System.Windows.FrameworkElement> объектов:  
  
1.  Задать `x:Name` атрибут для каждого <xref:System.Windows.FrameworkElement> , необходимо ссылаться в коде.  
  
2.  Определить частные свойства для каждого <xref:System.Windows.FrameworkElement> , необходимый для взаимодействия с.  
  
3.  Подписка и Отмена подписки на все события, которые обрабатывает элемент управления в <xref:System.Windows.FrameworkElement> доступа set свойства.  
  
4.  Задать <xref:System.Windows.FrameworkElement> свойства, определенные в шаге 2 <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> метод. Это связано с самой ранней, <xref:System.Windows.FrameworkElement> в <xref:System.Windows.Controls.ControlTemplate> доступен для элемента управления. Используйте `x:Name` из <xref:System.Windows.FrameworkElement> для получения его из <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Убедитесь, что <xref:System.Windows.FrameworkElement> не `null` перед получением доступа к его членам.  Если это `null`, не сообщает об ошибке.  
  
 В следующем примере показано как `NumericUpDown` элемент управления взаимодействует с <xref:System.Windows.FrameworkElement> объектов в соответствии с рекомендациями, перечисленные в списке.  
  
 В примере, который определяет структуру visual `NumericUpDown` управления <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton> , увеличивает `Value` имеет его `x:Name` атрибуту присвоено значение `UpButton`.  В следующем примере объявляется свойство с именем `UpButtonElement` , представляющий <xref:System.Windows.Controls.Primitives.RepeatButton> , объявленный в <xref:System.Windows.Controls.ControlTemplate>. `set` Доступа сначала отменяет подписку на кнопку <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий при `UpDownElement` не `null`, задает свойство, и затем подписывается на <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий. Также имеется свойство определено, но здесь не показаны, для других <xref:System.Windows.Controls.Primitives.RepeatButton>, который называется `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 В следующем примере показан <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> для `NumericUpDown` элемента управления.  В этом примере <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> метод, чтобы получить <xref:System.Windows.FrameworkElement> объектов из <xref:System.Windows.Controls.ControlTemplate>.  Обратите внимание, что в примере предотвращаются ситуации, когда <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> находит <xref:System.Windows.FrameworkElement> с указанным именем, который не относится к ожидаемому типу. Это также рекомендуемый способ игнорирования элементов, имеющих указанный `x:Name` , но имеет неправильный тип.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Следуя рекомендациям, показанных в предыдущих примерах, убедитесь, что элемент управления будет продолжать выполнять, когда <xref:System.Windows.Controls.ControlTemplate> отсутствует <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Используйте VisualStateManager для управления состояниями  
 <xref:System.Windows.VisualStateManager> Отслеживает состояния элемента управления и выполняет логику, необходимую для перехода между состояниями. При добавлении <xref:System.Windows.VisualState> объектов <xref:System.Windows.Controls.ControlTemplate>, добавьте их в <xref:System.Windows.VisualStateGroup> и добавьте <xref:System.Windows.VisualStateGroup> для <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> вложенное свойство, чтобы <xref:System.Windows.VisualStateManager> имеет к ним доступ.  
  
 В следующем примере повторяется в предыдущем примере, где показано <xref:System.Windows.VisualState> объектов, которые соответствуют `Positive` и `Negative` состояния элемента управления. <xref:System.Windows.Media.Animation.Storyboard> В `Negative` <xref:System.Windows.VisualState> включает <xref:System.Windows.Controls.TextBlock.Foreground%2A> из <xref:System.Windows.Controls.TextBlock> красным.   Когда `NumericUpDown` элемент управления находится в `Negative` состояние раскадровки в `Negative` состояние начинается.  Затем <xref:System.Windows.Media.Animation.Storyboard> в `Negative` состояние останавливается, когда управление возвращается `Positive` состояния.  `Positive` <xref:System.Windows.VisualState> Не содержать <xref:System.Windows.Media.Animation.Storyboard> так как при <xref:System.Windows.Media.Animation.Storyboard> для `Negative` останавливается, <xref:System.Windows.Controls.TextBlock.Foreground%2A> возвращает исходного цвета.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Обратите внимание, что <xref:System.Windows.Controls.TextBlock> присваивается имя, но <xref:System.Windows.Controls.TextBlock> не находится в контракте элемента управления для `NumericUpDown` , так как логика элемента управления никогда не ссылается <xref:System.Windows.Controls.TextBlock>.  Элементы, которые упоминаются в <xref:System.Windows.Controls.ControlTemplate> имеют имена, но не обязательно должны быть частью контракта элемента управления, так как новый <xref:System.Windows.Controls.ControlTemplate> для элемента управления не может потребоваться ссылка на этот элемент.  Например, кто создает новую <xref:System.Windows.Controls.ControlTemplate> для `NumericUpDown` может решить не указывать, `Value` путем изменения <xref:System.Windows.Controls.Control.Foreground%2A>.  В этом случае ни код, ни <xref:System.Windows.Controls.ControlTemplate> ссылки <xref:System.Windows.Controls.TextBlock> по имени.  
  
 Логика элемента управления отвечает за изменением состояния элемента управления. В следующем примере показано, что `NumericUpDown` управления вызовы <xref:System.Windows.VisualStateManager.GoToState%2A> метод углубляться `Positive` состояние при `Value` 0 или больше и `Negative` состояние при `Value` меньше 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 <xref:System.Windows.VisualStateManager.GoToState%2A> Метод выполняет логику, необходимую для запуска и остановки раскадровки соответствующим образом. Когда элемент управления вызывает <xref:System.Windows.VisualStateManager.GoToState%2A> для изменения его состояния <xref:System.Windows.VisualStateManager> делает следующее:  
  
-   Если <xref:System.Windows.VisualState> , элемент управления будет имеет <xref:System.Windows.Media.Animation.Storyboard>, раскадровки. Затем, если <xref:System.Windows.VisualState> откуда элемент управления имеет <xref:System.Windows.Media.Animation.Storyboard>, раскадровка останавливается.  
  
-   Если элемент управления уже находится в состоянии, которое указано, <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий и возвращает `true`.  
  
-   Если указанное состояние не существует в <xref:System.Windows.Controls.ControlTemplate> из `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий и возвращает `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Советы и рекомендации по работе с VisualStateManager  
 Рекомендуется выполнить следующую команду для поддержания состояния элемента управления.  
  
-   Используйте свойства для отслеживания состояния.  
  
-   Создайте вспомогательный метод для перехода между состояниями.  
  
 `NumericUpDown` Управления использует его `Value` свойства для отслеживания, является ли он в `Positive` или `Negative` состояния.  `NumericUpDown` Управления также определяет `Focused` и `UnFocused` состояний записей <xref:System.Windows.UIElement.IsFocused%2A> свойство. При использовании состояний, которые не соответствуют естественным образом свойство элемента управления, можно определить закрытое свойство для отслеживания состояния.  
  
 Один метод, который обновляет все состояния, централизованно выполняет вызовы <xref:System.Windows.VisualStateManager> и сохраняет код управляемым. В следующем примере показан `NumericUpDown` вспомогательного метода элемента управления, `UpdateStates`. Когда `Value` больше или равно 0, <xref:System.Windows.Controls.Control> в `Positive` состояние.  Когда `Value` — меньше 0, элемент управления находится в `Negative` состояние.  Когда <xref:System.Windows.UIElement.IsFocused%2A> — `true`, элемент управления находится в `Focused` состояния; в противном случае он находится в `Unfocused` состояние.  Элемент управления может вызывать `UpdateStates` каждый раз, когда ему необходимо изменить свое состояние, независимо от этого состояния.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Если вы передаете имя состояния для <xref:System.Windows.VisualStateManager.GoToState%2A> когда элемент управления уже находится в этом состоянии <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никаких действий, вам требуется для проверки текущего состояния элемента управления.  Например если `Value` изменяется от одного отрицательного числа на другое отрицательное число, раскадровка для `Negative` состояние не прерывается, и пользователь не увидит изменений в элементе управления.  
  
 <xref:System.Windows.VisualStateManager> Использует <xref:System.Windows.VisualStateGroup> объектов, чтобы определить, какие состояния производится выход при вызове <xref:System.Windows.VisualStateManager.GoToState%2A>. Элемент управления всегда находится в одном состоянии для каждой <xref:System.Windows.VisualStateGroup> , определенный в его <xref:System.Windows.Controls.ControlTemplate> и покидает это состояние только при переходе в другое состояние из того же <xref:System.Windows.VisualStateGroup>. Например <xref:System.Windows.Controls.ControlTemplate> из `NumericUpDown` управления определяет `Positive` и `Negative` <xref:System.Windows.VisualState> объектов в одном <xref:System.Windows.VisualStateGroup> и `Focused` и `Unfocused` <xref:System.Windows.VisualState> объектов в другом. (Вы увидите `Focused` и `Unfocused` <xref:System.Windows.VisualState> определенные в [полный пример](#complete_example) в этой статье, когда элемент управления выходит из `Positive` состояние `Negative` состояние, или наоборот, элемент управления остается в любом `Focused` или `Unfocused` состояния.  
  
 Существует три типичных места, где может изменить состояние элемента управления:  
  
-   Когда <xref:System.Windows.Controls.ControlTemplate> применяется к <xref:System.Windows.Controls.Control>.  
  
-   При изменении свойства.  
  
-   Когда происходит событие.  
  
 В следующих примерах демонстрируется обновление состояния `NumericUpDown` элемента управления в таких случаях.  
  
 Необходимо обновить состояние элемента управления в <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> метод отображения элемента управления в правильное состояние при <xref:System.Windows.Controls.ControlTemplate> применяется. В следующем примере вызывается `UpdateStates` в <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> для обеспечения правильности состояния элемента управления.  Предположим, например, создать `NumericUpDown` управления, а затем установите его <xref:System.Windows.Controls.Control.Foreground%2A> зеленым и `Value` значению -5.  Если вы не вызываете `UpdateStates` при <xref:System.Windows.Controls.ControlTemplate> применяется к `NumericUpDown` управления, элемент управления не находится в `Negative` состояния и значения зеленым, а не красным.  Необходимо вызвать `UpdateStates` для размещения элемента управления в `Negative` состояние.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Часто требуется для обновления состояния элемента управления при изменении свойства. В следующем примере показано всего `ValueChangedCallback` метод. Поскольку `ValueChangedCallback` вызывается, когда `Value` изменяется, вызывается метод `UpdateStates` в случае, если `Value` изменяется с положительного на отрицательное значение или наоборот. Допустимо вызывать `UpdateStates` при `Value` изменяется, но остается положительным или отрицательным, поскольку в этом случае элемент управления не изменяет состояние.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 Кроме того, может потребоваться обновить состояния при возникновении события. В следующем примере показано, что `NumericUpDown` вызовы `UpdateStates` на <xref:System.Windows.Controls.Control> для обработки <xref:System.Windows.UIElement.GotFocus> событий.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager> Помогает управлять состояния элемента управления. С помощью <xref:System.Windows.VisualStateManager>, убедитесь, что элемент управления правильные переходы между состояниями.  Если вы будете придерживаться рекомендаций, приведенных в этом разделе для работы с <xref:System.Windows.VisualStateManager>, код элемента управления будет оставаться читаемым и простым в обслуживании.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Предоставление контракта элемента управления  
 Укажите контракт элемента управления, чтобы <xref:System.Windows.Controls.ControlTemplate> авторы знали, что для размещения в шаблоне. Контракт элемента управления имеет три элемента:  
  
-   визуальный элемент, используемый логикой элемента управления;  
  
-   состояния элемента управления и группа, к которой принадлежит каждое состояние;  
  
-   общие свойства, визуально воздействующие на элемент управления.  
  
 Кто-то, которое создает новый <xref:System.Windows.Controls.ControlTemplate> необходимо знать, что <xref:System.Windows.FrameworkElement> объектов используется логика элемента управления, какой тип каждого объекта, который их имена. Объект <xref:System.Windows.Controls.ControlTemplate> автор должен также знать имя все возможные состояния может находиться в элемент управления, а какие <xref:System.Windows.VisualStateGroup> находится в состоянии.  
  
 Возврат к `NumericUpDown` примере, ожидает управления <xref:System.Windows.Controls.ControlTemplate> быть установлены следующие <xref:System.Windows.FrameworkElement> объектов:  
  
-   Объект <xref:System.Windows.Controls.Primitives.RepeatButton> вызывается `UpButton`.  
  
-   Объект <xref:System.Windows.Controls.Primitives.RepeatButton> вызывается `DownButton.`  
  
 Элемент управления может иметь следующие состояния:  
  
-   В `ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   В `FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Чтобы указать, что <xref:System.Windows.FrameworkElement> ожидает объектов управления, использовать <xref:System.Windows.TemplatePartAttribute>, которое указывает имя и тип ожидаемых элементов.  Для указания возможных состояний элемента управления, используйте <xref:System.Windows.TemplateVisualStateAttribute>, которое указывает имя состояния, а какие <xref:System.Windows.VisualStateGroup> она принадлежит.  Поместите <xref:System.Windows.TemplatePartAttribute> и <xref:System.Windows.TemplateVisualStateAttribute> в определении класса элемента управления.  
  
 Любое открытое свойство, которое влияет на внешний вид элемента управления также является частью контракта элемента управления.  
  
 В следующем примере задается <xref:System.Windows.FrameworkElement> объектов и состояний для `NumericUpDown` элемента управления.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Полный пример  
 Следующий пример является вся <xref:System.Windows.Controls.ControlTemplate> для `NumericUpDown` элемента управления.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 В следующем примере показано, что логика `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>См. также  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)
