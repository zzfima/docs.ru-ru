---
title: Оптимизация производительности. Дополнительные рекомендации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186304"
---
# <a name="optimizing-performance-other-recommendations"></a>Оптимизация производительности. Дополнительные рекомендации
<a name="introduction"></a> В этом разделе содержатся рекомендации по улучшению производительности в дополнение к описанным в разделах статьи [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md).  
  
 Этот раздел состоит из следующих подразделов.  
  
- [Сравнение прозрачности кисти с прозрачностью элементов](#Opacity)  
  
- [Переход к объекту](#Navigation_Objects)  
  
- [Проверка попадания курсора мыши на больших трехмерных поверхностях](#Hit_Testing)  
  
- [Событие CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
- [Избегайте использования ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Настройка службы кэширования шрифтов для сокращения времени загрузки](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Сравнение прозрачности кисти с прозрачностью элементов  
 При использовании <xref:System.Windows.Media.Brush> <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> элемента лучше установить <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> значение, а не настройку свойства элемента. <xref:System.Windows.UIElement.Opacity%2A> Изменение свойства элемента <xref:System.Windows.UIElement.Opacity%2A> может [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] привести к созданию временной поверхности.  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a>Переход к объекту  
 Объект <xref:System.Windows.Navigation.NavigationWindow> происходит от <xref:System.Windows.Window> и расширяет его с содержанием навигационной <xref:System.Windows.Navigation.NavigationService> поддержки, в первую очередь путем агрегирования и журнала. Вы можете обновить область <xref:System.Windows.Navigation.NavigationWindow> клиента, указав либо единый идентификатор ресурса (URI) или объект. В следующем примере демонстрируются оба способа.  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Каждый <xref:System.Windows.Navigation.NavigationWindow> объект имеет журнал, который записывает историю навигации пользователя в этом окне. Одной из целей создания журнала является возможность разрешить пользователям повторять действия.  
  
 При навигации с помощью единого идентификатора ресурсов (URI) журнал хранит только единый идентификатор ресурсов (URI). Это означает, что каждый раз при повторном посещении страницы она динамически перестраивается за время, зависящее от сложности страницы. В этом случае затраты на хранение журнала незначительны, а скорость воссоздания страниц является потенциально высокой.  
  
 При переходе с помощью объекта в журнал сохраняется полное визуальное дерево объекта. Это означает, что при каждом повторном посещении страницы она отображается немедленно без необходимости реконструирования. В этом случае затраты на хранение журнала высоки, а скорость воссоздания страниц низкая.  
  
 При использовании <xref:System.Windows.Navigation.NavigationWindow> объекта необходимо иметь в виду, как поддержка журналирования влияет на производительность приложения. Для получения дополнительной информации [см.](../app-development/navigation-overview.md)  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a>Проверка попадания курсора мыши на больших трехмерных поверхностях  
 Проверка попадания курсора мыши на больших трехмерных поверхностях является операцией, очень затратной по производительности и загрузке процессора. Особенно это относится к анимированным трехмерным поверхностям. Если проверка попадания курсора на этих поверхностях не требуется, то ее следует отключить. Объекты, полученные <xref:System.Windows.UIElement> из может отключить хит <xref:System.Windows.UIElement.IsHitTestVisible%2A> тестирования `false`путем установки свойства.  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a>Событие CompositionTarget.Rendering  
 Событие <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> приводит [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] к непрерывной анимировать. Если это событие используется, отключайте его при каждой возможности.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a>Избегайте использования ScrollBarVisibility=Auto  
 Когда это возможно, <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> избегайте `HorizontalScrollBarVisibility` использования `VerticalScrollBarVisibility` значения для свойств и свойств. Эти свойства <xref:System.Windows.Controls.RichTextBox>определены <xref:System.Windows.Controls.ScrollViewer>для <xref:System.Windows.Controls.TextBox> объектов и объектов, <xref:System.Windows.Controls.ListBox> а также как прилагаемое свойство для объекта. Вместо этого, <xref:System.Windows.Controls.ScrollBarVisibility.Disabled> <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>установить <xref:System.Windows.Controls.ScrollBarVisibility.Visible> <xref:System.Windows.Controls.ScrollBarVisibility> на , или .  
  
 Значение <xref:System.Windows.Controls.ScrollBarVisibility.Auto> предназначено для случаев, когда пространство ограничено, а прокрутки должны отображаться только при необходимости. Например, может быть полезно <xref:System.Windows.Controls.ScrollBarVisibility> использовать это <xref:System.Windows.Controls.ListBox> значение с 30 <xref:System.Windows.Controls.TextBox> элементами, в отличие от сотни строк текста.  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Настройка службы кэширования шрифтов для сокращения времени загрузки  
 Служба кэша шрифтов WPF делится данными шрифтов между приложениями WPF. Первое приложение WPF, которое вы запускаете, запускает эту службу, если служба еще не запущена. Если вы используете Windows Vista, вы можете настроить кэш шрифта "Windows Presentation Foundation (WPF) 3.0.0.0" с "Manual" (по умолчанию) на "Автоматический (задержка старта)", чтобы сократить начальное время запуска приложений WPF.  
  
## <a name="see-also"></a>См. также раздел

- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложения](optimizing-performance-application-resources.md)
- [Текст](optimizing-performance-text.md)
- [Связывание данных](optimizing-performance-data-binding.md)
- [Советы и рекомендации по анимации](../graphics-multimedia/animation-tips-and-tricks.md)
