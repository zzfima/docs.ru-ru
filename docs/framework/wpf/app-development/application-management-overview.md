---
title: Общие сведения об управлении приложением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: ee72925ceab37e871dc1a79a6260fca38bd5513c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="application-management-overview"></a>Общие сведения об управлении приложением
Все приложения имеют тенденцию совместно использовать общий набор функциональных возможностей, который применяется к реализации приложения и управлению им. Этот раздел содержит обзор функций в <xref:System.Windows.Application> класс для создания и управления приложениями.  
   
  
## <a name="the-application-class"></a>Класс Application  
 В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], общие функциональные возможности области приложения, содержащийся в <xref:System.Windows.Application> класса. <xref:System.Windows.Application> Класс включает в себя следующие функциональные возможности:  
  
-   отслеживание и взаимодействие со временем существования приложения;  
  
-   извлечение и обработка параметров командной строки;  
  
-   обнаружение необработанных исключений и реагирование на них;  
  
-   совместное использование свойств области определения приложения и ресурсов;  
  
-   управление окнами в автономных приложениях;  
  
-   отслеживание навигации и управление ею.  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Выполнение стандартных задач с помощью класса приложения  
 Если вы не интересуют все детали <xref:System.Windows.Application> класса, в следующей таблице перечислены некоторые распространенные задачи по <xref:System.Windows.Application> и порядок их выполнения. Чтобы получить дополнительные сведения и образец кода, просмотрите связанные API и разделы.  
  
|Задача|Подход|  
|----------|--------------|  
|Получение объекта, представляющего текущее приложение|Используйте свойство <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|  
|Добавление заставки в приложение|В разделе [добавить экран-заставку для приложения WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).|  
|Запуск приложения|Воспользуйтесь методом <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|  
|Остановка приложения|Используйте <xref:System.Windows.Application.Shutdown%2A> метод <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> объекта.|  
|Получение аргументов из командной строки|Обрабатывать <xref:System.Windows.Application.Startup?displayProperty=nameWithType> событий и использование <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> свойство. Пример см. в разделе <xref:System.Windows.Application.Startup?displayProperty=nameWithType> событий.|  
|Получение и задание кода завершения приложения|Задать <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> свойство в <xref:System.Windows.Application.Exit?displayProperty=nameWithType> обработчик событий, или вызов <xref:System.Windows.Application.Shutdown%2A> метод и передайте его в целое число.|  
|Обнаружение необработанных исключений и реагирование на них|Обрабатывать <xref:System.Windows.Application.DispatcherUnhandledException> событий.|  
|Получение и задание ресурсов области определения приложения|Используйте свойство <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|  
|Использование словаря ресурсов области определения приложения|В разделе [использование словаря ресурсов области приложения](../../../../docs/framework/wpf/app-development/how-to-use-an-application-scope-resource-dictionary.md).|  
|Получение и задание свойств области определения приложения|Используйте свойство <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|  
|Получение и сохранение состояния приложения|В разделе [сохранение и восстановление свойств области приложения между сеансами приложения](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).|  
|Управление файлами данных без кода, включая файлы ресурсов, файлы содержимого и файлы исходного сайта.|В разделе [ресурса приложения WPF, содержимое и файлы данных](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).|  
|Управление окнами в автономных приложениях|См. раздел [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).|  
|Отслеживание навигации и управление ею|В разделе [Общие сведения о навигации](../../../../docs/framework/wpf/app-development/navigation-overview.md).|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a>Определение приложения  
 Чтобы использовать функциональные возможности <xref:System.Windows.Application> класса, необходимо реализовать определение приложения. Объект [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] определение приложения — это класс, производный от <xref:System.Windows.Application> и настроен со специальным [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] параметр.  
  
### <a name="implementing-an-application-definition"></a>Реализация определения приложения  
 Типичный [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] определение приложения реализуется с помощью разметки и кода. Это позволяет использовать разметку для декларативного задания свойств и ресурсов приложения и регистрации событий, а обработку событий и поведение приложения реализовывать в коде программной части.  
  
 В следующем примере показано, как реализовать определение приложения с помощью разметки и кода программной части:  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 Для совместной работы файла разметки и файла кода программной части должны выполняться указанные ниже условия.  
  
-   В разметке `Application` элемент должен включать `x:Class` атрибута. При построении приложения существование `x:Class` в разметке вызывает файл [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] для создания `partial` класс, производный от <xref:System.Windows.Application> и имеет имя, которое определяется `x:Class` атрибута. Для этого необходимо добавление [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] объявление пространства имен для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] схемы ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).  
  
-   В коде программной части, класс должен быть `partial` класс с тем же именем, который задается параметром `x:Class` атрибута в разметке и должен быть производным от <xref:System.Windows.Application>. Это позволяет файл кода должны быть связаны с `partial` класс, который будет создан для файла разметки при построении приложения (см. [построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)).  
  
> [!NOTE]
>  При создании нового проекта приложения WPF или проекта приложения браузера WPF с помощью [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], определение приложения включается по умолчанию и определяется с помощью разметки и кода.  
  
 Этот код является минимумом, необходимым для реализации определения приложения. Тем не менее дополнительный [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] конфигурации должна использоваться только в определении приложения до построения и запуска приложения.  
  
### <a name="configuring-the-application-definition-for-msbuild"></a>Настройка определения приложения для MSBuild  
 Автономные приложения и [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] требуют реализацию инфраструктуры определенного уровня, до их выполнения. Наиболее важной частью этой инфраструктуры является точка входа. При запуске приложения пользователем операционная система вызывает точку входа, которая является известной функцией для запуска приложений.  
  
 Обычно разработчикам требовалось писать весь этот код или его часть самостоятельно в зависимости от технологии. Тем не менее [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] создается этот код при настройке файла разметки определения приложения в качестве [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` элемента, как показано в следующем [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] файл проекта:  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 Так как файл кода содержит код, он помечается как [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `Compile` элемента, как и в случае является нормальным.  
  
 Применение этих [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] конфигурации к файлам разметки и кода программной части определения приложения вызывает [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] для создания кода, как показано ниже:  
  
 [!code-csharp[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode1)]
 [!code-vb[AppDefAugSnippets#AppDefAugCODE1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode1)]  
[!code-csharp[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs#appdefaugcode2)]
[!code-vb[AppDefAugSnippets#AppDefAugCODE2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb#appdefaugcode2)]  
  
 Результирующий код дополняет ваше определение приложения дополнительным кодом инфраструктуры, которая включает метод точки входа `Main`. <xref:System.STAThreadAttribute> Атрибут `Main` метод, чтобы указать, что главный [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] потоков для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения является поток однопотокового Подразделения, которая требуется для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений. При вызове `Main` создает новый экземпляр `App` перед вызовом `InitializeComponent` метод для регистрации событий и задания свойств, реализованных в разметке. Поскольку `InitializeComponent` создается автоматически, не требуется явно вызывать `InitializeComponent` из определения приложения как для <xref:System.Windows.Controls.Page> и <xref:System.Windows.Window> реализации. Наконец <xref:System.Windows.Application.Run%2A> метод вызывается для запуска приложения.  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a>Получение текущего приложения  
 Поскольку функциональные возможности <xref:System.Windows.Application> являются общими для всего приложения, может существовать только один экземпляр <xref:System.Windows.Application> класса на <xref:System.AppDomain>. Для применения этого, <xref:System.Windows.Application> реализован класс как singleton-класса (в разделе [Реализация Singleton в C#](http://go.microsoft.com/fwlink/?LinkId=100567)), который создает один экземпляр самого себя и предоставляет общий доступ к нему с `static` <xref:System.Windows.Application.Current%2A> свойство.  
  
 В следующем коде показано, как получить ссылку на <xref:System.Windows.Application> для текущего <xref:System.AppDomain>.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <xref:System.Windows.Application.Current%2A> Возвращает ссылку на экземпляр <xref:System.Windows.Application> класса. Если требуется ссылку на ваш <xref:System.Windows.Application> производного класса, необходимо привести значение <xref:System.Windows.Application.Current%2A> свойства, как показано в следующем примере.  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 Вы можете проверить значение <xref:System.Windows.Application.Current%2A> в любой момент времени существования <xref:System.Windows.Application> объекта. Однако следует соблюдать осторожность. После <xref:System.Windows.Application> создается экземпляр класса, то период, в течение которого состояние <xref:System.Windows.Application> непредсказуемо. В течение этого периода <xref:System.Windows.Application> выполняет различные задачи инициализации, необходимые для кода для выполнения, включая установку инфраструктуры приложений, настройку свойств и регистрацию событий. При попытке использовать <xref:System.Windows.Application> объекта в течение этого периода, возможно, ваш код непредвиденные результаты, особенно в том случае, если он зависит от различных <xref:System.Windows.Application> свойства задаются.  
  
 Когда <xref:System.Windows.Application> завершает свою работу инициализации начинается времени его существования.  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a>Время существования приложения  
 Время существования [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложение помечено несколькими событиями, которые вызываются <xref:System.Windows.Application> чтобы знать, что был начат приложения активировано, деактивации и завершил работу.  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a>Заставка  
 Начиная с версии [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], можно задать изображение для использования в окне запуска, или *экран-заставка*. <xref:System.Windows.SplashScreen> Класс позволяет легко отобразить окно запуска во время загрузки приложения. <xref:System.Windows.SplashScreen> Окне создается и отображается перед <xref:System.Windows.Application.Run%2A> вызывается. Дополнительные сведения см. в разделе [время запуска приложения](../../../../docs/framework/wpf/advanced/application-startup-time.md) и [добавить экран-заставку для приложения WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a>Запуск приложения  
 После <xref:System.Windows.Application.Run%2A> вызывается и инициализации приложения, приложение готово к запуску. Этим моментом принимается при <xref:System.Windows.Application.Startup> события:  
  
 [!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind1)]
 [!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind1)]  
[!code-csharp[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#startupcodebehind2)]
[!code-vb[ApplicationStartupSnippets#StartupCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#startupcodebehind2)]  
  
 На этом этапе в жизни приложения наиболее распространенный способ — показать [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
<a name="Showing_a_User_Interface"></a>   
### <a name="showing-a-user-interface"></a>Отображение пользовательского интерфейса  
 Большинство автономных приложений Windows откройте <xref:System.Windows.Window> когда начинается выполнение. <xref:System.Windows.Application.Startup> Обработчик событий — одно расположение, из которого можно сделать это, как показано в следующем примере кода.  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  Первый <xref:System.Windows.Window> создающееся в автономное приложение становится главного окна приложения по умолчанию. Это <xref:System.Windows.Window> ссылается объект <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> свойство. Значение <xref:System.Windows.Application.MainWindow%2A> свойство может быть изменено программными средствами, если другое окно первый экземпляр <xref:System.Windows.Window> должно быть главного окна.  
  
 Когда [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] первого запуска, он скорее, чтобы перейти <xref:System.Windows.Controls.Page>. Это показано в приведенном ниже коде.  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 При обработке <xref:System.Windows.Application.Startup> открывать только <xref:System.Windows.Window> или перейдите к <xref:System.Windows.Controls.Page>, можно задать `StartupUri` атрибутом в разметке.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Application.StartupUri%2A> из отдельного приложения, чтобы открыть <xref:System.Windows.Window>.  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 В следующем примере показано, как использовать <xref:System.Windows.Application.StartupUri%2A> из [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] для перехода к <xref:System.Windows.Controls.Page>.  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 Эта разметка действует так же, как и предыдущий код для открытия окна.  
  
> [!NOTE]
>  Дополнительные сведения о навигации в разделе [Общие сведения о навигации](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 При необходимости обработки <xref:System.Windows.Application.Startup> события, чтобы открыть <xref:System.Windows.Window> необходимо создать экземпляр с помощью конструктора не по умолчанию, или необходимо задать его свойства или подписаться на его события перед его отображением необходимо полностью обработать все аргументы командной строки, были заданы при запуске приложения.  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a>Обработка аргументов командной строки  
 В Windows автономные приложения можно запустить из командной строки или с рабочего стола. В обоих случаях аргументы командной строки могут быть переданы приложению. В приведенном ниже примере показано приложение, которое запускается с одним аргументом командной строки /StartMinimized:  
  
 `wpfapplication.exe /StartMinimized`  
  
 Во время инициализации приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] извлекает аргументы командной строки от операционной системы и передает их <xref:System.Windows.Application.Startup> обработчиком событий с помощью <xref:System.Windows.StartupEventArgs.Args%2A> свойство <xref:System.Windows.StartupEventArgs> параметр. Аргументы командной строки можно извлечь и сохранить с помощью приведенного ниже кода.  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 Код обрабатывает <xref:System.Windows.Application.Startup> для проверки ли **/StartMinimized** предоставленный аргумент командной строки, в этом случае он открывает главное окно с <xref:System.Windows.WindowState> из <xref:System.Windows.WindowState.Minimized>. Обратите внимание, что поскольку <xref:System.Windows.Window.WindowState%2A> свойство должно быть задано программным путем, главный <xref:System.Windows.Window> должен открываться явно в коде.  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не удается получить и обработать аргументы командной строки, так как они запускаются с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] развертывания (см. [развертывания приложения WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)). Однако они могут извлекать и обрабатывать строковые параметры запроса из URL-адресов, которые используются для их запуска.  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a>Активация и отключение приложения  
 Windows пользователи могут переключаться между приложениями. Наиболее простой способ — использовать клавиши ALT+TAB. Приложение может быть переключено, только если оно содержит видимое <xref:System.Windows.Window> , может выбрать пользователь. Выбранный в данный момент <xref:System.Windows.Window> — *активного окна* (также известный как *окно переднего плана*) и <xref:System.Windows.Window> , получающий ввод данных пользователем. Приложение с активным окном *активного приложения* (или *активным*). Приложение становится активным в указанных ниже случаях.  
  
-   Он запускается и показывает <xref:System.Windows.Window>.  
  
-   Пользователь переключается из другого приложения, выбрав <xref:System.Windows.Window> в приложении.  
  
 Можно обнаружить, когда приложение активируется при обработке <xref:System.Windows.Application.Activated?displayProperty=nameWithType> событий.  
  
 Аналогичным образом приложение может стать неактивным в указанных ниже случаях.  
  
-   Пользователь переключается на другое приложение из текущего.  
  
-   Приложение завершает работу.  
  
 Можно обнаружить, когда приложение становится неактивным, обрабатывая <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> событий.  
  
 Следующий код иллюстрирует обработку <xref:System.Windows.Application.Activated> и <xref:System.Windows.Application.Deactivated> событий, чтобы определить, активен ли приложение.  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 Объект <xref:System.Windows.Window> также можно активировать и деактивировать. Дополнительные сведения см. в разделах <xref:System.Windows.Window.Activated?displayProperty=nameWithType> и <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.  
  
> [!NOTE]
>  Ни <xref:System.Windows.Application.Activated?displayProperty=nameWithType> , ни <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> возникает для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a>Завершение работы приложения  
 Время существования приложения заканчивается, когда оно завершает работу, что может возникнуть по указанным ниже причинам.  
  
-   Пользователь закрывает каждый <xref:System.Windows.Window>.  
  
-   Пользователь закрывает главный <xref:System.Windows.Window>.  
  
-   Пользователь завершает сеанс Windows с выходом из системы или завершает работу.  
  
-   Выполнено специальное условие для приложения.  
  
 Для управления завершением работы приложения, <xref:System.Windows.Application> предоставляет <xref:System.Windows.Application.Shutdown%2A> метода <xref:System.Windows.Application.ShutdownMode%2A> свойство и <xref:System.Windows.Application.SessionEnding> и <xref:System.Windows.Application.Exit> события.  
  
> [!NOTE]
>  <xref:System.Windows.Application.Shutdown%2A> может вызываться только из приложений, имеющих <xref:System.Security.Permissions.UIPermission>. Автономный [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения всегда имеют такое разрешение. Однако [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не работает в изолированной среде безопасности частичного доверия зоны Интернета.  
  
#### <a name="shutdown-mode"></a>Режим завершения работы  
 Большинство приложений завершают работу при закрытии главного окна или всех окон. Иногда, однако, другие условия конкретного приложения могут определить, когда приложение завершает работу. Можно указать условия, при которых приложение завершит работу, задав <xref:System.Windows.Application.ShutdownMode%2A> с одним из следующих <xref:System.Windows.ShutdownMode> значения перечисления:  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 Значение по умолчанию <xref:System.Windows.Application.ShutdownMode%2A> — <xref:System.Windows.ShutdownMode.OnLastWindowClose>, что означает, что приложение автоматически завершает работу при закрытии последнего окна в приложении пользователь. Тем не менее, если приложение необходимо завершить работу при закрытии главного окна, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] автоматически, если не задать <xref:System.Windows.Application.ShutdownMode%2A> для <xref:System.Windows.ShutdownMode.OnMainWindowClose>. Эти действия показаны в следующем примере.  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 При наличии условия завершения работы приложения, следует установить <xref:System.Windows.Application.ShutdownMode%2A> для <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. В этом случае он будет необходимо завершить работу приложения путем явного вызова <xref:System.Windows.Application.Shutdown%2A> метода; в противном случае приложение будет продолжать работать даже в случае закрытия всех окон. Обратите внимание, что <xref:System.Windows.Application.Shutdown%2A> вызывается неявно при <xref:System.Windows.Application.ShutdownMode%2A> либо <xref:System.Windows.ShutdownMode.OnLastWindowClose> или <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
> [!NOTE]
>  <xref:System.Windows.Application.ShutdownMode%2A> может принимать значения от [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], но учитывается; [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] всегда завершает работу при его переходе в браузере или в случаях, когда браузер, в котором размещается [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] закрыт. Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
#### <a name="session-ending"></a>Завершение сеанса  
 Завершение работы условия, которые описаны в документах <xref:System.Windows.Application.ShutdownMode%2A> свойства конкретного приложения. Однако в некоторых случаях приложение может завершить работу в результате выполнения внешнего условия. Наиболее распространенные внешних состояние возникает, когда пользователь завершает сеанс Windows при выполнении следующих действий:  
  
-   выход из системы;  
  
-   завершение работы;  
  
-   перезапуск;  
  
-   спящий режим.  
  
 Чтобы обнаружить при завершении сеанса Windows, можно обрабатывать <xref:System.Windows.Application.SessionEnding> события, как показано в следующем примере.  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 В этом примере код проверяет <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> свойства, чтобы определить, каким образом Windows сессии. Он использует это значение, чтобы отобразить сообщение подтверждения для пользователя. Если пользователь не требуется завершать сеанс, код задает <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> для `true` чтобы предотвратить завершение сеанса Windows.  
  
> [!NOTE]
>  <xref:System.Windows.Application.SessionEnding> вызывается для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
#### <a name="exit"></a>Exit  
 При завершении работы приложения может возникнуть необходимость выполнить окончательную обработку, например сохранение состояния приложения. В подобных случаях можно обрабатывать <xref:System.Windows.Application.Exit> событий.  
  
 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml1)]  
[!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml#persistrestoreappscopepropertiesxaml2)]  
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind1)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind1)]  
[!code-csharp[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs#persistappscopepropertiescodebehind2)]
[!code-vb[HOWTOApplicationModelSnippets#PersistAppScopePropertiesCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistappscopepropertiescodebehind2)]  
  
 Полный пример см. в разделе [сохранения и восстановления свойства через области приложения сеансов приложения](../../../../docs/framework/wpf/app-development/persist-and-restore-application-scope-properties.md).  
  
 <xref:System.Windows.Application.Exit> могут быть обработаны как для автономных приложений и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], <xref:System.Windows.Application.Exit> вызывается в следующих случаях:  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] Перехода на другую.  
  
-   В [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], когда вкладке, на котором размещается [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] закрыт.  
  
-   Закрывается браузер.  
  
#### <a name="exit-code"></a>Код выхода  
 Приложения, как правило, запускаются операционной системой в ответ на запрос пользователя. Однако приложение может быть запущено другим приложением для выполнения определенной задачи. При завершении работы запущенного приложения приложению, которое его запустило, может понадобиться выяснить условие, при котором запущенное приложение завершает работу. В таких ситуациях Windows позволяет приложениям вернуть код выхода приложения при завершении работы. По умолчанию [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения возвращать значение кода выхода 0.  
  
> [!NOTE]
>  При отладке из [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], код завершения приложения отображается в **вывода** окна, когда приложение завершает работу, в сообщении, выглядит следующим образом:  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  При открытии **выходные данные** окно, выбрав **вывода** на **представление** меню.  
  
 Чтобы изменить код выхода, можно вызвать <xref:System.Windows.Application.Shutdown%28System.Int32%29> перегрузку, которая принимает целочисленный аргумент для кода выхода:  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 Можно определить значение кода выхода и изменить его, обработав <xref:System.Windows.Application.Exit> событий. <xref:System.Windows.Application.Exit> Обработчик событий передается <xref:System.Windows.ExitEventArgs> , которые предоставляют доступ к коду выхода с <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> свойство. Дополнительные сведения см. в разделе <xref:System.Windows.Application.Exit>.  
  
> [!NOTE]
>  Можно задать код выхода в автономных приложениях и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]. Однако значение кода выхода игнорируется для [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)].  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a>Необработанные исключения  
 Иногда приложение может завершить работу из-за неправильного состояния, например когда создается непредвиденное исключение. В этом случае в приложении может не быть кода для обнаружения и обработки исключения. Исключение такого типа является необработанным. Перед закрытием приложения выводится уведомление, похожее на показанное на рисунке ниже.  
  
 ![Уведомление о необработанном исключении](../../../../docs/framework/wpf/app-development/media/applicationmanagementoverviewfigure2.png "ApplicationManagementOverviewFigure2")  
  
 С точки зрения работы пользователя такое поведение приложения по умолчанию лучше переопределить, выполнив некоторые или все следующие действия:  
  
-   отображение понятных для пользователя сведений;  
  
-   попытка продолжить выполнение приложения;  
  
-   Запись подробных, понятных разработчику особых сведений в журнале событий Windows.  
  
 Реализация этой поддержки зависит от возможности обнаружить необработанные исключения, который является то, что <xref:System.Windows.Application.DispatcherUnhandledException> для события.  
  
 [!code-xaml[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
 [!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind1)]
 [!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind1)]  
[!code-csharp[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs#handledispatcherunhandledexceptioncodebehind2)]
[!code-vb[ApplicationDispatcherUnhandledExceptionSnippets#HandleDispatcherUnhandledExceptionCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb#handledispatcherunhandledexceptioncodebehind2)]  
  
 <xref:System.Windows.Application.DispatcherUnhandledException> Обработчик событий передается <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> параметр, содержащий контекстные сведения, касающиеся необработанного исключения, включая исключение самого себя (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>). Эту информацию можно использовать для определения способа обработки исключений.  
  
 При обработке <xref:System.Windows.Application.DispatcherUnhandledException>, следует задать <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> свойства `true`; в противном случае [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] по-прежнему рассматривает необработанное исключение и возвращается к поведению по умолчанию, описанному выше. Если возникает необработанное исключение и либо <xref:System.Windows.Application.DispatcherUnhandledException> не обработано событие или событие обрабатывается и <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> имеет значение `false`, приложение немедленно завершает работу. Кроме того никакие другие <xref:System.Windows.Application> событий. Следовательно, необходимо обработать <xref:System.Windows.Application.DispatcherUnhandledException> Если приложение имеет код, который необходимо выполнить, прежде чем приложение завершает работу.  
  
 Хотя приложение может завершить работу в результате возникновения необработанного исключения, приложение обычно завершает работу в ответ на запрос пользователя, как описано в следующем разделе.  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a>Событий приложения  
 Автономные приложения и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не имеют точно одинакового времени жизни. На приведенном ниже рисунке продемонстрированы ключевые события времени существования автономного приложения и показана последовательность, в которой они создаются.  
  
 ![Автономное приложение — события объекта Application](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")  
  
 Аналогично, на следующем рисунке показана ключевые события времени жизни [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]и отображает последовательность, в которой они создаются.  
  
 ![XBAP — события объекта Application](../../../../docs/framework/wpf/app-development/media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Application>  
 [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md)  
 [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [Файлы ресурсов, содержимого и данных WPF-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)  
 [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)  
 [Модели приложения: Разделы руководства по](http://msdn.microsoft.com/library/76771b09-3688-4d1c-8818-9b3f4cf39a30)  
 [Разработка приложений](../../../../docs/framework/wpf/app-development/index.md)
