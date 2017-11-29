---
title: "Общие сведения о свойствах Alignment, Margin, Padding"
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
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c0a57018959aedc72e0fa02befa1733f66f265b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="alignment-margins-and-padding-overview"></a>Общие сведения о свойствах Alignment, Margin, Padding
<xref:System.Windows.FrameworkElement> Класс содержит несколько свойств, которые используются для точного размещения дочерних элементов. В этом разделе обсуждаются четыре наиболее важных свойства: <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. Очень важно иметь представление о результатах применения этих свойств, поскольку они обеспечивают основу для управления положением элементов в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
  
<a name="wcpsdk_layout_amp_introduction"></a>   
## <a name="introduction-to-element-positioning"></a>Введение в позиционирование элементов  
 Существуют разные способы позиционирования элементов с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Однако идеальный макет достигается не просто выбором право <xref:System.Windows.Controls.Panel> элемента. Точное управление размещением требует понимания <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства.  
  
 На следующем рисунке показан сценарий макета, использующий несколько свойств размещения.  
  
 ![Пример свойств размещения WPF](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 На первый взгляд <xref:System.Windows.Controls.Button> элементы на этом рисунке могут отображаться размещенными случайным образом. На самом деле их положение точно контролируется с помощью сочетания полей, выравнивания и заполнения.  
  
 В следующем примере демонстрируется создание макета, показанного на предыдущем рисунке. Объект <xref:System.Windows.Controls.Border> инкапсулирует родительский <xref:System.Windows.Controls.StackPanel>, с <xref:System.Windows.Controls.Border.Padding%2A> значение 15 аппаратно-независимых пикселях. Это учитывается для узкой <xref:System.Windows.Media.Brushes.LightBlue%2A> ленту, которая окружает дочерние <xref:System.Windows.Controls.StackPanel>. Дочерние элементы <xref:System.Windows.Controls.StackPanel> используются для иллюстрации каждого из различных свойств позиционирования, описанные в этом разделе. Три <xref:System.Windows.Controls.Button> элементы используются для демонстрации <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства.  
  
 [!code-csharp[MPALayoutSampleIntro#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Следующая схема обеспечивает подробное представление различных свойств размещения, примененных в предыдущем примере. В последующих разделах этой статьи более подробно описывается использование каждого свойства размещения.  
  
 ![Свойства размещения с выносками](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>   
## <a name="understanding-alignment-properties"></a>Общие сведения о свойствах Alignment  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> И <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства описывают, как дочерний элемент должен располагаться в родительском элементе выделенного пространства макета. При совместном использовании этих свойств можно точно расположить дочерние элементы. Например, дочерние элементы <xref:System.Windows.Controls.DockPanel> можно указать четыре разных горизонтальное выравнивание: <xref:System.Windows.HorizontalAlignment.Left>, <xref:System.Windows.HorizontalAlignment.Right>, или <xref:System.Windows.HorizontalAlignment.Center>, или <xref:System.Windows.HorizontalAlignment.Stretch> доступное пространство. Аналогичные значения доступны для вертикального размещения.  
  
> [!NOTE]
>  Явно набор <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства для элемента имеют приоритет над <xref:System.Windows.HorizontalAlignment.Stretch> значение свойства. Попытка задать <xref:System.Windows.FrameworkElement.Height%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение `Stretch` приводит к `Stretch` игнорированию запроса.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>   
### <a name="horizontalalignment-property"></a>Свойство HorizontalAlignment  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Свойство объявляет характеристик выравнивания по горизонтали для применения к дочерним элементам. В следующей таблице показаны каждого из возможных значений <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойство.  
  
|Член|Описание|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Дочерние элементы выравниваются по левому краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Дочерние элементы выравниваются по центру выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Дочерние элементы выравниваются по правому краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Stretch>(По умолчанию)|Дочерние элементы растягиваются для заполнения выделенного пространства макета родительского элемента. Явные <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения имеют более высокий приоритет.|  
  
 В следующем примере показано, как применить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.Controls.Button> элементов. Показаны все значения атрибутов, чтобы проиллюстрировать различные режимы отрисовки.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Приведенный выше код создает макет, похожий на следующий рисунок. Эффекты позиционирования каждого <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение видны на рисунке.  
  
 ![Пример HorizontalAlignment](../../../../docs/framework/wpf/advanced/media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>   
### <a name="verticalalignment-property"></a>Свойство VerticalAlignment  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Свойство описывает характеристики выравнивания по вертикали для применения к дочерним элементам. В следующей таблице приведены все возможные значения для <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства.  
  
|Член|Описание|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Дочерние элементы выравниваются по верхнему краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Center>|Дочерние элементы выравниваются по центру выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Дочерние элементы выравниваются по нижнему краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Stretch>(По умолчанию)|Дочерние элементы растягиваются для заполнения выделенного пространства макета родительского элемента. Явные <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения имеют более высокий приоритет.|  
  
 В следующем примере показано, как применить <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.Controls.Button> элементов. Показаны все значения атрибутов, чтобы проиллюстрировать различные режимы отрисовки. Для данного примера <xref:System.Windows.Controls.Grid> с видимым линиями сетки используется в качестве родительского элемента, чтобы лучше проиллюстрировать поведения каждого значения свойства.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Приведенный выше код создает макет, похожий на следующий рисунок. Эффекты позиционирования каждого <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> значение видны на рисунке.  
  
 ![Пример свойства VerticalAlignment](../../../../docs/framework/wpf/advanced/media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>   
## <a name="understanding-margin-properties"></a>Основные сведения о свойствах Margin  
 <xref:System.Windows.FrameworkElement.Margin%2A> Свойство описывает расстояние между элемента и его дочерние или одноранговых узлов. <xref:System.Windows.FrameworkElement.Margin%2A>значения могут быть универсальный, с помощью синтаксиса, подобного `Margin="20"`. Со следующим синтаксисом равномерного <xref:System.Windows.FrameworkElement.Margin%2A> 20 устройства независимых пикселях будут применяться к элементу. <xref:System.Windows.FrameworkElement.Margin%2A>значения могут также принимать форму четырьмя различными значениями, описывающими различные поля слева, сверху, справа и нижнее (в таком порядке), как `Margin="0,10,5,25"`. Правильное использование <xref:System.Windows.FrameworkElement.Margin%2A> свойство позволяет точно управлять отрисовкой положения элемента и положения его соседних и дочерних элементов.  
  
> [!NOTE]
>  Задает поля ненулевое значение в элементе <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 В следующем примере показано, как применить единые поля группы <xref:System.Windows.Controls.Button> элементов. <xref:System.Windows.Controls.Button> Равномерно элементы с буфером 10 точек в каждом направлении.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 Во многих случаях универсальные поля не подходят. В этих случаях можно применять неоднородные интервалы. В следующем примере показано применение неоднородных полей к дочерним элементам. Поля описываются в следующем порядке: слева, сверху, справа, снизу.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>   
## <a name="understanding-the-padding-property"></a>Основные сведения о свойстве Padding  
 Заполнение аналогичен <xref:System.Windows.FrameworkElement.Margin%2A> во многом. Свойства Padding предоставляется только в нескольких классах, главным образом для удобства: <xref:System.Windows.Documents.Block>, <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Control>, и <xref:System.Windows.Controls.TextBlock> являются примерами классов, которые предоставляют свойство Padding. <xref:System.Windows.Controls.Border.Padding%2A> Свойство увеличивает эффективный размер дочернего элемента с помощью указанного <xref:System.Windows.Thickness> значение.  
  
 В следующем примере показано, как применить <xref:System.Windows.Controls.Border.Padding%2A> к родительскому элементу <xref:System.Windows.Controls.Border> элемента.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>   
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Использование свойств Alignment, Margin и Padding в приложении  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>, и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> предоставляют управление позиционированием, необходимое для создания сложного [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Эффекты каждого свойства позволяют изменить размещение дочерних элементов, обеспечивая гибкость создания динамических приложений и интерфейсов пользователя.  
  
 В следующем примере демонстрируются понятия, описанные в этом разделе. Основываясь на инфраструктуре в первом примере в этом разделе, в этом примере добавляется <xref:System.Windows.Controls.Grid> элемента в качестве дочернего элемента <xref:System.Windows.Controls.Border> в первом примере. <xref:System.Windows.Controls.Border.Padding%2A>применяется к родительскому <xref:System.Windows.Controls.Border> элемента. <xref:System.Windows.Controls.Grid> Используется для разделения пространства между тремя дочерними <xref:System.Windows.Controls.StackPanel> элементов. <xref:System.Windows.Controls.Button>элементы снова используются для отображения различных результатов из <xref:System.Windows.FrameworkElement.Margin%2A> и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>. <xref:System.Windows.Controls.TextBlock>элементы добавляются к каждому <xref:System.Windows.Controls.ColumnDefinition> чтобы лучше определить различные свойства, применяемые к <xref:System.Windows.Controls.Button> элементов в каждом столбце.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](../../../../samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 При компиляции приведенное выше приложение создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который показан на рисунке ниже. Влияние различных значений свойств выражены в пространстве между элементами, а значительные значения свойств элементов в каждом столбце отображаются внутри <xref:System.Windows.Controls.TextBlock> элементов.  
  
 ![Несколько свойств размещения в одном приложении](../../../../docs/framework/wpf/advanced/media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>   
## <a name="whats-next"></a>Что дальше?  
 Свойства позиционирования, определенные <xref:System.Windows.FrameworkElement> класса обеспечивают точное управление размещением элементов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений. Вы получаете в свое распоряжение несколько способов, позволяющих более эффективно размещать элементы с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Доступны дополнительные ресурсы, в которых макет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рассматривается более подробно. [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md) раздел содержит дополнительные сведения о различных <xref:System.Windows.Controls.Panel> элементов. Раздел [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md) предоставляет дополнительные методы, использующие элементы макета для позиционирования компонентов и привязки их действий к источникам данных.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.Margin%2A>  
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Макет](../../../../docs/framework/wpf/advanced/layout.md)  
 [Пример коллекции макетов WPF](http://go.microsoft.com/fwlink/?LinkID=160054)
