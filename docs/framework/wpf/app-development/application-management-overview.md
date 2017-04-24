---
title: "Общие сведения об управлении приложением | Microsoft Docs"
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
  - "управление приложениями [WPF]"
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
caps.latest.revision: 56
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 52
---
# Общие сведения об управлении приложением
Все приложения имеют тенденцию совместно использовать общий набор функциональных возможностей, которая применяется к реализации и управлению приложения.  В этом разделе приводится обзор описаний функциональности в <xref:System.Windows.Application> класс для создания и управления приложениями.  
  
   
  
## Класс приложения  
 IN [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]общую функциональность, инкапсулируются в области определения приложения  <xref:System.Windows.Application> класс.  <xref:System.Windows.Application> класс включает в себя следующие функциональные возможности:  
  
-   Отслеживание и взаимодействие со временем жизни приложения.  
  
-   Извлечение и обработка параметров командной строки.  
  
-   Обнаружение и реагирование на необработанные исключения.  
  
-   Совместное использование свойств области приложения и ресурсов.  
  
-   Управление окнами в автономных приложениях.  
  
-   Отслеживание и управление ими навигация.  
  
<a name="The_Application_Class"></a>   
## Как выполнить типичные задачи с помощью класса приложения  
 Если нет необходимости в всех сведениях <xref:System.Windows.Application> класс, в следующей таблице перечислены некоторые из наиболее распространенных задач  <xref:System.Windows.Application> и выполнить их.  Просмотр связанных с API и темы, можно найти дополнительные сведения и образец кода.  
  
|Задача|Подход|  
|------------|------------|  
|Возвращает объект, представляющий текущее приложение|Используйте свойство <xref:System.Windows.Application.Current%2A?displayProperty=fullName>.|  
|Добавьте экран запуска приложения|Дополнительные сведения см. в разделе [Добавление в WPF\-приложение экрана\-заставки](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Запуск приложения|Воспользуйтесь методом <xref:System.Windows.Application.Run%2A?displayProperty=fullName>.|  
|Остановить приложение|Используйте метод <xref:System.Windows.Application.Shutdown%2A> объекта <xref:System.Windows.Application.Current%2A?displayProperty=fullName>.|  
|Получение аргументов из командной строки|Handle <xref:System.Windows.Application.Startup?displayProperty=fullName> событие и использует  <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=fullName> свойство.  Пример см. в разделе <xref:System.Windows.Application.Startup?displayProperty=fullName> событие.|  
|Получение и установка код завершения приложения|Установка <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=fullName> свойство  <xref:System.Windows.Application.Exit?displayProperty=fullName> обработчик событий или вызывает  <xref:System.Windows.Application.Shutdown%2A> метод и передайте целое число.|  
|Обнаружение и ответ на необработанные исключения|Обработайте событие <xref:System.Windows.Application.DispatcherUnhandledException>.|  
|Получение и задание ресурсов области определения приложения|Используйте свойство <xref:System.Windows.Application.Resources%2A?displayProperty=fullName>.|  
|Использование словаря ресурсов области определения приложения|Дополнительные сведения см. в разделе [Использование словаря ресурсов области определения приложения](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Получение и задание свойств области определения приложения|Используйте свойство <xref:System.Windows.Application.Properties%2A?displayProperty=fullName>.|  
|Получение и сохранить состояние приложения|Дополнительные сведения см. в разделе [Сохранение и восстановление свойств области определения приложения в сеансах приложения](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Управление им файлы данных non\-кода, включая файлы ресурсов, файлы содержимого и файлы сайт \-\- начала координат.|Дополнительные сведения см. в разделе [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Управление окнами в автономных приложениях|Дополнительные сведения см. в разделе [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).|  
|Отслеживание и управление навигация|Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## Определение приложения  
 Использовать функции <xref:System.Windows.Application> класс, следует реализовать определение приложения.  Определение приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] представляет собой класс, производный от <xref:System.Windows.Application> и настроенный со специальным параметром [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)].  
  
### Реализация определения приложения  
 Обычное определение приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализуется с помощью разметки и фонового кода.  Это позволяет использовать разметку для декларативного задания свойств, ресурсов и регистрации событий приложения во время обработки событий и реализации поведения приложения в фоновом коде.  
  
 В следующем примере показано, как реализовать определение приложения с помощью разметки и фонового кода:  
  
 [!code-xml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Чтобы разрешить файл разметки и файл кода программной части для совместной работы, нужно следующее:  
  
-   В разметке элемент `Application` должен включать атрибут `x:Class`.  При построении приложения существование `x:Class` в файле разметки приводит к тому, что [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] создает класс `partial`, который является производным от <xref:System.Windows.Application> и имя которого определяется атрибутом `x:Class`.  Для этого требуется добавить объявление пространства имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в схему [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`\).  
  
-   В фоновом коде класс должен быть `partial` классом с тем же именем, которое определяется атрибутом `x:Class` в разметке, и он должен быть производным от <xref:System.Windows.Application>.  Это позволяет связать файл кода программной части с классом `partial`, созданным для файла разметки при построении приложения \(см. раздел [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)\).  
  
> [!NOTE]
>  При создании нового проекта приложения WPF или проекта приложения браузера WPF с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], определение приложения включается по умолчанию и определяется с помощью разметки и фонового кода.  
  
 Этот код является минимумом, необходимым для реализации определения приложения.  Однако, должна быть создана дополнительная конфигурация [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] для определения приложения до построения и запуска приложения.  
  
### Настройка определения приложения для MSBuild  
 Автономные приложения и [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] требуют реализацию инфраструктуры определенного уровня перед своим запуском.  Наиболее важной частью этой инфраструктуры является точка входа.  При запуске пользователем приложения, операционная система вызывает точку входа, которая является известной функцией для запуска приложений.  
  
 Обычно разработчики должны были написать часть или весь этот код для себя, в зависимости от технологии.  Однако [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] создает этот код для вас при настройке файла разметки вашего определения приложения в качестве элемента [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition`, как показано в следующем файле проекта [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)]:  
  
```  
<Project   
  DefaultTargets="Build"  
  xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Так как файл кода программной части содержит код, он помечается как элемент [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile`, как обычный.  
  
 Применение этих конфигураций [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] к файлам разметки и файлам кода программной части определения приложения заставляет [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] создавать код следующим образом:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 Результирующий код дополняет ваше определение приложения дополнительным кодом инфраструктуры, которая включает метод точки входа `Main`.  Атрибут <xref:System.STAThreadAttribute> применяется к методу `Main` для указания того, что основной поток [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] является STA\-потоком, который необходим для приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. При своем вызове метод `Main` создает новый экземпляр класса `App` до вызова метода `InitializeComponent` для регистрации событий и установки свойств, реализованных в разметке.  Поскольку `InitializeComponent` создан для вас, вам не требуется явно вызывать `InitializeComponent` из определения приложения как для реализаций <xref:System.Windows.Controls.Page> и <xref:System.Windows.Window>.  Наконец, вызывается метод <xref:System.Windows.Application.Run%2A> для запуска приложения.  
  
<a name="Getting_the_Current_Application"></a>   
## Получение текущего приложения  
 Поскольку функциональные возможности <xref:System.Windows.Application> класс совместно используется приложение может составлял только один экземпляр  <xref:System.Windows.Application> класс  <xref:System.AppDomain>.  Для применения этого, класс <xref:System.Windows.Application> реализуется как одноэлементный класс \(см. раздел [Реализация Singleton в C\#](http://go.microsoft.com/fwlink/?LinkId=100567)\), который создает один экземпляр самого себя и обеспечивает общий доступ к нему с помощью свойства `static` <xref:System.Windows.Application.Current%2A>.  
  
 Следующий фрагмент кода иллюстрирует получение ссылки на объект <xref:System.Windows.Application> для текущего <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> возвращает ссылку на экземпляр класса <xref:System.Windows.Application>.  Если вам требуется ссылка на ваш производный класс <xref:System.Windows.Application>, вам необходимо привести значение свойства <xref:System.Windows.Application.Current%2A>, как показано в следующем примере.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Можно проверить значение <xref:System.Windows.Application.Current%2A> в любой момент времени жизни объекта <xref:System.Windows.Application>.  Однако следует соблюдать осторожность.  После того, как создается класс <xref:System.Windows.Application>, есть период, в течение которого состояние объекта <xref:System.Windows.Application> непредсказуемо.  В течение этого периода <xref:System.Windows.Application> выполняет различные задачи инициализации, необходимые коду для выполнения, включая установку инфраструктуры приложений, настройку свойств и регистрацию событий.  Если использовать объект <xref:System.Windows.Application> в течение этого периода, то выполнение кода может привести к неожиданным результатам, особенно если он зависит от различных установленных свойств <xref:System.Windows.Application>.  
  
 Когда <xref:System.Windows.Application> завершает свою работу инициализации, начинается его время жизни.  
  
<a name="Application_Lifetime"></a>   
## Время жизни приложения  
 Время жизни приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] помечено несколькими событиями, которые вызываются <xref:System.Windows.Application>, чтобы позволить вам знать, когда ваше приложении запущено, активировано, отключено и завершило работу.  
  
   
  
<a name="Splash_Screen"></a>   
### Экран\-заставка  
 Начиная с версии [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], можно указать изображение, которое должно использоваться в окне запуска, или на *экране\-заставке*.  Класс <xref:System.Windows.SplashScreen> позволяет легко отобразить окно запуска во время загрузки приложения.  Окно <xref:System.Windows.SplashScreen> создается и отображается перед вызовом <xref:System.Windows.Application.Run%2A>.  Дополнительные сведения см. в разделах [Время запуска приложения](../../../../docs/framework/wpf/advanced/application-startup-time.md) и [Добавление в WPF\-приложение экрана\-заставки](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### Запуск приложения  
 После того как <xref:System.Windows.Application.Run%2A> вызвано и инициализировано приложение, приложение готово к выполнению.  Этим моментом принимается вызов события <xref:System.Windows.Application.Startup>:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 В этот момент жизни приложения наиболее обычной вещью является показ [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### Отображение интерфейса пользователя  
 Большинство автономных приложений [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] открывают <xref:System.Windows.Window>, когда они начинают выполнение.  Обработчик событий <xref:System.Windows.Application.Startup> является одним расположением, откуда вы можете сделать это, как продемонстрировано следующим кодом.  
  
 [!code-xml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Первое <xref:System.Windows.Window>, создающееся в автономном приложении становится главным окном приложения по умолчанию.  Этот объект <xref:System.Windows.Window> ссылается на свойство <xref:System.Windows.Application.MainWindow%2A?displayProperty=fullName>.  Значение свойства <xref:System.Windows.Application.MainWindow%2A> может быть изменено программными средствами, если другое окно <xref:System.Windows.Window> станет главным окном.  
  
 При первом запуске [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], оно скорее всего перейдет на <xref:System.Windows.Controls.Page>.  Это показано в следующем коде.  
  
 [!code-xml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 Если вы обрабатываете <xref:System.Windows.Application.Startup> только чтобы открыть <xref:System.Windows.Window> или перейти на <xref:System.Windows.Controls.Page>, вместо этого вы можете установить атрибут `StartupUri` в разметке.  
  
 В следующем примере показано использование <xref:System.Windows.Application.StartupUri%2A> из изолированного приложения для открытия <xref:System.Windows.Window>.  
  
 [!code-xml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Application.StartupUri%2A> из [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], чтобы перейти на <xref:System.Windows.Controls.Page>.  
  
 [!code-xml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Эта разметка действует так же, как и предыдущий код для открытия окна.  
  
> [!NOTE]
>  Дополнительные сведения о навигации содержатся в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 Вам необходимо обрабатывать событие <xref:System.Windows.Application.Startup>, чтобы открыть <xref:System.Windows.Window>, если вам необходимо создать его экземпляр с помощью конструктора не по умолчанию или вам необходимо задать его свойства или подписаться на его события перед его отображением, или вам необходимо обработать любые аргументы командной строки, которые были заданы при запуске приложения.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### Обработка аргументов командной строки  
 В [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] автономные приложения можно запустить из командной строки или с рабочего стола.  В обоих случаях аргументы командной строки могут быть переданы приложению. В следующем примере показано приложение, которое запускается с одним аргументом командной строки, "\/StartMinimized":  
  
 `wpfapplication.exe /StartMinimized`  
  
 Во время инициализации приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] получает аргументы командной строки из операционной системы и передает их обработчику событий <xref:System.Windows.Application.Startup> с помощью свойства <xref:System.Windows.StartupEventArgs.Args%2A> параметра <xref:System.Windows.StartupEventArgs>.  Можно извлечь и сохранить аргументы командной строки с помощью следующего кода.  
  
 [!code-xml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Код обрабатывает <xref:System.Windows.Application.Startup>, чтобы проверить, передан ли аргумент командной строки **\/StartMinimized**; если это так, он открывает главное окно с <xref:System.Windows.WindowState> <xref:System.Windows.WindowState>.  Обратите внимание, что поскольку свойство <xref:System.Windows.Window.WindowState%2A> должно быть установлено программными средствами, главное <xref:System.Windows.Window> должно быть явным образом открыто в коде.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не может получить и обработать аргументы командной строки, так как они загружены с помощью развертывания [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] \(см.: [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)\).  Однако они могут извлекать и обрабатывать строковые параметры запроса из URL\-адресов, которые используются для их запуска.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### Активация и деактивация приложения  
 [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] позволяет пользователям переключаться между приложениями. Наиболее простой способ — использовать сочетание клавиш ALT \+ TAB.  Приложение может быть переключено, только если оно содержит видимое <xref:System.Windows.Window>, которое пользователь может выбрать.  Выбранный в данный момент объект <xref:System.Windows.Window> является *активным окном* \(также известным как *окно переднего плана*\), и именно <xref:System.Windows.Window> получает входные данные пользователя. Приложение с активным окном является *активным приложением* \(или *приложением переднего плана*\). Приложение становится активным в следующих случаях:  
  
-   Оно запущено и показывает <xref:System.Windows.Window>.  
  
-   Пользователь переключается из другого приложения, выбрав <xref:System.Windows.Window> в приложении.  
  
 Вы можете обнаружить, что приложение активируется при обработке события <xref:System.Windows.Application.Activated?displayProperty=fullName>.  
  
 Аналогичным образом приложение может стать неактивным в следующих случаях:  
  
-   Пользователь переключается на другое приложение из текущего.  
  
-   Когда приложение завершает работу.  
  
 Вы можете обнаружить, что приложение дезактивируется при обработке события <xref:System.Windows.Application.Deactivated?displayProperty=fullName>.  
  
 Следующий фрагмент кода показывает, как обрабатывать события <xref:System.Windows.Application.Activated> и <xref:System.Windows.Application.Deactivated>, чтобы определить, активно ли приложение.  
  
 [!code-xml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 <xref:System.Windows.Window> также может быть активировано и дезактивировано.  Дополнительные сведения см. в разделах <xref:System.Windows.Window.Activated?displayProperty=fullName> и <xref:System.Windows.Window.Deactivated?displayProperty=fullName>.  
  
> [!NOTE]
>  Ни <xref:System.Windows.Application.Activated?displayProperty=fullName>, ни <xref:System.Windows.Application.Deactivated?displayProperty=fullName> не вызывается для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Application_Shutdown"></a>   
### Завершение работы приложения  
 Время жизни приложения заканчивается, когда оно завершает работу, что может возникнуть по следующим причинам:  
  
-   Пользователь закрывает каждое <xref:System.Windows.Window>.  
  
-   Пользователь закрывает основное <xref:System.Windows.Window>.  
  
-   Пользователь завершает сеанс [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] выходом или завершением работы.  
  
-   Выполнено специальное условие для приложения.  
  
 Чтобы помочь вам в управлении завершением работы приложения, <xref:System.Windows.Application> предоставляет метод <xref:System.Windows.Application.Shutdown%2A>, свойство <xref:System.Windows.Application.ShutdownMode%2A>, и события <xref:System.Windows.Application.SessionEnding> и <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> может вызываться только из приложений, имеющих <xref:System.Security.Permissions.UIPermission>.  У автономных приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] всегда есть это разрешение.  Однако [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], выполняющееся в изолированной среде безопасности частичного доверия зоны Интернета, не обладают им.  
  
#### Режим завершения работы  
 Большинство приложений завершают работу при закрытии главного окна или при закрытии всех окон.  Иногда, однако, другие условия конкретного приложения могут определить, когда приложение завершает работу.  Можно задать условия при которых ваше приложение завершит работу установкой <xref:System.Windows.Application.ShutdownMode%2A> с помощью одного из следующих перечисленных значений <xref:System.Windows.ShutdownMode>:  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
-   <xref:System.Windows.ShutdownMode>  
  
 По умолчанию значение <xref:System.Windows.Application.ShutdownMode%2A> является <xref:System.Windows.ShutdownMode>, которое означает, что приложение автоматически завершает работу при закрытии пользователем последнего окна в приложении.  Однако если ваше приложение должно быть завершено при закрытии главного окна, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автоматически делает это, если вы установите <xref:System.Windows.Application.ShutdownMode%2A> в <xref:System.Windows.ShutdownMode>.  Это показано в следующем примере.  
  
 [!code-xml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 Когда у вас есть конкретные условия завершения работы приложения, установите <xref:System.Windows.Application.ShutdownMode%2A> в <xref:System.Windows.ShutdownMode>.  В этом случае ответственность завершить работу приложения, явно вызвав метод <xref:System.Windows.Application.Shutdown%2A> будет возложена на вас; в противном случае приложение продолжит выполнение, даже если все окна будут закрыты.  Обратите внимание на то, что <xref:System.Windows.Application.Shutdown%2A> вызывается неявно, когда <xref:System.Windows.Application.ShutdownMode%2A> установлено в <xref:System.Windows.ShutdownMode> или <xref:System.Windows.ShutdownMode>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> может быть задано из [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], но оно игнорируется;[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] всегда завершает работу, когда оно уходит из браузера или при закрытии браузера, на котором размещен [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### Завершение сеанса  
 Условия завершения работы, которые описаны свойством <xref:System.Windows.Application.ShutdownMode%2A> являются специфическими для приложения.  Хотя, в некоторых случаях, приложение может завершить работу в результате выполнения внешнего условия.  Наиболее обычное внешнее условие возникает, когда пользователь завершает сеанс [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] при выполнении следующих действий:  
  
-   Выход  
  
-   Завершение работы  
  
-   Перезапуск  
  
-   Спящий режим  
  
 Чтобы обнаружить, когда завершается сеанс [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)], вы можете обработать событие <xref:System.Windows.Application.SessionEnding>, как показано в следующем примере.  
  
 [!code-xml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 В этом примере код проверяет свойство <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> для определения способа завершения сеанса [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  Он использует это значение, чтобы отобразить сообщение подтверждения пользователю.  Если пользователю не нужно завершать сеанс, код устанавливает <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> в `true`, чтобы запретить завершение сеанса [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> не вызывается для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### Exit  
 При завершении работы приложения может возникнуть необходимость выполнить некоторую последнюю обработку, такую как сохранение состояния приложения.  В этих ситуациях можно обработать событие <xref:System.Windows.Application.Exit>.  
  
 [!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Полный пример см. в разделе [Сохранение и восстановление свойств области определения приложения в сеансах приложения](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> может обрабатываться автономными приложениями и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> вызывается в следующих случаях:  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] уходит из обозревателя.  
  
-   В [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], при закрытии вкладки, на которой размещены [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   При закрытии браузера.  
  
#### Код выхода  
 Приложения в основном загружаются операционной системой в ответ на запрос пользователя.  Однако приложение может быть запущено другим приложением для выполнения некоторой определенной задачи.  При завершении работы запущенного приложения, ему может понадобиться выяснить условие, при котором запущенное приложение завершит работу.  В этих случаях [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)] позволяет приложениям вернуть код выхода приложения при завершении работы.  По умолчанию приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] возвращают значение кода выхода равным 0.  
  
> [!NOTE]
>  При отладке из [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], код завершения приложения отображается в окне **Вывод**, когда приложение завершает работу, в сообщении, которое выглядит следующим образом:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  Выберите в меню **Вид** пункт **Вывод**, чтобы открыть окно **Вывод**.  
  
 Чтобы изменить код выхода, вы можете вызвать перегрузку <xref:System.Windows.Application.Shutdown%28System.Int32%29>, которая принимает целочисленный аргумент для кода выхода:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Вы можете определить значение кода выхода и изменить его, обработав событие <xref:System.Windows.Application.Exit>.  Обработчик событий <xref:System.Windows.Application.Exit> передает <xref:System.Windows.ExitEventArgs>, который обеспечивает доступ к коду выхода со свойством <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>.  Дополнительные сведения см. в разделе <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Вы можете задать код выхода в автономных приложениях и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  Однако значение кода выхода игнорируется для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### Необработанные исключения.  
 Иногда приложение может завершить работу вниз по неправильным условиям, например, когда создается непредвиденное исключение.  В этом случае в приложении может не быть кода для обнаружения и обработки исключений.  Этот тип исключения является необработанным исключением; уведомление, сходное с показанным на следующем рисунке, отображается перед закрытием приложения.  
  
 ![Уведомление о необработанном исключении](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 С точки зрения работы пользователя для приложения лучше всего избежать этого поведения по умолчанию, выполнив некоторое или все из следующего:  
  
-   Отображение удобных для пользователя данных.  
  
-   Попытка сохранить выполнение приложения.  
  
-   Запись подробных, понятных разработчику особых сведений в журнале событий [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Реализация этой поддержки зависит от возможности обнаружить необработанные исключения, при которых возникает событие <xref:System.Windows.Application.DispatcherUnhandledException>.  
  
 [!code-xml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 Обработчик событий <xref:System.Windows.Application.DispatcherUnhandledException> передает параметр <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs>, содержащий контекстные сведения, касающиеся необработанного исключения, включая исключение самого себя \(<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=fullName>\).  Можно использовать эту информацию для определения способа обработки исключений.  
  
 Когда вы обрабатываете <xref:System.Windows.Application.DispatcherUnhandledException>, вы должны установить свойство <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=fullName> в `true`; в противном случае [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] по\-прежнему рассматривает необработанное исключение и возвращается к поведению по умолчанию, описанному выше.  Если возникает необработанное исключение и событие <xref:System.Windows.Application.DispatcherUnhandledException> не обрабатывается, или событие обрабатывается и <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> устанавливается в `false`, приложение немедленно завершает работу.  Кроме того, никакие другие события <xref:System.Windows.Application> не вызываются.  Следовательно, вам необходимо обработать <xref:System.Windows.Application.DispatcherUnhandledException>, если ваше приложение имеет код, который должен запускаться перед завершением работы приложения.  
  
 Хотя приложение может завершить работу в результате выполнения необработанного исключения, приложение обычно завершает работу в ответ на запрос пользователя, как описано в следующем разделе.  
  
<a name="Application_Lifetime_Events"></a>   
### События времени жизни приложения  
 Значения времени существования автономных приложений и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не совпадают. На следующем рисунке демонстрируются ключевые события времени существования автономного приложения и показана последовательность, в которой они создаются.  
  
 ![Автономное приложение – события объекта приложения](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview\_ApplicationObjectEvents")  
  
 Аналогично, на следующем рисунке показаны ключевые события во времени жизни [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] и показана последовательность, в которой они вызываются.  
  
 ![XBAP – события объекта приложения](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview\_ApplicationObjectEvents\_xbap")  
  
## См. также  
 <xref:System.Windows.Application>   
 [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)   
 [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md)   
 [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)   
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [Application Model: How\-to Topics](http://msdn.microsoft.com/ru-ru/76771b09-3688-4d1c-8818-9b3f4cf39a30)   
 [Разработка приложений](../../../../docs/framework/wpf/app-development/index.md)