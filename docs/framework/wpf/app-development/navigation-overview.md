---
title: Общие сведения о переходах
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 24b872fcf58db3ef0ef7d04165129804dc46d641
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364285"
---
# <a name="navigation-overview"></a>Общие сведения о переходах

Windows Presentation Foundation (WPF) поддерживает навигацию в стиле браузера, которую можно использовать в приложениях двух типов: автономных приложений [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]и. Чтобы упаковать содержимое для навигации, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Controls.Page> предоставляет класс. Можно осуществлять переход от одного <xref:System.Windows.Controls.Page> к другому декларативно, <xref:System.Windows.Documents.Hyperlink>с помощью или <xref:System.Windows.Navigation.NavigationService>программно с помощью. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует журнал, чтобы запоминать страницы, с которых был осуществлен переход, и чтобы переходить к ним обратно.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], и журнал составляют основу поддержки навигации, предоставляемой. <xref:System.Windows.Navigation.NavigationService> В этом обзоре подробно рассматриваются эти функции, прежде чем будет рассмотрена поддержка расширенной навигации [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , включающая навигацию по свободным файлам, [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] файлам и объектам.

> [!NOTE]
> В этом разделе термин "браузер" относится только к браузерам, которые могут размещать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, которые в настоящее [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] время входят в состав и Firefox. Если конкретные [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] функции поддерживаются только определенным браузером, то ссылка на версию обозревателя называется.

## <a name="navigation-in-wpf-applications"></a>Переходы в приложениях WPF

В этом разделе приводится обзор основных возможностей навигации в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Эти возможности доступны как для автономных приложений, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]так и для них, хотя в этом разделе они представлены [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]в контексте.

> [!NOTE]
> В этом разделе не рассматривается построение и развертывание [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Дополнительные сведения о см [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. в разделе [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md).

В этом разделе объясняются и демонстрируются следующие аспекты переходов.

- [Реализация страницы](#CreatingAXAMLPage)

- [Настройка начальной страницы](#Configuring_a_Start_Page)

- [Настройка заголовка, ширины и высоты основного окна](#ConfiguringAXAMLPage)

- [Переход по гиперссылке](#NavigatingBetweenXAMLPages)

- [Переход к фрагменту](#FragmentNavigation)

- [Служба переходов](#NavigationService)

- [Программный переход с помощью службы переходов](#Programmatic_Navigation_with_the_Navigation_Service)

- [Время существования перехода](#Navigation_Lifetime)

- [Запоминание перехода в журнале](#NavigationHistory)

- [Время существования страницы и журнал](#PageLifetime)

- [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory)

- [Файлы "cookie"](#Cookies)

- [Структурная навигация](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>Реализация страницы

В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]можно переходить к нескольким типам содержимого, которые включают .NET Framework объекты, пользовательские объекты, значения перечисления, пользовательские элементы управления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , файлы и [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] файлы. Однако вы обнаружите, что наиболее распространенным и удобным способом упаковки содержимого является использование <xref:System.Windows.Controls.Page>. Кроме того <xref:System.Windows.Controls.Page> , реализует функции, связанные с навигацией, для улучшения их внешнего вида и упрощения разработки.

С <xref:System.Windows.Controls.Page>помощью можно декларативно реализовать [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страницу навигации с содержимым с помощью разметки, как в следующем примере.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

Объект <xref:System.Windows.Controls.Page> , реализованный в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке, имеет `Page` как корневой элемент [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и требует [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] объявления пространства имен. `Page` Элемент содержит содержимое, к которому необходимо перейти и отобразить. Содержимое добавляется путем установки `Page.Content` элемента свойства, как показано в следующей разметке.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content` может содержать только один дочерний элемент; как предложено в предыдущем примере, содержимым является отдельная строка "Hello, Page!". На практике элемент управления макета обычно используется как дочерний элемент (см. [Макет](../advanced/layout.md)) для хранения и составления содержимого.

Дочерние элементы `Page` элемента считаются содержимым <xref:System.Windows.Controls.Page> и, следовательно, не нужно использовать явное `Page.Content` объявление. Следующая разметка является декларативным эквивалентом предыдущего примера.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

В этом случае `Page.Content` автоматически задается дочерними элементами `Page` элемента. Дополнительные сведения см. в разделе [Модель содержимого WPF](../controls/wpf-content-model.md).

Только <xref:System.Windows.Controls.Page> разметка полезна для отображения содержимого. <xref:System.Windows.Controls.Page> Однако может также отображать элементы управления, позволяющие пользователям взаимодействовать со страницей, и может реагировать на взаимодействие с пользователем, обрабатывая события и вызывая логику приложения. Интерактивный <xref:System.Windows.Controls.Page> объект реализуется с помощью сочетания разметки и кода программной части, как показано в следующем примере.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

Чтобы разрешить совместную работу файла разметки и файла кода программной части, требуется следующая конфигурация.

- В разметке `Page` элемент должен `x:Class` включать атрибут. При сборке приложения существование `x:Class` в файле разметки вызывает [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] создание `partial` класса, производного от <xref:System.Windows.Controls.Page> , и имеет имя, заданное `x:Class` атрибутом. Для этого требуется добавить [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] объявление пространства имен для `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`схемы() [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . Созданный `partial` класс реализует `InitializeComponent`метод, который вызывается для регистрации событий и задания свойств, реализованных в разметке.

- В коде программной части класс должен быть `partial` классом с тем же именем, который указан `x:Class` атрибутом в разметке и должен быть производным от <xref:System.Windows.Controls.Page>класса. Это позволяет связать файл кода программной части с `partial` классом, созданным для файла разметки при сборке приложения (см. раздел [Создание приложения WPF](building-a-wpf-application-wpf.md)).

- В коде программной части <xref:System.Windows.Controls.Page> класс должен реализовывать конструктор, который `InitializeComponent` вызывает метод. `InitializeComponent`реализуется созданным `partial` классом файла разметки для регистрации событий и задания свойств, определенных в разметке.

> [!NOTE]
> При добавлении нового <xref:System.Windows.Controls.Page> в проект с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] <xref:System.Windows.Controls.Page> служб он реализуется с помощью разметки и кода программной части и включает необходимую конфигурацию для создания связи между файлами разметки и файлов кода программной части в виде описано здесь.

<xref:System.Windows.Controls.Page>После получения можно переходить к нему. Чтобы указать первый <xref:System.Windows.Controls.Page> , к которому приложение переходит, необходимо настроить запуск <xref:System.Windows.Controls.Page>.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>Настройка начальной страницы

Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] требуется определенная инфраструктура приложений, размещенных в браузере. В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]класс является частью определения приложения, которое устанавливает необходимую инфраструктуру приложений (см. [Обзор управления приложениями](application-management-overview.md)). <xref:System.Windows.Application>

Определение приложения обычно реализуется с помощью разметки и кода программной части с файлом разметки, настроенным [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] в качестве `ApplicationDefinition` элемента. Ниже приведено определение приложения для [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

Может использовать определение приложения для указания запуска <xref:System.Windows.Controls.Page>, который <xref:System.Windows.Controls.Page> автоматически загружается при [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] запуске. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Это можно сделать, задав <xref:System.Windows.Application.StartupUri%2A> для свойства значение [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] для требуемого <xref:System.Windows.Controls.Page>значения.

> [!NOTE]
> В большинстве случаев объект <xref:System.Windows.Controls.Page> либо компилируется в приложение, либо развертывается вместе с ним. В [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] этих случаях объект, <xref:System.Windows.Controls.Page> определяющий, является [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] пакетом [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], который соответствует схеме *Pack* . Пакет [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] обсуждается далее в [URI типа "Pack" в WPF](pack-uris-in-wpf.md). Для перехода к содержимому можно также использовать схему HTTP, которая рассматривается далее.

Можно задать <xref:System.Windows.Application.StartupUri%2A> декларативно в разметке, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

В этом примере `StartupUri` атрибут задается с относительным Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , идентифицирующим Homepage. XAML. [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] При запуске Homepage. XAML автоматически переходит на страницу и отображает ее. Это продемонстрировано на следующем рисунке, который показывает [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , что был запущен с веб-сервера.

![Страница XBAP](./media/navigation-overview/xbap-launched-from-a-web-server.png "Это показывает, что XBAP запускается с веб-сервера.")

> [!NOTE]
> Дополнительные сведения о разработке и развертывании [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]см. в разделе [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md) и развертывании [приложения WPF](deploying-a-wpf-application-wpf.md).

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>Настройка заголовка, ширины и высоты основного окна

Первое, что вы могли заметить на предыдущем рисунке, заключается в том, что заголовок как в браузере, так и на панели [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] вкладок является [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]для. Заголовок не только длинный, но также не является ни привлекательным, ни информативным. По этой причине <xref:System.Windows.Controls.Page> предлагает способ изменить заголовок, <xref:System.Windows.Controls.Page.WindowTitle%2A> задав свойство. Кроме того, можно настроить ширину и высоту окна браузера, установив <xref:System.Windows.Controls.Page.WindowWidth%2A> и <xref:System.Windows.Controls.Page.WindowHeight%2A>соответственно.

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> и<xref:System.Windows.Controls.Page.WindowHeight%2A> могут быть заданы декларативно в разметке, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

Результат показан на примере ниже.

![Заголовок окна, высота, ширина](./media/navigation-overview/window-title-width-height.png "Отображается заголовок, высота и ширина окна, которые можно настроить.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>Переход по гиперссылке

Обычно [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] состоит из нескольких страниц. Самый простой способ перехода с одной страницы на другой — использовать <xref:System.Windows.Documents.Hyperlink>. Можно декларативно добавить <xref:System.Windows.Documents.Hyperlink> в объект <xref:System.Windows.Controls.Page> , используя `Hyperlink` элемент, который показан в следующей разметке.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

Для `Hyperlink` элемента требуется следующее:

- Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] `NavigateUri` для перехода в, указанный атрибутом. <xref:System.Windows.Controls.Page>

- Содержимое, которое пользователь может щелкнуть для инициации навигации, например текст и изображения (для содержимого, которое `Hyperlink` может содержать элемент, см. раздел <xref:System.Windows.Documents.Hyperlink>).

На следующем рисунке показан объект [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Controls.Page> с, у которого есть <xref:System.Windows.Documents.Hyperlink>.

![Страница с гиперссылкой](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "Это показывает XBAP со страницей с гиперссылкой.")

Как и следовало бы ожидания, <xref:System.Windows.Documents.Hyperlink> Нажатие [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] кнопки вызывает переход к <xref:System.Windows.Controls.Page> объекту, определяемому `NavigateUri` атрибутом. Кроме того, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] добавляет запись для предыдущего <xref:System.Windows.Controls.Page> списка последних страниц в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Это показано на следующем рисунке.

![Кнопки назад и вперед](./media/navigation-overview/back-and-forward-navigation.png "Переход с помощью кнопок назад и вперед.")

А также поддержка переходов от одного <xref:System.Windows.Controls.Page> к другому, <xref:System.Windows.Documents.Hyperlink> также поддерживает навигацию по фрагментам.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>Переход к фрагменту

*Навигация* по фрагментам — это переход к фрагменту содержимого в текущем <xref:System.Windows.Controls.Page> или другом <xref:System.Windows.Controls.Page>. В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]фрагмент содержимого — это содержимое, содержащееся в именованном элементе. Именованный элемент — это элемент с `Name` установленным атрибутом. В следующей разметке показан `TextBlock` именованный элемент, содержащий фрагмент содержимого.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

Для перехода к фрагменту `NavigateUri` содержимого атрибут должен включать следующее: <xref:System.Windows.Documents.Hyperlink>

- Объект [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]сфрагментом содержимого,ккоторомунеобходимовыполнитьпереход.<xref:System.Windows.Controls.Page>

- Символ "#".

- Имя элемента <xref:System.Windows.Controls.Page> , содержащего фрагмент содержимого.

Фрагмент [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] имеет следующий формат.

*URI_страницы* `#` *имя_элемента*.

Ниже приведен пример `Hyperlink` , который настроен для перехода к фрагменту содержимого.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> В этом разделе описывается реализация навигации по умолчанию [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]фрагмента в. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]также позволяет реализовать собственную схему навигации по фрагментам, которая, в свою часть, требует обработки <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> события.

> [!IMPORTANT]
> Можно перейти к фрагментам на свободной [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] странице (файлы только [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки с `Page` корневым элементом), только если страницы можно просматривать с помощью [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)].
>
> Однако свободная [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страница может переходить к собственным фрагментам.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>Служба переходов

Хотя <xref:System.Windows.Documents.Hyperlink> позволяет пользователю инициировать навигацию по конкретному <xref:System.Windows.Controls.Page>, работа по поиску и скачиванию <xref:System.Windows.Navigation.NavigationService> страницы выполняется классом. По сути <xref:System.Windows.Navigation.NavigationService> , предоставляет возможность обработки запроса навигации от имени клиентского кода, например. <xref:System.Windows.Documents.Hyperlink> Кроме того <xref:System.Windows.Navigation.NavigationService> , реализует поддержку более высокого уровня для отслеживания и влияния на запрос навигации.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Page> При нажатии вызывается метод для нахождение и скачивания в указанном пакете [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. <xref:System.Windows.Documents.Hyperlink> Загруженный <xref:System.Windows.Controls.Page> файл преобразуется в дерево объектов, корневой объект которых является экземпляром скачанного <xref:System.Windows.Controls.Page>. Ссылка на корневой <xref:System.Windows.Controls.Page> объект хранится <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> в свойстве. Пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для содержимого, к которому осуществлялся переход, хранится <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> в свойстве, а в <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> хранится пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для последней страницы, к которой был выполнен переход.

> [!NOTE]
> В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложении может быть несколько активных <xref:System.Windows.Navigation.NavigationService>в настоящий момент. Дополнительные сведения см. в подразделе [узлы навигации](#Navigation_Hosts) далее в этой статье.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>Программный переход с помощью службы переходов

Вам не нужно знать о том <xref:System.Windows.Navigation.NavigationService> , реализована ли Навигация декларативно в разметке <xref:System.Windows.Documents.Hyperlink> с помощью <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Documents.Hyperlink>, поскольку использует от вашего имени. Это означает, что, если прямой или непрямой родительский элемент a <xref:System.Windows.Documents.Hyperlink> является узлом навигации (см. раздел [навигационные узлы](#Navigation_Hosts)) <xref:System.Windows.Documents.Hyperlink> , сможет найти и использовать службу навигации узла навигации для обработки запроса навигации.

Однако существуют ситуации, когда необходимо использовать <xref:System.Windows.Navigation.NavigationService> напрямую, включая следующие.

- Если необходимо создать экземпляр <xref:System.Windows.Controls.Page> с использованием конструктора без параметров.

- Если необходимо задать свойства для, <xref:System.Windows.Controls.Page> прежде чем переходить к нему.

- Если нужно выполнить переход к ,можноопределитьтолькововремявыполнения.<xref:System.Windows.Controls.Page>

В таких ситуациях необходимо написать код для программной инициации навигации путем вызова <xref:System.Windows.Navigation.NavigationService.Navigate%2A> метода <xref:System.Windows.Navigation.NavigationService> объекта. Для этого требуется получить ссылку на <xref:System.Windows.Navigation.NavigationService>.

#### <a name="getting-a-reference-to-the-navigationservice"></a>Получение ссылки на службу переходов

По причинам, описанным в разделе [узлы навигации](#Navigation_Hosts) , [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложение может иметь более одного <xref:System.Windows.Navigation.NavigationService>. Это означает, что вашему коду нужен способ поиска <xref:System.Windows.Navigation.NavigationService>, который <xref:System.Windows.Navigation.NavigationService> обычно используется для перехода к текущему <xref:System.Windows.Controls.Page>. Чтобы получить ссылку на <xref:System.Windows.Navigation.NavigationService> , можно `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> вызвать метод. Чтобы получить объект <xref:System.Windows.Navigation.NavigationService> , который переходит к определенному <xref:System.Windows.Controls.Page>объекту, в <xref:System.Windows.Controls.Page> качестве аргумента <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> метода передается ссылка. В следующем коде показано, <xref:System.Windows.Navigation.NavigationService> как получить для текущего. <xref:System.Windows.Controls.Page>

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

В качестве ярлыка для поиска <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page>для, <xref:System.Windows.Controls.Page> реализует <xref:System.Windows.Controls.Page.NavigationService%2A> свойство. Эти действия показаны в следующем примере.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> При <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService> вызове<xref:System.Windows.FrameworkElement.Loaded> события может получиться только ссылка на него. <xref:System.Windows.Controls.Page>

#### <a name="programmatic-navigation-to-a-page-object"></a>Программный переход к объекту страницы

В следующем примере показано, <xref:System.Windows.Navigation.NavigationService> как использовать для программного перехода <xref:System.Windows.Controls.Page>к. Программная Навигация необходима, так <xref:System.Windows.Controls.Page> как для перехода к которому можно создать экземпляр только с помощью одного конструктора без параметров. Объект <xref:System.Windows.Controls.Page> с конструктором без параметров показан в следующей разметке и коде.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

Объект <xref:System.Windows.Controls.Page> , который переходит к элементу <xref:System.Windows.Controls.Page> с конструктором без параметров, показан в следующей разметке и коде.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

При нажатии кнопки переход <xref:System.Windows.Controls.Page> инициируется путем создания экземпляра компонента для перехода к использованию конструктора <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> без параметров и вызова метода. <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A>принимает ссылку на объект, к которому <xref:System.Windows.Navigation.NavigationService> будет переходить, а не к пакету. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Программный переход с URI типа pack

Если необходимо создать пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] программным способом (например, если вы можете определить только пакет [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] во время выполнения) <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> , можно использовать метод. Эти действия показаны в следующем примере.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>Обновление текущей страницы

Не загружается, если он имеет тот же [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] пакет, что [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] и пакет, хранящийся <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> в свойстве. <xref:System.Windows.Controls.Page> Чтобы принудительно [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] скачать текущую страницу еще раз, можно <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> вызвать метод, как показано в следующем примере.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>Время существования перехода

Как вы уже видели, существует множество способов инициации перехода. При инициации навигации и при выполнении навигации можно отслеживать и повлиять на навигацию с помощью следующих событий, реализуемых <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. Появляется, когда запрошен новый переход. Можно использовать для отмены перехода.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. Происходит периодически во время загрузки, тем самым предоставляя информацию о ходе процесса навигации.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. Появляется, когда страница найдена и загружена.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. Происходит при остановке навигации (путем вызова <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>) или при запросе новой навигации во время выполнения текущей навигации.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. Появляется при возникновении ошибки во время перехода к запрошенному содержимому.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. Появляется, когда содержимое, к которому был осуществлен переход, загружено и проанализировано и начинается его отрисовка.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. Появляется в начале перехода к фрагменту содержимого, который происходит:

  - немедленно, если нужный фрагмент находится в текущем содержимом;

  - после загрузки исходного содержимого, если нужный фрагмент находится в другом содержимом.

События перехода вызываются в порядке, который показан на следующем рисунке.

![Блок-схема навигации] по страницам (./media/navigation-overview/order-of-navigation-events.png "Блок-схема событий навигации") по страницам

Как правило, это <xref:System.Windows.Controls.Page> не касается этих событий. Более вероятно, что приложение связано с ними, и по этой причине эти события также вызываются <xref:System.Windows.Application> классом:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

Каждый раз <xref:System.Windows.Navigation.NavigationService> при вызове события <xref:System.Windows.Application> класс вызывает соответствующее событие. <xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationWindow> предлагают те же события для обнаружения переходов в соответствующих областях.

В некоторых случаях <xref:System.Windows.Controls.Page> может заинтересовать эти события. Например, <xref:System.Windows.Controls.Page> может <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> обработано событие, чтобы определить, следует ли отменить переход от самого себя. Эти действия показаны в следующем примере.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

При регистрации обработчика с событием навигации из <xref:System.Windows.Controls.Page>, как в предыдущем примере, необходимо также отменить регистрацию обработчика событий. В противном случае могут возникнуть побочные эффекты в отношении того, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] как Навигация запоминает <xref:System.Windows.Controls.Page> навигацию с помощью журнала.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>Запоминание перехода в журнале

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] использует два стека для запоминания страниц, с которых был осуществлен переход: стек "Назад" и стек "Вперед". При переходе <xref:System.Windows.Controls.Page> от текущего объекта к новому <xref:System.Windows.Controls.Page> или пересылке к существующему <xref:System.Windows.Controls.Page>объекту, текущий <xref:System.Windows.Controls.Page> добавляется в *стек назад*. При переходе от текущего <xref:System.Windows.Controls.Page> момента к предыдущему <xref:System.Windows.Controls.Page>, текущее <xref:System.Windows.Controls.Page> значение добавляется в *стек вперед*. Стек "Назад", стек "Вперед" и функциональные возможности для управления ими в совокупности называются журналом. Каждый элемент в стеке заднего и прямого стека является экземпляром <xref:System.Windows.Navigation.JournalEntry> класса и называется записью в *журнале*.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Перемещение по журналу в браузере Internet Explorer

По сути, журнал работает так же, как кнопки [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] **назад** и **вперед** . Это показано на следующем рисунке.

![Кнопки назад и вперед](./media/navigation-overview/back-and-forward-navigation.png "Переход с помощью кнопок назад и вперед.")

Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] размещенных в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], интегрируетжурналв[!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]навигацию по. Это позволяет пользователям перемещаться по страницам [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] в с помощью кнопок **назад**, **вперед**и **Последние страницы** в [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]. Журнал не интегрирован [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] в в точно так же, как для [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] или Internet Explorer 8. Вместо этого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]отрисовывает замещающую навигацию. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]

> [!IMPORTANT]
> В [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]при переходе пользователя из режима и обратно [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]в в журнал сохраняются только записи журнала для страниц, которые не были сохранены в активном состоянии. Сведения о сохранении страниц в активном состоянии см. в разделе [время существования страницы и журнал](#PageLifetime) далее в этой статье.

<xref:System.Windows.Controls.Page> По умолчанию текст для каждого, отображаемый в [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] списке **последние** [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] страницы, — для <xref:System.Windows.Controls.Page>. В большинстве случаев это не особенно важно для пользователя. К счастью можно изменить текст, используя следующие параметры.

1. Значение присоединенного `JournalEntry.Name` атрибута.

2. Значение `Page.Title` атрибута.

3. Значение атрибута и для текущего <xref:System.Windows.Controls.Page>. [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] `Page.WindowTitle`

4. Интерфейс [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] для текущего объекта <xref:System.Windows.Controls.Page>. (Значение по умолчанию)

Порядок, в котором перечислены параметры, совпадает с порядком приоритета для поиска текста. Например, если `JournalEntry.Name` задано значение, другие значения игнорируются.

В следующем примере `Page.Title` атрибут используется для изменения текста, отображаемого для записи журнала.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>Перемещение по журналу с помощью WPF

Хотя пользователь может перемещаться по журналу с помощью **страниц** [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]« **назад**», « **вперед**» и «последние», можно также перемещаться по журналу [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]с помощью декларативных и программных механизмов, предоставляемых. Одной из причин для этого является предоставление настраиваемых переходов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] на страницах.

Можно декларативно добавить поддержку навигации по журналам с помощью команд навигации, <xref:System.Windows.Input.NavigationCommands>предоставляемых. В следующем примере показано, `BrowseBack` как использовать команду навигации.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

Можно программно перемещаться по журналу с помощью одного из следующих членов <xref:System.Windows.Navigation.NavigationService> класса:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

Журнал также можно манипулировать программно, как описано в статье [Сохранение состояния содержимого с помощью журнала переходов](#RetainingContentStateWithNavigationHistory) далее в этом разделе.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>Время существования страницы и журнал

[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Рассмотрим несколько страниц, содержащих обширное содержимое, включая графику, анимацию и мультимедиа. Объем памяти для подобных страниц может быть довольно большим, особенно если используются видеоматериалы и звуковые файлы. Учитывая, что журнал "запоминает" страницы, к которым перешел переход, [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] может быстро использовать большой и заметный объем памяти.

По этой причине поведение журнала по умолчанию заключается в хранении <xref:System.Windows.Controls.Page> метаданных в каждой записи журнала, а не в ссылке <xref:System.Windows.Controls.Page> на объект. При переходе к записи журнала ее <xref:System.Windows.Controls.Page> метаданные используются для создания нового экземпляра указанного <xref:System.Windows.Controls.Page>объекта. Как следствие, каждый <xref:System.Windows.Controls.Page> , к которому осуществляется переход, имеет время существования, показанное на следующем рисунке.

![Время существования страницы](./media/navigation-overview/navigated-page-lifetime.png "Это показывает время существования перехода на страницу.")

Несмотря на то, что использование поведения ведения журнала по умолчанию может сэкономить на потреблении памяти, производительность отрисовки на странице может снизиться; При повторном создании <xref:System.Windows.Controls.Page> экземпляра может потребоваться много времени, особенно если у него много содержимого. Если необходимо хранить <xref:System.Windows.Controls.Page> экземпляр в журнале, можно нарисовать два метода для этого. Во-первых, можно программным путем <xref:System.Windows.Controls.Page> выполнить переход к объекту <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> , вызвав метод.

Во-вторых, можно указать [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , чтобы хранить экземпляр <xref:System.Windows.Controls.Page> в журнале, задав <xref:System.Windows.Controls.Page.KeepAlive%2A> для `true` свойства значение (значение по умолчанию — `false`). Как показано в следующем примере, можно задать <xref:System.Windows.Controls.Page.KeepAlive%2A> декларативно в разметке.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

Время существования объекта <xref:System.Windows.Controls.Page> , который хранится в активном состоянии, незначительно отличается от того, который не является. При первом <xref:System.Windows.Controls.Page> переходе к объекту, который хранится в активном состоянии, он создается так же, как <xref:System.Windows.Controls.Page> и объект, который не поддерживается в активном состоянии. Однако, поскольку экземпляр класса <xref:System.Windows.Controls.Page> хранится в журнале, он никогда не создается повторно в течение времени, пока он остается в журнале. Следовательно, если <xref:System.Windows.Controls.Page> имеется логика инициализации, которая должна вызываться при каждом <xref:System.Windows.Controls.Page> переходе к, необходимо переместить его из конструктора <xref:System.Windows.FrameworkElement.Loaded> в обработчик события. Как показано на следующем рисунке, <xref:System.Windows.FrameworkElement.Loaded> события и <xref:System.Windows.FrameworkElement.Unloaded> <xref:System.Windows.Controls.Page> по-прежнему создаются каждый раз, когда осуществляется переход к и из соответственно.

![При возникновении загруженных и выгруженных событий](./media/navigation-overview/loaded-and-unloaded-events.png "Загруженные и выгруженные события вызываются при переходе на страницу и из нее.")

Если не <xref:System.Windows.Controls.Page> поддерживается в активном состоянии, не следует выполнять одно из следующих действий.

- Сохранять ссылку или любую его часть.

- Регистрировать обработчики событий с событиями, которые не реализованы в объекте.

При выполнении любого из этих действий будут созданы ссылки, <xref:System.Windows.Controls.Page> которые принудительно будут сохранены в памяти даже после удаления из журнала.

Как правило, предпочтительнее использовать <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> поведение по умолчанию, не сохраняя активность. Однако при этом существуют реализации состояния, которые описаны в следующем разделе.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>Сохранение состояния содержимого с помощью журнала переходов

Если объект <xref:System.Windows.Controls.Page> не хранится в активном состоянии и содержит элементы управления, собирающие данные от пользователя, что произойдет с данными, если пользователь отрывается от и обратно? <xref:System.Windows.Controls.Page> С точки зрения пользователя следует ожидать появления ранее введенных данных. К сожалению, поскольку новый экземпляр класса <xref:System.Windows.Controls.Page> создается с каждой навигацией, элементы управления, которые собирают данные, повторно создают экземпляры, а данные теряются.

К счастью, журнал обеспечивает поддержку для запоминания данных во <xref:System.Windows.Controls.Page> всех переходах, включая управляющие данные. В частности, запись журнала для каждого <xref:System.Windows.Controls.Page> из них выступает в качестве временного контейнера для <xref:System.Windows.Controls.Page> связанного состояния. Следующие шаги показывают, как эта поддержка используется при <xref:System.Windows.Controls.Page> переходе от:

1. Запись для текущего <xref:System.Windows.Controls.Page> объекта добавляется в журнал.

2. Состояние <xref:System.Windows.Controls.Page> объекта хранится в записи журнала для этой страницы, которая добавляется в стек назад.

3. Новый <xref:System.Windows.Controls.Page> переход к.

При переходе <xref:System.Windows.Controls.Page> назад к странице с помощью журнала выполняются следующие действия.

1. Создается <xref:System.Windows.Controls.Page> экземпляр (верхняя запись журнала в стеке сзади).

2. Обновляет состояние, которое было сохранено с записью журнала <xref:System.Windows.Controls.Page>для. <xref:System.Windows.Controls.Page>

3. <xref:System.Windows.Controls.Page> Переходит обратно к.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]автоматически использует эту поддержку при использовании следующих элементов управления в <xref:System.Windows.Controls.Page>:

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

Если компонент использует эти элементы управления, данные, которые они записывают <xref:System.Windows.Controls.Page> в них, запоминаются по  <xref:System.Windows.Controls.ListBox> переходам, как показано на следующем рисунке. <xref:System.Windows.Controls.Page>

![Страница с элементами управления, которые запоминают состояние](./media/navigation-overview/data-remembered-across-page-navigations.png "Указанные данные запоминаются по переходам между страницами.")

Если у <xref:System.Windows.Controls.Page> элемента есть элементы управления, отличные от указанных в приведенном выше списке, или если состояние хранится в пользовательских объектах, необходимо написать код, чтобы журнал запомнил <xref:System.Windows.Controls.Page> состояние в ходе переходов.

Если необходимо запомнить небольшие элементы состояния <xref:System.Windows.Controls.Page> при переходах, можно использовать свойства зависимостей (см <xref:System.Windows.DependencyProperty>.) <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> , настроенные с флагом метаданных.

Если ваше <xref:System.Windows.Controls.Page> состояние, которое необходимо запомнить в переходах, состоит из нескольких фрагментов данных, может оказаться, что для инкапсуляции вашего состояния в один класс и <xref:System.Windows.Navigation.IProvideCustomContentState> реализации интерфейса будет использоваться меньше кода.

Если необходимо перемещаться по различным состояниям <xref:System.Windows.Controls.Page>одного объекта, не переходя <xref:System.Windows.Controls.Page> от самого себя, можно использовать <xref:System.Windows.Navigation.IProvideCustomContentState> и <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>.

<a name="Cookies"></a>

### <a name="cookies"></a>Файлы cookie

Другим способом [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] хранения данных в приложениях являются файлы cookie, которые создаются, обновляются и удаляются с <xref:System.Windows.Application.SetCookie%2A> помощью методов и <xref:System.Windows.Application.GetCookie%2A> . Файлы cookie, которые можно создать в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] , — это те же файлы cookie, которые используются другими типами веб-приложений; файлы cookie — это произвольные фрагменты данных, которые хранятся приложением на клиентском компьютере во время или между сеансами приложения. Данные файлов cookie обычно представлены в форме пары "имя — значение" в следующем формате.

*имя* `=` *значение*

При передаче <xref:System.Windows.Application.SetCookie%2A>данных вместе <xref:System.Uri> с расположением, для которого должен быть задан файл cookie, файл cookie создается в памяти и доступен только в течение текущего сеанса приложения. Этот тип файлов cookie называется *сеансом cookie*.

Чтобы сохранить файл cookie на протяжении нескольких сеансов приложения, необходимо добавить в файл cookie дату окончания срока действия, используя следующий формат.

*имя* `=` *значение* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

Файл cookie с датой окончания срока действия хранится в папке временных файлов [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] текущей установки, пока не истечет срок действия файла cookie. Такой файл cookie называется *постоянным файлом cookie* , так как он сохраняется во всех сеансах приложения.

Вы получаете как сеанс, так и постоянные файлы cookie <xref:System.Windows.Application.GetCookie%2A> , вызывая метод <xref:System.Uri> , передав расположение, где <xref:System.Windows.Application.SetCookie%2A> файл cookie был задан методом.

Ниже приведены некоторые способы поддержки файлов cookie в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]автономные приложения [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] и могут создавать файлы cookie и управлять ими.

- Файлы cookie, созданные [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с помощью, можно получить из браузера.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] из одного домена могут создавать и совместно использовать файлы cookie.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)][!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] страницы из одного и того же домена могут создавать файлы cookie и предоставлять к ним общий доступ.

- Файлы cookie отправляются, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] когда и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] свободные страницы выполняют веб-запросы.

- Как элементы верхнего уровня [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] , [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] так и размещенные в iframe, могут обращаться к файлам cookie.

- Поддержка файлов cookie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в одинакова для всех поддерживаемых браузеров.

- В [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]политика P3P, относящаяся к файлам cookie, учитывается [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]в, особенно в отношении первого и стороннего производителей [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>Структурная навигация

Если необходимо передать данные из одного <xref:System.Windows.Controls.Page> в другой, можно передать данные в качестве аргументов в конструктор <xref:System.Windows.Controls.Page>без параметров. Обратите внимание, что при использовании этого <xref:System.Windows.Controls.Page> метода необходимо поддерживать активность. в противном случае при следующем переходе <xref:System.Windows.Controls.Page>к [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] объекту повторно создает экземпляр <xref:System.Windows.Controls.Page> с помощью конструктора без параметров.

Кроме того, <xref:System.Windows.Controls.Page> можно реализовать свойства, которые устанавливаются с данными, которые необходимо передать. Однако, когда <xref:System.Windows.Controls.Page> нужно передать данные обратно <xref:System.Windows.Controls.Page> в объект, к которому осуществляется переход. Проблема заключается в том, что Навигация изначально не поддерживает механизмы, гарантирующие, <xref:System.Windows.Controls.Page> что будет возвращено значение после перехода от. По существу переходы не поддерживают семантику вызова/возврата. Чтобы решить эту проблему, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <xref:System.Windows.Navigation.PageFunction%601> предоставляет класс, который можно <xref:System.Windows.Controls.Page> использовать, чтобы гарантировать, что компонент возвращается в прогнозируемом и структурированном виде. Дополнительные сведения см. в разделе [Общие сведения о структурной навигации](structured-navigation-overview.md).

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>Класс NavigationWindow

К этому моменту мы рассмотрели целый ряд служб переходов, которые с наибольшей вероятностью будут использоваться для построения приложений с содержимым, допускающим переходы. Эти службы обсуждались в контексте [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], хотя они и не [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]ограничиваются. Современные операционные системы и приложения для Windows используют преимущества браузера современных пользователей, чтобы внедрить навигацию в стиле браузера в автономные приложения. Вот наиболее распространенные примеры.

- **Тезаурус**: Переход по вариантам слов.

- **Обозреватель файлов**: Навигация по файлам и папкам.

- **Мастера**: Разбиение сложной задачи на несколько страниц, между которыми можно перемещаться. Примером является мастер компонентов Windows, который обрабатывает Добавление и удаление компонентов Windows.

Чтобы включить навигацию в стиле браузера в автономные приложения, можно использовать <xref:System.Windows.Navigation.NavigationWindow> класс. <xref:System.Windows.Navigation.NavigationWindow>является производным <xref:System.Windows.Window> от и расширяет его с помощью той же поддержки навигации [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] , которая предоставляет. Можно использовать <xref:System.Windows.Navigation.NavigationWindow> в качестве главного окна автономного приложения или вторичного окна, такого как диалоговое окно.

Для реализации <xref:System.Windows.Navigation.NavigationWindow>, как и в большинстве классов верхнего уровня в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>и т. д.), используется сочетание разметки и кода программной части. Эти действия показаны в следующем примере.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

Этот код создает объект <xref:System.Windows.Navigation.NavigationWindow> , который автоматически переходит <xref:System.Windows.Controls.Page> на страницу (Homepage <xref:System.Windows.Navigation.NavigationWindow> . XAML) при открытии. Если является основным окном приложения, можно `StartupUri` использовать атрибут для его запуска. <xref:System.Windows.Navigation.NavigationWindow> Это показано в следующем примере разметки.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

На следующем рисунке показано в <xref:System.Windows.Navigation.NavigationWindow> качестве главного окна автономного приложения.

![Главное окно](./media/navigation-overview/navigation-window-as-main-window.png "Окно навигации как главное окно")

На рисунке видно, что <xref:System.Windows.Navigation.NavigationWindow> имеет заголовок, даже если он не был задан <xref:System.Windows.Navigation.NavigationWindow> в коде реализации из предыдущего примера. Вместо этого заголовок задается с помощью <xref:System.Windows.Controls.Page.WindowTitle%2A> свойства, которое показано в следующем коде.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

Установка свойств <xref:System.Windows.Controls.Page.WindowHeight%2A> <xref:System.Windows.Navigation.NavigationWindow>и также влияет на. <xref:System.Windows.Controls.Page.WindowWidth%2A>

Обычно вы реализуете свой собственный <xref:System.Windows.Navigation.NavigationWindow> , когда необходимо настроить его поведение или внешний вид. Если вы этого не сделали, можно использовать команду быстрого вызова. Если указать в автономном [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <xref:System.Windows.Controls.Page> <xref:System.Windows.Application.StartupUri%2A> <xref:System.Windows.Application> приложениипакет<xref:System.Windows.Navigation.NavigationWindow> a как, автоматически создает для размещения. <xref:System.Windows.Controls.Page> В следующем примере разметки показано, как это сделать.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

Если требуется <xref:System.Windows.Navigation.NavigationWindow>, чтобы дополнительное окно приложения, такое как диалоговое окно, было, можно использовать код, приведенный в следующем примере, чтобы открыть его.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

На рисунке ниже показан результат.

![Диалоговое окно](./media/navigation-overview/navigation-window-as-dialog-box.png "Окно навигации как диалоговое окно")

<xref:System.Windows.Navigation.NavigationWindow> Как видите, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]отображаются кнопки со стилями **назад** и **вперед** , позволяющие пользователям перемещаться по журналу. Эти кнопки предоставляют пользователям те же возможности, что показаны на следующем рисунке.

![Кнопки назад и вперед в NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "Кнопки назад и вперед в окне навигации")

Если страницы предоставляют собственную поддержку навигации по журналам и пользовательский интерфейс, можно скрыть <xref:System.Windows.Navigation.NavigationWindow> кнопки **назад** и **вперед** , выводимые <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> свойством, задав для `false`свойства значение.

Кроме того, можно использовать поддержку настройки в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] замены <xref:System.Windows.Navigation.NavigationWindow> самого себя.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Класс Frame

Как браузер, так <xref:System.Windows.Navigation.NavigationWindow> и окна, в которых размещается содержимое для навигации. В некоторых случаях приложения имеют содержимое, которое не обязательно должно размещаться в целом окне. Такое содержимое помещается внутрь другого содержимого. Можно вставить содержимое для навигации в другое содержимое с помощью <xref:System.Windows.Controls.Frame> класса. <xref:System.Windows.Controls.Frame>предоставляет такую же поддержку, <xref:System.Windows.Navigation.NavigationWindow> как [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]и.

В следующем примере показано, как добавить <xref:System.Windows.Controls.Frame> <xref:System.Windows.Controls.Page> к `Frame` декларативно с помощью элемента.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

Эта разметка задает `Source` `Frame` атрибуту элемента [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] <xref:System.Windows.Controls.Page>Packдля , который долженизначальнопереходитьк.<xref:System.Windows.Controls.Frame> На следующем рисунке показан объект [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Controls.Page> с, который содержит объект <xref:System.Windows.Controls.Frame> с переходом между несколькими страницами.

![Кадр, перемещенный между несколькими страницами](./media/navigation-overview/frame-navigation-between-multiple-pages.png "Это демонстрирует навигацию по кадрам между несколькими страницами.")

Не нужно использовать <xref:System.Windows.Controls.Frame> только внутри содержимого <xref:System.Windows.Controls.Page>. Также обычно размещается <xref:System.Windows.Controls.Frame> внутри содержимого <xref:System.Windows.Window>.

По умолчанию <xref:System.Windows.Controls.Frame> использует собственный журнал только в отсутствие другого журнала. <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow> [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] <xref:System.Windows.Controls.Frame> [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]Если компонент являетсячастьюсодержимого,размещенноговнутриили,используетжурнал,принадлежащийкили.<xref:System.Windows.Controls.Frame> Однако иногда <xref:System.Windows.Controls.Frame> может потребоваться ответственный за собственный журнал. Одной из причин для этого является разрешение навигации по журналам на страницах, размещенных в <xref:System.Windows.Controls.Frame>. Это показано на следующем рисунке.

![Диаграмма фрейма и страницы](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "Это показывает навигацию по журналам на страницах, размещенных в кадре.")

В этом <xref:System.Windows.Controls.Frame> случае можно настроить для использования собственного журнала, <xref:System.Windows.Controls.Frame.JournalOwnership%2A> задав для <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>свойства объекта значение <xref:System.Windows.Controls.Frame> . Это показано в следующем примере разметки.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

На следующем рисунке показан результат перехода в <xref:System.Windows.Controls.Frame> , который использует собственный журнал.

![Кадр, использующий собственный журнал](./media/navigation-overview/frame-uses-its-own-journal.png "Это показывает результат перехода внутри фрейма, использующего собственный журнал.")

Обратите внимание, что записи журнала отображаются навигацией [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.Frame>в, а [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]не в.

> [!NOTE]
> Если компонент <xref:System.Windows.Window> <xref:System.Windows.Controls.Frame> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]является частью содержимого, размещенного в, использует собственный журнал и, следовательно, отображает собственную навигацию. <xref:System.Windows.Controls.Frame>

Если взаимодействие с пользователем требуется <xref:System.Windows.Controls.Frame> для предоставления собственного журнала без отображения навигации [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], можно скрыть навигацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , задав для <xref:System.Windows.Visibility.Hidden>свойства <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> значение. Это показано в следующем примере разметки.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>Узлы переходов

<xref:System.Windows.Controls.Frame>и <xref:System.Windows.Navigation.NavigationWindow> являются классами, называемыми узлами навигации. *Узел навигации* — это класс, который может перейти к содержимому и отобразить его. Для этого каждый узел навигации использует собственные <xref:System.Windows.Navigation.NavigationService> журналы и. На следующем рисунке показана основная структура узла переходов.

![Диаграммы навигатора](./media/navigation-overview/navigation-host-construction.png "Базовое создание узла навигации")

По сути, это <xref:System.Windows.Navigation.NavigationWindow> позволяет <xref:System.Windows.Controls.Frame> и предоставлять [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] такую же поддержку навигации, которая предоставляется при размещении в браузере.

Помимо использования <xref:System.Windows.Navigation.NavigationService> и журнала, узлы навигации реализуют те же члены, <xref:System.Windows.Navigation.NavigationService> которые реализуют. Это показано на следующем рисунке.

![Журнал в кадре и в NavigationWindow](./media/navigation-overview/navigation-window-and-frame.png "Окно навигации и фрейм")

Это позволяет программировать поддержку переходов непосредственно с ними. Это может быть полезно, если необходимо предоставить пользовательскую навигацию [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.Frame> для <xref:System.Windows.Window>, которая размещена в. Более того, оба типа реализуют дополнительные элементы, связанные с навигацией, <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>включая `BackStack` ( `ForwardStack` <xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>,<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>) <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>и (,), которые позволяют перечислить записи журнала в обратном стек Stack и forward, соответственно.

Как упоминалось ранее, в приложении может существовать несколько журналов. На следующем рисунке показано пример, когда это возможно.

![Несколько журналов в одном приложении](./media/navigation-overview/multiple-journals-in-one-application.png "Это пример более чем одного журнала в приложении.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>Переход к содержимому, отличному от страниц XAML

В этом разделе <xref:System.Windows.Controls.Page> и для демонстрации [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] различных возможностей навигации в этой статье используются функции [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Pack. Однако, компилируемый в приложение, — это не единственный тип содержимого, к которому можно осуществлять переход, а Pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] — не единственный способ определить содержимое. <xref:System.Windows.Controls.Page>

Как показано в этом разделе, можно также переходить к [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] свободным файлам [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] , файлам и объектам.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>Переход к свободным файлам XAML

Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл — это файл со следующими характеристиками:

- Содержит только [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (т. е. без кода).

- имеет объявление соответствующего пространства имен;

- имя файла имеет расширение XAML.

Например, рассмотрим следующее содержимое, которое хранится в виде свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла Person. XAML.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

Если дважды щелкнуть файл, браузер откроется, выполнит переход к содержимому и отобразит его. Это показано на следующем рисунке.

![Отображение содержимого в файле Person. XAML](./media/navigation-overview/contents-of-person-xaml-file.png "Отображает содержимое файла Person. XAML.")

Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл можно вывести из следующих файлов:

- веб-узел на локальном компьютере, в интрасети или Интернете;

- [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] Общая папка.

- локальный диск.

Свободный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл можно добавить в Избранное браузера или на домашнюю страницу браузера.

> [!NOTE]
> Дополнительные сведения о публикации и запуске свободных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] страниц см. в разделе [развертывание приложения WPF](deploying-a-wpf-application-wpf.md).

Единственное ограничение в отношении свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] : можно разместить только содержимое, которое может быть запущено в режиме частичного доверия. Например, `Window` не может быть корневым элементом свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файла. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>Переход к файлам HTML элемента управления Frame

Как вы можете ожидать, можно также переходить по [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]адресу. Необходимо просто предоставить [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] , который использует схему HTTP. Например, ниже [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Frame> показано [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] , что позволяет переходить к странице.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

Для перехода к [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] требуются специальные разрешения. Например, невозможно выполнить переход из [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] , который выполняется в песочнице безопасности частичного доверия в зоне Интернета. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>Переход к файлам HTML с помощью элемента управления WebBrowser

Элемент управления поддерживает [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] размещение документов, навигацию и взаимодействие сценариев и управляемого кода. <xref:System.Windows.Controls.WebBrowser> Подробные сведения об элементе управления <xref:System.Windows.Controls.WebBrowser> см. в <xref:System.Windows.Controls.WebBrowser>разделе.

Как <xref:System.Windows.Controls.Frame>и при переходе [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] к <xref:System.Windows.Controls.WebBrowser> использованию, требуются специальные разрешения. Например, из приложения с частичным доверием можно переходить только в [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] расположение, расположенное на исходном узле. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>Переход к пользовательским объектам

Если данные хранятся в виде пользовательских объектов, то один из способов отобразить эти данные — создать <xref:System.Windows.Controls.Page> с содержимым, привязанным к этим объектам (см. раздел [Общие сведения о привязке данных](../data/data-binding-overview.md)). Если не требуется создание всей страницы только для отображения объектов, то можно перейти непосредственно к ним.

`Person` Рассмотрим класс, реализованный в следующем коде.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

Для перехода к нему вызывается <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> метод, как показано в следующем коде.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

На рисунке ниже показан результат.

![Страница, которая выполняет переход к классу](./media/navigation-overview/page-navigates-to-an-object.png "Это пример страницы, которая выполняет переход к объекту.")

Из этого рисунка можно видеть, что ничего полезного не отобразилось. Фактически отображаемое значение является возвращаемым значением `ToString` метода для объекта **Person** ; по умолчанию это единственное значение, которое [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] может использоваться для представления объекта. Можно переопределить `ToString` метод для возврата более значимой информации, хотя он все равно будет строковым значением. Один из способов, который позволяет использовать преимущества возможностей [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] представления, — использовать шаблон данных. Можно реализовать шаблон данных, который [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] можно связать с объектом определенного типа. В следующем коде показан шаблон данных для `Person` объекта.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

Здесь шаблон данных связан с `Person` типом с `x:Type` помощью расширения разметки в `DataType` атрибуте. Затем шаблон данных привязывает `TextBlock` элементы (см <xref:System.Windows.Controls.TextBlock>.) `Person` к свойствам класса. На следующем рисунке показан обновленный внешний вид `Person` объекта.

![Переход к классу, который содержит шаблон данных](./media/navigation-overview/navigating-to-a-class.png "Переход к классу, который содержит шаблон данных.")

Преимуществом этого способа является связность, которая обеспечивается возможностью повторного использования шаблона данных для согласованного отображения объектов в любом месте приложения.

Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о создании шаблонов данных](../data/data-templating-overview.md).

<a name="Security"></a>

## <a name="security"></a>Безопасность

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]Поддержка навигации позволяет [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] перемещаться по Интернету и позволяет приложениям размещать сторонние материалы. Для защиты приложений и пользователей от вредоносного поведения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет разнообразные функции безопасности, обсуждаемые в разделе [Безопасность](../security-wpf.md) и [Безопасность частичного доверия в WPF](../wpf-partial-trust-security.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [Общие сведения об управлении приложением](application-management-overview.md)
- [URI типа "pack" в WPF](pack-uris-in-wpf.md)
- [Общие сведения о структурной навигации](structured-navigation-overview.md)
- [Общие сведения о топологиях навигации](navigation-topologies-overview.md)
- [Разделы практического руководства](navigation-how-to-topics.md)
- [Развертывание приложений WPF](deploying-a-wpf-application-wpf.md)
