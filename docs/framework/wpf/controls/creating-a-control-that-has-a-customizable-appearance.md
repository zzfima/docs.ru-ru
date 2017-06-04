---
title: "Создание элемента управления с настраиваемым внешним видом | Microsoft Docs"
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
  - "элементы управления [WPF], настройка"
  - "элементы управления [WPF], определение визуальной структуры и поведения"
  - "ControlTemplate [WPF], настройка внешнего вида"
  - "настройка внешнего вида [WPF], ControlTemplate"
  - "управление состояниями элементов управления [WPF], VisualStateManager"
  - "VisualStateManager [WPF], рекомендации"
  - "VisualStateManager [WPF], управление состоянием элемента управления"
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Создание элемента управления с настраиваемым внешним видом
<a name="introduction"></a> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет возможность создания элемента управления с настраиваемым внешним видом.  Например, можно изменить внешний вид элемента управления <xref:System.Windows.Controls.CheckBox> дополнительно к тому, что будут делать установленные свойства, создав новый шаблон <xref:System.Windows.Controls.ControlTemplate>.  На следующем рисунке показан элемент управления <xref:System.Windows.Controls.CheckBox>, использующий шаблон <xref:System.Windows.Controls.ControlTemplate>, установленный по умолчанию, и элемент управления <xref:System.Windows.Controls.CheckBox>, использующий пользовательский шаблон <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Флажок с шаблоном элемента управления по умолчанию.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию  
  
 ![Флажок с пользовательским шаблоном элемента управления.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления  
  
 Если элемент управления создается согласно модели частей и состояний, то его внешний вид будет настраиваемым.  Средства конструирования, такие как Microsoft Expression Blend, поддерживают модель частей и состояний, поэтому при следовании этой модели элемент управления будет настраиваемым в таких типах приложений.  В этой теме рассматривается модель частей и состояний и порядок создания собственного элемента управления согласно этой модели.  Для иллюстрации философии этой модели в данной теме используется пример пользовательского элемента управления `NumericUpDown`.  Элемент управления `NumericUpDown` отображает числовое значение, которое пользователь может увеличить или уменьшить, нажимая кнопки этого элемента управления.  На следующем рисунке показан элемент управления `NumericUpDown`, рассматриваемый в этой теме.  
  
 ![Пользовательский элемент управления NumericUpDown.](../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP\_NumericUPDown")  
Пользовательский элемент управления NumericUpDown  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Предварительные требования](#prerequisites)  
  
-   [Модель частей и состояний](#parts_and_states_model)  
  
-   [Определение визуальной структуры и визуального поведения элемента управления в шаблоне ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Использование частей ControlTemplate в коде](#using_parts_of_the_controltemplate_in_code)  
  
-   [Предоставление контракта элемента управления](#providing_the_control_contract)  
  
-   [Полный пример](#complete_example)  
  
<a name="prerequisites"></a>   
## Предварительные требования  
 В этой теме предполагается, что читатели знакомы с процедурой создания нового шаблона <xref:System.Windows.Controls.ControlTemplate> для существующего элемента управления, с тем, какие элементы входят в контракт элемента управления, а также с основными понятиями, которые рассматриваются в теме [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Чтобы создать элемент управления с настраиваемым внешним видом, необходимо создать элемент управления, наследующий от класса <xref:System.Windows.Controls.Control> или от одного из его подклассов, отличных от <xref:System.Windows.Controls.UserControl>.  Элемент управления, наследующий от класса <xref:System.Windows.Controls.UserControl>, это элемент управления, который можно быстро создать, но который не использует шаблон <xref:System.Windows.Controls.ControlTemplate>, и его внешний вид настраивать нельзя.  
  
<a name="parts_and_states_model"></a>   
## Модель частей и состояний  
 Модель частей и состояний задает способ определения визуальной структуры и визуального поведения элемента управления.  Согласно модели частей и состояний необходимо выполнить следующие действия:  
  
-   задать визуальную структуру и визуальное поведение в шаблоне <xref:System.Windows.Controls.ControlTemplate> элемента управления;  
  
-   выполнять определенные рекомендации при взаимодействии логики элемента управления с частями шаблона элемента управления;  
  
-   предоставить контракту элемента управления указывать, что должно быть включено в шаблон <xref:System.Windows.Controls.ControlTemplate>.  
  
 При задании визуальной структуры и визуального поведения в шаблоне <xref:System.Windows.Controls.ControlTemplate> элемента управления разработчики приложения могут изменять визуальную структуру и поведение элемента управления. создавая новый шаблон <xref:System.Windows.Controls.ControlTemplate> вместо написания кода.  Необходимо предоставить контракт элемента управления, который будет указывать разработчикам, какие объекты <xref:System.Windows.FrameworkElement> и состояния должны быть заданы в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  При взаимодействии с частями в шаблоне <xref:System.Windows.Controls.ControlTemplate> необходимо следовать некоторым рекомендациям, чтобы элемент управления обрабатывал незавершенный шаблон <xref:System.Windows.Controls.ControlTemplate>.  При следовании этим трем принципам разработчики приложений будут иметь возможность создавать шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления так же просто, как это можно делать для элементов управления, поставляемых с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В следующем разделе дается подробное объяснение каждой из этих рекомендаций.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## Определение визуальной структуры и визуального поведения элемента управления в шаблоне ControlTemplate  
 При создании пользовательского элемента управления с помощью модели частей и состояний визуальная структура и визуальное поведение элемента управления задается не в его логике, а в его шаблоне <xref:System.Windows.Controls.ControlTemplate>.  Визуальная структура элемента управления состоит из объектов <xref:System.Windows.FrameworkElement>, которые составляют элемент управления.  Визуальное поведение – это способ отображения элемента управления в определенных состояниях.  Дополнительные сведения о создании шаблона <xref:System.Windows.Controls.ControlTemplate>, задающего визуальную структуру и визуальное поведение элемента управления см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 В примере элемента управления `NumericUpDown` визуальная структура состоит из двух элементов управления <xref:System.Windows.Controls.Primitives.RepeatButton> и блока текста <xref:System.Windows.Controls.TextBlock>.  При добавлении этих элементов управления в код элемента управления `NumericUpDown`, например в его конструкторе, положение этих элементов управления может быть неизменяемым.  Вместо того чтобы задавать визуальную структуру и визуальное поведение элемента управления в его коде, следует задать их в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  Затем разработчик приложения может настроить положение кнопок и текста <xref:System.Windows.Controls.TextBlock>, а также указать поведение при отрицательном значении `Value`, поскольку шаблон <xref:System.Windows.Controls.ControlTemplate> может быть заменен.  
  
 В следующем примере показана визуальная структура элемента управления `NumericUpDown`, состоящая из элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton> для увеличения значения `Value`, элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton> для уменьшения значения `Value` и блока текста <xref:System.Windows.Controls.TextBlock> для отображения `Value`.  
  
 [!code-xml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Визуальное поведение элемента управления `NumericUpDown` состоит в том, что отрицательное значение отображается красным цветом.  При изменении свойства <xref:System.Windows.Controls.TextBlock.Foreground%2A> элемента <xref:System.Windows.Controls.TextBlock> в коде в случае, если значение `Value` отрицательное, `NumericUpDown` все равно будет показывать красное отрицательное значение.  Визуальное поведение элемента управления в шаблоне <xref:System.Windows.Controls.ControlTemplate> задается путем добавления объектов <xref:System.Windows.VisualState> в шаблон <xref:System.Windows.Controls.ControlTemplate>.  В следующем примере показаны объекты <xref:System.Windows.VisualState> для состояний `Positive` и `Negative`.  Состояния `Positive` и `Negative` являются взаимоисключающими \(элемент управления всегда находится в одном из этих двух состояний\), поэтому в примере эти объекты <xref:System.Windows.VisualState> помещаются в одну группу <xref:System.Windows.VisualStateGroup>.  Когда элемент управления переходит в состояние `Negative`, свойство <xref:System.Windows.Controls.TextBlock.Foreground%2A> элемента <xref:System.Windows.Controls.TextBlock> включает красный цвет.  Если элемент управления переходит в состояние `Positive`, свойство <xref:System.Windows.Controls.TextBlock.Foreground%2A> возвращается в первоначальное значение.  Определение объектов <xref:System.Windows.VisualState> в шаблоне <xref:System.Windows.Controls.ControlTemplate> подробнее рассматривается в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Необходимо задать присоединенное свойство <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> для корневого элемента <xref:System.Windows.FrameworkElement> шаблона <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## Использование частей ControlTemplate в коде  
 Разработчик <xref:System.Windows.Controls.ControlTemplate> может пропустить объекты <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState> сознательно или по ошибке, но логика элемента управления требует, чтобы эти части работали соответствующим образом.  Модель частей и состояний указывает, что элемент управления должен быть устойчив к шаблону <xref:System.Windows.Controls.ControlTemplate>, в котором пропущены объекты <xref:System.Windows.FrameworkElement> или <xref:System.Windows.VisualState>.  Элемент управления не должен вызывать исключение или сообщение об ошибке, если объекты <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState> или <xref:System.Windows.VisualStateGroup> пропущены в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  В этом разделе даются рекомендации по взаимодействию с объектами <xref:System.Windows.FrameworkElement> и управляемыми состояниями.  
  
### Предупреждение пропуска объектов FrameworkElement  
 При определении объектов <xref:System.Windows.FrameworkElement> в шаблоне <xref:System.Windows.Controls.ControlTemplate> логике элемента управления может требоваться взаимодействие с некоторыми из этих объектов.  Например, элемент управления `NumericUpDown` подписывается на событие кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, чтобы увеличивать или уменьшать `Value`, и устанавливает свойство <xref:System.Windows.Controls.TextBlock.Text%2A> объекта <xref:System.Windows.Controls.TextBlock> в `Value`.  Если в настраиваемом шаблоне <xref:System.Windows.Controls.ControlTemplate> пропущен объект <xref:System.Windows.Controls.TextBlock> или кнопки, то потеря элементом управления некоторой своей функциональности допустима, но элемент управления не должен создавать ошибку.  Например, если шаблон не содержит <xref:System.Windows.Controls.ControlTemplate> кнопки для изменения значения `Value`, то элемент управления `NumericUpDown` теряет свою функциональность, но приложение, использующее шаблон <xref:System.Windows.Controls.ControlTemplate>, продолжает работать.  
  
 Приведенные далее рекомендации обеспечат должную реакцию элемента управления на пропуск объектов <xref:System.Windows.FrameworkElement>.  
  
1.  Установите атрибут `x:Name` для каждого объекта <xref:System.Windows.FrameworkElement>, на который необходимы ссылки в коде.  
  
2.  Задайте частные свойства для каждого объекта <xref:System.Windows.FrameworkElement>, с которым необходимо взаимодействовать.  
  
3.  Подпишитесь и отмените подписку на все события, которые обрабатывает элемент управления, в методе доступа, установленном свойством объекта <xref:System.Windows.FrameworkElement>.  
  
4.  Установите свойства <xref:System.Windows.FrameworkElement>, заданные на этапе 2 в методе <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>.  Это более близкие свойства, чем объект <xref:System.Windows.FrameworkElement> в шаблоне <xref:System.Windows.Controls.ControlTemplate>, доступные элементу управления.  Воспользуйтесь атрибутом `x:Name` объекта <xref:System.Windows.FrameworkElement> для получения их из шаблона <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Перед доступом к элементам объекта <xref:System.Windows.FrameworkElement> проверьте, не задан ли он как `null`.  Если он `null`, не следует выводить сообщение об ошибке.  
  
 В следующем примере показано взаимодействие элемента управления `NumericUpDown` с объектами <xref:System.Windows.FrameworkElement> согласно рекомендациям из предыдущего списка.  
  
 В примере, в котором задается визуальная структура элемента управления `NumericUpDown` в шаблоне <xref:System.Windows.Controls.ControlTemplate>, элемент <xref:System.Windows.Controls.Primitives.RepeatButton>, увеличивающий значение `Value`, имеет атрибут `x:Name`, установленный в значение `UpButton`.  В следующем примере объявляется свойство с именем `UpButtonElement`, которое представляет объект <xref:System.Windows.Controls.Primitives.RepeatButton>, объявленный в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  Метод доступа `set` сначала отменяет подписку на событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки, если объект `UpDownElement` не является `null`, затем устанавливает свойство, и затем подписывается на событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  В примере также имеется заданное, но не показанное здесь свойство для другого объекта <xref:System.Windows.Controls.Primitives.RepeatButton> с именем `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 В следующем примере показывается метод <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> для элемента управления `NumericUpDown`.  В этом примере метод <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> используется для получения объектов <xref:System.Windows.FrameworkElement> из шаблона <xref:System.Windows.Controls.ControlTemplate>.  Следует отметить, что в примере предотвращаются ситуации, когда метод <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> обнаруживает объект <xref:System.Windows.FrameworkElement> с указанным именем, но не того типа, который ожидается.  Это также рекомендуемый способ игнорирования элементов, имеющих указанный атрибут `x:Name`, но неправильный тип.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Следуя рекомендациям, показанным в предыдущих примерах, можно гарантировать, что элемент управления будет продолжать работать, когда в шаблоне <xref:System.Windows.Controls.ControlTemplate> пропущен объект <xref:System.Windows.FrameworkElement>.  
  
### Использование VisualStateManager для управления состояниями  
 <xref:System.Windows.VisualStateManager> отслеживает состояния элемента управления и выполняет логику, необходимую для перехода между состояниями.  При добавлении объектов <xref:System.Windows.VisualState> в шаблон <xref:System.Windows.Controls.ControlTemplate> происходит добавление этих объектов в группу <xref:System.Windows.VisualStateGroup> и добавление группы <xref:System.Windows.VisualStateGroup> в подключенное свойство <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>, поэтому <xref:System.Windows.VisualStateManager> имеет к ним доступ.  
  
 В следующем примере повторяется предыдущий пример, в котором показаны объекты <xref:System.Windows.VisualState>, соответствующие состояниям `Positive` и `Negative` элемента управления.  Объект <xref:System.Windows.Media.Animation.Storyboard> в состоянии <xref:System.Windows.VisualState>, имеющем значение `Negative`, переключает свойство <xref:System.Windows.Controls.TextBlock.Foreground%2A> объекта <xref:System.Windows.Controls.TextBlock> на красный цвет.  Когда элемент управления `NumericUpDown` переходит в состояние `Negative`, начинается раскадровка в состоянии `Negative`.  Затем, когда элемент управления возвращается в состояние `Positive` раскадровка <xref:System.Windows.Media.Animation.Storyboard> в состоянии `Negative` останавливается.  Объекту `Positive` <xref:System.Windows.VisualState> не требуется содержать объект <xref:System.Windows.Media.Animation.Storyboard>, поскольку когда раскадровка <xref:System.Windows.Media.Animation.Storyboard> для состояния `Negative` останавливается, свойство <xref:System.Windows.Controls.TextBlock.Foreground%2A> возвращается в первоначальный цвет.  
  
 [!code-xml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Следует отметить, что объекту <xref:System.Windows.Controls.TextBlock> присваивается имя, но объект <xref:System.Windows.Controls.TextBlock> не находится в контракте элемента управления для `NumericUpDown`, поскольку логика элемента управления никогда не обращается к объекту <xref:System.Windows.Controls.TextBlock>.  Элементы, на которые есть ссылки в шаблоне <xref:System.Windows.Controls.ControlTemplate>, получают имена, но их не надо включать в контракт элемента управления, поскольку новому шаблону <xref:System.Windows.Controls.ControlTemplate> для этого элемента управления может не требоваться ссылка на этот элемент.  Например, разработчик, создавший новый шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления `NumericUpDown`, может решить не указывать отрицательность значения `Value` путем изменения свойства <xref:System.Windows.Controls.Control.Foreground%2A>.  В таком случае ни код, ни шаблон <xref:System.Windows.Controls.ControlTemplate> не будут ссылаться на объект <xref:System.Windows.Controls.TextBlock> по имени.  
  
 Логика элемента управления отвечает за изменение его состояния.  В следующем примере показывается, что элемент управления `NumericUpDown` вызывает метод <xref:System.Windows.VisualStateManager.GoToState%2A> для перехода в состояние `Positive`, когда значение `Value` равно 0 или больше 0, и в состояние `Negative`, когда значение `Value` меньше 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Метод <xref:System.Windows.VisualStateManager.GoToState%2A> выполняет логику, необходимую для запуска и остановки раскадровки соответствующим образом.  Когда элемент управления вызывает метод <xref:System.Windows.VisualStateManager.GoToState%2A> для изменения своего состояния, <xref:System.Windows.VisualStateManager> выполняет приведенные далее действия.  
  
-   Если объект <xref:System.Windows.VisualState>, в который переходит элемент управления, имеет объект <xref:System.Windows.Media.Animation.Storyboard>, то начинается раскадровка.  Далее, если объект <xref:System.Windows.VisualState>, из которого переходит элемент управления, имеет объект <xref:System.Windows.Media.Animation.Storyboard>, то раскадровка останавливается.  
  
-   Если элемент управления уже находится в указанном состоянии, то метод <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никакие действия и возвращает значение `true`.  
  
-   Если указанное состояние не существует в шаблоне <xref:System.Windows.Controls.ControlTemplate> элемента управления `control`, то метод <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никакие действия и возвращает значение `false`.  
  
#### Рекомендации по работе с VisualStateManager  
 Для обслуживания состояний элемента управления рекомендуется выполнить следующие действия:  
  
-   воспользоваться свойствами для отслеживания состояния элемента управления;  
  
-   создать вспомогательный метод для перехода между состояниями.  
  
 Элемент управления `NumericUpDown` использует свое свойство `Value` для отслеживания, находится ли он в состоянии `Positive` или `Negative`.  Элемент управления `NumericUpDown` также задает состояния `Focused` и `UnFocused` которые отслеживает свойство <xref:System.Windows.UIElement.IsFocused%2A>.  При использовании состояний, не соответствующих обычным свойствам элемента управления, можно задать частное свойство для отслеживания этого состояния.  
  
 Один метод, который обновляет все состояния, централизованно выполняет вызовы <xref:System.Windows.VisualStateManager> и сохраняет код управляемым.  В следующем примере показан вспомогательный метод `UpdateStates` элемента управления `NumericUpDown`.  Когда значение `Value` больше или равно 0, элемент управления <xref:System.Windows.Controls.Control> находится в состоянии `Positive`.  Когда значение `Value` меньше 0, этот элемент управления находится в состоянии `Negative`.  Когда свойство <xref:System.Windows.UIElement.IsFocused%2A> имеет значение `true`, элемент управления находится в состоянии `Focused`; в противном случае он находится в состоянии `Unfocused`.  Элемент управления может вызвать метод `UpdateStates`, когда ему необходимо изменить свое состояние, независимо от этого состояния.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Если имя состояния передается в метод <xref:System.Windows.VisualStateManager.GoToState%2A>, когда элемент управления уже находится в этом состоянии, то метод <xref:System.Windows.VisualStateManager.GoToState%2A> не выполняет никакие действия, поэтому не требуется проверять текущее состояние элемента управления.  Например, если значение `Value` изменяется от одного отрицательного числа на другое отрицательное число, раскадровка для состояния `Negative` не прерывается, и пользователь не увидит изменение элемента управления.  
  
 <xref:System.Windows.VisualStateManager> использует объекты <xref:System.Windows.VisualStateGroup> для определения, из какого состояния производится выход при вызове метода <xref:System.Windows.VisualStateManager.GoToState%2A>.  Элемент управления всегда находится в одном состоянии для каждой группы <xref:System.Windows.VisualStateGroup>, заданной в его шаблоне <xref:System.Windows.Controls.ControlTemplate>, и покидает это состояние только при переходе в другое состояние из этой же группы <xref:System.Windows.VisualStateGroup>.  Например, шаблон <xref:System.Windows.Controls.ControlTemplate> элемента управления `NumericUpDown` задает состояния `Positive` и `Negative` объекта <xref:System.Windows.VisualState> в одной группе <xref:System.Windows.VisualStateGroup>, а состояния `Focused` и `Unfocused` объекта <xref:System.Windows.VisualState> – в другой группе.  \(Заданные состояния `Focused` и `Unfocused` объекта <xref:System.Windows.VisualState> можно увидеть в разделе [Полный пример](#complete_example) этой темы. Когда элемент управления переходит из состояния `Positive` в состояние `Negative` или наоборот, он остается либо в состоянии `Focused` либо в состоянии `Unfocused`.  
  
 Существует три обычные ситуации, в которых состояние элемента управления может изменяться:  
  
-   когда шаблон <xref:System.Windows.Controls.ControlTemplate> применяется к элементу управления <xref:System.Windows.Controls.Control>;  
  
-   когда изменяется свойство;  
  
-   когда возникает событие.  
  
 В следующих примерах показывается обновление состояния элемента управления `NumericUpDown` в таких ситуациях.  
  
 Следует обновить состояние элемента управления в методе <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>, чтобы этот элемент управления отображался в правильном состоянии, когда применяется шаблон <xref:System.Windows.Controls.ControlTemplate>.  В следующем примере для проверки правильности состояния элемента управления вызывается вспомогательный метод `UpdateStates` из метода <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A>.  В качестве примера предположим, что создается элемент управления `NumericUpDown`, а затем его свойство <xref:System.Windows.Controls.Control.Foreground%2A> устанавливается в зеленый цвет, а `Value` – в значение \-5.  Если при применении шаблона <xref:System.Windows.Controls.ControlTemplate> к элементу управления `NumericUpDown` не вызывается `UpdateStates`, то элемент управления не находится в состоянии `Negative`, и значение отображается зеленым, а не красным цветом.  Необходимо вызвать метод `UpdateStates`, чтобы перевести элемент управления в состояние `Negative`.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Часто бывает необходимо обновлять состояния элементов управления при изменении свойств.  В следующем примере показан весь метод `ValueChangedCallback`.  Поскольку метод `ValueChangedCallback` вызывается при изменении значения `Value`, этот метод вызывает `UpdateStates` в том случае, когда `Value` изменяется с положительного на отрицательное значение или наоборот.  Допустимо вызвать метод `UpdateStates`, когда `Value` изменяется, но остается положительным или отрицательным, поскольку в этом случае элемент управления не изменяет состояние.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 Может также потребоваться обновить состояния при возникновении события.  В следующем примере показывается, что `NumericUpDown` вызывает метод `UpdateStates` в элементе управления <xref:System.Windows.Controls.Control> для обработки события <xref:System.Windows.UIElement.GotFocus>.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 <xref:System.Windows.VisualStateManager> помогает управлять состояниями элементов управления.  С помощью <xref:System.Windows.VisualStateManager> можно гарантировать правильные переходы элемента управления между состояниями.  При выполнении рекомендаций, приведенных в этом разделе для работы с <xref:System.Windows.VisualStateManager>, код элемента управления будет сохраняться понятным и обслуживаемым.  
  
<a name="providing_the_control_contract"></a>   
## Предоставление контракта элемента управления  
 Контракт элемента управления предоставляется, чтобы разработчикам шаблона <xref:System.Windows.Controls.ControlTemplate> было известно, что следует включать в шаблон.  Контракт элемента управления имеет три элемента:  
  
-   визуальный элемент, используемый логикой элемента управления;  
  
-   состояния элемента управления и группа, к которой принадлежит каждое состояние;  
  
-   общие свойства, визуально воздействующие на элемент управления.  
  
 Разработчику, создающему новый шаблон <xref:System.Windows.Controls.ControlTemplate>, необходимо знать, какие объекты <xref:System.Windows.FrameworkElement> использует логика элемента управления, типы этих объектов и их имена.  Разработчику шаблона <xref:System.Windows.Controls.ControlTemplate> также необходимо знать имена всех возможных состояний элемента управления и группу <xref:System.Windows.VisualStateGroup> каждого из этих состояний.  
  
 Возвращаясь к примеру `NumericUpDown`, можно видеть, что элемент управления ожидает, что в шаблоне <xref:System.Windows.Controls.ControlTemplate> имеются следующие объекты <xref:System.Windows.FrameworkElement>:  
  
-   объект <xref:System.Windows.Controls.Primitives.RepeatButton> с именем `UpButton`;  
  
-   объект <xref:System.Windows.Controls.Primitives.RepeatButton> с именем `DownButton.`;  
  
 Элемент управления может находиться в следующих состояниях.  
  
-   В группе `ValueStates` <xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   В группе `FocusStates` <xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Для указания, какие объекты <xref:System.Windows.FrameworkElement> ожидаются элементом управления, используется атрибут <xref:System.Windows.TemplatePartAttribute>, который задает имена и типы ожидаемых элементов.  Для указания возможных состояний элемента управления используется <xref:System.Windows.TemplateVisualStateAttribute>, который задается имя состояния и группу <xref:System.Windows.VisualStateGroup>, которой он принадлежит.  Поместите атрибуты <xref:System.Windows.TemplatePartAttribute> и <xref:System.Windows.TemplateVisualStateAttribute> в определение класса элемента управления.  
  
 Какие\-либо общие свойства, влияющие на внешний вид элемента управления, также включаются в контракт элемента управления.  
  
 В следующем примере задаются объект <xref:System.Windows.FrameworkElement> и состояния для элемента управления `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## Полный пример  
 В следующем примере приводится полный шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления `NumericUpDown`.  
  
 [!code-xml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 В следующем примере показывается логика элемента управления `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## См. также  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)