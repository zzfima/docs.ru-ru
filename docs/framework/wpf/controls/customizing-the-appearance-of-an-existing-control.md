---
title: "Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate | Microsoft Docs"
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
  - "контракт элементов управления [WPF]"
  - "элементы управления [WPF], внешний вид, определяемый состоянием"
  - "элементы управления [WPF], изменения визуальной структуры"
  - "ControlTemplate [WPF], настройка для существующих элементов управления"
  - "элементы управления темами [WPF]"
  - "шаблоны [WPF], пользовательские, для существующих элементов управления"
ms.assetid: 678dd116-43a2-4b8c-82b5-6b826f126e31
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate
<a name="introduction"></a> Объект <xref:System.Windows.Controls.ControlTemplate> задает визуальную структуру и визуальное поведение элемента управления.  Можно настраивать внешний вид элемента управления, предоставляя ему новый шаблон <xref:System.Windows.Controls.ControlTemplate>.  При создании <xref:System.Windows.Controls.ControlTemplate> заменяется внешний вид существующего элемента управления без воздействия на его функциональность.  Например, можно сделать кнопки в приложении круглыми вместо установленных по умолчанию квадратных, но кнопка по\-прежнему будет вызывать событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click>.  
  
 В этой теме даются объяснения разных частей <xref:System.Windows.Controls.ControlTemplate>, демонстрируется создание простого шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>, а также объясняется, как следует понимать контракт элемента управления, чтобы можно было настроить его внешний вид.  Путем создания <xref:System.Windows.Controls.ControlTemplate> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно изменить внешний вид элемента управления без написания какого\-либо кода.  Можно также использовать конструктор, например Microsoft expression blend, чтобы создать шаблоны пользовательского элемента управления.  В этой теме приведены примеры [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], в которых выполняется настройка внешнего вида элемента управления <xref:System.Windows.Controls.Button>. Список всех примеров содержится в конце темы.  Дополнительные сведения об использовании Expression Blend см. в статье [Настройка стиля элемента управления, поддерживающего шаблоны \(статья может быть на английском языке\)](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
 На следующих рисунках показан элемент управления <xref:System.Windows.Controls.Button>, который использует шаблон <xref:System.Windows.Controls.ControlTemplate>, создаваемый в этой теме.  
  
 ![Кнопка с пользовательским шаблоном элемента управления.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Кнопка, использующая пользовательский шаблон элемента управления  
  
 ![Кнопка с красной границей.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Кнопка, использующая пользовательский шаблон элемента управления, когда в ней находится указатель мыши  
  
   
  
<a name="prerequisites"></a>   
## Предварительные требования  
 В этой теме предполагается, что пользователь понимает процесс создания и использования элементов управления и стилей, который рассматривался в разделе [Элементы управления](../../../../docs/framework/wpf/controls/index.md).  Понятия, рассматриваемые в этой теме, применяются к элементам, которые наследуют от класса <xref:System.Windows.Controls.Control>, за исключением <xref:System.Windows.Controls.UserControl>.  Применять шаблон <xref:System.Windows.Controls.ControlTemplate> к объекту <xref:System.Windows.Controls.UserControl> нельзя.  
  
<a name="when_you_should_create_a_controltemplate"></a>   
## Когда следует создавать шаблон ControlTemplate  
 Элементы управления имеют много свойств, таких как <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontFamily%2A>, которые можно задавать для установки разных аспектов внешнего вида элемента управления, но изменения, которые можно вносить путем установки этих свойств, ограничены.  Например, для элемента управления <xref:System.Windows.Controls.CheckBox> можно установить значение "blue" \(синий\) свойства <xref:System.Windows.Controls.Control.Foreground%2A> и значение "italic" \(курсив\) свойства <xref:System.Windows.Controls.Control.FontStyle%2A>.  
  
 Без возможности создания нового шаблона <xref:System.Windows.Controls.ControlTemplate> для элементов управления все элементы управления приложения на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] будут иметь один и тот же общий внешний вид, что ограничивает возможность создания приложения с настраиваемым внешним видом и функциями.  По умолчанию каждый элемент управления <xref:System.Windows.Controls.CheckBox> имеет одинаковые характеристики.  Например, содержимое элемента управления <xref:System.Windows.Controls.CheckBox> всегда находится справа от индикатора выделения, и для указания того, что выбран <xref:System.Windows.Controls.CheckBox>, всегда используется флажок.  
  
 Шаблон <xref:System.Windows.Controls.ControlTemplate>создается тогда, когда требуется настроить внешний вид элемента управления помимо того, что сделано установкой других его свойств.  Возьмем для примера элемент управления <xref:System.Windows.Controls.CheckBox> и предположим, что требуется отображать его содержимое над индикатором выделения, и для указания того, что элемент управления <xref:System.Windows.Controls.CheckBox> выбран, использовать знак X.  Эти изменения задаются в шаблоне <xref:System.Windows.Controls.ControlTemplate> для этого элемента управления <xref:System.Windows.Controls.CheckBox>.  
  
 На следующем рисунке показан элемент управления <xref:System.Windows.Controls.CheckBox>, который использует шаблон <xref:System.Windows.Controls.ControlTemplate>, установленный по умолчанию.  
  
 ![Флажок с шаблоном элемента управления по умолчанию.](../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP\_CheckBoxDefault")  
Элемент управления CheckBox, использующий шаблон элемента управления по умолчанию  
  
 На следующем рисунке показан элемент управления <xref:System.Windows.Controls.CheckBox>, использующий пользовательский шаблон <xref:System.Windows.Controls.ControlTemplate> для размещения содержимого <xref:System.Windows.Controls.CheckBox> над индикатором выделения и отображения знака X при выборе <xref:System.Windows.Controls.CheckBox>.  
  
 ![Флажок с пользовательским шаблоном элемента управления.](../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP\_CheckBoxCustom")  
Элемент управления CheckBox, использующий пользовательский шаблон элемента управления  
  
 Шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.CheckBox> в этом примере относительно сложный, поэтому в этой теме используется более простой пример создания шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.  
  
<a name="changing_the_visual_structure_of_a_control"></a>   
## Изменение визуальной структуры элемента управления  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент управления часто составлен из объектов <xref:System.Windows.FrameworkElement>.  При создании шаблона <xref:System.Windows.Controls.ControlTemplate> объекты <xref:System.Windows.FrameworkElement> объединяются для построения одного элемента управления.  Шаблон <xref:System.Windows.Controls.ControlTemplate> должен иметь только один элемент <xref:System.Windows.FrameworkElement> в качестве корневого элемента.  Корневой элемент обычно содержит другие объекты <xref:System.Windows.FrameworkElement>.  Комбинация объектов составляет визуальную структуру элемента управления.  
  
 В следующем примере создается пользовательский шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button>.  Шаблон <xref:System.Windows.Controls.ControlTemplate> создает визуальную структуру элемента управления <xref:System.Windows.Controls.Button>.  В этом примере не меняется внешний вид кнопки при перемещении на нее указателя мыши или при ее нажатии.  Изменение внешнего вида кнопки при ее переходе в другое состояние рассматривается в этой теме позднее.  
  
 В данном примере визуальная структура состоит из следующих частей:  
  
-   элемента <xref:System.Windows.Controls.Border> с именем `RootElement`, который служит в качестве корневого элемента <xref:System.Windows.FrameworkElement> для данного шаблона;  
  
-   элемента <xref:System.Windows.Controls.Grid>, который является дочерним по отношению к элементу `RootElement`;  
  
-   элемента <xref:System.Windows.Controls.ContentPresenter>, который отображает содержимое кнопки.  Элемент <xref:System.Windows.Controls.ContentPresenter> разрешает отображение любого типа объекта.  
  
 [!code-xml[VSMButtonTemplate#BasicTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#basictemplate)]  
  
### Сохранение функциональности свойств элемента управления с помощью TemplateBinding  
 При создании нового шаблона <xref:System.Windows.Controls.ControlTemplate> может также потребоваться использовать общие свойства для изменения внешнего вида элемента управления.  Расширение разметки [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) привязывает свойство элемента из шаблона <xref:System.Windows.Controls.ControlTemplate> к общему свойству, которое задается элементом управления.  Использование расширения [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) позволяет свойствам элемента управления действовать в качестве параметров шаблона.  Это означает, что при задании свойства элемента управления соответствующее значение передается в элемент, который содержит [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md).  
  
 В следующем примере повторяется часть предыдущего примера, в которой с помощью расширения разметки [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) используются для привязки свойств элементов из шаблона <xref:System.Windows.Controls.ControlTemplate> к общим свойствам, задаваемым кнопкой.  
  
 [!code-xml[VSMButtonTemplate#TemplateBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#templatebinding)]  
  
 В этом примере привязанное к шаблону свойство <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> элемента <xref:System.Windows.Controls.Grid> имеет значение <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName>.  Поскольку свойство <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=fullName> является привязанным к шаблону, можно создать несколько кнопок, использующих один шаблон <xref:System.Windows.Controls.ControlTemplate>, и установить свойство <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> в разные значения для каждой кнопки.  Если свойство <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> не было привязано к шаблону свойства элемента в шаблоне <xref:System.Windows.Controls.ControlTemplate>, то установка свойства <xref:System.Windows.Controls.Control.Background%2A?displayProperty=fullName> не влияет на внешний вид кнопки.  
  
 Следует отметить, что не требуется, чтобы имена этих двух свойств совпадали.  В предыдущем примере свойство <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> элемента управления <xref:System.Windows.Controls.Button> привязано к шаблону свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName> элемента управления <xref:System.Windows.Controls.ContentPresenter>.  Это позволяет располагать содержимое кнопки горизонтально.  У элемента управления <xref:System.Windows.Controls.ContentPresenter> отсутствует свойство с именем `HorizontalContentAlignment`, но свойство <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A?displayProperty=fullName> может быть привязано к свойству <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A?displayProperty=fullName>.  Перед привязкой свойства к шаблону следует убедиться, что целевое и исходное свойства имеют один и тот же тип.  
  
 Класс <xref:System.Windows.Controls.Control> определяет конкретные свойства, которые должен использовать шаблон элемента управления, чтобы их установка оказывала действие на элемент управления.  Каким образом шаблон <xref:System.Windows.Controls.ControlTemplate> использует свойство, зависит от свойства.  Шаблон <xref:System.Windows.Controls.ControlTemplate> должен использовать свойство одним из трех следующих способов:  
  
-   элемент в шаблоне <xref:System.Windows.Controls.ControlTemplate> привязывается к свойству;  
  
-   элемент в шаблоне <xref:System.Windows.Controls.ControlTemplate> наследует свойство от родительского <xref:System.Windows.FrameworkElement>.  
  
 В следующей таблице представлены визуальные свойства, наследуемые элементом управления от класса <xref:System.Windows.Controls.Control>.  В таблице также указывается, использует ли шаблон элемента управления по умолчанию значение наследуемого свойства, или оно должно быть привязано к шаблону.  
  
|Свойство.|Способ использования|  
|---------------|--------------------------|  
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
  
 В следующей таблице представлены только визуальные свойства, наследуемые от класса <xref:System.Windows.Controls.Control>.  Кроме свойств, приведенных в этой таблице, элемент управления может также наследовать свойства <xref:System.Windows.FrameworkElement.DataContext%2A>, <xref:System.Windows.FrameworkElement.Language%2A> и <xref:System.Windows.Controls.TextBlock.TextDecorations%2A> от родительского элемента структуры.  
  
 Кроме того, если элемент управления <xref:System.Windows.Controls.ContentPresenter> находится в шаблоне <xref:System.Windows.Controls.ControlTemplate> элемента управления <xref:System.Windows.Controls.ContentControl>, то <xref:System.Windows.Controls.ContentPresenter> будет автоматически привязывать свойства <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.Content%2A>.  Аналогично, элемент управления <xref:System.Windows.Controls.ItemsPresenter>, который находится в шаблоне <xref:System.Windows.Controls.ControlTemplate> элемента управления <xref:System.Windows.Controls.ItemsControl>, будет автоматически привязываться к свойствам <xref:System.Windows.Controls.ItemsControl.Items%2A> и <xref:System.Windows.Controls.ItemsPresenter>.  
  
 В следующем примере создаются две кнопки, которые используют шаблон <xref:System.Windows.Controls.ControlTemplate>, заданный в предыдущем примере.  В примере устанавливаются свойства <xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontSize%2A> каждой кнопки.  Установка свойства <xref:System.Windows.Controls.Control.Background%2A> оказывает влияние, поскольку оно привязано к шаблону <xref:System.Windows.Controls.ControlTemplate>.  Хотя свойства <xref:System.Windows.Controls.Control.Foreground%2A> и <xref:System.Windows.Controls.Control.FontSize%2A> не привязаны к шаблону, их установка тоже оказывает влияние, поскольку их значения являются наследуемыми.  
  
 [!code-xml[VSMButtonTemplate#ButtonDeclaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#buttondeclaration)]  
  
 В предыдущем примере получался результат, аналогичный показанному на следующем рисунке.  
  
 ![Две кнопки, одна синяя, а другая — фиолетовая.](../../../../docs/framework/wpf/controls/media/ndp-buttontwo.png "NDP\_ButtonTwo")  
Две кнопки с различными цветами фона  
  
<a name="changing_the_appearance_of_a_control_depending_on_its_state"></a>   
## Изменение внешнего вида элемента управления в зависимости от его состояния  
 Разница между кнопкой с внешним видом по умолчанию и кнопкой из предыдущего примера состоит в том, что кнопка по умолчанию слегка изменяется при переходе в другое состояние.  Например, внешний вид кнопки по умолчанию изменяется при нажатии этой кнопки или при наведении на нее указателя мыши.  Хотя шаблон <xref:System.Windows.Controls.ControlTemplate> не изменяет функциональность элемента управления, он изменяет визуальное поведение этого элемента.  Визуальное поведение описывает внешний вид элемента управления в определенных состояниях.  Чтобы лучше понять разницу между функциональностью и визуальным поведением элемента управления, рассмотрим пример с кнопкой.  Функциональность кнопки состоит в том, чтобы вызывать событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> при ее нажатии, а визуальное поведение кнопки состоит в том, чтобы изменять внешний вид при ее нажатии или наведении на нее указателя мыши.  
  
 Чтобы задать внешний вид элемента управления в определенных состояниях, используется объект <xref:System.Windows.VisualState>.  Объект <xref:System.Windows.VisualState> содержит объект <xref:System.Windows.Media.Animation.Storyboard>, который изменяет внешний вид элементов, находящихся в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  Нет необходимости писать какой\-либо код, чтобы это происходило, поскольку логика элемента управления изменяет состояние с помощью <xref:System.Windows.VisualStateManager>.  Когда элемент управления оказывается в состоянии, заданном свойством <xref:System.Windows.VisualState.Name%2A?displayProperty=fullName>, запускается <xref:System.Windows.Media.Animation.Storyboard>.  Когда элемент управления выходит из этого состояния, <xref:System.Windows.Media.Animation.Storyboard> останавливается.  
  
 В следующем примере показан объект <xref:System.Windows.VisualState>, который изменяет внешний вид элемента управления <xref:System.Windows.Controls.Button> при наведении на него указателя мыши.  <xref:System.Windows.Media.Animation.Storyboard> изменяет цвет границы кнопки путем изменения цвета `BorderBrush`.  Если обратиться к примеру <xref:System.Windows.Controls.ControlTemplate> в начале этой темы, то можно увидеть, что `BorderBrush` – это имя объекта <xref:System.Windows.Media.SolidColorBrush>, назначенного свойству <xref:System.Windows.Controls.Border.Background%2A> элемента <xref:System.Windows.Controls.Border>.  
  
 [!code-xml[VSMButtonTemplate#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#4)]  
  
 Элемент управления отвечает за определение состояний как часть своего контракта, что подробно рассматривается в разделе [Настройка других элементов управления через понимание контракта элемента управления](#customizing_other_controls_by_understanding_the_control_contract) далее в этой теме.  В следующей таблице перечислены состояния элемента управления <xref:System.Windows.Controls.Button>.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|---------------------|--------------------------|--------------|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Pressed|CommonStates|Элемент управления нажат.|  
|Disabled|CommonStates|Элемент управления отключен.|  
|Focused|FocusStates|Элемент управления имеет фокус.|  
|Unfocused|FocusStates|Элемент управления не имеет фокуса.|  
  
 Элемент управления <xref:System.Windows.Controls.Button> задает две группы состояний. Группа `CommonStates` содержит состояния `Normal`, `MouseOver`, `Pressed` и `Disabled`.  Группа `FocusStates` содержит состояния `Focused` и `Unfocused`.  Состояния, входящие в одну группу, являются взаимоисключающими.  Элемент управления всегда находится строго в одном состоянии из каждой группы.  Например, элемент управления <xref:System.Windows.Controls.Button> может иметь фокус, даже если в нем не находится указатель мыши, таким образом элемент <xref:System.Windows.Controls.Button> в состоянии `Focused` может также быть в одном из состояний `MouseOver`, `Pressed`, или `Normal`.  
  
 Объекты <xref:System.Windows.VisualState> добавляются в объекты <xref:System.Windows.VisualStateGroup>.  Объекты <xref:System.Windows.VisualStateGroup> добавляются в присоединенное свойство <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName>.  В следующем примере задаются объекты <xref:System.Windows.VisualState> для состояний `Normal`, `MouseOver` и `Pressed`, которые входят в группу `CommonStates`.  Имя <xref:System.Windows.VisualState.Name%2A> каждого состояния <xref:System.Windows.VisualState> соответствует имени, указанному в предыдущей таблице.  Состояние `Disabled` и состояния из группы `FocusStates` опущены для сохранения краткости примера, но они включены в полный пример, приведенный в конце этой темы.  
  
> [!NOTE]
>  Необходимо задать присоединенное свойство <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=fullName> для корневого элемента <xref:System.Windows.FrameworkElement> шаблона <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xml[VSMButtonTemplate#VisualStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualstates)]  
  
 В предыдущем примере получался результат, аналогичный показанному на следующих рисунках.  
  
 ![Кнопка с пользовательским шаблоном элемента управления.](../../../../docs/framework/wpf/controls/media/ndp-buttonnormal.png "NDP\_ButtonNormal")  
Кнопка, использующая пользовательский шаблон элемента управления в нормальном состоянии  
  
 ![Кнопка с красной границей.](../../../../docs/framework/wpf/controls/media/ndp-buttonmouseover.png "NDP\_ButtonMouseOver")  
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда указатель мыши находится вне кнопки  
  
 ![Граница прозрачна на нажатой кнопке.](../../../../docs/framework/wpf/controls/media/ndp-buttonpressed.png "NDP\_ButtonPressed")  
Кнопка, использующая пользовательский шаблон элемента управления в состоянии, когда она нажата  
  
 Визуальные состояния элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
<a name="specifying_the_behavior_of_a_control_when_it_transitions_between_states"></a>   
## Задание поведения элемента управления, когда он переходит между состояниями  
 В предыдущем примере внешний вид кнопки изменяется, когда пользователь нажимает ее, но если кнопка остается нажатой менее полной секунды, то пользователь не видит эффекта нажатия.  По умолчанию для запуска анимации требуется одна секунда.  Поскольку пользователи, вероятно, нажимают и освобождают кнопку за гораздо меньшее время, визуальный отклик будет неэффективен, если шаблон <xref:System.Windows.Controls.ControlTemplate> будет оставлен в состоянии по умолчанию.  
  
 Можно указать интервал времени, который требуется для запуска анимации, чтобы элемент управления плавно переходил из одного состояние в другое, добавив объекты <xref:System.Windows.VisualTransition> в шаблон <xref:System.Windows.Controls.ControlTemplate>.  При создании объектов <xref:System.Windows.VisualTransition> можно указать один или несколько следующих параметров:  
  
-   время, которое занимает переход между состояниями;  
  
-   дополнительные изменения внешнего вида элемента управления, возникающие во время перехода;  
  
-   состояния, к которым применяется объект <xref:System.Windows.VisualTransition>.  
  
### Задание продолжительности перехода  
 Продолжительность перехода можно указать путем установки свойства <xref:System.Windows.VisualTransition.GeneratedDuration%2A>.  В предыдущем примере имеется элемент <xref:System.Windows.VisualState>, который указывает, что граница кнопки становится прозрачной при нажатии на эту кнопку, но анимация продолжается слишком долго, чтобы быть заметной при быстром нажатии и освобождении кнопки.  С помощью <xref:System.Windows.VisualTransition> можно указать период времени, который занимает переход этого элемента управления в состояние нажатия.  В следующем примере задается, что переход элемента управления в нажатое состояние занимает одну сотую секунды.  
  
 [!code-xml[VSMButtonTemplate#PressedTransition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#pressedtransition)]  
  
### Задание изменений внешнего вида элемента управления во время перехода  
 Объект <xref:System.Windows.VisualTransition> содержит анимацию <xref:System.Windows.Media.Animation.Storyboard>, которая начинается при переходе элемента управления из одного состояния в другое.  Например, можно указать, что определенная анимация происходит при переходе элемента управления от состояния `MouseOver` в состояние `Normal`.  В следующем примере создается объект <xref:System.Windows.VisualTransition>, который задает, что при перемещении указателя мыши за пределы кнопки граница кнопки изменяет цвет на синий, затем на желтый и затем на черный в течение полутора секунд.  
  
 [!code-xml[VSMButtonTemplate#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#8)]  
  
### Указание места применения VisualTransition  
 Применение <xref:System.Windows.VisualTransition> можно ограничить только определенными состояниями, или задать его применение при переходе элемента управления между любыми состояниями.  В предыдущем примере <xref:System.Windows.VisualTransition> применяется, когда элемент управления переходит от состояния `MouseOver` в состояние `Normal`; в примере перед ним <xref:System.Windows.VisualTransition> применяется, когда элемент управления переходит в состояние `Pressed`.  Применение <xref:System.Windows.VisualTransition> ограничивается путем установки свойств <xref:System.Windows.VisualTransition.To%2A> и <xref:System.Windows.VisualTransition.From%2A>.  В следующей таблице приведено описание уровней ограничений от наибольшего до наименьшего.  
  
|Тип ограничения|Состояние, из которого выполняется переход|Состояние, в которое выполняется переход|  
|---------------------|------------------------------------------------|----------------------------------------------|  
|Из указанного состояния в другое указанное состояние|Имя <xref:System.Windows.VisualState>.|Имя <xref:System.Windows.VisualState>.|  
|Из любого состояния в указанное состояние|Не задано|Имя <xref:System.Windows.VisualState>.|  
|Из указанного состояния в любое состояние|Имя <xref:System.Windows.VisualState>.|Не задано|  
|Из любого состояния в любое другое состояние|Не задано|Не задано|  
  
 Можно использовать несколько объектов <xref:System.Windows.VisualTransition> в группе <xref:System.Windows.VisualStateGroup>, относящихся к одному и тому же состоянию, но они будут применяться согласно порядку, указанному в предыдущей таблице.  В следующем примере имеется два объекта <xref:System.Windows.VisualTransition>.  Когда элемент управления переходит из состояния `Pressed` в состояние `MouseOver`, используется объект <xref:System.Windows.VisualTransition>, у которого установлены оба атрибута <xref:System.Windows.VisualTransition.From%2A> и <xref:System.Windows.VisualTransition.To%2A>.  Когда элемент управления переходит из состояния, отличного от `Pressed`, в состояние `MouseOver`, используется другой объект VisualTransition.  
  
 [!code-xml[VSMButtonTemplate#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#7)]  
  
 Группа <xref:System.Windows.VisualStateGroup> имеет свойство <xref:System.Windows.VisualStateGroup.Transitions%2A>, в котором содержатся объекты <xref:System.Windows.VisualTransition>, применяемые к объектам <xref:System.Windows.VisualState> в группе <xref:System.Windows.VisualStateGroup>.  Автор <xref:System.Windows.Controls.ControlTemplate> может включать любые желаемые объекты <xref:System.Windows.VisualTransition>.  Однако если в качестве значений свойств <xref:System.Windows.VisualTransition.To%2A> и <xref:System.Windows.VisualTransition.From%2A> установлены имена состояний, не входящих в группу <xref:System.Windows.VisualStateGroup>, то объект <xref:System.Windows.VisualTransition> игнорируется.  
  
 В следующем примере показана группа <xref:System.Windows.VisualStateGroup> для группы состояний `CommonStates`.  В этом примере задается объект <xref:System.Windows.VisualTransition> для каждого из следующих переходов кнопки:  
  
-   в состояние `Pressed`;  
  
-   в состояние `MouseOver`;  
  
-   из состояния `Pressed` в состояние `MouseOver`;  
  
-   из состояния `MouseOver` в состояние `Normal`.  
  
 [!code-xml[VSMButtonTemplate#VisualTransitions](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/buttonstages.xaml#visualtransitions)]  
  
<a name="customizing_other_controls_by_understanding_the_control_contract"></a>   
## Настройка других элементов управления через понимание контракта элемента управления  
 Элемент управления, использующий шаблон <xref:System.Windows.Controls.ControlTemplate> для задания визуальной структуры \(с помощью объектов <xref:System.Windows.FrameworkElement>\) и визуального поведения \(с помощью объектов <xref:System.Windows.VisualState>\), применяет модель частей элемента управления.  Множество элементов управления, имеющихся в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 4, используют эту модель.  Части, которые должен учитывать автор шаблона <xref:System.Windows.Controls.ControlTemplate>, взаимодействуют с помощью контракта элемента управления.  Поняв части контракта элемента управления, можно настроить внешний вид любого элемента управления, использующего модель частей элемента управления.  
  
 Контракт элемента управления имеет три элемента:  
  
-   визуальный элемент, используемый логикой элемента управления;  
  
-   состояния элемента управления и группа, к которой принадлежит каждое состояние;  
  
-   общие свойства, визуально воздействующие на элемент управления.  
  
### Визуальные элементы в контракте элемента управления  
 Время от времени логика элемента управления взаимодействует с элементом <xref:System.Windows.FrameworkElement>, который находится в шаблоне <xref:System.Windows.Controls.ControlTemplate>.  Например, элемент управления может обрабатывать событие одного из своих элементов.  Когда элемент управления ожидает найти конкретный элемент <xref:System.Windows.FrameworkElement> в шаблоне <xref:System.Windows.Controls.ControlTemplate>, он должен передать эти сведения автору шаблона <xref:System.Windows.Controls.ControlTemplate>.  Элемент управления использует атрибут <xref:System.Windows.TemplatePartAttribute> для передачи типа ожидаемого элемента и имени, которое он должен иметь.  В контракте элемента управления <xref:System.Windows.Controls.Button> отсутствуют части <xref:System.Windows.FrameworkElement>, но в контрактах других элементах управления, таких как <xref:System.Windows.Controls.ComboBox>, части имеются.  
  
 В следующем примере показаны объекты <xref:System.Windows.TemplatePartAttribute>, заданные в классе <xref:System.Windows.Controls.ComboBox>.  Логика элемента управления <xref:System.Windows.Controls.ComboBox> ожидает найти в своем шаблоне <xref:System.Windows.Controls.ControlTemplate> элемент <xref:System.Windows.Controls.TextBox> с именем `PART_EditableTextBox` и элемент <xref:System.Windows.Controls.Primitives.Popup> с именем `PART_Popup`.  
  
 [!code-csharp[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#comboboxcontract)]
 [!code-vb[VSMButtonTemplate#ComboBoxContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#comboboxcontract)]  
  
 В следующем примере показан упрощенный шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ComboBox>, включающий элементы, которые заданы объектами <xref:System.Windows.TemplatePartAttribute> в классе <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xml[VSMButtonTemplate#ComboBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/window1.xaml#comboboxtemplate)]  
  
### Состояния в контракте элемента управления  
 Состояния элемента управления также являются частями его контракта.  В примере создания шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Button> показывается порядок задания внешнего вида элемента управления <xref:System.Windows.Controls.Button> в зависимости от его состояния.  Процесс создания <xref:System.Windows.VisualState> для каждого указанного состояния и помещения всех объектов <xref:System.Windows.VisualState>, совместно использующих <xref:System.Windows.TemplateVisualStateAttribute.GroupName%2A> в группе <xref:System.Windows.VisualStateGroup>, описан в разделе [Изменение внешнего вида элемента управления в зависимости от его состояния](#changing_the_appearance_of_a_control_depending_on_its_state) ранее в этой теме.  Сторонние элементы управления должны указывать состояния с помощью <xref:System.Windows.TemplateVisualStateAttribute>, разрешающее средства проектирования, например expression blend, чтобы предоставить состояния элемента управления для создания шаблонов элементов управления.  
  
 Контракты элементов управления, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в разделе [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md).  
  
### Свойства в контракте элемента управления  
 Общие свойства, визуально влияющие на элемент управления, также включаются в контракт элемента управления.  Эти свойства можно устанавливать для изменения внешнего вида элемента управления без создания нового шаблона <xref:System.Windows.Controls.ControlTemplate>.  Можно также воспользоваться расширением разметки [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), чтобы привязать свойства элементов, которые имеются в шаблоне <xref:System.Windows.Controls.ControlTemplate>, к общим свойствам, заданным элементом управления <xref:System.Windows.Controls.Button>.  
  
 В следующем примере показан контракт элемента управления "Кнопка".  
  
 [!code-csharp[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/controlcontracts.cs#buttoncontract)]
 [!code-vb[VSMButtonTemplate#ButtonContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmbuttontemplate/visualbasic/window1.xaml.vb#buttoncontract)]  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> часто бывает проще начать с существующего шаблона <xref:System.Windows.Controls.ControlTemplate> и вносить в него изменения.  Чтобы изменить существующий шаблон <xref:System.Windows.Controls.ControlTemplate>, можно выполнить одно из приведенных ниже действий.  
  
-   Воспользоваться конструктором, таким как Expression Blend, который предоставляет графический пользовательский интерфейс для создания шаблонов элементов управления.  Дополнительные сведения см. в статье [Настройка стиля элемента управления, поддерживающего шаблоны \(статья может быть на английском языке\)](http://go.microsoft.com/fwlink/?LinkId=161153).  
  
-   Вызвать шаблон <xref:System.Windows.Controls.ControlTemplate>, установленный по умолчанию, и изменить его.  Шаблоны элементов управления по умолчанию, включенных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], см. в документе [Default WPF Themes](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
<a name="complete_example"></a>   
## Полный пример  
 В следующем примере показан полный шаблон <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.ControlTemplate>, который рассматривается в этой теме.  
  
 [!code-xml[VSMButtonTemplate#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmbuttontemplate/csharp/skinnedbutton.xaml#3)]  
  
## См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)