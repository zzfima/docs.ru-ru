---
title: "Общие сведения о свойствах Alignment, Margin, Padding | Microsoft Docs"
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
  - "выравнивание"
  - "классы, FrameworkElement"
  - "FrameworkElement - класс"
  - "поля"
  - "заполнение"
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Общие сведения о свойствах Alignment, Margin, Padding
Класс <xref:System.Windows.FrameworkElement> предоставляет ряд свойств, используемых для точного размещения дочерних элементов.  В этом разделе рассмотрены четыре наиболее важных свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  Эффекты этих свойств важно понимать, поскольку они обеспечивают основу для контроля положения элементов в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## Введение в позиционирование элемента  
 Существуют разные способы позиционирования элементов с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Однако идеальный макет достигается не просто выбором правильного элемента класса <xref:System.Windows.Controls.Panel>.  Точное управление размещением требует понимания свойств <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  
  
 На следующем изображении показан скрипт макета, использующий несколько свойств позиционирования.  
  
 ![Пример использования свойств позиционирования WPF](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.png "layout\_margins\_padding\_alignment\_graphic1")  
  
 На первый взгляд, элементы <xref:System.Windows.Controls.Button> на этом изображении кажутся размещенными случайным образом.  Однако на самом деле их положения задаются с помощью комбинации выравниваний, внутренних и внешних границ.  
  
 В следующем примере описывается создание макета, показанного на предыдущем рисунке.  Элемент <xref:System.Windows.Controls.Border> инкапсулирует родительский <xref:System.Windows.Controls.StackPanel> со значением <xref:System.Windows.Controls.Border.Padding%2A> в 15 [аппаратно\-независимых пикселей](GTMT).  Это учитывается для узкой полосы цвета <xref:System.Windows.Media.Brushes.LightBlue%2A>, окружающей дочерний <xref:System.Windows.Controls.StackPanel>.  Дочерние элементы <xref:System.Windows.Controls.StackPanel> используются для демонстрации каждого из свойств позиционирования, рассматриваемых в данном разделе.  Три элемента <xref:System.Windows.Controls.Button> используются для демонстрации свойств <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 На следующей диаграмме приведено представление различных свойств позиционирования, которые использованы в предыдущем примере.  В последующих подразделах этого раздела подробно описывается использование каждого свойства позиционирования.  
  
 ![Свойства размещения с экранными вызовами](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.png "layout\_margins\_padding\_alignment\_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## Общее представление о свойствах Alignment  
 Свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> описывают, как дочерний элемент должен располагаться в выделенном родительскому элементу пространстве макета.  Используя эти свойства вместе, можно точно расположить дочерние элементы.  Например, дочерние элементы <xref:System.Windows.Controls.DockPanel> можно задать четырьмя различными горизонтальными выравниваниями: <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.HorizontalAlignment> или <xref:System.Windows.HorizontalAlignment>, или <xref:System.Windows.HorizontalAlignment> для заполнения доступного места.  Аналогичные значения доступны для вертикального выравнивания.  
  
> [!NOTE]
>  Явно заданные свойства <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> элемента имеют приоритет над значением свойства <xref:System.Windows.HorizontalAlignment>.  Попытка задать <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A> и значение <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> `Stretch` приводит к игнорированию запроса `Stretch`.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### Свойство HorizontalAlignment  
 Свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> описывает характеристики горизонтального выравнивания, которые нужно применить к дочерним элементам.  В следующей таблице приведены все возможные значения свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  
  
|Элемент|Описание|  
|-------------|--------------|  
|<xref:System.Windows.HorizontalAlignment>|Дочерние элементы выравниваются по левому краю выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.HorizontalAlignment>|Дочерние элементы выравниваются по центру выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.HorizontalAlignment>|Дочерние элементы выравниваются по правому краю выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.HorizontalAlignment> \(по умолчанию\)|Дочерние элементы растягиваются для заполнения выделенного родительскому элементу пространства макета.  Явные значения <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> имеют приоритет.|  
  
 В следующем примере показано, как применять свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> к элементам <xref:System.Windows.Controls.Button>.  Каждое значение атрибута отображается для наглядного представления различного поведения при отрисовке.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Приведенный выше код создает макет, похожий на приведенный выше рисунок.  На рисунке видны эффекты позиционирования каждого значения <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  
  
 ![Пример HorizontalAlignment](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.png "layout\_horizontal\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### Свойство VerticalAlignment  
 Свойство <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> описывает характеристики вертикального выравнивания, которые нужно применить к дочерним элементам.  В следующей таблице приведены все возможные значения свойства <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  
  
|Элемент|Описание|  
|-------------|--------------|  
|<xref:System.Windows.VerticalAlignment>|Дочерние элементы выравниваются по верхнему краю выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.VerticalAlignment>|Дочерние элементы выравниваются по центру выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.VerticalAlignment>|Дочерние элементы выравниваются по нижнему краю выделенного родительскому элементу пространства макета.|  
|<xref:System.Windows.VerticalAlignment> \(по умолчанию\)|Дочерние элементы растягиваются для заполнения выделенного родительскому элементу пространства макета.  Явные значения <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> имеют приоритет.|  
  
 В следующем примере показано, как применять свойство <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> к элементам <xref:System.Windows.Controls.Button>.  Каждое значение атрибута отображается для наглядного представления различного поведения при отрисовке.  В этом примере элемент <xref:System.Windows.Controls.Grid> с видимым линиями сетки используется в качестве родительского для лучшей иллюстрации поведения каждого значения свойства.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Приведенный выше код создает макет, похожий на приведенный выше рисунок.  На рисунке видны эффекты позиционирования каждого значения <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>.  
  
 ![Пример свойства VerticalAlignment](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.png "layout\_vertical\_alignment\_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## Общее представление о свойствах Margin  
 Свойство <xref:System.Windows.FrameworkElement.Margin%2A> описывает расстояние между элементом и его дочерним элементом или узлами.  Значения свойства <xref:System.Windows.FrameworkElement.Margin%2A> могут быть унифицированы путем использования такого синтаксиса, как `Margin="20"`.  При помощи этого синтаксиса к элементу будет применено универсальное свойство <xref:System.Windows.FrameworkElement.Margin%2A> 20 [аппаратно\-независимых пикселей](GTMT).  Значения свойства <xref:System.Windows.FrameworkElement.Margin%2A> могут также быть четырьмя различными значениями, описывающими различные поля: левое, верхнее, правое и нижнее \(в таком порядке\), например `Margin="0,10,5,25"`.  Соответствующее использование свойства <xref:System.Windows.FrameworkElement.Margin%2A> позволяет точно управлять отрисовкой положения элемента подготовки и положения его соседних и дочерних элементов.  
  
> [!NOTE]
>  Ненулевое значение задает поля вне <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> элемента.  
  
 В следующем примере показано, как применить единые поля к группе элементов <xref:System.Windows.Controls.Button>.  Элементы <xref:System.Windows.Controls.Button> расположены равномерно на расстоянии в 10 пикселей в каждом направлении.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 Во многих случаях универсальные поля не подходят.  В этих случаях могут быть применены неоднородные интервалы.  В следующем примере показано, как применять неоднородные поля к дочерним элементам.  Поля описываются в следующем порядке: \(левое, верхнее, правое и нижнее\).  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## Общее представление о свойстве Padding  
 Внутренние поля \(Padding\) во многом похожи на <xref:System.Windows.FrameworkElement.Margin%2A>.  Свойство Padding предоставляется только в нескольких классах, главным образом для удобства: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control> и <xref:System.Windows.Controls.TextBlock> являются примерами классов, которые предоставляют свойство Padding.  Свойство <xref:System.Windows.Controls.Border.Padding%2A> увеличивает эффективный размер дочернего элемента на заданное значение <xref:System.Windows.Thickness>.  
  
 В следующем примере показано применение свойства <xref:System.Windows.Controls.Border.Padding%2A> к родительскому элементу элемента <xref:System.Windows.Controls.Border>.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## Использование свойств Alignment, Margin и Padding в приложении  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> предоставляют управление позиционированием, необходимое для создания сложного [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  Можно использовать эффекты каждого свойства для изменения позиционирования потомков элементов, обеспечивая гибкость создания динамических приложений и возможностей пользователя.  
  
 В следующем примере показано каждое понятие, подробно описанное в данном разделе.  Основываясь на инфраструктуре первого примера данного раздела, этот пример добавляет элемент <xref:System.Windows.Controls.Grid> в качестве дочернего элемента <xref:System.Windows.Controls.Border> из первого примера.  Свойство <xref:System.Windows.Controls.Border.Padding%2A> применяется к родительскому элементу <xref:System.Windows.Controls.Border>.  Элемент <xref:System.Windows.Controls.Grid> используется для разделения пространства между тремя дочерними элементами <xref:System.Windows.Controls.StackPanel>.  Элементы <xref:System.Windows.Controls.Button> повторно используются для отображения различных результатов свойств <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>.  Элементы <xref:System.Windows.Controls.TextBlock> добавляются каждому классу <xref:System.Windows.Controls.ColumnDefinition> для лучшего определения различных свойств, применяемых к элементам <xref:System.Windows.Controls.Button> в каждом столбце.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 При компиляции приведенное выше приложение создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который выглядит как на следующем рисунке.  Эффекты различных значений свойств выражены в пространстве между элементами, а значительные значения свойств элементов в каждом столбце отображаются внутри элементов <xref:System.Windows.Controls.TextBlock>.  
  
 ![Несколько свойств размещения в одном приложении](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.png "layout\_margins\_padding\_aligment\_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## Что дальше?  
 Свойства позиционирования, определенные классом <xref:System.Windows.FrameworkElement>, обеспечивают точное управление размещением элементов в приложениях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Можно использовать несколько методов для лучшего расположения элементов с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Доступны дополнительные ресурсы, в которых подробно объясняется макет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Раздел [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md) содержит более подробные сведения о различных элементах <xref:System.Windows.Controls.Panel>.  В разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) рассмотрены дополнительные методы, использующие элементы макета для позиционирования компонентов и привязки их действий к источникам данных.  
  
## См. также  
 <xref:System.Windows.FrameworkElement>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.Margin%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)   
 [WPF Layout Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160054)