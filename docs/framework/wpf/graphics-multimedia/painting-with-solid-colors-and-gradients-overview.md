---
title: "Общие сведения о закраске сплошным цветом и градиентом | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "кисти, закрашивание с градиентом"
  - "кисти, закраска сплошным цветом"
  - "градиенты, рисование с помощью"
  - "закрашивание с градиентом"
  - "закраска сплошным цветом"
  - "сплошной цвет, рисование с помощью"
ms.assetid: f5b182f3-c5c7-4cbe-9f2f-65e690d08255
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Общие сведения о закраске сплошным цветом и градиентом
В этом разделе описано использование объектов <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.LinearGradientBrush> и <xref:System.Windows.Media.RadialGradientBrush> для закраски сплошным цветом, линейным градиентом и радиальным градиентом.  
  
   
  
<a name="solidcolor"></a>   
## Закраска области сплошным цветом  
 Одной из наиболее общих операций в любой платформе является закраска области сплошным <xref:System.Windows.Media.Color>.  Для выполнения этой задачи [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет класс <xref:System.Windows.Media.SolidColorBrush>.  В следующих разделах описаны различные способы закраски с помощью <xref:System.Windows.Media.SolidColorBrush>.  
  
<a name="solidcolorinxaml"></a>   
### Использование SolidColorBrush в "XAML"  
 Для закраски области сплошным цветом в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] воспользуйтесь одним из следующих параметров.  
  
-   Выберите стандартную сплошную цветную кисть по имени.  Например, можно установить для <xref:System.Windows.Controls.Control.Background%2A> кнопки значение "Red" или "MediumBlue".  Список других стандартных сплошных цветных кистей содержатся в разделе статических свойств класса <xref:System.Windows.Media.Brushes>.  Пример.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushNamedColor1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushnamedcolor1xaml)]  
  
-   Выберите цвет из 32\-разрядной цветовой палитры, указав количество красного, зеленого и синего компонентов для объединения в один сплошной цвет.  Формат для указания цвета из 32\-разрядной палитры имеет вид "*\#RRGGBB*", где *RR* — две цифры шестнадцатеричного числа, задающего относительный объем красного цвета, *GG* задает объем зеленого, а *BB* задает объем синего цвета.  Кроме того, цвет может быть указан в виде "\#*AARRGGBB*",где *AA* указывает значение *альфа*, или прозрачность, цвета.  Этот подход позволяет создавать частично прозрачные цвета.  В следующем примере для <xref:System.Windows.Controls.Control.Background%2A> элемента управления<xref:System.Windows.Controls.Button> устанавливается значение полностью непрозрачного красного цвета с помощью шестнадцатеричного формата.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushHex1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushhex1xaml)]  
  
-   Используйте синтаксис тега свойства для описания <xref:System.Windows.Media.SolidColorBrush>.  Этот синтаксис является более подробным, но он позволяет указать дополнительные параметры, такие как непрозрачность кисти.  В следующем примере для свойств <xref:System.Windows.Controls.Control.Background%2A> двух элементов <xref:System.Windows.Controls.Button> устанавливается значение полностью непрозрачного красного.  Цвет первой кисти описан с использованием имени стандартного цвета.  Цвет второй кисти описаны с помощью шестнадцатеричного формата.  
  
     [!code-xml[BrushOverviewExamples_snip#SolidColorBrushPropertyTag1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/SolidColorBrushExample.xaml#solidcolorbrushpropertytag1xaml)]  
  
<a name="solidcolorsincode"></a>   
### Закраска с помощью SolidColorBrush в коде  
 Для закраски области сплошным цветом в коде воспользуйтесь одним из следующих параметров.  
  
-   Воспользуйтесь одной из стандартных кистей, предоставленных классом <xref:System.Windows.Media.Brushes>.  В следующем примере свойство <xref:System.Windows.Controls.Control.Background%2A> элемента управления <xref:System.Windows.Controls.Button> установлено в значение <xref:System.Windows.Media.Brushes.Red%2A>.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedBrush1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedbrush1csharp)]  
  
-   Создайте <xref:System.Windows.Media.SolidColorBrush> и задайте его свойство <xref:System.Windows.Media.SolidColorBrush.Color%2A> с помощью структуры <xref:System.Windows.Media.Color>.  Можно использовать стандартный цвет из класса <xref:System.Windows.Media.Colors> или можно создать <xref:System.Windows.Media.Color> с помощью статического метода <xref:System.Windows.Media.Color.FromArgb%2A>.  
  
     В следующем примере показано, как установить свойство <xref:System.Windows.Media.SolidColorBrush.Color%2A> класса <xref:System.Windows.Media.SolidColorBrush> с использованием стандартного цвета.  
  
     [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushPredefinedColor1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushpredefinedcolor1csharp)]  
  
 Статический <xref:System.Windows.Media.Color.FromArgb%2A> позволяет указать значения [альфа](GTMT), красной, зеленой и синей составляющих цвета.  Обычно диапазон для каждого из этих значений составляет от 0 до 255.  Например, значение [альфа](GTMT), равное 0, указывает, что цвет является полностью прозрачным, в то время как значение 255 указывает на полностью непрозрачный цвет.  Аналогично, значение красного, равное 0, указывает, что цвет не имеет красной составляющей, в то время как значение 255 указывает на то, что цвет имеет максимальный объем красной составляющей.  В следующем примере цвет кисти цвета описан путем указания значений альфа, красной, зеленой и синей составляющих.  
  
 [!code-csharp[BrushOverviewExamples_snip#SolidColorBrushfromArgbExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushfromargbexample1csharp)]  
  
 Дополнительные способы задания цвета содержатся в разделе с описанием <xref:System.Windows.Media.Color>.  
  
<a name="gradient"></a>   
## Закраска области градиентом  
 Кисть градиента закрашивает область несколькими цветами, сливающимися друг с другом вдоль оси.  Можно использовать их для создания впечатления света и тени, что представляет элемент управления в трехмерном виде.  Их также можно использовать для имитации стекла, хрома, воды и других гладких поверхностей.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет два типа градиентных кистей: <xref:System.Windows.Media.LinearGradientBrush> и <xref:System.Windows.Media.RadialGradientBrush>.  
  
<a name="lineargradientbrush"></a>   
## Линейный градиент  
 <xref:System.Windows.Media.LinearGradientBrush> закрашивает область градиентом, определенным вдоль линии, *оси градиента*.  Необходимо указать цвета градиента и их расположение вдоль оси градиента с помощью объектов <xref:System.Windows.Media.GradientStop>.  Можно также изменить ось градиента, которая позволяет создавать горизонтальный и вертикальные градиенты и обращать направление градиента.  Ось градиента описан в следующем разделе.  По умолчанию создается диагональный градиент.  
  
 В следующем примере показан код, создающий линейный градиент четырьмя цветами.  
  
 [!code-xml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 В результате получается следующий градиент.  
  
 ![Диагональный линейный градиент](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diaglgradient-nolabel.png "wcpsdk\_graphicsmm\_diaglgradient\_nolabel")  
  
 **Примечание:**В примерах градиента в этом разделе используется система координат по умолчанию для установки начальной и конечной точки.  Система координат по умолчанию связана с ограничивающим прямоугольником: 0 указывает 0 процентов ограничивающего прямоугольника и 1 — 100 процентов.  Можно изменить эту систему координат, задав свойству <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode>.  Абсолютная система координат определяется не относительно ограничивающего прямоугольника.  Значения интерпретируются непосредственно в локальной области.  
  
 <xref:System.Windows.Media.GradientStop> представляет основные блоки построения кисти градиента.  Позиция градиента указывает <xref:System.Windows.Media.GradientStop.Color%2A> на <xref:System.Windows.Media.GradientStop.Offset%2A> вдоль оси градиента.  
  
-   Свойство <xref:System.Windows.Media.GradientStop.Color%2A> позиции градиент определяет цвет позиции градиента.  Можно установить цвет с помощью стандартного цвета \(предоставленного классом <xref:System.Windows.Media.Colors>\) или путем указания значений ScRGB или ARGB.  В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно также использовать шестнадцатиричный формат для описания цвета.  Дополнительные сведения см. в разделе <xref:System.Windows.Media.Color>.  
  
-   Свойство <xref:System.Windows.Media.GradientStop.Offset%2A> позиции градиента указывает положение цвета позиции градиента на оси градиента.  Смещение представлено типом <xref:System.Double> в диапазоне от 0 до 1.  Чем ближе значение смещения ограничения градиента к 0, тем ближе цвет к началу градиента.  Чем ближе значение смещения градиента к 1, тем ближе цвет к концу градиента.  
  
 Цвет каждой точки между позициями градиента является линейно интерполируемой, как сочетание цвета, указанное двумя ограниченными позициями градиента.  На следующем рисунке выделяются позиции градиент из предыдущего примера.  Круги помечают расположение позиции градиента, а пунктирная линия показывает ось градиента.  
  
 ![Ограничения градиента в линейном градиенте](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops.png "wcpsdk\_graphicsmm\_4gradientstops")  
  
 Первая позиция градиента определяет желтый цвет на некотором смещении от `0.0`.  Вторая позиция градиента определяет красный цвет на некотором смещении от `0.25`.  Точки между этими двумя позициями постепенно изменяются с желтого на красный при перемещении слева направо вдоль оси градиента.  Третья позиция градиента определяет синий цвет на некотором смещении от `0.75`.  Точки между второй и третьей позициями градиента постепенно изменяются от красного к голубому.  Четвертая позиция градиента определяет цвет зеленого лайма на некотором смещении от `1.0`.  Точки между третьей и четвертой позициями градиента постепенно изменяются от синего к цвету зеленого лайма.  
  
<a name="gradientaxis"></a>   
### Ось градиента  
 Как было упомянуто выше, позиции градиента кисти линейного градиента расположены вдоль линии, оси градиента.  Можно изменить ориентацию и размер строки с помощью свойств <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> кисти.  Управляя свойствами <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> кисти, можно создавать горизонтальные и вертикальные градиенты, разворачивать направление градиента, сжимать градиент и многое другое.  
  
 По умолчанию свойства <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> кисти линейного градиента кисти относятся к области закраски.  Точка \(0,0\) представляет верхний левый угол закрашиваемой области, а \(1,1\) — правый нижний угол закрашиваемой области.  <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> элемента <xref:System.Windows.Media.LinearGradientBrush> по умолчанию равна \(0,0\), а его <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> по умолчанию равна \(1,1\), что создает градиент по диагонали, начиная из верхнего левого угла и распространяясь в правый нижний угол области закрашивания.  На следующем рисунке показана ось градиента кисти линейного градиента со свойствами <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> по умолчанию.  
  
 ![Ось градиента для диагонального линейного градиента](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-diagonalgradientaxis.png "wcpsdk\_graphicsmm\_diagonalgradientaxis")  
  
 В следующем примере показано, как создать горизонтальный градиент, указав свойства <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A> кисти.  Обратите внимание, что позиции градиента такте же, как и в предыдущих примерах; просто изменяя <xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A> и <xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>, градиент был изменен с диагонального на горизонтальный.  
  
 [!code-xml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 На следующем рисунке показан созданный градиент.  Ось градиента помечается пунктирной линией, а позиции градиента отмечаются кругами.  
  
 ![Ось градиента для горизонтального линейного градиента](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-horizontalgradient.png "wcpsdk\_graphicsmm\_horizontalgradient")  
  
 В следующем примере показано создание вертикального градиента.  
  
 [!code-xml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 На следующем рисунке показан созданный градиент.  Ось градиента помечается пунктирной линией, а позиции градиента отмечаются кругами.  
  
 ![Ось градиента для вертикального градиента](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-verticalgradient.png "wcpsdk\_graphicsmm\_verticalgradient")  
  
<a name="radialgradients"></a>   
## Радиальные градиенты  
 Как и <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush> закрашивает область цветами, которые переходят друг в друга вдоль оси.  В предыдущих примерах показано, что ось кисти линейного градиента является прямой линией.  Ось кисти радиального градиента определяется кругом; цвета расходятся по кругу от начала координат.  
  
 В следующем примере кисть радиального градиента используется для закрашивания внутренней части прямоугольника.  
  
 [!code-xml[GradientBrushExamples_snip#RadialGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/RadialGradientBrushExample.xaml#radialgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#RadialGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/RadialGradientBrushExample.cs#radialgradient1csharp)]  
  
 Ниже показан градиент, созданный в предыдущем примере.  Позиции градиента кисти подсвечены.  Обратите внимание, что, несмотря на то, что результаты различаются, позиции градиента в этом примере идентичны позициям градиента в предыдущих примерах кисти линейного градиента.  
  
 ![Остановки градиента в радиусном градиенте](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk\_graphicsmm\_4gradientstops\_rg")  
  
 <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A> задает начальную точку оси градиента кисти линейного градиента.  Ось градиента расходится по кругу от начала градиента к кругу градиента.  Круг градиента кисти определяется свойствами <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> и <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A>.  
  
 На следующем рисунке показано несколько радиальных градиентов с разными параметрами <xref:System.Windows.Media.RadialGradientBrush.GradientOrigin%2A>, <xref:System.Windows.Media.RadialGradientBrush.Center%2A>, <xref:System.Windows.Media.RadialGradientBrush.RadiusX%2A> и <xref:System.Windows.Media.RadialGradientBrush.RadiusY%2A>.  
  
 ![Параметры RadialGradientBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-originscirclesandradii.png "wcpsdk\_graphicsmm\_originscirclesandradii")  
RadialGradientBrushes с различными параметрами GradientOrigin, Center, RadiusX и RadiusY.  
  
<a name="specifyinggradientcolors"></a>   
## Задание прозрачных или частично прозрачных позиций градиента  
 Поскольку позиции градиента не предоставляют свойство непрозрачности, необходимо указать альфа\-канал цветов с помощью шестнадцатеричного формата [!INCLUDE[TLA#tla_argb](../../../../includes/tlasharptla-argb-md.md)] в разметке или использовать метод <xref:System.Windows.Media.Color.FromScRgb%2A?displayProperty=fullName> для создания позиций градиента, которые являются частично прозрачными или прозрачными.  В следующих разделах даны более подробные инструкции по созданию частично прозрачных позиций градиента в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и коде.  Сведения о настройке прозрачности кисти содержатся в разделе [Задание прозрачности кисти](#brushesAndOpacity).  
  
<a name="argbsyntax"></a>   
### Указание непрозрачности цвета в "XAML"  
 В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] используется шестнадцатеричный формат [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] для указания прозрачности отдельных цветов.  Шестнадцатеричный формат [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] использует следующий синтаксис.  
  
 `#`**aa** *rrggbb*  
  
 *aa* в предыдущей строке представляет двузначное шестнадцатеричное значение, используемое для указания непрозрачности цвета.  *rr*, *gg*, и *bb* представляют собой двузначные шестнадцатеричные значения, используемые для указания красной, зеленой и синей компоненты цвета.  Каждая шестнадцатеричная цифра может иметь значение от 0 до 9 либо от A до F.  0 соответствует наименьшему значению, а F — наибольшему.  Альфа\-значение 00 указывает на то, что цвет является полностью прозрачным, в то время как альфа\-значение FF создает цвет, который является полностью непрозрачным.  В следующем примере шестнадцатеричная форма записи [!INCLUDE[TLA2#tla_argb](../../../../includes/tla2sharptla-argb-md.md)] используется для задания двух цветов.  Первый — частично прозрачный \(он имеет альфа\-значение x20\), в то время как второй — полностью непрозрачный.  
  
 [!code-xml[GradientBrushExamples_snip#TransparentGradientStopExample1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/GradientStopsExample.xaml#transparentgradientstopexample1xaml)]  
  
<a name="fromscrgbsyntax"></a>   
### Задание непрозрачности цвета в коде  
 При использовании кода статический метод <xref:System.Windows.Media.Color.FromArgb%2A> позволяет задать значение альфа при создании цвета.  Метод принимает четыре параметра типа <xref:System.Byte>.  Первый параметр задает альфа\-канал цвета; другие три параметра определяют значения красной, зеленой и синей компоненты цвета.  Каждое значение должно быть в диапазоне от 0 до 255, включительно.  Альфа\-значение, равное 0, указывает на то, что цвет является полностью прозрачным, в то время как альфа\-значение FF создает цвет, который является полностью непрозрачным.  В следующем примере метод <xref:System.Windows.Media.Color.FromArgb%2A> используется для создания двух цветов.  Первый цвет является частично прозрачным \(он имеет значение альфа\-32\), в то время как второй — полностью непрозрачный.  
  
 [!code-csharp[GradientBrushExamples_snip#TransparentGradientStopExample1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/GradientStopsExample.cs#transparentgradientstopexample1csharp)]  
  
 Кроме того, можно использовать метод <xref:System.Windows.Media.Color.FromScRgb%2A>, который позволяет использовать значения ScRGB для создания цвета.  
  
<a name="otherbrushes"></a>   
## Закраска с использованием изображений, рисунков, визуализаций и шаблонов  
 Классы <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush> позволяют закрашивать область, используя изображения, рисунки или визуализации.  Сведения о закрашивании с использованием изображений, рисунков и шаблонов содержатся в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## См. также  
 <xref:System.Windows.Media.Brush>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.LinearGradientBrush>   
 <xref:System.Windows.Media.RadialGradientBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Общие сведения о преобразованиях объекта Brush](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [Уровни графической отрисовки](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)