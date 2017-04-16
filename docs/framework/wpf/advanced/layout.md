---
title: "Макет | Microsoft Docs"
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
  - "элементы управления [WPF], система макета"
  - "система макета [WPF]"
  - "система макета WPF"
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Макет
В этом разделе описывается система макета [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Для создания пользовательских интерфейсов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] важно понимание того, как и когда происходят вычисления макета.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Ограничивающие прямоугольники элемента](#LayoutSystem_BoundingBox)  
  
-   [Система макета](#LayoutSystem_Overview)  
  
-   [Измерение и расположение дочерних элементов](#LayoutSystem_Measure_Arrange)  
  
-   [Элементы панели и пользовательские расширения функциональности макета](#LayoutSystem_PanelsCustom)  
  
-   [Вопросы производительности макета](#LayoutSystem_Performance)  
  
-   [Субпиксельная отрисовка и округление макета](#LayoutSystem_LayoutRounding)  
  
-   [Что дальше?](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## Ограничивающие прямоугольники элемента  
 При планировании макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] важно понимать принцип функционирования ограничивающих прямоугольников, которые окружают все элементы.  Каждый <xref:System.Windows.FrameworkElement>, обрабатываемый макетом системы, может быть рассмотрен как прямоугольник, вставленный в макет.  Класс <xref:System.Windows.Controls.Primitives.LayoutInformation> возвращает границы области, выделенной макетом для элемента, или ячейки.  Размер этого прямоугольника определяется путем вычисления доступного пространства экрана, размера каких\-либо ограничений, свойств макета \(таких как поля и заполнение\), а также индивидуального поведения родительского элемента <xref:System.Windows.Controls.Panel>.  Обрабатывая эти данные, система макета имеет возможность вычислить положение всех потомков конкретного элемента <xref:System.Windows.Controls.Panel>.  Важно помнить, что характеристики размеров, определенные для родительского элемента, такого как <xref:System.Windows.Controls.Border>, влияют на его дочерние элементы.  
  
 На следующем рисунке представлен простой макет.  
  
 ![Обычная сетка, без обрамляющего прямоугольника.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Этот макет можно получить с помощью следующего [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Один элемент управления <xref:System.Windows.Controls.TextBlock> расположен в элементе управления <xref:System.Windows.Controls.Grid>.  Хотя текст заполняет только верхний левый угол первого столбца, выделенное пространство для элемента <xref:System.Windows.Controls.TextBlock> на самом деле гораздо больше.  Ограничивающий прямоугольник какого\-либо элемента <xref:System.Windows.FrameworkElement> можно извлечь с помощью метода <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>.  На следующем рисунке показан ограничивающий прямоугольник для элемента <xref:System.Windows.Controls.TextBlock>.  
  
 ![Теперь обрамляющий прямоугольник для TextBlock отображается.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Как показано желтым прямоугольником, выделенное пространство для элемента <xref:System.Windows.Controls.TextBlock> фактически гораздо больше пространства, в котором он отображается.  При добавлении дополнительных элементов к <xref:System.Windows.Controls.Grid> данное распределение может сжиматься или растягиваться в зависимости от типа и размера добавляемых элементов.  
  
 Ячейка макета элемента <xref:System.Windows.Controls.TextBlock> передается в объект <xref:System.Windows.Shapes.Path> с помощью метода <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A>.  Этот способ может быть полезен для отображения ограничивающего прямоугольника элемента.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## Система макета  
 В самом простом случае макет является рекурсивной системой, которая изменяет размер и расположение элемента и отображает его на экране.  В частности, макет описывает процесс измерения и расположения членов коллекции <xref:System.Windows.Controls.Panel.Children%2A> элемента <xref:System.Windows.Controls.Panel>.  Макет является интенсивным процессом.  Чем больше коллекция <xref:System.Windows.Controls.Panel.Children%2A>, тем больший объем вычислений должен быть выполнен.  Сложность может также быть вызвана поведением макета, определяемым элементом <xref:System.Windows.Controls.Panel>, которому принадлежит коллекция.  Относительно простой макет <xref:System.Windows.Controls.Panel>, такой как <xref:System.Windows.Controls.Canvas>, может иметь лучшую производительность, чем более сложный макет <xref:System.Windows.Controls.Panel>, такой как <xref:System.Windows.Controls.Grid>.  
  
 Каждый раз, когда дочерний элемент <xref:System.Windows.UIElement> изменяет свое положение, он потенциально имеет возможность запустить новый проход системы макета.  Таким образом, важно понимать события, которые может вызвать система макета, так как ненужный вызов может привести к ухудшению производительности приложения.  Далее описывается процесс, который возникает при вызове системы макета.  
  
1.  Дочерний элемент <xref:System.Windows.UIElement> начинает процесс макета с измерения его основных свойств.  
  
2.  Вычисляются размерные свойства, определенные в элементе <xref:System.Windows.FrameworkElement>. Такими свойствами являются <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  Применяется специальная логика <xref:System.Windows.Controls.Panel>, такая как направление <xref:System.Windows.Controls.Dock> или наложение <xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  Содержимое располагается после того, как все потомки были измерены.  
  
5.  Коллекция <xref:System.Windows.Controls.Panel.Children%2A> отображается на экране.  
  
6.  Процесс вызывается снова, если в коллекцию добавляются дополнительные <xref:System.Windows.Controls.Panel.Children%2A>, применяется <xref:System.Windows.FrameworkElement.LayoutTransform%2A> или вызывается метод <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
 Этот процесс и порядок его вызова более подробно рассматриваются в следующих разделах.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## Измерение и расположение дочерних элементов  
 Система макета совершает два прохода для каждого члена коллекции <xref:System.Windows.Controls.Panel.Children%2A>, проход измерения и проход компоновки.  Каждый дочерний элемент <xref:System.Windows.Controls.Panel> предоставляет свои собственные методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>, чтобы добиться собственного определенного поведения макета.  
  
 Во время выполнения измерения оценивается каждый член коллекции <xref:System.Windows.Controls.Panel.Children%2A>.  Процесс начинается с вызова метода <xref:System.Windows.UIElement.Measure%2A>.  Этот метод вызывается в реализации родительского элемента <xref:System.Windows.Controls.Panel>; он не должен вызываться явным образом для вызова макета.  
  
 Во\-первых, вычисляются собственные свойства размера <xref:System.Windows.UIElement>, такие как <xref:System.Windows.UIElement.Clip%2A> и <xref:System.Windows.UIElement.Visibility%2A>.  Это создает значение с именем `constraintSize`, которое передается в метод <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 Затем обрабатываются свойства структуры, определенные в элементе <xref:System.Windows.FrameworkElement>. Это влияет на значение `constraintSize`.  Эти свойства в основном описывают размерные характеристики базового элемента <xref:System.Windows.UIElement>, например его <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.Style%2A>.  Каждое из этих свойств может изменить пространство, необходимое для отображения элемента.  Затем вызывается метод <xref:System.Windows.FrameworkElement.MeasureOverride%2A> с параметром `constraintSize`.  
  
> [!NOTE]
>  Свойства <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A> различаются.  Например, свойство <xref:System.Windows.FrameworkElement.ActualHeight%2A> является значением, вычисляемым на основе других вводимых высот и системы макета.  Значение задается самой системой макета на основе фактического прохождения отрисовки, а поэтому может немного отставать от установки значений свойств, например <xref:System.Windows.FrameworkElement.Height%2A>, которые являются основой для изменения ввода.  
>   
>  Поскольку <xref:System.Windows.FrameworkElement.ActualHeight%2A> является вычисляемым значением, следует иметь в виду, что в результате различных операций, выполняемых системой макета, с этим значением могут производиться многократные или добавочные сообщаемые изменения.  Система макета может вычислять требуемое место измерения для дочерних элементов, ограничения родительского элемента и т. д.  
  
 Конечной целью прохода измерения для дочернего элемента является определение его <xref:System.Windows.UIElement.DesiredSize%2A>, которое происходит во время вызова метода <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  Значение <xref:System.Windows.UIElement.DesiredSize%2A> сохраняется методом <xref:System.Windows.UIElement.Measure%2A> для использования во время процесса компоновки содержимого.  
  
 Процесс компоновки начинается с вызова метода <xref:System.Windows.UIElement.Arrange%2A>.  Во время прохода компоновки родительский элемент <xref:System.Windows.Controls.Panel> создает прямоугольник, представляющий границы потомка.  Это значение передается методу <xref:System.Windows.FrameworkElement.ArrangeCore%2A> для обработки.  
  
 Метод <xref:System.Windows.FrameworkElement.ArrangeCore%2A> оценивает свойство <xref:System.Windows.UIElement.DesiredSize%2A> дочернего элемента и оценивает все дополнительные границы, которые могут повлиять на отображаемый размер элемента.  Метод <xref:System.Windows.FrameworkElement.ArrangeCore%2A> создает параметр `arrangeSize`, который передается методу <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> объекта <xref:System.Windows.Controls.Panel> как параметр.  Метод <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> создает `finalSize` дочернего объекта.  Наконец, метод <xref:System.Windows.FrameworkElement.ArrangeCore%2A> выполняет окончательную оценку свойств смещения, таких как границы и выравнивание, и помещает дочерний объект в его ячейку макета.  Дочерний объект не должен обязательно заполнять все выделенное пространство \(и в большинстве случаев не делает этого\).  Затем элемент управления возвращается к родительскому объекту <xref:System.Windows.Controls.Panel>, и обработка макета завершается.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## Элементы панели и пользовательские расширения функциональности макета  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется группа элементов, производных от <xref:System.Windows.Controls.Panel>.  Эти элементы <xref:System.Windows.Controls.Panel> включают многие сложные макеты.  Например, вложенные элементы можно легко получить с помощью элемента <xref:System.Windows.Controls.StackPanel>, в то время как более сложные и свободно располагаемые макеты создаются при помощи <xref:System.Windows.Controls.Canvas>.  
  
 В следующей таблице перечислены доступные элементы макета <xref:System.Windows.Controls.Panel>.  
  
|Имя панели|Описание|  
|----------------|--------------|  
|<xref:System.Windows.Controls.Canvas>|Определяет область, внутри которой можно явным образом разместить дочерние элементы при помощи относительных координат в области <xref:System.Windows.Controls.Canvas>.|  
|<xref:System.Windows.Controls.DockPanel>|Определяет область, внутри которой можно упорядочить дочерние элементы по горизонтали или по вертикали друг относительно друга.|  
|<xref:System.Windows.Controls.Grid>|Определяет гибкую область сетки, состоящую из столбцов и строк.|  
|<xref:System.Windows.Controls.StackPanel>|Располагает дочерние элементы в одну строку, которую можно ориентировать по горизонтали или по вертикали.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Предоставляет структуру для элементов <xref:System.Windows.Controls.Panel>, которые виртуализируют свою коллекцию дочерних данных.  Этот класс является абстрактным.|  
|<xref:System.Windows.Controls.WrapPanel>|Размещает дочерние элементы последовательно слева направо, разбивая содержимое до следующей строки на краю содержащего окна.  Дальнейшее упорядочивание происходит последовательно сверху вниз или справа налево в зависимости от значения свойства <xref:System.Windows.Controls.WrapPanel.Orientation%2A>.|  
  
 Для приложений, которым требуется макет, который невозможно создать при помощи любого из предварительно определенных элементов <xref:System.Windows.Controls.Panel>, пользовательские расширения функциональности макета можно получить путем наследования из <xref:System.Windows.Controls.Panel> и переопределения методов <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  Пример см. на странице [Пример "Custom Radial Panel" \(страница может отображаться на английском языке\)](http://go.microsoft.com/fwlink/?LinkID=159982)  
  
<a name="LayoutSystem_Performance"></a>   
## Вопросы производительности макета  
 Макет является рекурсивным процессом.  Все дочерние элементы в коллекции <xref:System.Windows.Controls.Panel.Children%2A> обрабатываются при каждом вызове системы макета.  Это означает, что следует избегать запуска системы макета при отсутствии необходимости.  Выполнение следующих рекомендаций поможет добиться более высокой производительности.  
  
-   Следует учитывать, что определенные изменения значений свойств могут привести к выполнению системой макета рекурсивного обновления.  
  
     Свойства зависимостей, чьи значения могут привести к инициализации системы макета. помечаются общими флагами.  Свойства <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> и <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> предоставляют полезные указания о том, какие изменения значений свойств вызовут рекурсивное обновление системы макета.  В целом любое свойство, которое может повлиять на размер ограничивающего прямоугольника элемента, должно иметь флаг <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, установленный в значение true.  Дополнительные сведения см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   Рекомендуется использовать свойство <xref:System.Windows.UIElement.RenderTransform%2A> вместо <xref:System.Windows.FrameworkElement.LayoutTransform%2A> везде, где это возможно.  
  
     <xref:System.Windows.FrameworkElement.LayoutTransform%2A> — это удобный способ определения содержимого [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Однако если результат преобразования не влияет на положение других элементов, рекомендуется использовать свойство <xref:System.Windows.UIElement.RenderTransform%2A>, поскольку <xref:System.Windows.UIElement.RenderTransform%2A> не вызывает систему макета.  Свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A> применяет свое преобразование и вызывает рекурсивное обновление макета для учета нового положения затронутого элемента.  
  
-   Избегайте ненужных вызовов <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     Метод <xref:System.Windows.UIElement.UpdateLayout%2A> вызывает рекурсивное обновление макета, что зачастую не требуется.  Если нет уверенности в необходимости обновления, следует предоставить вызов этого метода системе макета.  
  
-   При работе с большой коллекцией <xref:System.Windows.Controls.Panel.Children%2A> рекомендуется рассмотреть возможность использования элемента <xref:System.Windows.Controls.VirtualizingStackPanel> вместо обычного <xref:System.Windows.Controls.StackPanel>.  
  
     Виртуализация дочерней коллекции приводит к тому, что <xref:System.Windows.Controls.VirtualizingStackPanel> сохраняет в памяти только те объекты, которые в текущий момент находятся внутри родительского элемента [ViewPort](GTMT).  В результате этого производительность значительно увеличивается в большинстве скриптов.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## Субпиксельная отрисовка и округление макета  
 Графическая система [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует аппаратно\-независимые модули для поддержки разрешения и независимости от устройства.  Каждый независимый от устройства пиксель автоматически масштабируется согласно параметрам системы [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)].  Это обеспечивает приложениям [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] корректное масштабирование для различных параметров [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] и автоматически предоставляет приложениям поддержку [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)].  
  
 Однако эта независимость [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] может создать неравномерную отрисовку границ из\-за сглаживания.  Эти эффекты, обычно выглядящие как смазанные или полупрозрачные границы, могут появиться, когда положение границы попадает в середину пикселя устройства, а не между пикселями.  В системе макета имеется способ настройки границ с помощью округления макета.  Округление макета происходит, когда система макета округляет все нецелочисленные значения пикселей во время прохода макета.  
  
 По умолчанию округление макета отключено.  Чтобы включить округление макета, следует установить свойство <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> в значение `true` в любом элементе <xref:System.Windows.FrameworkElement>.  Поскольку это свойство зависимостей, значение будет распространено на все дочерние объекты в визуальном дереве.  Чтобы включить округление макета для всего пользовательского интерфейса, следует установить свойство <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> в значение `true` в корневом контейнере.  Пример см. в разделе <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## Что дальше?  
 Понимание механизма измерения и упорядочивания элементов – это первый шаг к пониманию макета.  Дополнительные сведения о доступных элементах <xref:System.Windows.Controls.Panel> см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).  Чтобы лучше понять различные свойства размещения, которые могут повлиять на макет, обратитесь к [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md).  Пример пользовательского элемента <xref:System.Windows.Controls.Panel> см. на странице [Пример "Custom Radial Panel" \(страница может отображаться на английском языке\)](http://go.microsoft.com/fwlink/?LinkID=159982).  Когда все элементы будут готовы к помещению в облегченное приложение, просмотрите раздел [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## См. также  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.UIElement>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)