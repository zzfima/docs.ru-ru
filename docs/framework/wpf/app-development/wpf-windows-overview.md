---
title: "Общие сведения об окнах WPF | Microsoft Docs"
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
  - "приложения, размещение"
  - "содержание, отображение"
  - "содержание, отображение в процедурном коде"
  - "содержание, отображение значков"
  - "создание, окна"
  - "диалоговые окна"
  - "отображение содержимого"
  - "отображение содержимого в процедурном коде"
  - "отображение страниц XAML"
  - "события"
  - "размещение, приложения"
  - "управление окнами"
  - "модальные диалоговые окна"
  - "модальные окна"
  - "NavigationWindow - объекты"
  - "Page - объект"
  - "процедурный код, отображение содержимого"
  - "события окон"
  - "управление окнами"
  - "объекты окон"
  - "окна"
  - "XAML-страницы, отображение"
  - "XAML, отображение содержимого"
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
caps.latest.revision: 65
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 60
---
# Общие сведения об окнах WPF
Пользователи взаимодействуют с автономными приложениями [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] при помощи окон.  Основным предназначением окна является размещение содержимого, которое отображает данные и позволяет пользователям взаимодействовать с ними. Автономные приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляют свои собственные окна с помощью класса <xref:System.Windows.Window>.  В этом разделе перед рассмотрением основ создания и управления окнами в автономных приложениях описывается <xref:System.Windows.Window>.  
  
> [!NOTE]
>  Приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], реализуемые в браузере, включая [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободные страницы [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], не предоставляют свои собственные окна.  Вместо этого они размещаются в окнах, предоставляемых [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)].  См. раздел [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
   
  
<a name="TheWindowClass"></a>   
## Класс "Окно"  
 На следующем рисунке показаны составные части окна.  
  
 ![Элементы окна](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure1.PNG "WindowOverviewFigure1")  
  
 Окно разделено на две области: неклиентскую и клиентскую область.  
  
 *Неклиентская область* окна реализована с помощью [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и включает части окна, являющиеся общими для большинства окон, в том числе следующие:  
  
-   Граница.  
  
-   Заголовок окна.  
  
-   Значок.  
  
-   Кнопки "Свернуть", "Развернуть" и "Восстановить".  
  
-   Кнопка "Закрыть".  
  
-   Системное меню с элементами, которые позволяют пользователям сворачивать, разворачивать, восстанавливать, перемещать, изменять размер и закрывать окно.  
  
 *Клиентская область* окна является областью, входящей в неклиентскую область, и используется разработчиками для добавления содержимого конкретного приложения, такого как строки меню, панели инструментов и элементы управления.  
  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] окно инкапсулируется классом <xref:System.Windows.Window>, предназначенным для выполнения следующих действий.  
  
-   Отображение окна.  
  
-   Настройка размера, положения и внешнего вида окна.  
  
-   Размещение содержимого конкретного приложения.  
  
-   Управление временем существования окна.  
  
<a name="DefiningAWindow"></a>   
## Реализация окна  
 Реализация типичного окна включает как вид, так и поведение, где *вид* определяет, как окно отображается для пользователей, а *поведение* определяет способ функционирования окна при взаимодействии пользователей с ним.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] можно реализовать внешний вид и поведение окна либо с помощью кода, либо с помощью разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Однако, как правило, внешний вид окна реализуется с помощью разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а его поведение реализуется с помощью кода программной части, как показано в следующем примере.  
  
 [!code-xml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Чтобы обеспечить взаимодействие файла разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и файла кода программной части, необходимо выполнить следующее:  
  
-   В разметке элемент `Window` должен включать атрибут `x:Class`.  При построении приложения существование `x:Class` в файле разметки приводит к тому, что [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] создает класс `partial`, производный от <xref:System.Windows.Window> с именем, которое определяется атрибутом `x:Class`.  Для этого требуется добавить объявление пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в схему [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  Созданный класс `partial` реализует метод `InitializeComponent`, который вызывается для регистрации событий и задания свойств, реализованных в разметке.  
  
-   В коде программной части класс должен быть классом `partial` с тем же именем, которое определено атрибутом `x:Class` в разметке, и он должен быть производным от <xref:System.Windows.Window>.  Это позволяет связать файл кода программной части с классом `partial`, созданным для файла разметки при построении приложения \(см. раздел [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
-   В коде программной части класс <xref:System.Windows.Window> должен реализовать конструктор, вызывающий метод `InitializeComponent`.  Метод `InitializeComponent` реализуется классом `partial`, созданным файлом разметки, для регистрации событий и задания свойств, определенных в разметке.  
  
> [!NOTE]
>  Когда в проект добавляется новый класс <xref:System.Windows.Window> с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], <xref:System.Windows.Window> реализуется с помощью разметки и с помощью кода программной части и включает необходимую конфигурацию для создания связи между файлами разметки и файлами кода программной части.  
  
 При такой конфигурации можно сосредоточиться на определении внешнего вида окна в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и реализации его поведения в коде программной реализации.  В следующем примере показано окно с кнопкой, реализованное в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], и обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки, реализованный в коде программной части.  
  
 [!code-xml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## Настройка определения окна для MSBuild  
 Реализация окна определяет его конфигурацию для [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  Для окна, определенного как с помощью разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так и с помощью кода программной части:  
  
-   Файлы разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] настраиваются как элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Page`.  
  
-   Файлы кода программной части настраиваются как элементы [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile`.  
  
 Это показано в следующем файле проекта [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)].  
  
```  
<Project ... xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Сведения о построении приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] см. в разделе [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## Время существования окна  
 Как и любой класс, окно имеет время существования, которое начинается с момента создания, после которого осуществляется его открытие, активация, деактивация и, в конечном счете, закрытие.  
  
   
  
<a name="Opening_a_Window"></a>   
### Открытие окна  
 Чтобы открыть окно, сначала создайте его экземпляр, как показано в следующем примере.  
  
 [!code-xml[WindowsOverviewStartupEventSnippets#AppMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 В этом примере при запуске приложения создается `MarkupAndCodeBehindWindow`, которое появляется при возникновении события <xref:System.Windows.Application.Startup>.  
  
 После создания окна ссылка на него автоматически добавляется в список окон, управление которым осуществляется объектом <xref:System.Windows.Application> \(см. <xref:System.Windows.Application.Windows%2A?displayProperty=fullName>\).  Кроме того, по умолчанию первый экземпляр окна устанавливается <xref:System.Windows.Application> как главное окно приложения \(см. <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName>\).  
  
 Окончательное открытие окна осуществляется вызовом метода <xref:System.Windows.Window.Show%2A>; результат показан на следующем рисунке.  
  
 ![Окно, открытое посредством вызова Window.Show](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure8.png "WindowOverviewFigure8")  
  
 Окно, открытое с помощью вызова <xref:System.Windows.Window.Show%2A>, является безрежимным, что означает, что приложение работает в режиме, позволяющем пользователям активировать другие окна в том же приложении.  
  
> [!NOTE]
>  <xref:System.Windows.Window.ShowDialog%2A> вызывается для открытия модальных окон, таких как диалоговые окна.  Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
 При вызове <xref:System.Windows.Window.Show%2A> окно перед отображением выполняет инициализацию для установки инфраструктуры, позволяющей получать вводимые пользователем данные.  После инициализации окна возникает событие <xref:System.Windows.Window.SourceInitialized>, и окно отображается.  
  
 Для быстрого запуска может быть установлен <xref:System.Windows.Application.StartupUri%2A>, указывающий первое окно, которое открывается автоматически при запуске приложения.  
  
 [!code-xml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 При запуске приложения окно, заданное значением <xref:System.Windows.Application.StartupUri%2A>, открывается безрежимно, а внутри приложения окно открывается с помощью вызова метода <xref:System.Windows.Window.Show%2A>.  
  
<a name="Ownership"></a>   
#### Владение окном  
 Окно, открытое с помощью метода <xref:System.Windows.Window.Show%2A>, не имеет неявной связи с окном, которое его создало; пользователи могут взаимодействовать с одним окном независимо от другого, что означает, что любое из окон может выполнять следующее:  
  
-   Перекрывать другое \(если свойство <xref:System.Windows.Window.Topmost%2A> одного из окон установлено в `true` \).  
  
-   Сворачиваться, разворачиваться и восстанавливаться без влияния на другое окно.  
  
 Для некоторых окон требуется связь с окном, которое их открывает.  Например, приложение [!INCLUDE[TLA#tla_ide](../../../../includes/tlasharptla-ide-md.md)] может открыть окна свойств и окна инструментов, которые обычно перекрывают создавшее их окно.  Кроме того, такие окна должны всегда закрываться, сворачиваться, разворачиваться и восстанавливаться вместе с окном, в котором они созданы.  Такая связь может быть установлена путем задания одного окна как *владельца* другого, что достигается путем установки свойства <xref:System.Windows.Window.Owner%2A> *собственного окна* в значение ссылки на *окно владельца*.  Это показано в следующем примере.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 После установки владельца:  
  
-   Собственное окно может ссылаться на окно владельца, путем проверки значения свойства <xref:System.Windows.Window.Owner%2A>.  
  
-   Окно владельца может обнаруживать все окна, которыми оно владеет, путем проверки значения свойства <xref:System.Windows.Window.OwnedWindows%2A>.  
  
<a name="Preventing"></a>   
#### Предотвращение активации окна  
 В некоторых случаях не следует активировать отображаемые окна; примером таких окон являются окна беседы в приложениях, предназначенных для обмена сообщениями через Интернет, и окна уведомлений в приложениях электронной почты.  
  
 Если в приложении имеется окно, которое не следует активировать при отображении, присвойте свойству <xref:System.Windows.Window.ShowActivated%2A> этого окна значение `false` перед первым вызовом метода <xref:System.Windows.Window.Show%2A>.  Ниже перечислены результаты выполнения этих действий.  
  
-   Окно не активируется.  
  
-   Событие <xref:System.Windows.Window.Activated> этого окна не вызывается.  
  
-   Окно, активированное к настоящему моменту, остается активированным.  
  
 Тем не менее, окно будет активировано только тогда, когда пользователь щелкнет его в клиентской или иной области.  В этом случае будут иметь место указанные ниже последствия.  
  
-   Окно активируется.  
  
-   Вызывается событие <xref:System.Windows.Window.Activated> этого окна.  
  
-   Ранее активированное окно деактивируется.  
  
-   В ответ на действия пользователя вызываются события <xref:System.Windows.Window.Deactivated> и <xref:System.Windows.Window.Activated> этого окна.  
  
<a name="Window_Activation"></a>   
### Активация окна  
 Когда окно открывается в первый раз, оно становится активным \(за исключением случая, когда свойству <xref:System.Windows.Window.ShowActivated%2A> этого окна присвоено значение `false`\).  *Активное окно* — это окно, которое в настоящее время перехватывает пользовательский ввод, например нажатие клавиш или щелчки мыши.  Когда окно становится активным, оно вызывает событие <xref:System.Windows.Window.Activated>.  
  
> [!NOTE]
>  При первом открытии окна события <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.Window.ContentRendered> вызываются после события <xref:System.Windows.Window.Activated>.  С учетом этого окно может считаться открытым при возникновении события <xref:System.Windows.Window.ContentRendered>.  
  
 После того как окно становится активным, пользователь может активировать другое окно того же приложения или активировать другое приложение.  При этом текущее активное окно становится неактивным и вызывается событие <xref:System.Windows.Window.Deactivated>.  Аналогичным образом, когда пользователь выбирает неактивное в данный момент окно, оно снова становится активным и вызывается <xref:System.Windows.Window.Activated>.  
  
 Одной из распространенных причин для обработки <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> является включение и отключение функций, которые должны выполняться только в активном окне.  Например, некоторые окна отображают интерактивное содержимое, которое требует постоянного ввода данных пользователем или внимания со стороны пользователя, например игры и видеопроигрыватели.  В следующем примере показан упрощенный видеопроигрыватель, демонстрирующий обработку <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> для реализации этого поведения.  
  
 [!code-xml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Другие типы приложений при деактивации окна могут по\-прежнему выполнять код в фоновом режиме.  Например, почтовый клиент может продолжить опрашивать почтовый сервер, даже когда пользователь использует другое приложение.  Такие приложения во время деактивации главного окна часто выполняют отличные или дополнительные действия.  В почтовой программе это может означать как добавление нового элемента почты в почтовый ящик, так и добавление значка уведомлений в панель задач.  Значок уведомлений требуется отображать, только если почтовое окно неактивно, что может быть определено с помощью проверки свойства <xref:System.Windows.Window.IsActive%2A>.  
  
 Если фоновая задача завершается, то окну может потребоваться срочно сообщить об этом пользователю с помощью вызова метода <xref:System.Windows.Window.Activate%2A>.  Если пользователь взаимодействует с другим приложением, активированным после вызова метода <xref:System.Windows.Window.Activate%2A>, то кнопка панели задач окна начинает мигать.  Если пользователь взаимодействует с текущим приложением, то вызов <xref:System.Windows.Window.Activate%2A> переместит окно на передний план.  
  
> [!NOTE]
>  Можно обработать активацию области определения приложения с помощью событий <xref:System.Windows.Application.Activated?displayProperty=fullName> и <xref:System.Windows.Application.Deactivated?displayProperty=fullName>.  
  
<a name="Closing_a_Window"></a>   
### Закрытие окна  
 Время существования окна подходит к концу, когда пользователь закрывает его.  Окно может быть закрыто с помощью следующих элементов неклиентской области:  
  
-   Пункт **Закрыть** меню **Система**.  
  
-   Нажатие комбинации клавиш ALT \+ F4.  
  
-   Нажатие кнопки **Закрыть**.  
  
 Можно указать дополнительные способы закрытия окна для клиентской области, к наиболее общим из которых относятся:  
  
-   Пункт **Выход** меню **Файл** \(обычно для главных окон приложений\).  
  
-   Пункт **Закрыть** меню **Файл** \(обычно для дополнительного окна приложения\).  
  
-   Кнопка **Отмена** \(обычно для модального диалогового окна\).  
  
-   Кнопка **Закрыть** \(обычно для немодального диалогового окна\).  
  
 Чтобы закрыть окно одним из этих пользовательских способов, необходимо вызвать метод <xref:System.Windows.Window.Close%2A>.  В следующем примере реализуется возможность закрытия окна с помощью выбора пункта **Выход** в меню **Файл**.  
  
 [!code-xml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 При закрытии окно вызывает два события: <xref:System.Windows.Window.Closing> и <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> вызывается перед закрытием окна и предоставляет механизм, с помощью которого закрытие окна может быть прервано.  Одной из основных причин для предотвращения закрытия окна является изменение данных в содержимом окна.  В этом случае событие <xref:System.Windows.Window.Closing> может быть обработано, чтобы определить, являются ли данные "грязными", и, если это так, спросить у пользователя, следует ли отменить закрытие окна или закрыть его без сохранения данных.  В следующем примере показаны ключевые аспекты обработки <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind1)]
 [!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind1)]  
[!code-csharp[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs#windowclosingcodebehind2)]
[!code-vb[WindowClosingSnippets#WindowClosingCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb#windowclosingcodebehind2)]  
  
 Обработчику событий <xref:System.Windows.Window.Closing> передается <xref:System.ComponentModel.CancelEventArgs>, который реализует свойство `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, устанавливаемое в `true` для предотвращения закрытия окна.  
  
 Если <xref:System.Windows.Window.Closing> не обрабатывается или обрабатывается, но не было отменено, то окно будет закрыто.  Перед фактическим закрытием окна вызывается <xref:System.Windows.Window.Closed>.  В этом случае закрытие окна предотвратить нельзя.  
  
> [!NOTE]
>  Приложение может быть настроено на завершение работы автоматически, либо когда закрывается главное окно приложения \(см. <xref:System.Windows.Application.MainWindow%2A>\), либо когда закрывается последнее окно.  Дополнительные сведения см. в разделе <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Хотя окно может быть закрыто явным образом с помощью механизмов, предоставленных в клиентской и неклиентской областях, окно может быть закрыто неявно в результате поведения других элементов приложения или [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], к которым относятся следующие:  
  
-   Пользователь выходит из системы или завершает работу [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
-   Владелец окна закрывается \(см. <xref:System.Windows.Window.Owner%2A>\).  
  
-   Закрывается главное окно приложения, а <xref:System.Windows.Application.ShutdownMode%2A> устанавливается в <xref:System.Windows.ShutdownMode>.  
  
-   Вызывается метод <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
>  Окно не может быть открыто повторно после его закрытия.  
  
<a name="Window_Lifetime_Events"></a>   
### События времени существования окна  
 На следующем рисунке показана последовательность основных событий времени существования окна.  
  
 ![Время существования окна](../../../../docs/framework/wpf/app-development/media/windowlifetimeevents.png "WindowLifetimeEvents")  
  
 На приведенном ниже рисунке показана последовательность основных событий во время существования окна, которое отображается без активации \(перед отображением окна свойству <xref:System.Windows.Window.ShowActivated%2A> присваивается значение `false`\).  
  
 ![Время существования окна &#40;Window.ShowActivated &#61; False&#41;](../../../../docs/framework/wpf/app-development/media/windowlifetimenoact.png "WindowLifetimeNoAct")  
  
<a name="WindowLocation"></a>   
## Расположение окон  
 Пока окно открыто, для него задано положение и размеры по осям X и Y относительно рабочего стола.  Это расположение можно определить путем проверки свойств <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> соответственно.  Можно задать эти свойства для изменения расположения окна.  
  
 Также можно задать начальное расположение <xref:System.Windows.Window> при его первом появлении с помощью свойства <xref:System.Windows.Window.WindowStartupLocation%2A> и одного из следующих значений перечисления <xref:System.Windows.WindowStartupLocation>:  
  
-   <xref:System.Windows.WindowStartupLocation> \(по умолчанию\)  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
-   <xref:System.Windows.WindowStartupLocation>  
  
 Если начальное расположение указано как <xref:System.Windows.WindowStartupLocation>, а свойства <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> не были установлены, то <xref:System.Windows.Window> запросит [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] для определения места появления.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### Окна переднего плана и Z\-порядок  
 Помимо координат X и Y окно также имеет координату по оси Z, которая определяет его вертикальную позицию относительно других окон.  Это явление называется Z\-порядком окна. Их существует два типа: обычный Z\-порядок и верхний Z\-порядок.  Расположение окна в *обычном Z\-порядке* определяется его активностью.  По умолчанию окно находится в нормальном Z\-порядке.  Расположение окна в *верхнем Z\-порядке* также определяется его активностью.  Кроме того, окна в верхнем z\-порядке всегда расположены над окнами обычного Z\-порядка.  Окно можно расположить в верхнем Z\-порядке, установив для его свойства <xref:System.Windows.Window.Topmost%2A> значение `true`.  
  
 [!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TopmostWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup2)]  
  
 Внутри каждого z\-порядка текущее активное окно появляется поверх всех остальных окон одного Z\-порядка.  
  
<a name="WindowSize"></a>   
## Размер окна  
 Помимо расположения на рабочем столе окно имеет размер, определяемый несколькими свойствами, включая различные свойства ширины, высоты и <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> используются для управления диапазоном ширины, которую может иметь окно во время существования, и настроены, как показано в следующем примере.  
  
 [!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WidthWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup2)]  
  
 Высота окна управляется <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A>, которые настраиваются, как показано в следующем примере.  
  
 [!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#HeightWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup2)]  
  
 Поскольку различные значения высоты и ширины определяют диапазон, существует возможность устанавливать ширину и высоту изменяемого в размерах окна в любое значение в пределах указанного диапазона для соответствующего измерения.  Чтобы определить текущую ширину и высоту, проверьте <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A> соответственно.  
  
 Если необходимо, чтобы ширина и высота окна имели размер, соответствующий содержимому окна, то можно использовать свойство <xref:System.Windows.Window.SizeToContent%2A>, которое имеет следующие значения:  
  
-   <xref:System.Windows.SizeToContent>.  Не оказывает влияние \(по умолчанию\).  
  
-   <xref:System.Windows.SizeToContent>.  Растяжение окна по ширине содержимого имеет тот же эффект, что и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> по ширине содержимого.  
  
-   <xref:System.Windows.SizeToContent>.  Растяжение окна по высоте содержимого имеет тот же эффект, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> по высоте содержимого.  
  
-   <xref:System.Windows.SizeToContent>.  Растяжение окна по ширине и высоте содержимого имеет тот же эффект, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> по высоте содержимого, а <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> по ширине содержимого.  
  
 В следующем примере показано окно, автоматически изменяет размер в соответствии с размером его содержимого и по вертикали и по горизонтали, при первом отображении.  
  
 [!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#SizeToContentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup2)]  
  
 В следующем примере показано, как присвоить <xref:System.Windows.Window.SizeToContent%2A> свойство в коде для указания способа изменения размеров окна с размером его содержимого.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## Порядок приоритета свойств изменения размера  
 По существу, различные свойства изменения размера окна объединяются для определения диапазона ширины и высоты для изменяемого в размерах окна.  Чтобы гарантировать сохранение допустимого диапазона, <xref:System.Windows.Window> вычисляет значения свойств размера, используя следующие приоритеты.  
  
 **Для свойств высоты:**  
  
1.  <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=fullName>  
  
 **Для свойств ширины:**  
  
1.  <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=fullName> \>  
  
2.  <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=fullName> \>  
  
3.  <xref:System.Windows.SizeToContent?displayProperty=fullName>\/<xref:System.Windows.SizeToContent?displayProperty=fullName> \>  
  
4.  <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=fullName>  
  
 Порядок приоритета может также определять размер развернутого окна, что управляется с помощью свойства <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="WindowState"></a>   
## Состояние окна  
 Во время существования изменяемое в размерах окно может находиться в трех состояниях: обычном, свернутом и развернутом.  *Обычное* состояние является состоянием окна по умолчанию.  Если окно находится в этом состоянии, пользователь может перемещать его и изменять его размеры с помощью захвата для изменения размера или перетаскивания границы, если окно изменяется в размерах.  
  
 Окно в *свернутом* состоянии сворачивается в кнопку на панели задач, если <xref:System.Windows.Window.ShowInTaskbar%2A> имеет значение `true`. В противном случае оно сворачивается до наименьшего допустимого размера и размещается в левом нижнем углу рабочего стола.  Ни один тип свернутого окна не может быть изменен в размерах с помощью границ или захвата, хотя свернутое окно, которое не отображается на панели задач, можно перетаскивать по всему рабочему столу.  
  
 Окно в *развернутом* состоянии расширяется до максимально допустимого размера, который определяется свойствами <xref:System.Windows.FrameworkElement.MaxWidth%2A>,<xref:System.Windows.FrameworkElement.MaxHeight%2A> и <xref:System.Windows.Window.SizeToContent%2A>.  Как и свернутое окно, развернутое окно не может быть изменено в размерах с помощью захвата для изменения размера или перетаскиванием границ.  
  
> [!NOTE]
>  Значения свойств окна <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> всегда представляют значения для нормального состояния, даже когда окно развернуто на весь экран или свернуто.  
  
 Состояние окна можно настроить путем установки его свойства <xref:System.Windows.Window.WindowState%2A>, которое может иметь одно из следующих значений перечисления <xref:System.Windows.WindowState>:  
  
-   <xref:System.Windows.WindowState> \(по умолчанию\)  
  
-   <xref:System.Windows.WindowState>  
  
-   <xref:System.Windows.WindowState>  
  
 В следующем примере показано создание окна, которое при открытии отображается развернутым.  
  
 [!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStateWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup2)]  
  
 В общем случае следует задать <xref:System.Windows.Window.WindowState%2A> для настройки начального состояния окна.  После отображения изменяемого в размерах окна пользователи могут нажимать кнопки свертывания, развертывания и восстановления в строке заголовка для изменения состояния окна.  
  
<a name="WindowAppearance"></a>   
## Вид окна  
 Можно изменить внешний вид клиентской области окна с помощью добавления характерного для окна содержимого, такого как кнопки, метки и текстовые поля.  Для настройки неклиентской области <xref:System.Windows.Window> предоставляет несколько свойств, включающих <xref:System.Windows.Window.Icon%2A> для задания значка окна и <xref:System.Windows.Window.Title%2A> для задания его заголовка.  
  
 Также можно изменить вид и поведение границы неклиентской области, настраивая режим изменения размера окна, стиль окна и будет ли оно отображается в виде кнопки на панели задач рабочего стола.  
  
   
  
<a name="Resize_Mode"></a>   
### Режим изменения размера  
 С помощью значений свойства <xref:System.Windows.Window.WindowStyle%2A> можно управлять способами изменения размера окна пользователями \(если это разрешено\).  Выбор стиля окна влияет на то, может ли пользователь изменять размеры окна путем перетаскивания его границы с помощью мыши, отображаются ли кнопки **Свернуть**, **Развернуть** и **Изменить размер** в неклиентской области и доступны ли они, если они отображаются.  
  
 Можно настроить изменение размера окна путем установки его свойства <xref:System.Windows.Window.ResizeMode%2A>, которое может принимать одно из следующих значений перечисления <xref:System.Windows.ResizeMode>:  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode>  
  
-   <xref:System.Windows.ResizeMode> \(по умолчанию\)  
  
-   <xref:System.Windows.ResizeMode>  
  
 Как и в случае с <xref:System.Windows.Window.WindowStyle%2A>, режим изменения размера окна нежелательно менять во время существования. Это означает, что лучше всего задать его из разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ResizeModeWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup2)]  
  
 Обратите внимание, что можно обнаружить, развернуто, свернуто или восстановлено окно, с помощью просмотра свойства <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="Window_Style"></a>   
### Стиль окна  
 Граница, предоставляемая из неклиентской области окна, может использоваться в большинстве приложений.  Однако существуют ситуации, когда в зависимости от типа окна требуются различные типы границ, или границы не требуются вовсе.  
  
 Для управления типом границы окна, установите его свойство <xref:System.Windows.Window.WindowStyle%2A> с помощью одного из следующих значений перечисления <xref:System.Windows.WindowStyle>:  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle> \(по умолчанию\)  
  
-   <xref:System.Windows.WindowStyle>  
  
-   <xref:System.Windows.WindowStyle>  
  
 Воздействие этих оконных стилей показано на следующем рисунке.  
  
 ![Стили окна](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure6.png "WindowOverviewFigure6")  
  
 Можно задать <xref:System.Windows.Window.WindowStyle%2A> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используя либо разметку, либо код. Поскольку его вряд ли можно изменить во время существования окна, то лучше всего задать его из разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#WindowStyleWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup2)]  
  
#### Непрямоугольный стиль окна  
 Существуют также ситуации, когда недостаточно стилей границ, предоставляемых <xref:System.Windows.Window.WindowStyle%2A>.  Например, возможно, потребуется создать приложение с непрямоугольной границей, подобно той, которую использует [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)].  
  
 Например, рассмотрим окно типа "Облачко", показанное на следующем рисунке.  
  
 ![Непрямоугольное окно](../../../../docs/framework/wpf/app-development/media/nonrectangularwindowfigure.PNG "NonRectangularWindowFigure")  
  
 Этот тип окна можно создать, задав свойству <xref:System.Windows.Window.WindowStyle%2A> значение <xref:System.Windows.WindowStyle>, и с помощью специальной поддержки прозрачности <xref:System.Windows.Window>.  
  
 [!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#TransparentWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup2)]  
  
 Это сочетание значений приводит к тому, что окно отображается полностью прозрачным.  В этом состоянии нельзя использовать элементы оформления неклиентской области окна \(меню "Закрыть", кнопки "Свернуть", "Развернуть" и "Восстановить" и т. д.\).  Следовательно, необходимо предоставить свои собственные.  
  
<a name="Task_Bar_Presence"></a>   
### Наличие панели задач  
 По умолчанию вид окна включает кнопку панели задач, как показано на следующем рисунке.  
  
 ![Окно с кнопкой панели задач](../../../../docs/framework/wpf/app-development/media/windowoverviewfigure7.png "WindowOverviewFigure7")  
  
 Некоторые типы окон не имеют кнопки панели задач, например окна сообщений и диалоговые окна \(см. [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)\).  Можно управлять отображением кнопки панели задач окна с помощью свойства <xref:System.Windows.Window.ShowInTaskbar%2A> \(по умолчанию `true`\).  
  
 [!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
[!code-xml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup2)]  
  
<a name="SecurityConsiderations"></a>   
## Вопросы безопасности  
 <xref:System.Windows.Window> требует создания разрешения безопасности `UnmanagedCode`.  Для приложений, установленных и запускаемых с локального компьютера, они включены в набор разрешений, которые предоставляются приложению.  
  
 Однако для приложений, запускаемых из Интернета или локальной интрасети с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)], они не попадут в этот набор разрешений.  Следовательно, пользователи будут получать предупреждение безопасности [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] и необходимо расширить набор разрешений приложения до полного доверия.  
  
 Кроме того, по умолчанию [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не может отображать окна или диалоговые окна.  Вопросы безопасности в автономных приложениях рассматриваются в разделе [Стратегия безопасности WPF — безопасность платформы](../../../../docs/framework/wpf/wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## Другие типы окон  
 <xref:System.Windows.Navigation.NavigationWindow> представляет собой окно, предназначенное для предоставления навигации по содержимому.  Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Диалоговые окна являются окнами, которые часто используются для сбора сведений от пользователя, необходимых для выполнения функции.  Например, когда пользователь хочет открыть файл, то обычно приложение отображает диалоговое окно **Открытие файла** для получения имени файла от пользователя.  Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
## См. также  
 <xref:System.Windows.Window>   
 <xref:System.Windows.MessageBox>   
 <xref:System.Windows.Navigation.NavigationWindow>   
 <xref:System.Windows.Application>   
 [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md)   
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)