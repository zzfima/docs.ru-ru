---
title: "Оптимизация производительности. Дополнительные рекомендации | Microsoft Docs"
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
  - "кисти, производительность"
  - "проверка нажатия объектов [WPF]"
  - "непрозрачность"
  - "ScrollBarVisibility - перечисление"
  - "отрисовка служб терминалов"
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Оптимизация производительности. Дополнительные рекомендации
<a name="introduction"></a> В этом разделе содержатся рекомендации по улучшению производительности в дополнение к описанным в подразделе раздела [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md).  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Сравнение прозрачности кисти с прозрачностью элементов](#Opacity)  
  
-   [Переход к объекту](#Navigation_Objects)  
  
-   [Проверка попадания курсора мыши на больших трехмерных поверхностях](#Hit_Testing)  
  
-   [Событие CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
-   [Избегайте использования ScrollBarVisibility\=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Настройка службы кэширования шрифтов для сокращения времени загрузки](#FontCache)  
  
<a name="Opacity"></a>   
## Сравнение прозрачности кисти с прозрачностью элементов  
 При использовании <xref:System.Windows.Media.Brush> для установки свойства <xref:System.Windows.Shapes.Shape.Fill%2A> или <xref:System.Windows.Shapes.Shape.Stroke%2A> элемента лучше установить значение <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=fullName> вместо свойства элемента <xref:System.Windows.UIElement.Opacity%2A>.  Изменение свойства элемента <xref:System.Windows.UIElement.Opacity%2A> может вызвать среду [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для создания временной поверхности.  
  
<a name="Navigation_Objects"></a>   
## Переход к объекту  
 Объект <xref:System.Windows.Navigation.NavigationWindow> является производным от <xref:System.Windows.Window> и расширяет его возможностью навигации по содержимому, главным образом, статистической обработкой <xref:System.Windows.Navigation.NavigationService> и журналированием.  Можно обновить клиентскую область <xref:System.Windows.Navigation.NavigationWindow>, указав [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] или объект.  В следующем примере демонстрируются оба способа.  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Каждый объект <xref:System.Windows.Navigation.NavigationWindow> имеет журнал, в котором регистрируется история переходов данного пользователя в этом окне.  Одной из целей создания журнала является возможность разрешить пользователям повторять действия.  
  
 При переходе с помощью [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] журнал сохраняет только ссылку [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  Это означает, что каждый раз при повторном посещении страницы, она динамически перестраивается за время, зависящее от сложности страницы.  В этом случае затраты на хранение журнала незначительны, а скорость воссоздания страниц является потенциально высокой.  
  
 При переходе с помощью объекта, в журнал сохраняется полное визуальное дерево объекта.  Это означает, что при каждом повторном посещении страницы она отображается немедленно без необходимости реконструирования.  В этом случае затраты на хранение журнала высоки, а скорость воссоздания страниц мала.  
  
 При использовании объекта <xref:System.Windows.Navigation.NavigationWindow> необходимо учитывать влияние журналирования на производительность приложения.  Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## Проверка попадания курсора мыши на больших трехмерных поверхностях  
 Проверка попадания курсора мыши на больших трехмерных поверхностях является операцией, очень затратной по производительности и загрузке процессора.  Особенно это относится к анимированным трехмерным поверхностям.  Если проверка попадания курсора на этих поверхностях не требуется, то ее следует отключить.  Объекты, производные от <xref:System.Windows.UIElement>, могут отключить проверку, установив для свойства <xref:System.Windows.UIElement.IsHitTestVisible%2A> значение `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## Событие CompositionTarget.Rendering  
 Событие <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=fullName> вызывает среду [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для поддержки постоянной анимации.  Если это событие используется, отключайте его при каждой возможности.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## Избегайте использования ScrollBarVisibility\=Auto  
 Везде, где это возможно, избегайте использования значения <xref:System.Windows.Controls.ScrollBarVisibility?displayProperty=fullName> для свойств `HorizontalScrollBarVisibility` и `VerticalScrollBarVisibility`.  Эти свойства определены для объектов <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer> и <xref:System.Windows.Controls.TextBox> и в качестве вложенного свойства для объекта <xref:System.Windows.Controls.ListBox>.  Вместо этого установите для свойства <xref:System.Windows.Controls.ScrollBarVisibility> значение <xref:System.Windows.Controls.ScrollBarVisibility>, <xref:System.Windows.Controls.ScrollBarVisibility> или <xref:System.Windows.Controls.ScrollBarVisibility>.  
  
 Значение <xref:System.Windows.Controls.ScrollBarVisibility> предназначено для случаев, когда пространство ограничено и полосы прокрутки должны отображаться только при необходимости.  Например, значение <xref:System.Windows.Controls.ScrollBarVisibility> может использоваться для элемента <xref:System.Windows.Controls.ListBox> с 30\-тью элементами в списке, в отличие от <xref:System.Windows.Controls.TextBox> с сотнями строк текста.  
  
<a name="FontCache"></a>   
## Настройка службы кэширования шрифтов для сокращения времени загрузки  
 Служба кэширования шрифтов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] используется для совместной обработки данных шрифтов приложениями [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Первое запускаемое приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] запускает эту службу, если она еще не запущена.  При использовании [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] можно изменить параметр запуска службы [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Font Cache 3.0.0.0 со значения "Вручную" \(по умолчанию\) на "Автоматически \(отложенный запуск\)", чтобы уменьшить длительность начального запуска приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
## См. также  
 [Планирование производительности приложения](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Использование преимуществ оборудования](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Разметка и разработка](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Поведение объекта](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Ресурсы приложения](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Привязка данных](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Советы и рекомендации по анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)