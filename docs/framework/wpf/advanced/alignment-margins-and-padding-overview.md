---
title: Общие сведения о свойствах Alignment, Margin, Padding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- margins [WPF]
- padding [WPF]
- aligning [WPF]
ms.assetid: 9c6a2009-9b86-4e40-8605-0a2664dc3973
ms.openlocfilehash: bec2d9cd224febb650e2de67bb7406365d075963
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145479"
---
# <a name="alignment-margins-and-padding-overview"></a>Общие сведения о свойствах Alignment, Margin, Padding
Класс <xref:System.Windows.FrameworkElement> предоставляет несколько свойств, которые используются для точного расположения элементов ребенка. Эта тема обсуждает четыре из наиболее важных <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>свойств: , <xref:System.Windows.FrameworkElement.Margin%2A>, <xref:System.Windows.Controls.Border.Padding%2A>и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>. Очень важно иметь представление о результатах применения этих свойств, поскольку они обеспечивают основу для управления положением элементов в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="wcpsdk_layout_amp_introduction"></a>
## <a name="introduction-to-element-positioning"></a>Введение в позиционирование элементов  
 Существуют разные способы позиционирования элементов с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Тем не менее, достижение идеального макета выходит за рамки простого выбора правильного <xref:System.Windows.Controls.Panel> элемента. Тонкий контроль позиционирования требует <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> <xref:System.Windows.FrameworkElement.Margin%2A>понимания, <xref:System.Windows.Controls.Border.Padding%2A> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> и, и свойства.  
  
 На следующем рисунке показан сценарий макета, использующий несколько свойств размещения.  
  
 ![Пример использования свойств позиционирования WPF](./media/layout-margins-padding-alignment-graphic1.PNG "layout_margins_padding_alignment_graphic1")  
  
 На первый <xref:System.Windows.Controls.Button> взгляд, элементы на этой иллюстрации могут показаться случайным образом. На самом деле их положение точно контролируется с помощью сочетания полей, выравнивания и заполнения.  
  
 В следующем примере демонстрируется создание макета, показанного на предыдущем рисунке. Элемент <xref:System.Windows.Controls.Border> инкапсулирует родительский <xref:System.Windows.Controls.StackPanel>элемент со <xref:System.Windows.Controls.Border.Padding%2A> значением 15 независимых пикселей устройства. Это объясняет узкую <xref:System.Windows.Media.Brushes.LightBlue%2A> полосу, <xref:System.Windows.Controls.StackPanel>которая окружает ребенка. <xref:System.Windows.Controls.StackPanel> Элементы ребенка используются для иллюстрации каждого из различных свойств позиционирования, которые подробно описаны в этой теме. Для <xref:System.Windows.Controls.Button> демонстрации <xref:System.Windows.FrameworkElement.Margin%2A> свойств используются <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> три элемента.  
  
 [!code-csharp[MPALayoutSampleIntro#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutSampleIntro/CSharp/MPA_Layout_Sample_Intro.cs#1)]
 [!code-vb[MPALayoutSampleIntro#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutSampleIntro/VisualBasic/MPALayoutIntro.vb#1)]  
  
 Следующая схема обеспечивает подробное представление различных свойств размещения, примененных в предыдущем примере. В последующих разделах этой статьи более подробно описывается использование каждого свойства размещения.  
  
 ![Позиционирование Свойства с screen Call&#45;аутов](./media/layout-margins-padding-alignment-graphic2.PNG "layout_margins_padding_alignment_graphic2")  
  
<a name="wcpsdk_layout_amp_alignment_properties"></a>
## <a name="understanding-alignment-properties"></a>Общие сведения о свойствах Alignment  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Свойства <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> описывают, как элемент ребенка должен быть расположен в выделенном пространстве макета родительского элемента. При совместном использовании этих свойств можно точно расположить дочерние элементы. Например, элементы <xref:System.Windows.Controls.DockPanel> ребенка могут указывать <xref:System.Windows.HorizontalAlignment.Left>четыре <xref:System.Windows.HorizontalAlignment.Right>различных горизонтальных выравнивания: или, или <xref:System.Windows.HorizontalAlignment.Center> <xref:System.Windows.HorizontalAlignment.Stretch> для заполнения доступного пространства. Аналогичные значения доступны для вертикального размещения.  
  
> [!NOTE]
> Явно установленные <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.Width%2A> свойства элемента имеют приоритет над <xref:System.Windows.HorizontalAlignment.Stretch> значением свойства. Попытка <xref:System.Windows.FrameworkElement.Height%2A>установить, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> значение `Stretch` результатов `Stretch` в запросе игнорируется.  
  
<a name="wcpsdk_layout_amp_horizontalalignment_properties"></a>
### <a name="horizontalalignment-property"></a>Свойство HorizontalAlignment  
 Свойство <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> декларирует горизонтальные характеристики выравнивания для применения к элементам ребенка. В следующей таблице показаны все <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> возможные значения свойства.  
  
|Участник|Описание|  
|------------|-----------------|  
|<xref:System.Windows.HorizontalAlignment.Left>|Дочерние элементы выравниваются по левому краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Center>|Дочерние элементы выравниваются по центру выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Right>|Дочерние элементы выравниваются по правому краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.HorizontalAlignment.Stretch> (по умолчанию)|Дочерние элементы растягиваются для заполнения выделенного пространства макета родительского элемента. Явные <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения имеют приоритет.|  
  
 Ниже приводится следующий <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> пример, <xref:System.Windows.Controls.Button> как применить свойство к элементам. Показаны все значения атрибутов, чтобы проиллюстрировать различные режимы отрисовки.  
  
 [!code-csharp[MPALayoutHorizontalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/CSharp/MPA_Layout_HorizontalAlignment.cs#2)]
 [!code-vb[MPALayoutHorizontalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutHorizontalAlignment/VisualBasic/MPA_Layout_HorizontalAlignment.vb#2)]  
  
 Приведенный выше код создает макет, похожий на следующий рисунок. Эффекты позиционирования <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> каждого значения видны на иллюстрации.  
  
 ![Пример HorizontalAlignment](./media/layout-horizontal-alignment-graphic.PNG "layout_horizontal_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_verticalalignment_properties"></a>
### <a name="verticalalignment-property"></a>Свойство VerticalAlignment  
 Свойство <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> описывает вертикальные характеристики выравнивания для применения к элементам ребенка. В следующей таблице показаны все <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> возможные значения для свойства.  
  
|Участник|Описание|  
|------------|-----------------|  
|<xref:System.Windows.VerticalAlignment.Top>|Дочерние элементы выравниваются по верхнему краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Center>|Дочерние элементы выравниваются по центру выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Bottom>|Дочерние элементы выравниваются по нижнему краю выделенного пространства макета родительского элемента.|  
|<xref:System.Windows.VerticalAlignment.Stretch> (по умолчанию)|Дочерние элементы растягиваются для заполнения выделенного пространства макета родительского элемента. Явные <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значения имеют приоритет.|  
  
 Ниже приводится следующий <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> пример, <xref:System.Windows.Controls.Button> как применить свойство к элементам. Показаны все значения атрибутов, чтобы проиллюстрировать различные режимы отрисовки. Для целей этого образца <xref:System.Windows.Controls.Grid> элемент с видимыми сетками используется в качестве родительского элемента, чтобы лучше проиллюстрировать поведение макета каждого значения свойства.  
  
 [!code-csharp[MPALayoutVerticalAlignment#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MPALayoutVerticalAlignment/CSharp/MPA_Layout_VerticalAlignment.cs#2)]
 [!code-vb[MPALayoutVerticalAlignment#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MPALayoutVerticalAlignment/VisualBasic/MPA_Layout_VerticalAlignment.vb#2)]
 [!code-xaml[MPALayoutVerticalAlignment#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MPALayoutVerticalAlignment/XAML/default.xaml#2)]  
  
 Приведенный выше код создает макет, похожий на следующий рисунок. Эффекты позиционирования <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> каждого значения видны на иллюстрации.  
  
 ![Пример свойства VerticalAlignment](./media/layout-vertical-alignment-graphic.PNG "layout_vertical_alignment_graphic")  
  
<a name="wcpsdk_layout_amp_margin_properties"></a>
## <a name="understanding-margin-properties"></a>Основные сведения о свойствах Margin  
 Свойство <xref:System.Windows.FrameworkElement.Margin%2A> описывает расстояние между элементом и его ребенком или сверстниками. <xref:System.Windows.FrameworkElement.Margin%2A>значения могут быть однородными, `Margin="20"`с помощью синтаксиса, как . С помощью этого <xref:System.Windows.FrameworkElement.Margin%2A> синтаксиса к элементу будет применена форма из 20 независимых пикселей. <xref:System.Windows.FrameworkElement.Margin%2A>значения могут также принимать форму четырех различных значений, каждое значение, описывающее определенную маржу, чтобы `Margin="0,10,5,25"`применить к левой, верхней, правой и нижней (в этом порядке), как. Правильное использование <xref:System.Windows.FrameworkElement.Margin%2A> свойства обеспечивает очень тонкий контроль положения рендеринга элемента и положения рендеринга его соседских элементов и детей.  
  
> [!NOTE]
> Ненулевой запас применяет пространство за пределами элемента <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A>.  
  
 Ниже приводится следующий пример, как применять <xref:System.Windows.Controls.Button> единые поля вокруг группы элементов. Элементы <xref:System.Windows.Controls.Button> расположены равномерно с десятипиксельным запасом поля в каждом направлении.  
  
 [!code-cpp[MarginPaddingAlignmentSample#1](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#1)]
 [!code-csharp[MarginPaddingAlignmentSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#1)]
 [!code-vb[MarginPaddingAlignmentSample#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#1)]
 [!code-xaml[MarginPaddingAlignmentSample#1](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#1)]  
  
 Во многих случаях универсальные поля не подходят. В этих случаях можно применять неоднородные интервалы. В следующем примере показано применение неоднородных полей к дочерним элементам. Поля описываются в следующем порядке: слева, сверху, справа, снизу.  
  
 [!code-cpp[MarginPaddingAlignmentSample#2](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#2)]
 [!code-csharp[MarginPaddingAlignmentSample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#2)]
 [!code-vb[MarginPaddingAlignmentSample#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#2)]
 [!code-xaml[MarginPaddingAlignmentSample#2](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#2)]  
  
<a name="wcpsdk_layout_amp_padding_properties"></a>
## <a name="understanding-the-padding-property"></a>Основные сведения о свойстве Padding  
 Обивка <xref:System.Windows.FrameworkElement.Margin%2A> похожа на во многом. Свойство Padding подвергается только на нескольких классах, <xref:System.Windows.Documents.Block> <xref:System.Windows.Controls.Border>в <xref:System.Windows.Controls.Control>первую очередь для удобства: , , и <xref:System.Windows.Controls.TextBlock> образцы классов, которые подвергают Свойство Padding. Свойство <xref:System.Windows.Controls.Border.Padding%2A> увеличивает эффективный размер элемента ребенка <xref:System.Windows.Thickness> на указанное значение.  
  
 В следующем примере <xref:System.Windows.Controls.Border.Padding%2A> показано, <xref:System.Windows.Controls.Border> как применять родительский элемент.  
  
 [!code-cpp[MarginPaddingAlignmentSample#3](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#3)]
 [!code-csharp[MarginPaddingAlignmentSample#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#3)]
 [!code-vb[MarginPaddingAlignmentSample#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#3)]
 [!code-xaml[MarginPaddingAlignmentSample#3](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#3)]  
  
<a name="wcpsdk_layout_amp_summary"></a>
## <a name="using-alignment-margins-and-padding-in-an-application"></a>Использование свойств Alignment, Margin и Padding в приложении  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.Controls.Border.Padding%2A>, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> , и обеспечить контроль позиционирования, необходимых для создания комплекса. [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Эффекты каждого свойства позволяют изменить размещение дочерних элементов, обеспечивая гибкость создания динамических приложений и интерфейсов пользователя.  
  
 В следующем примере демонстрируются понятия, описанные в этом разделе. Опираясь на инфраструктуру, найденную в первом примере в этой теме, этот пример добавляет <xref:System.Windows.Controls.Grid> элемент в качестве ребенка <xref:System.Windows.Controls.Border> в первом примере. <xref:System.Windows.Controls.Border.Padding%2A>применяется к <xref:System.Windows.Controls.Border> родительскому элементу. Используется <xref:System.Windows.Controls.Grid> для раздела пространства между <xref:System.Windows.Controls.StackPanel> тремя элементами ребенка. <xref:System.Windows.Controls.Button>элементы снова используются, чтобы <xref:System.Windows.FrameworkElement.Margin%2A> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>показать различные эффекты и . <xref:System.Windows.Controls.TextBlock>элементы добавляются <xref:System.Windows.Controls.ColumnDefinition> к каждому, чтобы <xref:System.Windows.Controls.Button> лучше определить различные свойства, применяемые к элементам в каждой колонке.  
  
 [!code-cpp[MarginPaddingAlignmentSample#4](~/samples/snippets/cpp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CPP/Margin_Padding_Alignment_Sample.cpp#4)]
 [!code-csharp[MarginPaddingAlignmentSample#4](~/samples/snippets/csharp/VS_Snippets_Wpf/MarginPaddingAlignmentSample/CSharp/Margin_Padding_Alignment_Sample.cs#4)]
 [!code-vb[MarginPaddingAlignmentSample#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarginPaddingAlignmentSample/VisualBasic/MarginPaddingAlignment.vb#4)]
 [!code-xaml[MarginPaddingAlignmentSample#4](~/samples/snippets/xaml/VS_Snippets_Wpf/MarginPaddingAlignmentSample/XAML/default.xaml#4)]  
  
 При компиляции приведенное выше приложение создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который показан на рисунке ниже. Влияние различных значений свойств проявляется в интервале между элементами, а значительные значения свойств <xref:System.Windows.Controls.TextBlock> для элементов в каждом столбце отображаются внутри элементов.  
  
 ![Несколько свойств размещения в одном приложении](./media/layout-margins-padding-aligment-graphic3.PNG "layout_margins_padding_aligment_graphic3")  
  
<a name="wcpsdk_layout_amp_alignment_whatsnext"></a>
## <a name="whats-next"></a>Что дальше?  
 Свойства позиционирования, <xref:System.Windows.FrameworkElement> определяемые [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] классом, позволяют контролировать размещение элементов в приложениях. Вы получаете в свое распоряжение несколько способов, позволяющих более эффективно размещать элементы с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Доступны дополнительные ресурсы, в которых макет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рассматривается более подробно. Тема [Обзора групп](../controls/panels-overview.md) содержит более подробную информацию о различных элементах. <xref:System.Windows.Controls.Panel> Тема [Walkthrough: Мое первое настольное приложение WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md) представляет передовые методы, которые используют элементы макета для размещения компонентов и привязки их действий к источникам данных.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- <xref:System.Windows.FrameworkElement.Margin%2A>
- [Общие сведения о панелях](../controls/panels-overview.md)
- [Макет](layout.md)
- [Пример коллекции макетов WPF](https://go.microsoft.com/fwlink/?LinkID=160054)
