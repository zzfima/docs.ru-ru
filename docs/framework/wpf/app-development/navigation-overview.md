---
title: "Общие сведения о переходах | Microsoft Docs"
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
  - "состояние содержимого [WPF]"
  - "пользовательские объекты [WPF]"
  - "переход к фрагменту [WPF]"
  - "фреймы [WPF]"
  - "HTML-файлы [WPF]"
  - "гиперссылки [WPF]"
  - "журналы [WPF]"
  - "время существования [WPF]"
  - "файлы на свободном языке XAML [WPF]"
  - "узлы переходов [WPF]"
  - "страницы [WPF]"
  - "программные переходы [WPF]"
  - "сохранение состояния содержимого [WPF]"
  - "Начальная страница [WPF]"
  - "структурный переход [WPF]"
  - "Универсальные коды ресурсов (URI)"
  - "URI (универсальные коды ресурсов)"
  - "окна [WPF]"
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
caps.latest.revision: 69
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 65
---
# Общие сведения о переходах
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] поддерживает навигацию в стиле браузера, которая может использоваться в приложениях двух типов: автономных приложениях и [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]. Чтобы упаковать содержимое для навигации, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет класс <xref:System.Windows.Controls.Page>.  Можно переходить от одного класса <xref:System.Windows.Controls.Page> к другому декларативным способом, с использованием объекта <xref:System.Windows.Documents.Hyperlink>, или программным способом, с использованием объекта <xref:System.Windows.Navigation.NavigationService>. Приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует журнал, чтобы запоминать страницы, с которых был осуществлен переход, и чтобы переходить к ним обратно.  
  
 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> и журнал образуют основу для предоставляемой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддержки переходов.  В данном обзоре подробно анализируются эти особенности перед описанием расширенной поддержки переходов, которая включает переход к свободным файлам [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], файлам [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] и объектам.  
  
> [!NOTE]
>  В этом разделе термин "браузер" относится только к браузерам, в которых можно размещать приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. В настоящее время к этим браузерам относятся [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] и Firefox.  В случае, когда специфические компоненты [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживаются только одним определенным браузером, указывается версия браузера.  
  
   
  
<a name="XAMLBrowserApplications"></a>   
## Переходы в приложениях WPF  
 В этом разделе дается обзор основных возможностей перехода в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Эти возможности доступны как для автономных приложений, так и для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], хотя в этом разделе они представлены в контексте [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
> [!NOTE]
>  В этом разделе не обсуждается построение и развертывание [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Дополнительные сведения о [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] см. в разделе [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 В этом разделе объясняются и демонстрируются следующие аспекты переходов:  
  
-   [Реализация страницы](#CreatingAXAMLPage)  
  
-   [Настройка домашней страницы](#Configuring_a_Start_Page)  
  
-   [Настройка заголовка, ширины и высоты основного окна](#ConfiguringAXAMLPage)  
  
-   [Переход по гиперссылке](#NavigatingBetweenXAMLPages)  
  
-   [Переход к фрагменту](#FragmentNavigation)  
  
-   [Служба переходов](#NavigationService)  
  
-   [Программный переход с помощью службы переходов](#Programmatic_Navigation_with_the_Navigation_Service)  
  
-   [Время существования перехода](#Navigation_Lifetime)  
  
-   [Запоминание перехода в журнале](#NavigationHistory)  
  
-   [Время существования страницы и журнал](#PageLifetime)  
  
-   [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory)  
  
-   [Файлы Cookie](#Cookies)  
  
-   [Структурная навигация](#Structured_Navigation)  
  
<a name="CreatingAXAMLPage"></a>   
### Реализация страницы  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] можно перейти к нескольким типам содержимого, включающего объекты [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)], пользовательские объекты, значения перечисления, пользовательские элементы управления, файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и файлы [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)].  Однако наиболее распространенным и удобным способом упаковки содержимого является использование <xref:System.Windows.Controls.Page>.  Более того, <xref:System.Windows.Controls.Page> реализует особые возможности перехода в целях улучшения их внешнего вида и упрощения разработки.  
  
 С помощью <xref:System.Windows.Controls.Page> можно декларативно реализовать доступную для перехода страницу содержимого [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используя разметку так, как показано на рисунке.  
  
 [!code-xml[NavigationOverviewSnippets#Page1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]  
  
 Класс <xref:System.Windows.Controls.Page>, реализованный в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержит `Page` в качестве корневого элемента и требует объявления пространства имен [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  В элементе `Page` находится содержимое, к которому требуется перейти и отобразить.  Для добавления содержимого задается свойство `Page.Content` элемента, как показано в следующем примере разметки.  
  
 [!code-xml[NavigationOverviewSnippets#Page2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]  
  
 `Page.Content` может содержать только один дочерний элемент; как предложено в предыдущем примере, содержимым является отдельная строка "Привет, Страница\!". На практике в качестве дочернего элемента для создания и хранения нужного содержимого обычно используется элемент управления макета \(см. раздел [Макет](../../../../docs/framework/wpf/advanced/layout.md)\).  
  
 Дочерние элементы элемента `Page` считаются содержимым класса <xref:System.Windows.Controls.Page> и, следовательно, нет необходимости использовать явное объявление `Page.Content`.  Следующая разметка является декларативным эквивалентом предыдущего примера.  
  
 [!code-xml[NavigationOverviewSnippets#Page3XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]  
  
 В этом случае `Page.Content` автоматически задается вместе с дочерними элементами элемента `Page`.  Дополнительные сведения см. в разделе [Модель содержимого WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
 Класс <xref:System.Windows.Controls.Page> \(только для разметки\) используется для отображения содержимого.  Однако <xref:System.Windows.Controls.Page> может также отображать элементы управления, позволяющие пользователям взаимодействовать со страницей, и может отвечать на действия пользователя, выполняя обработку событий и вызывая логику приложения.  Интерактивный класс <xref:System.Windows.Controls.Page> реализован с помощью комбинации разметки и кода программной части, как показано в следующем примере.  
  
 [!code-xml[XBAPAppDefSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
 [!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]  
  
 Чтобы разрешить совместную работу файла разметки и файла кода программной части, требуется следующая конфигурация:  
  
-   В разметке элемент `Page` должен включать атрибут `x:Class`.  При построении приложения существование `x:Class` в файле разметки приводит к тому, что [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] создает класс `partial`, который является производным от <xref:System.Windows.Controls.Page> и имя которого определяется атрибутом `x:Class`.  Для этого требуется добавить объявление пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в схему [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  Созданный класс `partial` реализует `InitializeComponent`, который вызывается для регистрации событий и задания свойств, реализованных в разметке.  
  
-   В коде программной части класс должен быть классом `partial` с тем же именем, которое определено атрибутом `x:Class` в разметке, и он должен быть производным от <xref:System.Windows.Controls.Page>.  Это позволяет связать файл кода программной части с классом `partial`, созданным для файла разметки при построении приложения \(см. раздел [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
-   В коде программной части класс <xref:System.Windows.Controls.Page> должен реализовать конструктор, вызывающий метод `InitializeComponent`.  Метод `InitializeComponent` реализуется классом `partial`, созданным файлом разметки, для регистрации событий и задания свойств, определенных в разметке.  
  
> [!NOTE]
>  Когда в проект добавляется новый класс <xref:System.Windows.Controls.Page> с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Controls.Page> реализуется с помощью разметки и кода программной части и включает необходимую конфигурацию для создания связи между файлами разметки и файлами кода программной части.  
  
 После получения класса <xref:System.Windows.Controls.Page> к нему можно перейти.  Чтобы указать первый объект <xref:System.Windows.Controls.Page>, к которому переходит приложение, необходимо настроить домашнюю страницу <xref:System.Windows.Controls.Page>.  
  
<a name="Configuring_a_Start_Page"></a>   
### Настройка домашней страницы  
 Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] требуется определенная инфраструктура приложений, размещенных в браузере.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] класс <xref:System.Windows.Application> является частью определения приложения, которое устанавливает необходимую инфраструктуру приложений \(см. раздел [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)\).  
  
 Определение приложения обычно реализуется с помощью разметки и кода программной части, причем файл разметки настраивается как элемент `ApplicationDefinition` системы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. Ниже приводится определение приложения для [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 [!code-xml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 [!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
 [!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]  
  
 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] может использовать определение приложения, чтобы указать начальный объект <xref:System.Windows.Controls.Page>, представляющий собой <xref:System.Windows.Controls.Page>, автоматически загружаемую при запуске [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Для этого задайте свойство <xref:System.Windows.Application.StartupUri%2A> со значением [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] для нужной <xref:System.Windows.Controls.Page>.  
  
> [!NOTE]
>  В большинстве случаев <xref:System.Windows.Controls.Page> либо компилируется в приложение, либо развертывается вместе с ним.  В этих случаях [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], определяющий <xref:System.Windows.Controls.Page>, является [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", который представляет собой [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], соответствующий схеме *pack*.  [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" обсуждаются далее в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md). Для перехода к содержимому можно также использовать схему HTTP, которая рассматривается далее.  
  
 Можно задать <xref:System.Windows.Application.StartupUri%2A> декларативно в разметке, как показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]  
  
 В этом примере атрибут `StartupUri` задается с относительным [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", определяющим HomePage.xaml.  При запуске [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] автоматически осуществляется переход и отображение HomePage.xaml.  Это продемонстрировано на приведенном ниже рисунке, который показывает приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], запущенное с веб\-сервера.  
  
 ![XBAP&#45;страница](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure9.png "NavigationOverviewFigure9")  
  
> [!NOTE]
>  Дополнительные сведения о разработке и развертывании [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] см. в разделах [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md) и [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="ConfiguringAXAMLPage"></a>   
### Настройка заголовка, ширины и высоты основного окна  
 В предыдущем примере можно заметить, что заголовком как браузера, так и панели вкладок является [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Заголовок не только длинный, но также не является ни привлекательным, ни информативным.  По этой причине <xref:System.Windows.Controls.Page> предлагает способ для изменения заголовка с помощью задания свойства <xref:System.Windows.Controls.Page.WindowTitle%2A>.  Более того, можно настроить ширину и высоту окна браузера, задав свойства <xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A> соответственно.  
  
 Свойства <xref:System.Windows.Controls.Page.WindowTitle%2A>,<xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A> могут быть заданы декларативно в разметке, как показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#HomePageMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]  
  
 Результат показан на следующем рисунке.  
  
 ![Название окна, высота, ширина](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure2.png "NavigationOverviewFigure2")  
  
<a name="NavigatingBetweenXAMLPages"></a>   
### Переход по гиперссылке  
 Обычно [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] состоит из нескольких страниц.  Самый простой способ перехода от одной страницы к другой заключается в использовании объекта <xref:System.Windows.Documents.Hyperlink>.  Можно декларативно добавить <xref:System.Windows.Documents.Hyperlink> в <xref:System.Windows.Controls.Page>, используя элемент `Hyperlink`, показанный в следующем примере разметки.  
  
 [!code-xml[NavigationOverviewSnippets#HyperlinkXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]  
[!code-xml[NavigationOverviewSnippets#HyperlinkXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]  
  
 Для элемента `Hyperlink` необходимо следующее:  
  
-   [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" из <xref:System.Windows.Controls.Page> для перехода, заданный атрибутом `NavigateUri`.  
  
-   Содержимое, которое пользователь может щелкнуть для инициации перехода, например текст и изображения \(содержимое, которое может содержать элемент `Hyperlink`, см. в разделе <xref:System.Windows.Documents.Hyperlink>\).  
  
 На следующем рисунке показано [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с объектом <xref:System.Windows.Controls.Page>, содержащим <xref:System.Windows.Documents.Hyperlink>.  
  
 ![Страница с гиперссылкой](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure3.png "NavigationOverviewFigure3")  
  
 Как и следовало ожидать, если щелкнуть <xref:System.Windows.Documents.Hyperlink>, вызывается [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] для перехода к объекту <xref:System.Windows.Controls.Page>, определяемому атрибутом `NavigateUri`.  Кроме того, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] добавляет вход для предыдущего объекта <xref:System.Windows.Controls.Page> в список последних страниц в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Это показано на следующем рисунке.  
  
 ![Кнопки “Дальше” и “Назад”](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Помимо поддержки перехода от одной <xref:System.Windows.Controls.Page> к другой, <xref:System.Windows.Documents.Hyperlink> также поддерживает переход к фрагменту.  
  
<a name="FragmentNavigation"></a>   
### Переход к фрагменту  
 *Переход к фрагменту* — это переход к фрагменту содержимого в текущей <xref:System.Windows.Controls.Page> или другой <xref:System.Windows.Controls.Page>.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] фрагмент содержимого представляет собой данные, содержащиеся в именованном элементе.  Именованный элемент — это элемент с набором атрибутов `Name`.  В следующей разметке показан именованный элемент `TextBlock`, включающий фрагмент содержимого.  
  
 [!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]  
[!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]  
[!code-xml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]  
  
 Для перехода по <xref:System.Windows.Documents.Hyperlink> к фрагменту содержимого атрибут `NavigateUri` должен включать следующее:  
  
-   [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] из <xref:System.Windows.Controls.Page> с фрагментом содержимого для перехода.  
  
-   Символ "\#".  
  
-   Имя элемента в объекте <xref:System.Windows.Controls.Page>, включающего фрагмент содержимого.  
  
 Фрагмент [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] имеет следующий формат.  
  
 *URI\_страницы* `#` *имя\_элемента*  
  
 Ниже показан пример `Hyperlink`, настроенной на переход к фрагменту содержимого.  
  
 [!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]  
[!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]  
[!code-xml[NavigationOverviewSnippets#PageThatNavigatesXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]  
  
> [!NOTE]
>  Этот раздел описывает реализацию переходов фрагмента по умолчанию в приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] также позволяет реализовать собственную схему переходов фрагмента, которая отчасти требует обработки события <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Можно перейти к фрагменту свободных страниц [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(файлы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] только для разметки с `Page` в качестве корневого элемента\), если только страницы можно просмотреть с помощью [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].  
>   
>  Однако свободная страница [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может поддерживать переходы на свои собственные фрагменты.  
  
<a name="NavigationService"></a>   
### Служба переходов  
 Тогда как <xref:System.Windows.Documents.Hyperlink> позволяет пользователю инициировать переход к конкретной <xref:System.Windows.Controls.Page>, работа по поиску и загрузке страницы выполняется с помощью класса <xref:System.Windows.Navigation.NavigationService>.  По существу <xref:System.Windows.Navigation.NavigationService> предоставляет возможность обработки запроса перехода со стороны кода клиента, например <xref:System.Windows.Documents.Hyperlink>.  Кроме того, <xref:System.Windows.Navigation.NavigationService> реализует поддержку более высокого уровня для отслеживания запроса перехода и влияния на него.  
  
 Если щелкнуть <xref:System.Windows.Documents.Hyperlink> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], вызывается <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName> для обнаружения и загрузки <xref:System.Windows.Controls.Page> в указанном [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack".  Загруженная <xref:System.Windows.Controls.Page> преобразуется в дерево объектов, корневой объект которого является экземпляром загруженной <xref:System.Windows.Controls.Page>.  Ссылка на корневой объект <xref:System.Windows.Controls.Page> сохраняется в свойстве <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=fullName>.  Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для содержимого, к которому был осуществлен переход, сохраняется в свойстве <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=fullName>, тогда как <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=fullName> сохраняет пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для последней посещенной страницы.  
  
> [!NOTE]
>  Приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] может иметь несколько активных <xref:System.Windows.Navigation.NavigationService>.  Дополнительные сведения см. далее в разделе [узлы переходов](#Navigation_Hosts).  
  
<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>   
### Программный переход с помощью службы переходов  
 Не требуется знать о <xref:System.Windows.Navigation.NavigationService>, если переход реализован декларативно в разметке с помощью <xref:System.Windows.Documents.Hyperlink>, поскольку <xref:System.Windows.Documents.Hyperlink> использует <xref:System.Windows.Navigation.NavigationService> с вашей стороны.  Это значит, что пока прямой или непрямой родительский объект элемента <xref:System.Windows.Documents.Hyperlink> является узлом перехода \(см. раздел [узлы переходов](#Navigation_Hosts)\), <xref:System.Windows.Documents.Hyperlink> сможет найти и использовать службу переходов этого узла для обработки запроса перехода.  
  
 Однако бывают ситуации, когда необходимо использовать <xref:System.Windows.Navigation.NavigationService> напрямую, например:  
  
-   Если необходимо создать экземпляр <xref:System.Windows.Controls.Page> с использованием конструктора, отличного от конструктора по умолчанию.  
  
-   Если требуется задать свойства в объекте <xref:System.Windows.Controls.Page> перед переходом к нему.  
  
-   Если объект <xref:System.Windows.Controls.Page>, к которому необходимо перейти, можно определить только во время выполнения.  
  
 В таких случаях необходимо написать код для программной инициации перехода посредством вызова метода <xref:System.Windows.Navigation.NavigationService.Navigate%2A> объекта <xref:System.Windows.Navigation.NavigationService>.  Для этого требуется получить ссылку на <xref:System.Windows.Navigation.NavigationService>.  
  
#### Получение ссылки на службу переходов  
 В силу причин, описанных в разделе [узлы переходов](#Navigation_Hosts), приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] может иметь несколько <xref:System.Windows.Navigation.NavigationService>.  Это означает, что в коде необходимо предусмотреть способ поиска службы <xref:System.Windows.Navigation.NavigationService>, которая обычно представляет собой службу <xref:System.Windows.Navigation.NavigationService>, приводящую к текущей <xref:System.Windows.Controls.Page>. Ссылку на службу <xref:System.Windows.Navigation.NavigationService> можно получить, вызвав метод <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=fullName> типа `static`.  Чтобы получить службу <xref:System.Windows.Navigation.NavigationService>, осуществляющую переход к конкретной <xref:System.Windows.Controls.Page>, передайте ссылку в объект <xref:System.Windows.Controls.Page> в качестве аргумента метода <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A>.  В следующем фрагменте кода показано, как получить <xref:System.Windows.Navigation.NavigationService> для текущей <xref:System.Windows.Controls.Page>.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]  
  
 <xref:System.Windows.Controls.Page> реализует свойство <xref:System.Windows.Controls.Page.NavigationService%2A>, чтобы быстро найти <xref:System.Windows.Navigation.NavigationService> для <xref:System.Windows.Controls.Page>.  Это показано в следующем примере.  
  
 [!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]  
  
> [!NOTE]
>  <xref:System.Windows.Controls.Page> может получить ссылку на соответствующую <xref:System.Windows.Navigation.NavigationService>, только когда <xref:System.Windows.Controls.Page> вызывает событие <xref:System.Windows.FrameworkElement.Loaded>.  
  
#### Программный переход к объекту страницы  
 В следующем примере показано, как с помощью <xref:System.Windows.Navigation.NavigationService> осуществить программный переход к <xref:System.Windows.Controls.Page>.  Программные переходы необходимы, поскольку экземпляр <xref:System.Windows.Controls.Page>, к которому осуществляется переход, можно создать только с помощью одного конструктора, отличного от конструктора по умолчанию.  Объект <xref:System.Windows.Controls.Page> с нестандартным конструктором показан в следующей разметке и коде.  
  
 [!code-xml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
 [!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]  
  
 Объект <xref:System.Windows.Controls.Page>, осуществляющий переход к <xref:System.Windows.Controls.Page> с конструктором, отличным от используемого по умолчанию, показан в следующей разметке и коде.  
  
 [!code-xml[NavigationOverviewSnippets#NSNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]  
  
 Если щелкнуть объект <xref:System.Windows.Documents.Hyperlink> на странице <xref:System.Windows.Controls.Page>, запускается переход путем создания экземпляра страницы <xref:System.Windows.Controls.Page>, на которую необходимо перейти, с использованием конструктора, отличного от заданного по умолчанию, и с вызовом метода <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  Метод <xref:System.Windows.Navigation.NavigationService.Navigate%2A> принимает ссылку на объект, к которому осуществит переход объект <xref:System.Windows.Navigation.NavigationService>, скорее чем пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
#### Программный переход с URI типа "pack"  
 Если необходимо создать [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" программным образом \(например, когда [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" определяется только во время выполнения\), можно использовать метод <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  Это показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#NSUriNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]  
  
#### Обновление текущей страницы  
 <xref:System.Windows.Controls.Page> не загружается, если содержит [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", совпадающий с [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack", который хранится в свойстве <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=fullName>.  Чтобы вынудить [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] повторно загрузить текущую страницу, можно вызвать метод <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=fullName>, как показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]  
  
 [!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]  
  
<a name="Navigation_Lifetime"></a>   
### Время существования перехода  
 Как вы уже видели, существует множество способов инициации перехода.  Когда переход инициирован и находится в процессе выполнения, можно отследить его и повлиять на него с помощью следующих событий, реализованных в <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigating>.  Появляется, когда запрошен новый переход.  Может использоваться для отмены перехода.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationProgress>.  Появляется периодически во время загрузки, предоставляя сведения о ходе выполнения перехода.  
  
-   <xref:System.Windows.Navigation.NavigationService.Navigated>.  Появляется, когда страница найдена и загружена.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationStopped>.  Появляется, когда переход остановлен \(посредством вызова метода <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>\) или когда поступил запрос нового перехода во время выполнения текущего перехода.  
  
-   <xref:System.Windows.Navigation.NavigationService.NavigationFailed>.  Появляется при появлении ошибки во время перехода к запрошенному содержимому.  
  
-   <xref:System.Windows.Navigation.NavigationService.LoadCompleted>.  Появляется, когда содержимое, к которому был осуществлен переход, загружено и проанализировано, и начинается его отрисовка.  
  
-   <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>.  Появляется в начале перехода к фрагменту содержимого, который происходит:  
  
    -   Немедленно, если нужный фрагмент находится в текущем содержимом.  
  
    -   После загрузки исходного содержимого, если нужный фрагмент находится в другом содержимом.  
  
 События перехода вызываются в порядке, который показан на следующем рисунке.  
  
 ![Таблица потока навигации страницы](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure11.png "NavigationOverviewFigure11")  
  
 Обычно объект <xref:System.Windows.Controls.Page> не связан с этими событиями.  Более вероятно, что приложение связано с ними, поэтому эти события также вызываются классом <xref:System.Windows.Application>:  
  
-   <xref:System.Windows.Application.Navigating?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationProgress?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.Navigated?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationFailed?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.NavigationStopped?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.LoadCompleted?displayProperty=fullName>  
  
-   <xref:System.Windows.Application.FragmentNavigation?displayProperty=fullName>  
  
 Каждый раз, когда <xref:System.Windows.Navigation.NavigationService> создает событие, класс <xref:System.Windows.Application> создает соответствующее событие.  <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> предлагают одни и те же события для обнаружения переходов в соответствующих областях.  
  
 В некоторых случаях объект <xref:System.Windows.Controls.Page> может быть заинтересован в этих событиях.  Например, <xref:System.Windows.Controls.Page> может обработать событие <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=fullName>, чтобы определить необходимость отмены перехода с текущей страницы.  Это показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#CancelNavigationPageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]  
  
 [!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
 [!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]  
  
 Если регистрируется обработчик с событием перехода из <xref:System.Windows.Controls.Page>, как это сделано в предыдущем примере, то необходимо также отменить регистрацию обработчика событий.  Если этого не сделать, могут возникнуть побочные эффекты в отношении того, как [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] запоминает переходы <xref:System.Windows.Controls.Page> с помощью журнала.  
  
<a name="NavigationHistory"></a>   
### Запоминание перехода в журнале  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует два стека для запоминания страниц, с которых был осуществлен переход: стек "Назад" и стек "Вперед".  При переходе с текущей <xref:System.Windows.Controls.Page> на новую <xref:System.Windows.Controls.Page> или вперед на существующую <xref:System.Windows.Controls.Page> текущая <xref:System.Windows.Controls.Page> добавляется в *стек "Назад"*.  При переходе с текущей <xref:System.Windows.Controls.Page> обратно на предыдущую <xref:System.Windows.Controls.Page> текущая <xref:System.Windows.Controls.Page> добавляется в  *стек "Вперед"*.  Стек "Назад", стек "Вперед" и функциональные возможности для управления ими в совокупности называются журналом.  Каждый элемент стеков "Вперед" и "Назад" является экземпляром класса <xref:System.Windows.Navigation.JournalEntry> и называется *записью журнала*.  
  
#### Перемещение по журналу в браузере Internet Explorer  
 На понятийном уровне журнал функционирует подобно кнопкам **Вперед** и **Назад** в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Это показано на следующем рисунке.  
  
 ![Кнопки “Дальше” и “Назад”](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure4.png "NavigationOverviewFigure4")  
  
 Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], размещенных в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] осуществляет интеграцию журнала в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перехода для приложения [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  Это позволяет пользователям перемещаться по страницам в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с помощью кнопок **Назад**, **Вперед** и **Последние страницы** в браузере [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Журнал не интегрирован в [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] так же, как это сделано для [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] или Internet Explorer 8.  Вместо этого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] отображает заменяющий [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перехода.  
  
> [!IMPORTANT]
>  В [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] при переходе со страницы и обратно в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] в журнале сохраняются только те страницы, которые не поддерживались в активном состоянии.  Обсуждение поддержки страниц в активном состоянии см. далее в разделе [Время существования страницы и журнал](#PageLifetime).  
  
 По умолчанию текст для каждой <xref:System.Windows.Controls.Page>, находящейся в списке **Последние страницы** приложения [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], представляет собой [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для <xref:System.Windows.Controls.Page>.  В большинстве случаев это не особенно важно для пользователя.  К счастью, можно изменить текст, используя следующие параметры:  
  
1.  Значение вложенного атрибута `JournalEntry.Name`.  
  
2.  Значение атрибута `Page.Title`.  
  
3.  Значение атрибута `Page.WindowTitle` и [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для текущего объекта <xref:System.Windows.Controls.Page>.  
  
4.  [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для текущего объекта <xref:System.Windows.Controls.Page>.  \(Значение по умолчанию\)  
  
 Порядок, в котором перечислены параметры, совпадает с порядком приоритета для поиска текста.  Например, если задан атрибут `JournalEntry.Name`, то другие значения игнорируются.  
  
 В следующем примере для изменения текста, который отображается в записи журнала, используется атрибут `Page.Title`.  
  
 [!code-xml[NavigationOverviewSnippets#PageTitleMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]  
[!code-xml[NavigationOverviewSnippets#PageTitleMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]  
  
 [!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
 [!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]  
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]  
  
#### Перемещение по журналу с помощью WPF  
 Хотя пользователь может перемещаться по журналу с помощью кнопок **Назад**, **Вперед** и **Последние страницы** в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], для перемещения по журналу можно также использовать декларативные и программные механизмы, предоставленные [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Одна из причин для этого — предоставление [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] пользовательских переходов в нужных страницах.  
  
 Можно декларативно добавить поддержку журнального перехода с помощью команд перехода, предоставляемых <xref:System.Windows.Input.NavigationCommands>.  В следующем примере показано, как использовать команды перехода `BrowseBack`.  
  
 [!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]  
[!code-xml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]  
  
 Можно программно перемещаться по журналу с помощью одного из следующих членов класса <xref:System.Windows.Navigation.NavigationService>:  
  
-   <xref:System.Windows.Navigation.NavigationService.GoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.GoForward%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>  
  
-   <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>  
  
 Журналом можно также управлять программным образом, как описано в разделе [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory) далее.  
  
<a name="PageLifetime"></a>   
### Время существования страницы и журнал  
 Рассмотрим [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с несколькими страницами, содержащий большое количество рисунков, анимаций и медиафайлов.  Объем памяти для подобных страниц может быть довольно большим, особенно если используются видеоматериалы и звуковые файлы.  Исходя из того, что в журнале "запоминаются" посещенные страницы, приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] может быстро расходовать значительный объем памяти.  
  
 Поэтому в журнале по умолчанию сохраняются метаданные <xref:System.Windows.Controls.Page> в каждой записи, а не ссылки на объект <xref:System.Windows.Controls.Page>.  При переходе к записи журнала соответствующие метаданные <xref:System.Windows.Controls.Page> используются для создания нового экземпляра указанного объекта <xref:System.Windows.Controls.Page>.  В итоге время существования каждого объекта <xref:System.Windows.Controls.Page>, к которому осуществляется переход, определяется, как показано на следующем рисунке.  
  
 ![Время существования страницы](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure10.PNG "NavigationOverviewFigure10")  
  
 Хотя при использовании поведения журнала по умолчанию можно сэкономить потребление памяти, производительность отрисовки каждой страницы может уменьшиться; повторное создание экземпляров <xref:System.Windows.Controls.Page> может занимать много времени, особенно при наличии объемного содержимого.  Если требуется сохранить экземпляр <xref:System.Windows.Controls.Page> в журнале, можно сделать это двумя способами.  Во\-первых, можно осуществить программный переход к объекту <xref:System.Windows.Controls.Page> посредством вызова метода <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=fullName>.  
  
 Во\-вторых, можно установить, чтобы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] сохранял экземпляр объекта <xref:System.Windows.Controls.Page> в журнале, задавая для свойства <xref:System.Windows.Controls.Page.KeepAlive%2A> значение `true` \(по умолчанию — `false`\).  Можно задать <xref:System.Windows.Controls.Page.KeepAlive%2A> декларативно в разметке, как показано в следующем примере.  
  
 [!code-xml[NavigationOverviewSnippets#KeepAlivePageXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]  
  
 Время существования объекта <xref:System.Windows.Controls.Page>, который поддерживается в активном состоянии, немного отличается от объекта, активность которого не поддерживается.  При первом переходе к объекту <xref:System.Windows.Controls.Page>, который поддерживается в активном состоянии, создается экземпляр страницы, как и для объекта <xref:System.Windows.Controls.Page>, активное состояние которого не поддерживается.  Однако, поскольку экземпляр объекта <xref:System.Windows.Controls.Page> сохраняется в журнале, его экземпляр не требуется создавать повторно до тех пор, пока он остается в журнале.  Следовательно, если <xref:System.Windows.Controls.Page> имеет логику инициализации, которая должна вызываться при каждом переходе к объекту <xref:System.Windows.Controls.Page>, следует переместить ее из конструктора в обработчик для события <xref:System.Windows.FrameworkElement.Loaded>.  Как показано на следующем рисунке, события <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.FrameworkElement.Unloaded> по\-прежнему вызываются при каждом переходе к объекту <xref:System.Windows.Controls.Page> и от него соответственно.  
  
 ![При генерации событий загрузки и выгрузки](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure17.png "NavigationOverviewFigure17")  
  
 Когда <xref:System.Windows.Controls.Page> не поддерживается в активном состоянии, не следует выполнять следующие действия:  
  
-   Сохранять ссылку на объект или любую его часть.  
  
-   Регистрировать обработчики событий с событиями, которые не реализованы в объекте.  
  
 В случае выполнения любого из этих действий будут созданы ссылки, которые вынудят объект <xref:System.Windows.Controls.Page> оставаться в памяти даже после его удаления из журнала.  
  
 В общем случае следует предпочесть поведение <xref:System.Windows.Controls.Page> по умолчанию, при котором активность <xref:System.Windows.Controls.Page> не поддерживается.  Однако при этом существуют реализации состояния, которые описаны в следующем разделе.  
  
<a name="RetainingContentStateWithNavigationHistory"></a>   
### Сохранение состояния содержимого с помощью журнала переходов  
 Если <xref:System.Windows.Controls.Page> не поддерживается в активном состоянии, но имеет элементы управления, принимающие данные от пользователя, то что же происходит с данными, когда пользователь переходит с объекта <xref:System.Windows.Controls.Page> и возвращается к нему?  С точки зрения пользователя следует ожидать появления ранее введенных данных.  К сожалению, поскольку новый экземпляр класса <xref:System.Windows.Controls.Page> создается при каждом переходе, элементы управления, собирающие данные, инициализируются заново и информация теряется.  
  
 К счастью, журнал обеспечивает запоминание данных в объекте <xref:System.Windows.Controls.Page> при переходах, включая данные элементов управления.  В частности, запись журнала для каждого объекта <xref:System.Windows.Controls.Page> действует как временный контейнер для соответствующего состояния <xref:System.Windows.Controls.Page>.  На следующих этапах описывается схема осуществления поддержки при переходе со страницы <xref:System.Windows.Controls.Page>:  
  
1.  Запись для текущей страницы <xref:System.Windows.Controls.Page> добавляется в журнал.  
  
2.  Состояние страницы <xref:System.Windows.Controls.Page> сохраняется в записи журнала для этой страницы, которая добавляется в стек "Назад".  
  
3.  Выполняется переход к новой <xref:System.Windows.Controls.Page>.  
  
 При возврате к <xref:System.Windows.Controls.Page> с использованием журнала выполняются следующие действия:  
  
1.  Создается экземпляр <xref:System.Windows.Controls.Page> \(самая верхняя запись журнала в стеке "Назад"\).  
  
2.  Восстанавливается состояние <xref:System.Windows.Controls.Page>, которое было сохранено в записи журнала для <xref:System.Windows.Controls.Page>.  
  
3.  Выполняется обратный переход к <xref:System.Windows.Controls.Page>.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автоматически использует эту поддержку, когда в объекте <xref:System.Windows.Controls.Page> имеются следующие элементы управления:  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ProgressBar>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Slider>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
 Если в объекте <xref:System.Windows.Controls.Page> используются эти элементы управления, то введенные в них данные запоминаются при выполнении переходов <xref:System.Windows.Controls.Page>, как показано на примере элемента управления **Favorite Color** в <xref:System.Windows.Controls.ListBox> \(см. следующий рисунок\).  
  
 ![Страница с элементами управления, помнящими состояние](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure13.png "NavigationOverviewFigure13")  
  
 Когда <xref:System.Windows.Controls.Page> содержит элементы управления, не упомянутые в предыдущем списке, или когда состояние сохраняется в пользовательских объектах, необходимо написать код для сохранения в журнале состояния страницы при переходах <xref:System.Windows.Controls.Page>.  
  
 Если требуется запомнить небольшие части состояния страницы при переходах <xref:System.Windows.Controls.Page>, то можно использовать свойства зависимостей \(см. раздел <xref:System.Windows.DependencyProperty>\), настроенные с флагом метаданных <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=fullName>.  
  
 Если состояние, которое требуется запомнить при переходах <xref:System.Windows.Controls.Page>, состоит из нескольких фрагментов данных, то может оказаться, что проще \(с меньшим объемом кода\) выполнить инкапсуляцию состояния в отдельный класс и реализацию интерфейса <xref:System.Windows.Navigation.IProvideCustomContentState>.  
  
 Если требуется осуществить переход по различным состояниям одной <xref:System.Windows.Controls.Page>, не переходя с самой <xref:System.Windows.Controls.Page>, можно использовать <xref:System.Windows.Navigation.IProvideCustomContentState> и <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=fullName>.  
  
<a name="Cookies"></a>   
### Файлы Cookie  
 Другой способ, при котором приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] могут сохранять данные — это использование файлов cookie, которые создаются, обновляются и удаляются с помощью методов <xref:System.Windows.Application.SetCookie%2A> и <xref:System.Windows.Application.GetCookie%2A>.  Файлы cookie, которые создаются в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] — это те же cookie, которые используются в других типах веб\-приложений; файлы cookie представляют собой произвольные фрагменты данных, которые сохраняются приложением на клиентском компьютере во время сеанса приложения или на протяжении нескольких сеансов приложения.  Данные файлов cookie обычно представлены в форме пары "имя\=значение" в следующем формате.  
  
 *Имя* `=` *Значение*  
  
 При передаче данных в метод <xref:System.Windows.Application.SetCookie%2A> вместе с <xref:System.Uri> расположения, для которого должны быть заданы файлы cookie, файл cookie создается в оперативной памяти и будет доступен только в течение текущего сеанса приложения.  Этот тип файла cookie называют *файлом cookie сеанса*.  
  
 Чтобы сохранить файл cookie на протяжении нескольких сеансов приложения, необходимо добавить в файл cookie дату окончания срока действия, используя следующий формат.  
  
 *ИМЯ* `=` *ЗНАЧЕНИЕ* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`  
  
 Файл cookie с датой окончания срока действия хранится в текущей папке временных файлов Интернета для установки [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], пока не истечет срок действия cookie.  Такой файл cookie называется *постоянным файлом cookie*, поскольку он продолжает существовать на протяжении нескольких сеансов приложения.  
  
 Чтобы получить и файл cookie сеанса, и постоянный файл cookie, вызовите метод <xref:System.Windows.Application.GetCookie%2A>, передавая <xref:System.Uri> расположения, где был задан файл cookie с помощью метода <xref:System.Windows.Application.SetCookie%2A>.  
  
 Ниже перечислены некоторые способы, с помощью которых файлы cookie поддерживаются в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
-   Автономные приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] могут создавать файлы cookie и управлять ими.  
  
-   Доступ к файлам cookie, созданным [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], можно получить из браузера.  
  
-   [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] из одного домена могут создавать и совместно использовать файлы cookie.  
  
-   Страницы [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] из одного домена могут создавать и совместно использовать файлы cookie.  
  
-   Файлы cookie отправляются, когда [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и свободные страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] выполняют веб\-запросы.  
  
-   Как [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] верхнего уровня, так и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], помещенные в IFRAMES, могут получить доступ к файлам cookie.  
  
-   Поддержка файлов cookie в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] одинакова для всех поддерживаемых браузеров.  
  
-   В [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] политика P3P, которая относятся к файлам cookie, соблюдается системой [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], особенно по отношению к [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] Майкрософт и сторонних поставщиков.  
  
<a name="Structured_Navigation"></a>   
### Структурная навигация  
 Если требуется передать данные из одного объекта <xref:System.Windows.Controls.Page> в другой, можно передать данные в качестве аргументов не используемого по умолчанию конструктора класса <xref:System.Windows.Controls.Page>.  Обратите внимание, что если используется этот способ, то необходимо поддерживать <xref:System.Windows.Controls.Page> в активном состоянии; если же нет, то при следующем переходе к <xref:System.Windows.Controls.Page> [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] повторно создаст экземпляр <xref:System.Windows.Controls.Page> с помощью конструктора по умолчанию.  
  
 <xref:System.Windows.Controls.Page> может также реализовать свойства, задаваемые данными, которые необходимо передать.  Однако все усложняется, когда объекту <xref:System.Windows.Controls.Page> необходимо передать данные обратно в объект <xref:System.Windows.Controls.Page>, из которого выполнен переход.  Проблема в том, что изначально переходы не поддерживают механизмы, гарантирующие, что объект <xref:System.Windows.Controls.Page> осуществит возврат после перехода из него.  По существу, переходы не поддерживают семантику вызова\/возврата.  Чтобы решить эту проблему, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет класс <xref:System.Windows.Navigation.PageFunction%601>, с помощью которого можно обеспечить возврат <xref:System.Windows.Controls.Page> в прогнозируемом и структурированном виде.  Дополнительные сведения см. в разделе [Общие сведения о структурной навигации](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  
  
<a name="The_NavigationWindow_Class"></a>   
## Класс NavigationWindow  
 К этому моменту мы рассмотрели целый ряд служб переходов, которые с наибольшей вероятностью будут использоваться для построения приложений с содержимым, допускающим переходы.  Эти службы обсуждались в контексте [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], хотя они не ограничиваются [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Современные операционные системы и приложения [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] используют опыт работы современных пользователей с браузерами для включения навигации в стиле браузера в автономные приложения. Вот наиболее распространенные примеры.  
  
-   **Тезаурус**: переход по вариантам слов.  
  
-   **Обозреватель файлов**: переход по файлам и папкам.  
  
-   **Мастеры**: разбиение сложной задачи на несколько страниц, которые имеют переходы между собой.  В качестве примера можно привести мастер компонентов Windows, который обрабатывает добавление и удаление свойств [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Чтобы совершать переходы в стиле браузера в автономных приложениях, можно использовать класс <xref:System.Windows.Navigation.NavigationWindow>.  Объект <xref:System.Windows.Navigation.NavigationWindow> является производным от объекта <xref:System.Windows.Window> и расширяет его такой же поддержкой навигации, которую предоставляют приложения [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Объект <xref:System.Windows.Navigation.NavigationWindow> можно использовать как главное окно автономного приложения либо как дополнительное окно, например диалоговое окно.  
  
 Для реализации объекта <xref:System.Windows.Navigation.NavigationWindow>, как с классами самого верхнего уровня в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] \(объекты <xref:System.Windows.Window>, <xref:System.Windows.Controls.Page> и т.д.\) используйте комбинацию разметки и программного кода.  Это показано в следующем примере.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
 [!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]  
  
 С помощью этого кода создается объект <xref:System.Windows.Navigation.NavigationWindow>, осуществляющий автоматический переход к <xref:System.Windows.Controls.Page> \(HomePage.XAML\), когда открывается <xref:System.Windows.Navigation.NavigationWindow>.  Если <xref:System.Windows.Navigation.NavigationWindow> является главным окном приложения, можно использовать атрибут `StartupUri` для его запуска.  Это показано в следующем примере разметки.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]  
  
 На следующем рисунке показан объект <xref:System.Windows.Navigation.NavigationWindow> в качестве главного окна автономного приложения.  
  
 ![Главное окно](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure18.png "NavigationOverviewFigure18")  
  
 Как видно из рисунка, <xref:System.Windows.Navigation.NavigationWindow> имеет заголовок, даже если он не задан в коде реализации <xref:System.Windows.Navigation.NavigationWindow> из предыдущего примера.  Заголовок задается с помощью свойства <xref:System.Windows.Controls.Page.WindowTitle%2A>, как показано в следующем коде.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]  
[!code-xml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]  
  
 Задание свойств <xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A> также влияет на <xref:System.Windows.Navigation.NavigationWindow>.  
  
 Обычно вы реализуете собственный объект <xref:System.Windows.Navigation.NavigationWindow>, когда необходимо изменить его поведение или внешний вид.  Если вы этого не сделали, воспользуйтесь командой быстрого вызова.  Если задать [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для <xref:System.Windows.Controls.Page> в качестве <xref:System.Windows.Application.StartupUri%2A> в автономном приложении, то <xref:System.Windows.Application> автоматически создает <xref:System.Windows.Navigation.NavigationWindow> для помещения <xref:System.Windows.Controls.Page>.  В следующем примере разметки показано, как это сделать.  
  
 [!code-xml[IntroToNavNavigationWindowSnippets#AppLaunchPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]  
  
 Если требуется, чтобы дополнительное окно приложения, например диалоговое окно, представляло собой <xref:System.Windows.Navigation.NavigationWindow>, то для его открытия можно использовать код следующего примера.  
  
 [!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
 [!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]  
  
 На следующем рисунке показан результат.  
  
 ![Диалоговое окно](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure19.png "NavigationOverviewFigure19")  
  
 Как видим, <xref:System.Windows.Navigation.NavigationWindow> отображает кнопки **Назад** и **Вперед** в стиле [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], с помощью которых пользователи могут перемещаться по журналу.  Эти кнопки предоставляют пользователям те же возможности, что показаны на следующем рисунке.  
  
 ![Кнопки “Дальше” и “Назад” в NavigationWindow](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure20.png "NavigationOverviewFigure20")  
  
 Если страницы предоставляют собственную поддержку перемещения по журналу и пользовательский интерфейс, то можно скрыть кнопки **Назад** и **Вперед**, отображаемые объектом <xref:System.Windows.Navigation.NavigationWindow>, задав для свойства <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> значение `false`.  
  
 Кроме того, можно использовать поддержку настройки в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для замены [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] самого объекта <xref:System.Windows.Navigation.NavigationWindow>.  
  
<a name="Frame_in_Standalone_Applications"></a>   
## Класс фрейм  
 И браузер, и <xref:System.Windows.Navigation.NavigationWindow> представляют собой окна, предоставляющие содержимое с возможностью переходов.  В некоторых случаях приложения имеют содержимое, которое не обязательно должно размещаться в целом окне.  Такое содержимое помещается внутрь другого содержимого.  С помощью класса <xref:System.Windows.Controls.Frame> можно вставить содержимое, по которому можно переходить, в другое содержимое.  Класс <xref:System.Windows.Controls.Frame> предоставляет такую же поддержку, что и <xref:System.Windows.Navigation.NavigationWindow> и приложения [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
 В следующем примере показано, как добавить <xref:System.Windows.Controls.Frame> в <xref:System.Windows.Controls.Page> декларативно с помощью элемента `Frame`.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]  
  
 Эта разметка задает атрибут `Source` элемента `Frame` с помощью [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] типа "pack" для объекта <xref:System.Windows.Controls.Page>, в который <xref:System.Windows.Controls.Frame> должен перейти сначала.  На следующем рисунке показано [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с <xref:System.Windows.Controls.Page>, где имеется <xref:System.Windows.Controls.Frame>, осуществляющий переходы между несколькими страницами.  
  
 ![Фрейм, осуществивший переход по нескольким страницам](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure5.png "NavigationOverviewFigure5")  
  
 Не обязательно использовать <xref:System.Windows.Controls.Frame> только внутри содержимого <xref:System.Windows.Controls.Page>.  Можно также поместить <xref:System.Windows.Controls.Frame> внутрь содержимого <xref:System.Windows.Window>.  
  
 По умолчанию <xref:System.Windows.Controls.Frame> использует собственный журнал только при отсутствии другого журнала.  Если <xref:System.Windows.Controls.Frame> является частью содержимого, которое размещено внутри класса <xref:System.Windows.Navigation.NavigationWindow> или приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], то элемент управления <xref:System.Windows.Controls.Frame> использует журнал, который принадлежит классу <xref:System.Windows.Navigation.NavigationWindow> или приложению [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Однако иногда требуется, чтобы элемент управления <xref:System.Windows.Controls.Frame> вел свой собственный журнал.  Одной из причин для этого является необходимость разрешения переходов в журнале по страницам, которые размещены объектом <xref:System.Windows.Controls.Frame>.  Это показано на следующем рисунке.  
  
 ![Схема фрейма и страницы](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure7.png "NavigationOverviewFigure7")  
  
 В этом случае можно настроить <xref:System.Windows.Controls.Frame> на использование собственного журнала путем задания для свойства <xref:System.Windows.Controls.Frame.JournalOwnership%2A> объекта <xref:System.Windows.Controls.Frame> значения <xref:System.Windows.Navigation.JournalOwnership>.  Это показано в следующем примере разметки.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]  
  
 На следующем рисунке показано влияние перехода к <xref:System.Windows.Controls.Frame>, где используется собственный журнал.  
  
 ![Фрейм с собственным журналом](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure8.png "NavigationOverviewFigure8")  
  
 Обратите внимание, что записи журнала отображаются с помощью [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] навигации в элементе управления <xref:System.Windows.Controls.Frame>, а не с помощью [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].  
  
> [!NOTE]
>  Если <xref:System.Windows.Controls.Frame> является частью содержимого, помещенного в <xref:System.Windows.Window>, то <xref:System.Windows.Controls.Frame> использует собственный журнал и, следовательно, отображает собственный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перехода.  
  
 Если вам требуется, чтобы <xref:System.Windows.Controls.Frame> предоставил собственный журнал без отображения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перехода, то можно скрыть [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] перехода, задав для свойства <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> значение <xref:System.Windows.Visibility>.  Это показано в следующем примере разметки.  
  
 [!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]  
[!code-xml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]  
  
<a name="Navigation_Hosts"></a>   
## узлы переходов  
 <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> являются классами, которые называются узлами переходов.  *узел переходов* — это класс, который может осуществить переход к содержимому и отобразить его.  Для этого в каждом узле переходов используется собственная служба <xref:System.Windows.Navigation.NavigationService> и журнал.  Основная структура узла переходов показана на следующем рисунке.  
  
 ![Схемы перехода](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure15.png "NavigationOverviewFigure15")  
  
 По существу, это позволяет <xref:System.Windows.Navigation.NavigationWindow> и <xref:System.Windows.Controls.Frame> обеспечить такую же поддержку переходов, какую [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] предоставляет при размещении в браузере.  
  
 Помимо использования <xref:System.Windows.Navigation.NavigationService> и журнала, узлы переходов реализуют те же члены, что и <xref:System.Windows.Navigation.NavigationService>.  Это показано на следующем рисунке.  
  
 ![Журнал во фрейме и в NavigationWindow](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure24.png "NaivgationOverviewFigure24")  
  
 Это позволяет программировать поддержку переходов непосредственно с ними.  Это можно использовать, если необходимо обеспечить [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] навигации для элемента управления <xref:System.Windows.Controls.Frame>, размещенного в <xref:System.Windows.Window>. Кроме того, оба типа реализуют дополнительные, связанные с навигацией члены, включая `BackStack` \(<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=fullName>\) и `ForwardStack` \(<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=fullName>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=fullName>\), которые позволяют перебирать записи журнала в стеке "Назад" и стеке "Вперед" соответственно.  
  
 Как упоминалось ранее, в приложении может существовать более одного журнала.  На следующем рисунке показан пример, когда это может произойти.  
  
 ![Несколько журналов в одном приложении](../../../../docs/framework/wpf/app-development/media/naivgationoverviewfigure25.png "NaivgationOverviewFigure25")  
  
<a name="Navigating_to_Content_Other_than_Pages"></a>   
## Переход к содержимому, отличному от страниц XAML  
 В этом разделе на примере <xref:System.Windows.Controls.Page> и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] типа "pack" демонстрировались различные возможности переходов в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Однако <xref:System.Windows.Controls.Page>, скомпилированный в приложение, не является единственным типом содержимого, к которому можно осуществить переход, и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] типа "pack" не является единственным способом определения содержимого.  
  
 Как показано в этом разделе, можно также осуществлять переходы к свободным файлам [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], файлам [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] и объектам.  
  
<a name="Navigating_to_Loose_XAML_Files"></a>   
### Переход к свободным файлам XAML  
 Свободный файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — это файл со следующими характеристиками:  
  
-   Содержит только [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(то есть не код\).  
  
-   Имеет объявление соответствующего пространства имен.  
  
-   Имя файла имеет расширение XAML.  
  
 Например, рассмотрим следующее содержимое, сохраненное как свободный файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] — Person.xaml.  
  
 [!code-xml[NavigationOverviewSnippets#LooseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]  
  
 Если дважды щелкнуть файл, браузер откроется, выполнит переход к содержимому и отобразит его.  Это показано на следующем рисунке.  
  
 ![Отображение содержимого в файле Person.XAML](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure21.png "NavigationOverviewFigure21")  
  
 Свободный файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно отобразить из одного из следующих источников:  
  
-   Веб\-узел на локальном компьютере, в интрасети или Интернете.  
  
-   Общая папка [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)].  
  
-   Локальный диск.  
  
 Свободный файл [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] можно добавить в избранные ссылки браузера или сделать домашней страницей браузера.  
  
> [!NOTE]
>  Дополнительные сведения о публикации и запуске свободных страниц [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] см. в разделе [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
 Единственным ограничением в отношении свободных файлов [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] является возможность размещения только такого содержимого, которое безопасно для запуска в режиме частичного доверия.  Например, `Window` не может быть корневым элементом свободного файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_Frame"></a>   
### Переход по HTML\-файлам с помощью элемента управления Frame  
 Как и следовало ожидать, возможен также переход к [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  Необходимо просто предоставить [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], в котором используется схема HTTP.  Например, следующий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] показывает <xref:System.Windows.Controls.Frame>, осуществляющий переход на страницу [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 [!code-xml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]  
  
 Для перехода к [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] требуются специальные разрешения.  Например, нельзя перейти из приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], запущенного в песочнице с частичным доверием в зоне Интернета. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>   
### Переход по HTML\-файлам с помощью элемента управления WebBrowser  
 Элемент управления <xref:System.Windows.Controls.WebBrowser> поддерживает размещение документов [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], навигацию и взаимодействие скриптов\/управляемого кода.  Подробные сведения об элементе управления <xref:System.Windows.Controls.WebBrowser> см. в разделе <xref:System.Windows.Controls.WebBrowser>.  
  
 Как и в случае с элементом управления <xref:System.Windows.Controls.Frame>, для перехода по страницам [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] с помощью элемента управления <xref:System.Windows.Controls.WebBrowser> требуются особые разрешения.  Например, из приложения с частичным доверием можно перейти только на страницу [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], расположенную на исходном веб\-узле.  Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="Navigating_to_Objects"></a>   
### Переход к пользовательским объектам  
 Если имеются данные, сохраненные в качестве пользовательских объектов, то одним из способов отображения этих данных является создание <xref:System.Windows.Controls.Page> с содержимым, привязанным к таким объектам \(см. раздел [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md)\).  Если не требуется создание всей страницы только для отображения объектов, то можно перейти непосредственно к ним.  
  
 Рассмотрим класс `Person`, реализованный в следующем коде.  
  
 [!code-csharp[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
 [!code-vb[NavigateToObjectSnippets#PersonClassCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]  
  
 Для перехода к нему вызовите метод <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=fullName>, как показано в следующем коде.  
  
 [!code-xml[NavigateToObjectSnippets#PageThatNavsToObject1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]  
[!code-xml[NavigateToObjectSnippets#PageThatNavsToObject2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]  
[!code-xml[NavigateToObjectSnippets#PageThatNavsToObject3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]  
  
 [!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
 [!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]  
  
 На следующем рисунке показан результат.  
  
 ![Страница, осуществляющая переход в класс](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure22.png "NavigationOverviewFigure22")  
  
 Из этого рисунка можно видеть, что ничего полезного не отобразилось.  В действительности отображаемое значение является возвращаемым значением метода `ToString` для объекта **Person**; по умолчанию это единственное значение, которое [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] может использовать для представления объекта.  Можно переопределить метод `ToString` для возврата более значимой информации, хотя она будет по\-прежнему строковым значением.  Одним из способов, который позволяет воспользоваться преимуществами возможностей представления [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], является использование шаблона данных.  Можно реализовать шаблон данных, который [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] свяжет с объектом определенного типа.  В следующем коде показан шаблон данных для объекта `Person`.  
  
 [!code-xml[NavigateToObjectSnippets#DataTemplateMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]  
  
 В данном случае шаблон данных связан с типом `Person` с помощью расширения разметки `x:Type` в атрибуте `DataType`.  Затем шаблон данных осуществляет привязку элементов `TextBlock` \(см. раздел <xref:System.Windows.Controls.TextBlock>\) к свойствам класса `Person`.  На следующем рисунке показан обновленный внешний вид объекта `Person`.  
  
 ![Переход к классу с шаблоном данных](../../../../docs/framework/wpf/app-development/media/navigationoverviewfigure23.png "NavigationOverviewFigure23")  
  
 Преимуществом этого способа является связность, которая обеспечивается возможностью повторного использования шаблона данных для согласованного отображения объектов в любом месте приложения.  
  
 Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
<a name="Security"></a>   
## Безопасность  
 Поддержка переходов в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] осуществлять переходы через Интернет, а также позволяет приложениям размещать стороннее содержимое.  Для защиты приложений и пользователей от опасных изменений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет разнообразные средства безопасности, описанные в разделах [Безопасность](../../../../docs/framework/wpf/security-wpf.md) и [Безопасность частичного доверия в WPF](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
## См. также  
 <xref:System.Windows.Application.SetCookie%2A>   
 <xref:System.Windows.Application.GetCookie%2A>   
 [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Общие сведения о структурной навигации](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md)   
 [Общие сведения о топологии переходов](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/app-development/navigation-how-to-topics.md)   
 [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)