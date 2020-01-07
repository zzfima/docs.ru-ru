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
ms.openlocfilehash: b6d99d90a3da232e1873ebe8433e01ceb2977de6
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636436"
---
# <a name="optimizing-performance-other-recommendations"></a>Оптимизация производительности. Дополнительные рекомендации
<a name="introduction"></a> В этом разделе содержатся рекомендации по улучшению производительности в дополнение к описанным в разделах статьи [Улучшение производительности приложений WPF](optimizing-wpf-application-performance.md).  
  
 В этом разделе содержатся следующие подразделы.  
  
- [Сравнение прозрачности кисти с прозрачностью элементов](#Opacity)  
  
- [Переход к объекту](#Navigation_Objects)  
  
- [Проверка попадания курсора мыши на больших трехмерных поверхностях](#Hit_Testing)  
  
- [Событие CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
- [Избегайте использования ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Настройка службы кэширования шрифтов для сокращения времени загрузки](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Сравнение прозрачности кисти с прозрачностью элементов  
 При использовании <xref:System.Windows.Media.Brush> для задания <xref:System.Windows.Shapes.Shape.Fill%2A> или <xref:System.Windows.Shapes.Shape.Stroke%2A> элемента лучше задать значение <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType>, а не задать свойство <xref:System.Windows.UIElement.Opacity%2A> элемента. Изменение свойства <xref:System.Windows.UIElement.Opacity%2A> элемента может привести к тому, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создаст временную поверхность.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Переход к объекту  
 Объект <xref:System.Windows.Navigation.NavigationWindow> является производным от <xref:System.Windows.Window> и расширяет его с помощью поддержки навигации по содержимому, в основном путем статистической обработки <xref:System.Windows.Navigation.NavigationService> и журнала. Вы можете обновить клиентскую область <xref:System.Windows.Navigation.NavigationWindow>, указав универсальный код ресурса (URI) или объект. В следующем примере демонстрируются оба способа.  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Каждый объект <xref:System.Windows.Navigation.NavigationWindow> имеет журнал, записывающий журнал переходов пользователя в этом окне. Одной из целей создания журнала является возможность разрешить пользователям повторять действия.  
  
 При переходе по универсальному идентификатору ресурса (URI) в журнале хранится только ссылка на универсальный код ресурса (URI). Это означает, что каждый раз при повторном посещении страницы она динамически перестраивается за время, зависящее от сложности страницы. В этом случае затраты на хранение журнала незначительны, а скорость воссоздания страниц является потенциально высокой.  
  
 При переходе с помощью объекта в журнал сохраняется полное визуальное дерево объекта. Это означает, что при каждом повторном посещении страницы она отображается немедленно без необходимости реконструирования. В этом случае затраты на хранение журнала высоки, а скорость воссоздания страниц низкая.  
  
 При использовании объекта <xref:System.Windows.Navigation.NavigationWindow> необходимо учитывать, как поддержка ведения журнала влияет на производительность приложения. Дополнительные сведения см. в разделе [Общие сведения о переходах](../app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Проверка попадания курсора мыши на больших трехмерных поверхностях  
 Проверка попадания курсора мыши на больших трехмерных поверхностях является операцией, очень затратной по производительности и загрузке процессора. Особенно это относится к анимированным трехмерным поверхностям. Если проверка попадания курсора на этих поверхностях не требуется, то ее следует отключить. Объекты, производные от <xref:System.Windows.UIElement>, могут отключить проверку попадания, установив для свойства <xref:System.Windows.UIElement.IsHitTestVisible%2A> значение `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>Событие CompositionTarget.Rendering  
 Событие <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> вызывает непрерывную анимацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Если это событие используется, отключайте его при каждой возможности.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Избегайте использования ScrollBarVisibility=Auto  
 По возможности избегайте использования значения <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> для свойств `HorizontalScrollBarVisibility` и `VerticalScrollBarVisibility`. Эти свойства определяются для <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>и <xref:System.Windows.Controls.TextBox> объектов, а также как вложенное свойство для объекта <xref:System.Windows.Controls.ListBox>. Вместо этого задайте для <xref:System.Windows.Controls.ScrollBarVisibility> значение <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>или <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 Значение <xref:System.Windows.Controls.ScrollBarVisibility.Auto> предназначено для случаев, когда пространство ограничено, а полосы прокрутки должны отображаться только при необходимости. Например, может быть полезно использовать это <xref:System.Windows.Controls.ScrollBarVisibility> значение с <xref:System.Windows.Controls.ListBox> 30 элементами, а не <xref:System.Windows.Controls.TextBox> с сотнями строк текста.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Настройка службы кэширования шрифтов для сокращения времени загрузки  
 Служба кэша шрифтов WPF совместно использует данные шрифтов между приложениями WPF. Первое запускаемое приложение WPF запускает эту службу, если она еще не запущена. Если вы используете Windows Vista, можно задать для свойства "Windows Presentation Foundation (WPF) кэша шрифтов 3.0.0.0" (по умолчанию) значение "автоматически (отложенный запуск)", чтобы сократить начальное время запуска приложений WPF.  
  
## <a name="see-also"></a>См. также:

- [Планирование производительности приложения](planning-for-application-performance.md)
- [Использование преимуществ оборудования](optimizing-performance-taking-advantage-of-hardware.md)
- [Разметка и разработка](optimizing-performance-layout-and-design.md)
- [Двумерная графика и изображения](optimizing-performance-2d-graphics-and-imaging.md)
- [Поведение объекта](optimizing-performance-object-behavior.md)
- [Ресурсы приложений](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Привязка данных](optimizing-performance-data-binding.md)
- [Советы и рекомендации по анимации](../graphics-multimedia/animation-tips-and-tricks.md)
