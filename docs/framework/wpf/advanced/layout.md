---
title: "Макет"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WPF layout system [WPF]
- controls [WPF], layout system
- layout system [WPF]
ms.assetid: 3eecdced-3623-403a-a077-7595453a9221
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82f5f69390f2b4d27f1f41050971afa9faede960
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="layout"></a>Макет
В этом разделе описывается система макета [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Для создания пользовательских интерфейсов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] важно понимание того, как и когда происходят вычисления макета.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Ограничивающие прямоугольники элемента](#LayoutSystem_BoundingBox)  
  
-   [Система макета](#LayoutSystem_Overview)  
  
-   [Измерение и расположение дочерних элементов](#LayoutSystem_Measure_Arrange)  
  
-   [Элементы панели и пользовательские расширения функциональности макета](#LayoutSystem_PanelsCustom)  
  
-   [Вопросы производительности макета](#LayoutSystem_Performance)  
  
-   [Субпиксельная отрисовка и округление макета](#LayoutSystem_LayoutRounding)  
  
-   [Дальнейшие действия](#LayoutSystem_whatsnext)  
  
<a name="LayoutSystem_BoundingBox"></a>   
## <a name="element-bounding-boxes"></a>Ограничивающие прямоугольники элемента  
 При планировании макета в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] важно понимать принцип функционирования ограничивающих прямоугольников, которые окружают все элементы. Каждый <xref:System.Windows.FrameworkElement> потребляет макетом системы можно рассматривать как прямоугольник, вставленный в макет. <xref:System.Windows.Controls.Primitives.LayoutInformation> Класс возвращает границы макета выделения, или элемента слота. Размер прямоугольника определяется путем вычисления доступного пространства экрана, размера любых ограничений, свойств макета (например, поля и заполнение) и отдельных поведения родительского <xref:System.Windows.Controls.Panel> элемента. Обрабатывая эти данные, система макета имеет возможность вычислить положение всех потомков конкретного <xref:System.Windows.Controls.Panel>. Важно помнить, что характеристики размеров, определенные для родительского элемента, такие как <xref:System.Windows.Controls.Border>, влияют на его дочерние элементы.  
  
 На рисунке ниже представлен простой макет.  
  
 ![Обычная сетка без ограничивающего прямоугольника.](../../../../docs/framework/wpf/advanced/media/boundingbox1.png "boundingbox1")  
  
 Этот макет можно получить с помощью приведенного ниже кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[LayoutInformation#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml#1)]  
  
 Один <xref:System.Windows.Controls.TextBlock> элемент размещается в <xref:System.Windows.Controls.Grid>. Хотя текст заполняет только верхний левый угол первого столбца, выделенное пространство для <xref:System.Windows.Controls.TextBlock> фактически значительно больше. Ограничивающий прямоугольник любого <xref:System.Windows.FrameworkElement> можно получить с помощью <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> метод. На следующем рисунке показан ограничивающий прямоугольник для <xref:System.Windows.Controls.TextBlock> элемента.  
  
 ![Теперь ограничивающий прямоугольник для TextBlock отображается.](../../../../docs/framework/wpf/advanced/media/boundingbox2.png "boundingbox2")  
  
 Как показано желтым прямоугольником, выделенное пространство для <xref:System.Windows.Controls.TextBlock> элемент фактически гораздо больше он отображается. При добавлении дополнительных элементов <xref:System.Windows.Controls.Grid>, это выделение может сжать или растянуть, в зависимости от типа и размера добавляемых элементов.  
  
 О расположении <xref:System.Windows.Controls.TextBlock> преобразуется в <xref:System.Windows.Shapes.Path> с помощью <xref:System.Windows.Controls.Primitives.LayoutInformation.GetLayoutSlot%2A> метод. Этот способ может быть полезен для отображения ограничивающего прямоугольника элемента.  
  
 [!code-csharp[LayoutInformation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LayoutInformation/CSharp/Window1.xaml.cs#2)]
 [!code-vb[LayoutInformation#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/LayoutInformation/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="LayoutSystem_Overview"></a>   
## <a name="the-layout-system"></a>Система макета  
 В самом простом случае макет является рекурсивной системой, которая изменяет размер и расположение элемента и отображает его на экране. В частности, макет описывает процесс измерения и упорядочения объекта <xref:System.Windows.Controls.Panel> элемента <xref:System.Windows.Controls.Panel.Children%2A> коллекции. Макет является интенсивным процессом. Чем больше <xref:System.Windows.Controls.Panel.Children%2A> коллекции, тем больше число вычислений, которые необходимо сделать. Сложность может также быть вызвана поведением макета, определяемым <xref:System.Windows.Controls.Panel> элемент, которому принадлежит коллекция. Относительно простые <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Canvas>, может иметь лучшую производительность, чем более сложное <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Grid>.  
  
 Каждый раз, дочерний элемент <xref:System.Windows.UIElement> изменяет свое положение, он потенциально имеет возможность запустить новый проход системы макета. Таким образом, важно понимать события, которые может вызывать система макета, так как ненужный вызов может привести к ухудшению производительности приложения. Далее описывается процесс, который происходит при вызове системы макета.  
  
1.  Дочерний элемент <xref:System.Windows.UIElement> начинает процесс разметки первым, задав его основные измеряемые свойства.  
  
2.  Свойства, определенные для размера <xref:System.Windows.FrameworkElement> вычисляются, таких как <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, и <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
3.  <xref:System.Windows.Controls.Panel>-применяется логика, таких как <xref:System.Windows.Controls.Dock> направление или наложение <xref:System.Windows.Controls.StackPanel.Orientation%2A>.  
  
4.  Содержимое располагается после того, как все потомки были измерены.  
  
5.  <xref:System.Windows.Controls.Panel.Children%2A> Коллекции выводится на экран.  
  
6.  Процесс вызывается снова, если дополнительные <xref:System.Windows.Controls.Panel.Children%2A> добавляются в коллекцию <xref:System.Windows.FrameworkElement.LayoutTransform%2A> применяется, или <xref:System.Windows.UIElement.UpdateLayout%2A> вызывается метод.  
  
 Этот процесс и порядок его вызова более подробно рассматриваются в следующих разделах.  
  
<a name="LayoutSystem_Measure_Arrange"></a>   
## <a name="measuring-and-arranging-children"></a>Измерение и расположение дочерних элементов  
 Система макета совершает два прохода для каждого члена <xref:System.Windows.Controls.Panel.Children%2A> коллекции, проход измерения и проход компоновки. Каждый дочерний элемент <xref:System.Windows.Controls.Panel> предоставляет собственный <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> способов достижения свое поведение определенного макета.  
  
 Во время прохода мер, каждый член <xref:System.Windows.Controls.Panel.Children%2A> вычисляется коллекции. Процесс начинается с вызова <xref:System.Windows.UIElement.Measure%2A> метод. Этот метод вызывается в реализации родительского <xref:System.Windows.Controls.Panel> элемент и не должен вызываться явным образом для выполнения макета.  
  
 Во-первых, собственный размер свойства <xref:System.Windows.UIElement> вычисляются, таких как <xref:System.Windows.UIElement.Clip%2A> и <xref:System.Windows.UIElement.Visibility%2A>. Это приводит к возникновению ошибки значение с именем `constraintSize` , передаваемое в <xref:System.Windows.FrameworkElement.MeasureCore%2A>.  
  
 Во-вторых, framework свойства, определенные на <xref:System.Windows.FrameworkElement> обрабатываются, что влияет на значение `constraintSize`. Как правило, эти свойства описывают размерные характеристики базового <xref:System.Windows.UIElement>, такие как его <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, и <xref:System.Windows.FrameworkElement.Style%2A>. Каждое из этих свойств может изменить пространство, необходимое для отображения элемента. <xref:System.Windows.FrameworkElement.MeasureOverride%2A>Затем вызывается с `constraintSize` как параметр.  
  
> [!NOTE]
>  Есть разница между свойства <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> и <xref:System.Windows.FrameworkElement.ActualWidth%2A>. Например <xref:System.Windows.FrameworkElement.ActualHeight%2A> свойство является вычисляемым значением на основе других входных значений высоты и системы макета. Значение задается самой системой макета в зависимости от фактического прохода отрисовки, а может поэтому немного отставать от установки значений свойств, таких как <xref:System.Windows.FrameworkElement.Height%2A>, которые являются основой для изменения ввода.  
>   
>  Поскольку <xref:System.Windows.FrameworkElement.ActualHeight%2A> является вычисляемым значением, следует иметь в виду, может существовать несколько или инкрементные делает его в результате выполнения различных операций системы макета. Система макета может вычислять требуемое место измерения для дочерних элементов, ограничения родительского элемента и т. д.  
  
 Является конечной целью проход измерения для дочернего элемента для определения его <xref:System.Windows.UIElement.DesiredSize%2A>, которое происходит во время <xref:System.Windows.FrameworkElement.MeasureCore%2A> вызова. <xref:System.Windows.UIElement.DesiredSize%2A> Значение сохраняется с <xref:System.Windows.UIElement.Measure%2A> для использования во время компоновки содержимого.  
  
 Порядок передачи начинается с вызова <xref:System.Windows.UIElement.Arrange%2A> метод. Во время компоновки родительского <xref:System.Windows.Controls.Panel> элемент формирует прямоугольник, представляющий границы потомка. Это значение передается <xref:System.Windows.FrameworkElement.ArrangeCore%2A> метод для обработки.  
  
 <xref:System.Windows.FrameworkElement.ArrangeCore%2A> Метод вычисляет <xref:System.Windows.UIElement.DesiredSize%2A> дочернего элемента и оценивает все дополнительные границы, которые могут повлиять на отображаемый размер элемента. <xref:System.Windows.FrameworkElement.ArrangeCore%2A>приводит к возникновению ошибки `arrangeSize`, который передается <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> метод <xref:System.Windows.Controls.Panel> как параметр. <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>приводит к возникновению ошибки `finalSize` дочернего элемента. Наконец <xref:System.Windows.FrameworkElement.ArrangeCore%2A> метод выполняет окончательную оценку свойств смещения, таких как границы и выравнивание и помещает дочерний объект в его расположении. Дочерний объект не должен обязательно заполнять все выделенное пространство (и в большинстве случаев не делает этого). Затем управление возвращается к родительскому <xref:System.Windows.Controls.Panel> и завершения процесса компоновки.  
  
<a name="LayoutSystem_PanelsCustom"></a>   
## <a name="panel-elements-and-custom-layout-behaviors"></a>Элементы панели и пользовательские расширения функциональности макета  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]включает группу элементов, которые являются производными от <xref:System.Windows.Controls.Panel>. Эти <xref:System.Windows.Controls.Panel> элементы включать множество сложных макетов. Например, наложение элементов можно легко получить с помощью <xref:System.Windows.Controls.StackPanel> элемент, пока более сложные и свободно потоковые макеты создаются при помощи <xref:System.Windows.Controls.Canvas>.  
  
 В следующей таблице перечислены доступные макета <xref:System.Windows.Controls.Panel> элементов.  
  
|Имя панели|Описание|  
|----------------|-----------------|  
|<xref:System.Windows.Controls.Canvas>|Определяет область, внутри которой можно явным образом разместить дочерние элементы при помощи относительных координат в <xref:System.Windows.Controls.Canvas> области.|  
|<xref:System.Windows.Controls.DockPanel>|Определяет область, в которой можно горизонтально либо вертикально упорядочивать дочерние элементы относительно друг друга.|  
|<xref:System.Windows.Controls.Grid>|Задание области с таблицей переменного размера, состоящей из столбцов и строк.|  
|<xref:System.Windows.Controls.StackPanel>|Выравнивает дочерние элементы в одну линию, ориентированную горизонтально или вертикально.|  
|<xref:System.Windows.Controls.VirtualizingPanel>|Предоставляет платформу для <xref:System.Windows.Controls.Panel> элементов, виртуализирующих свои дочерние коллекции данных. Этот класс является абстрактным.|  
|<xref:System.Windows.Controls.WrapPanel>|Размещает дочерние элементы последовательно слева направо, перенося содержимое на следующую строку на краю содержащего поля. Дальнейшее упорядочивание происходит последовательно сверху вниз или справа налево, в зависимости от значения <xref:System.Windows.Controls.WrapPanel.Orientation%2A> свойство.|  
  
 Для приложений, требующих макет, который не поддерживается с помощью готовых <xref:System.Windows.Controls.Panel> элементы, пользовательские расширения функциональности макета можно получить путем наследования из <xref:System.Windows.Controls.Panel> и переопределение <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы. Пример см. на странице [Пример Custom Radial Panel](http://go.microsoft.com/fwlink/?LinkID=159982).  
  
<a name="LayoutSystem_Performance"></a>   
## <a name="layout-performance-considerations"></a>Вопросы производительности макета  
 Макет является рекурсивным процессом. Каждый дочерний элемент в <xref:System.Windows.Controls.Panel.Children%2A> коллекции обрабатываются при каждом вызове системы макета. Это означает, что следует избегать запуска системы макета при отсутствии необходимости. Выполнение приведенных ниже рекомендаций поможет добиться более высокой производительности.  
  
-   Следует учитывать, что определенные изменения значений свойств могут привести к выполнению системой макета рекурсивного обновления.  
  
     Свойства зависимостей, значения которых могут привести к инициализации системы макета, помечаются общими флагами. <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>и <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> предоставляют полезные указания о том, какое свойство изменяется вызовут рекурсивное обновление системы макета. Как правило, должны иметь любое свойство, которое может повлиять на размер ограничивающего прямоугольника элемента <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A> для флага. Дополнительные сведения см. в [обзоре свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
-   По возможности используйте <xref:System.Windows.UIElement.RenderTransform%2A> вместо <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.  
  
     Объект <xref:System.Windows.FrameworkElement.LayoutTransform%2A> может быть очень удобный способ определения содержимого [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Тем не менее, если результат преобразования не влияет на положение других элементов, лучше всего использовать <xref:System.Windows.UIElement.RenderTransform%2A> вместо этого, так как <xref:System.Windows.UIElement.RenderTransform%2A> не вызывает систему макета. <xref:System.Windows.FrameworkElement.LayoutTransform%2A>применяет его преобразования и вызывает рекурсивное обновление макета для учета нового положения затронутого элемента.  
  
-   Число вызовов <xref:System.Windows.UIElement.UpdateLayout%2A>.  
  
     <xref:System.Windows.UIElement.UpdateLayout%2A> Метод вызывает рекурсивное обновление макета и часто не является обязательным. Если нет уверенности в необходимости обновления, следует предоставить вызов этого метода системе макета.  
  
-   При работе с большим <xref:System.Windows.Controls.Panel.Children%2A> коллекции, рассмотрите возможность использования <xref:System.Windows.Controls.VirtualizingStackPanel> вместо обычного <xref:System.Windows.Controls.StackPanel>.  
  
     При помощи виртуализации Дочерняя коллекция <xref:System.Windows.Controls.VirtualizingStackPanel> только сохраняет объекты в памяти, которые в данный момент в области просмотра родительского элемента. В результате этого производительность значительно увеличивается в большинстве сценариев.  
  
<a name="LayoutSystem_LayoutRounding"></a>   
## <a name="sub-pixel-rendering-and-layout-rounding"></a>Субпиксельная отрисовка и округление макета  
 Графическая система [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует аппаратно-независимые модули для обеспечения независимости от разрешения и устройства. Каждый аппаратно-независимый пиксель автоматически масштабируется согласно параметру [!INCLUDE[TLA#tla_dpi](../../../../includes/tlasharptla-dpi-md.md)] системы. Это обеспечивает приложениям [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] корректное масштабирование для различных параметров [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] и автоматически предоставляет приложениям поддержку [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)].  
  
 Однако такая независимость от [!INCLUDE[TLA2#tla_dpi](../../../../includes/tla2sharptla-dpi-md.md)] может привести к неравномерной отрисовке границ из-за сглаживания. Эти эффекты, обычно выглядящие как смазанные или полупрозрачные границы, могут появиться, когда положение границы попадает в середину пикселя устройства, а не между пикселями. В системе макета имеется способ настройки границ с помощью округления макета. Округление макета заключается в том, что система макета округляет все нецелочисленные значения пикселей во время прохода макета.  
  
 По умолчанию округление макета отключено. Чтобы включить округление макета, задайте <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> свойства `true` для какого-либо <xref:System.Windows.FrameworkElement>. Так как это свойство зависимости, значение будет распространено на все дочерние объекты в визуальном дереве. Чтобы макет округления для всего пользовательского интерфейса, установите <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A> для `true` на корневой контейнер. Пример см. в разделе <xref:System.Windows.FrameworkElement.UseLayoutRounding%2A>.  
  
<a name="LayoutSystem_whatsnext"></a>   
## <a name="whats-next"></a>Что дальше?  
 Понимание механизма измерения и упорядочивания элементов — это первый шаг к пониманию макета. Дополнительные сведения о доступных <xref:System.Windows.Controls.Panel> см [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md). Чтобы лучше понять различные свойства размещения, которые могут повлиять на макет, см. раздел [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md). Пример настраиваемого <xref:System.Windows.Controls.Panel> элемент, в разделе [пользовательский образец радиальной панели](http://go.microsoft.com/fwlink/?LinkID=159982). Когда будете готовы собрать все вместе в облегченное приложение, в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.UIElement>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Общие сведения о свойствах Alignment, Margin, Padding](../../../../docs/framework/wpf/advanced/alignment-margins-and-padding-overview.md)  
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
