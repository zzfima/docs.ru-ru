---
title: "Общие сведения об окнах WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c176f08904bac8e9c3877977c1e52afb57d5daca
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="wpf-windows-overview"></a>Общие сведения об окнах WPF
Пользователи взаимодействуют с автономными приложениями [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] через окна. Основная цель окна — разместить содержимое, которое визуализирует данные и позволяет пользователям взаимодействовать с ними. Автономный [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений предоставляют свои собственные окна с помощью <xref:System.Windows.Window> класса. В этом разделе описываются <xref:System.Windows.Window> перед рассмотрением основ создания и управления окнами в автономных приложений.  
  
> [!NOTE]
>  Размещенные в браузере [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений, включая [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободные [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы, не предоставляют свои собственные окна. Вместо этого они размещаются в окнах [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]. В разделе [Обзор приложений браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
  
<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Класс окна  
 На следующем рисунке показаны составляющие части окна.  
  
 ![Элементы окна](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Окно разделено на две области: неклиентскую и клиентскую.  
  
 *Неклиентскую область* окна реализуется [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и включает части окна, которые являются общими для большинства окон, включая следующие:  
  
-   Граница.  
  
-   Заголовок окна.  
  
-   Значок.  
  
-   Кнопки "Свернуть", "Развернуть" и "Восстановить".  
  
-   Кнопка "Закрыть".  
  
-   Системное меню с элементами, которые позволяют пользователям свернуть, развернуть, восстановить, перемещать, изменять размеры и закрыть окно.  
  
 *Клиентской области* окна — это область в пределах неклиентской области окна и используется разработчиками для добавления содержимого конкретного приложения, такие как строки меню, панелей инструментов и элементов управления.  
  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], окно инкапсулируется <xref:System.Windows.Window> класс, который позволяет выполните следующие действия:  
  
-   Отобразить окно.  
  
-   Настроить размер, положение и внешний вид окна.  
  
-   Разместить содержимое конкретного приложения.  
  
-   Управлять временем существования окна.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Реализация окна  
 Реализация типичного окна включает внешний вид и поведение, где *внешний вид* определяет, как окно отображается для пользователей и *поведение* определяет способ окна функции, как пользователи взаимодействуют с ним. В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], можно реализовать внешний вид и поведение окна с помощью кода, либо или [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 Как правило, тем не менее, внешний вид окна реализуется с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметка, а его поведение реализуется с помощью кода, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Чтобы включить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл разметки и файл кода для совместной работы, требуются следующие сертификаты:  
  
-   В разметке `Window` элемент должен включать `x:Class` атрибута. При построении приложения существование `x:Class` в разметке вызывает файл [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] для создания `partial` класс, производный от <xref:System.Windows.Window> и имеет имя, которое определяется `x:Class` атрибута. Для этого необходимо добавление [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] объявление пространства имен для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] схемы ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). Созданный `partial` класс реализует `InitializeComponent` метод, который вызывается для регистрации событий и задания свойств, реализованных в разметке.  
  
-   В коде программной части, класс должен быть `partial` класс с тем же именем, который задается параметром `x:Class` атрибута в разметке и он должен быть производным от <xref:System.Windows.Window>. Это позволяет файл кода должны быть связаны с `partial` класс, который будет создан для файла разметки при построении приложения (см. [построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
-   В коде программной части <xref:System.Windows.Window> класс должен реализовывать конструктор, который вызывает `InitializeComponent` метод. `InitializeComponent` реализуется разметки созданный файл, `partial` класса для регистрации событий и задания свойств, которые определены в разметке.  
  
> [!NOTE]
>  При добавлении нового <xref:System.Windows.Window> в проект с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Window> реализуется с помощью разметки и кода и включает необходимую конфигурацию для создания связи между файлами разметки и кода как описанные здесь.  
  
 При такой конфигурации можно сосредоточиться на определении внешнего вида окна в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки и реализации его поведения в коде. В следующем примере показано окно с кнопкой, реализованное в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки и обработчик событий для кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события, реализованы в коде.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Настройка определения окна для MSBuild  
 Реализация окна определяет, как оно настроено для [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]. Для окна, который определен с помощью обоих [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки и кода:  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файлы разметки настраиваются как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page` элементов.  
  
-   Файлы кода настраиваются как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` элементов.  
  
 Это показано в следующем [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] файл проекта.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Сведения о построении [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, см. [построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Время существования окна  
 Как и любой класс, окно имеет время существования, которое начинается с момента создания его экземпляра, после чего оно открывается, активируется, деактивируется и, в конечном счете, закрывается.  
  
  
<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Открытие окна  
 Чтобы открыть окно, сначала создайте его экземпляр, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 В этом примере `MarkupAndCodeBehindWindow` создается при запуске приложения, который происходит при <xref:System.Windows.Application.Startup> события.  
  
 При создании окна ссылка на него автоматически добавляется в список окон, управляемых службой <xref:System.Windows.Application> объекта (в разделе <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Кроме того, первое окно для создания экземпляра по умолчанию задается <xref:System.Windows.Application> как главное окно приложения (см. <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 Наконец открывается окно путем вызова <xref:System.Windows.Window.Show%2A> метода; результат показан на следующем рисунке.  
  
 ![Окно, открытое посредством вызова метода Window.Show](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Окно, которое открывается вызовом <xref:System.Windows.Window.Show%2A> немодальное окно, это означает, что приложение работает в режиме, который позволяет пользователям активировать другие окна, в том же приложении.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> вызывается, чтобы открыть windows, таких как диалоговые окна, как модальная. В разделе [Общие сведения о полях диалогового окна](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md) для получения дополнительной информации.  
  
 Если <xref:System.Windows.Window.Show%2A> является вызове окна выполняет инициализацию перед его отображением для установки инфраструктуры, позволяет принимать ввод данных пользователем. При инициализации окна <xref:System.Windows.Window.SourceInitialized> событие и отображением этого окна.  
  
 Для быстрого вызова <xref:System.Windows.Application.StartupUri%2A> может быть настроен на указание первое окно, которое открывается автоматически при запуске приложения.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 При запуске приложения, окна, указанную значением <xref:System.Windows.Application.StartupUri%2A> открыт немодальных; внутренне, открывается окно путем вызова его <xref:System.Windows.Window.Show%2A> метод.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Владение окном  
 Окно, которое открывается с помощью <xref:System.Windows.Window.Show%2A> метод не имеет явную связь с окном, в которой он был создан, пользователи могут взаимодействовать с одним окном независимо от другого, это означает, что в любом окне можно выполнять следующие задачи:  
  
-   Перекрывать другое (если только не имеет одного из окон его <xref:System.Windows.Window.Topmost%2A> свойство `true`).  
  
-   Сворачиваться, разворачиваться и восстанавливаться без влияния на другое окно.  
  
 Для некоторых окон требуется связь с окном, которое их открывает. Например [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] приложение может открывать окна свойств и окна инструментов, поведение которой обычно является окно, который создает их. Кроме того, такие окна должны всегда закрываться, сворачиваться, разворачиваться и восстанавливаться вместе с окном, которое их создало. Такая связь может быть установлена путем задания одного окна *собственной* другой и достигается путем установки <xref:System.Windows.Window.Owner%2A> свойство *собственного окна* со ссылкой на *владельца окно*. Эти действия показаны в следующем примере.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 После установки владения:  
  
-   Собственное окно может ссылаться на окно владельца путем проверки значения его <xref:System.Windows.Window.Owner%2A> свойство.  
  
-   Окно-владелец может обнаруживать все окна, он владеет, проверяя значение его <xref:System.Windows.Window.OwnedWindows%2A> свойство.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Предотвращение активации окна  
 Существуют сценарии, где windows не следует активировать отображаемые диалога windows messenger стиле интернет-приложения или уведомления windows приложения электронной почты.  
  
 Если приложение имеет окна, который не должен быть активирован при отображении, можно задать его <xref:System.Windows.Window.ShowActivated%2A> свойства `false` перед вызовом <xref:System.Windows.Window.Show%2A> метода в первый раз. Результат:  
  
-   Окно не активируется.  
  
-   В окне <xref:System.Windows.Window.Activated> событие не происходит.  
  
-   Текущее активированное окно останется активным.  
  
 Однако окно активируется, если пользователь щелкнет его неклиентскую или клиентскую область. В этом случае:  
  
-   Окно активируется.  
  
-   В окне <xref:System.Windows.Window.Activated> события.  
  
-   Ранее активированное окно деактивируется.  
  
-   В окне <xref:System.Windows.Window.Deactivated> и <xref:System.Windows.Window.Activated> вызываются события в ответ на действия пользователя.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Активация окна  
 При первом открытии окна его окно становится активным (если он отображается с <xref:System.Windows.Window.ShowActivated%2A> значение `false`). *Активного окна* — это окно, в настоящее время захват пользовательского ввода, например нажатий клавиш и щелчки мышью. Если окно становится активным, происходит <xref:System.Windows.Window.Activated> событий.  
  
> [!NOTE]
>  При первом открытии окна <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.Window.ContentRendered> события вызываются только после <xref:System.Windows.Window.Activated> события. С учетом этого окно может считаться открытым при <xref:System.Windows.Window.ContentRendered> возникает.  
  
 После активизации окна пользователь может активировать другое окно в том же приложении или активировать другое приложение. В этом случае текущее активное окно становится неактивным и вызывает <xref:System.Windows.Window.Deactivated> событий. Аналогично, когда пользователь выбирает в настоящее время отключено окна, снова становится активным и <xref:System.Windows.Window.Activated> возникает.  
  
 Одна из основных причин для обработки <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> должен включать и отключать функции, которые можно выполнять только при включенном окна. Например, некоторые окна отображают интерактивное содержимое, которое требует постоянного ввода данных или внимания пользователя, включая игры и видеопроигрыватели. Ниже приведен упрощенный видеопроигрыватель, показано, как обрабатывать <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> для реализации этого поведения.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Другие типы приложений могут выполнять код в фоновом режиме, когда окно деактивировано. Например, почтовый клиент может продолжать опрашивать почтовый сервер, пока пользователь работает с другими приложениями. Такие приложения часто обеспечивают другое или дополнительное поведение, когда главное окно не активно. В случае почтовой программы это может означать как добавление нового почтового элемента в папку "Входящие", так и добавление значка уведомления на панель задач. Значок уведомления о необходимости отображаются, только если почтовое окно неактивно, что можно определить, проверив <xref:System.Windows.Window.IsActive%2A> свойство.  
  
 Если фоновая задача завершается, окно может потребоваться срочно уведомлять пользователя путем вызова <xref:System.Windows.Window.Activate%2A> метод. Если пользователь взаимодействует с другим приложением активируется, когда <xref:System.Windows.Window.Activate%2A> вызывается, мигает кнопку панели задач. Если пользователь взаимодействует с текущим приложением, при вызове <xref:System.Windows.Window.Activate%2A> переместит окно отображается на переднем плане.  
  
> [!NOTE]
>  Можно обработать с помощью активации области приложения <xref:System.Windows.Application.Activated?displayProperty=nameWithType> и <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> события.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Закрытие окна  
 Время существования окна заканчивается, когда пользователь его закрывает. Окно может быть закрыто с помощью элементов в неклиентской области, включая следующие:  
  
-   **Закрыть** элемент **системы** меню.  
  
-   Нажатие клавиш ALT+F4.  
  
-   Нажав клавишу **закрыть** кнопки.  
  
 Можно указать дополнительные способы закрытия окна для клиентской области, к наиболее типичным из которых относятся следующие:  
  
-   **Выхода** элемент **файл** меню, как правило, для основного приложения windows.  
  
-   Объект **закрыть** элемент **файл** меню, обычно для дополнительного окна приложения.  
  
-   Объект **отменить** кнопка, обычно для модального диалогового окна.  
  
-   Объект **закрыть** кнопка, обычно для немодального диалогового окна.  
  
 Чтобы закрыть окно, в результате одного из этих пользовательских механизмов, необходимо вызвать <xref:System.Windows.Window.Close%2A> метод. В следующем примере реализуется возможность закрыть окно, выбрав **выхода** на **файл** меню.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 При закрытии окна, он вызывает два события: <xref:System.Windows.Window.Closing> и <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> Возникает перед закрытием окна и предоставляет механизм, с помощью окно, которое может быть прервано закрытия. Одна из распространенных причин, препятствующих закрытию окна, заключается в том, что содержимое окна содержит измененные данные. В этом случае <xref:System.Windows.Window.Closing> событие может быть обработано, чтобы определить, являются ли данные "грязные" и если это так, чтобы запрашивать у пользователя, следует ли отменить закрытие окна или закрыть окно без сохранения данных. В следующем примере показано ключевые аспекты обработки <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  
 
  
 <xref:System.Windows.Window.Closing> Обработчик событий передается <xref:System.ComponentModel.CancelEventArgs>, который реализует `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> свойство, которое устанавливается в значение `true` для предотвращения закрытия окна.  
  
 Если <xref:System.Windows.Window.Closing> не обрабатывается, или обрабатывается, но не отменено, оно будет закрыто. Перед фактическим закрытием окна <xref:System.Windows.Window.Closed> возникает. На этом этапе невозможно предотвратить закрытие окна.  
  
> [!NOTE]
>  Приложение можно настроить на завершение работы автоматически при любом главное окно приложения закрывает (см. <xref:System.Windows.Application.MainWindow%2A>) или закрывается. Дополнительные сведения см. в разделе <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Хотя посредством механизмов, предоставляемых в областях, отличных от клиента и может явно закрыто окно, окно может быть закрыто неявно в результате поведение в других частях приложения или [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], включая следующие:  
  
-   Пользователь выходит из системы или завершает работу [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
-   Владелец окна закрывается (см. <xref:System.Windows.Window.Owner%2A>).  
  
-   Главное окно приложения закрывается и <xref:System.Windows.Application.ShutdownMode%2A> — <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
-   вызывается метод <xref:System.Windows.Application.Shutdown%2A>;  
  
> [!NOTE]
>  После закрытия окно нельзя открыть повторно.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>События времени существования окна  
 На следующем рисунке показана последовательность основных событий во время существования окна.  
  
 ![Время существования окна](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 На следующем рисунке показана последовательность основных событий во время существования окна, которое отображается без активации (<xref:System.Windows.Window.ShowActivated%2A> равно `false` перед отображением этого окна).  
  
 ![Время существования окна &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Расположение окна  
 Когда окно открыто, оно располагается в координатах x и y относительно рабочего стола. Это расположение можно определить, проверив <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> свойства, соответственно. Можно задать эти свойства, чтобы изменить расположение окна.  
  
 Можно также указать исходное расположение <xref:System.Windows.Window> при его первом появлении <xref:System.Windows.Window.WindowStartupLocation%2A> с одним из следующих <xref:System.Windows.WindowStartupLocation> значения перечисления:  
  
-   <xref:System.Windows.WindowStartupLocation.CenterOwner> (по умолчанию)  
  
-   <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
-   <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Если начальное расположение указано как <xref:System.Windows.WindowStartupLocation.Manual>и <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> свойства не задано, <xref:System.Windows.Window> запросит [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] для расположения в.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Окна верхнего уровня и Z-порядок  
 Помимо расположения в координатах x и y, окно имеет координату по оси z, которая определяет его вертикальную позицию относительно других окон. Это называется z-порядком окна. Существует два типа: обычный z-порядок и верхний z-порядок. Расположение окна в *обычном z порядке* определяется, является ли текущий активный или не. По умолчанию окно находится в обычном z-порядке. Расположение окна в *верхнем z порядке* также определяется, является ли текущий активный или не. Кроме того, окна в самом верхнем z-порядке всегда расположены над окнами в обычном z-порядке. Окно находится в верхнем z порядке, установив его <xref:System.Windows.Window.Topmost%2A> свойства `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 В каждом z-порядке активное в данный момент окно появляется поверх всех других окон в том же z-порядке.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Размер окна  
 Помимо расположения на рабочем столе, окно имеет размер, который определяется несколько свойств, включая различные свойства ширины и высоты и <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, и <xref:System.Windows.FrameworkElement.MaxWidth%2A> используются для управления диапазоном ширины, окно может быть во время существования и настроены, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Высота окна управляется <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, и <xref:System.Windows.FrameworkElement.MaxHeight%2A>и настроены, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Так как различные значения ширины и высоты определяют диапазон, то что ширина и высота изменяемого окна могут находиться в любом месте указанного диапазона для соответствующего измерения. Чтобы определить текущую ширину и высоту, проверьте <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A>соответственно.  
  
 Если вы хотите ширину и высоту окна будет иметь размер, который соответствует размеру окна содержимое элемента, можно использовать <xref:System.Windows.Window.SizeToContent%2A> свойства, которое имеет следующие значения:  
  
-   <xref:System.Windows.SizeToContent.Manual>. Нет эффекта (по умолчанию).  
  
-   <xref:System.Windows.SizeToContent.Width>. По ширине в содержимого, который имеет тот же эффект, что и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> содержимое по ширине.  
  
-   <xref:System.Windows.SizeToContent.Height>. По размеру содержимого высоту, которая имеет тот же эффект, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> по высоте содержимого.  
  
-   <xref:System.Windows.SizeToContent.WidthAndHeight>. По ширине и высоте, который имеет тот же эффект, что и установка содержимого <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> по высоте содержимого, а оба <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> содержимое по ширине.  
  
 В следующем примере показано окно, размеры которого автоматически устанавливаются равными его содержимому по вертикали и по горизонтали при первом отображении.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 Следующий пример показывает, как задать <xref:System.Windows.Window.SizeToContent%2A> свойства в коде, чтобы указать, изменение размера окна в соответствии с содержимым.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Порядок приоритета для свойств размера  
 Различные свойства размеров окна объединяются для определения диапазона ширины и высоты окна изменяемого размера. Чтобы гарантировать сохранение допустимого диапазона, <xref:System.Windows.Window> вычисляет значения свойств размера, используя следующие приоритеты.  
  
 **Для свойств высоты:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Для свойств ширины:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType> >  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType> >  
  
3.  <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType> >  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 Очередность выполнения также можно определить размер окна, когда она развернута, управляемую с <xref:System.Windows.Window.WindowState%2A> свойство.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Состояние окна  
 В течение времени существования окна изменяемого размера оно может иметь три состояния: обычное, свернутое и развернутое. Окно с *обычного* состояние находится в состоянии по умолчанию окна. Окно с этим состоянием позволяет пользователю перемещать его и изменять размер, используя захват для изменения размера или границу.  
  
 Окно с *к минимуму* сворачивает состояние на кнопке панели задач, если <xref:System.Windows.Window.ShowInTaskbar%2A> равно `true`; в противном случае оно сворачивается до наименьшего возможного размера, он может быть и размещается в левом нижнем углу рабочего стола. Ни один из типов свернутого окна не может быть изменен с помощью границы или захвата для изменения размера, хотя свернутое окно, которое не отображается на панели задач, можно перетаскивать на рабочем столе.  
  
 Окно с *развернуто* состояние при развертывании максимальный размер, который определяется размером до его <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, и <xref:System.Windows.Window.SizeToContent%2A> свойствами. Как и для свернутого окна, размер развернутого окна нельзя изменить с помощью захвата для изменения размера или перетаскивания границы.  
  
> [!NOTE]
>  Значения <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, и <xref:System.Windows.FrameworkElement.Height%2A> свойств окна всегда представляют значения для нормальное состояние, даже в том случае, если в данный момент окно свернуто или развернуто.  
  
 Состояние окна можно настроить, задав его <xref:System.Windows.Window.WindowState%2A> свойство, которое может иметь одно из следующих <xref:System.Windows.WindowState> значения перечисления:  
  
-   <xref:System.Windows.WindowState.Normal> (по умолчанию)  
  
-   <xref:System.Windows.WindowState.Maximized>  
  
-   <xref:System.Windows.WindowState.Minimized>  
  
 В следующем примере показано создание окна, которое отображается развернутым при его открытии.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 Как правило, следует задать <xref:System.Windows.Window.WindowState%2A> для настройки начального состояния окна. После отображения окна изменяемого размера пользователи могут нажимать кнопки свертывания, развертывания и восстановления на панели заголовка окна, чтобы изменить состояние окна.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Внешний вид окна  
 Можно изменить внешний вид клиентской области окна, добавляя в нее определенное содержимое, такое как кнопки, метки и текстовые поля. Для настройки неклиентской области, <xref:System.Windows.Window> предоставляет несколько свойств, которые включают <xref:System.Windows.Window.Icon%2A> для задания значка окна и <xref:System.Windows.Window.Title%2A> для задания его заголовка.  
  
 Можно также изменить внешний вид и поведение границы неклиентской области, настраивая режим изменения размера окна, стиль окна и отображение в виде кнопки на панели задач рабочего стола.  
  
  
<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Режим изменения размера  
 В зависимости от <xref:System.Windows.Window.WindowStyle%2A> свойства, можно управлять как (и если) пользователи могут изменять размеры окна. Выбор стиля окна влияет ли пользователь изменять размеры окна путем перетаскивания его границы с помощью мыши ли **свернуть**, **развернуть**, и **изменения размера** кнопки отображаются в неклиентской области, и, если они отображаются, доступны ли они.  
  
 Можно настроить изменение размера окна, установив его <xref:System.Windows.Window.ResizeMode%2A> свойство, которое может принимать одно из следующих <xref:System.Windows.ResizeMode> значения перечисления:  
  
-   <xref:System.Windows.ResizeMode.NoResize>  
  
-   <xref:System.Windows.ResizeMode.CanMinimize>  
  
-   <xref:System.Windows.ResizeMode.CanResize> (по умолчанию)  
  
-   <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Как и в <xref:System.Windows.Window.WindowStyle%2A>, режим изменения размера окна не приводит к изменению во время существования, означает, что вы будете скорее его из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Обратите внимание, что можно определить, является ли окно развернуто, свернуто, или база данных, проверяя <xref:System.Windows.Window.WindowState%2A> свойство.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Стиль окна  
 Граница, предоставляемая из неклиентской области окна, подходит для большинства приложений. Однако существуют ситуации, когда требуются различные типы границ либо границы вовсе не требуются, в зависимости от типа окна.  
  
 Для управления типом границы окна, установите его <xref:System.Windows.Window.WindowStyle%2A> с одним из следующих значений <xref:System.Windows.WindowStyle> перечисления:  
  
-   <xref:System.Windows.WindowStyle.None>  
  
-   <xref:System.Windows.WindowStyle.SingleBorderWindow> (по умолчанию)  
  
-   <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
-   <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Эффект этих стилей окон показан на следующем рисунке.  
  
 ![Стили окна](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.PNG "WindowOverviewFigure6")  
  
 Можно задать <xref:System.Windows.Window.WindowStyle%2A> одним [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки или кода, поскольку это приводит к изменению во время существования окна, скорее всего настраивается с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Непрямоугольный стиль окна  
 Также существуют ситуации, когда, стилей границ <xref:System.Windows.Window.WindowStyle%2A> позволяет иметь недостаточно. Например, может потребоваться создать приложение с нестандартной границей как [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] использует.  
  
 Рассмотрим окно "облачко с текстом", показанное на следующем рисунке.  
  
 ![Непрямоугольное окно](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Этот тип окна можно создать путем установки <xref:System.Windows.Window.WindowStyle%2A> свойства <xref:System.Windows.WindowStyle.None>и с помощью специальной поддержки <xref:System.Windows.Window> прозрачности.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Это сочетание значений указывает, что окно отрисовывается полностью прозрачным. В этом состоянии нельзя использовать элементы оформления неклиентской области окна (кнопки "Закрыть", "Минимизировать", "Развернуть" и "Восстановить" и т. д.). Следовательно, необходимо предоставить свои собственные элементы.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Наличие панели задач  
 По умолчанию внешний вид окна включает кнопку панели задач, как показано на следующем рисунке.  
  
 ![Окно с кнопкой панели задач](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.PNG "WindowOverviewFigure7")  
  
 Некоторые типы windows не имеют кнопки панели задач, таких как окна сообщений и диалоговые окна (в разделе [Общие сведения о полях диалогового окна](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)). Можно управлять, отображаются ли кнопки панели задач для окна, задав <xref:System.Windows.Window.ShowInTaskbar%2A> свойство (`true` по умолчанию).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Вопросы безопасности  
 <xref:System.Windows.Window> требуется `UnmanagedCode` создания разрешения безопасности. Для приложений, установленных и запускаемых с локального компьютера, это включено в набор разрешений, предоставленных приложению.  
  
 Тем не менее, попадут в набор разрешений для приложений, запускаемых из Интернета или локальной интрасети с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]. Следовательно, пользователи будут получать [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] предупреждение системы безопасности и необходимо повысить набора разрешений для приложения до полного доверия.  
  
 Кроме того [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не может отображать окна или диалоговые окна по умолчанию. Дополнительные сведения о вопросах безопасности автономные приложения, в разделе [стратегия безопасности WPF — безопасность платформы](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Другие типы окон  
 <xref:System.Windows.Navigation.NavigationWindow> — Это окно, предназначенное для предоставления навигации по содержимому. Дополнительные сведения см. в разделе [Общие сведения о навигации](../../../../docs/framework/wpf/app-development/navigation-overview.md)).  
  
 Диалоговые окна — это окна, которые часто используются для сбора информации от пользователя для выполнения функции. Например, если пользователю для открытия файла, **открыть файл** приложением для получения имени файла от пользователя обычно отображается диалоговое окно. Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Window>  
 <xref:System.Windows.MessageBox>  
 <xref:System.Windows.Navigation.NavigationWindow>  
 <xref:System.Windows.Application>  
 [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)  
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
