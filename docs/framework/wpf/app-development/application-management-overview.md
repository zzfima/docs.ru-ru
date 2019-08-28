---
title: Общие сведения об управлении приложением
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: d0e3ecbfd42d14ea468adf8a99be0f525c5eb39d
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040971"
---
# <a name="application-management-overview"></a>Общие сведения об управлении приложением

Все приложения имеют тенденцию совместно использовать общий набор функциональных возможностей, который применяется к реализации приложения и управлению им. В этом разделе приводятся общие сведения о функциональных <xref:System.Windows.Application> возможностях класса для создания приложений и управления ими.

## <a name="the-application-class"></a>Класс Application

В WPF общие функциональные возможности с областью действия приложения инкапсулированы в <xref:System.Windows.Application> классе. <xref:System.Windows.Application> Класс включает следующие функциональные возможности:

- отслеживание и взаимодействие со временем существования приложения;

- извлечение и обработка параметров командной строки;

- обнаружение необработанных исключений и реагирование на них;

- совместное использование свойств области определения приложения и ресурсов;

- управление окнами в автономных приложениях;

- отслеживание навигации и управление ею.

<a name="The_Application_Class"></a>

## <a name="how-to-perform-common-tasks-using-the-application-class"></a>Выполнение стандартных задач с помощью класса приложения

Если вы не заинтересованы в подробностях <xref:System.Windows.Application> класса, в следующей таблице перечислены некоторые распространенные задачи для <xref:System.Windows.Application> и способы их выполнения. Чтобы получить дополнительные сведения и образец кода, просмотрите связанные API и разделы.

|Задача|Подход|
|----------|--------------|
|Получение объекта, представляющего текущее приложение|Используйте свойство <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>.|
|Добавление заставки в приложение|См. раздел [Добавление экрана-заставки в приложение WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).|
|Запуск приложения|Воспользуйтесь методом <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType>.|
|Остановка приложения|<xref:System.Windows.Application.Shutdown%2A> Используйте метод<xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> объекта.|
|Получение аргументов из командной строки|Обработайте <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> событие и используйте свойство. <xref:System.Windows.Application.Startup?displayProperty=nameWithType> Пример см. в <xref:System.Windows.Application.Startup?displayProperty=nameWithType> описании события.|
|Получение и задание кода завершения приложения|Задайте свойство в обработчике <xref:System.Windows.Application.Shutdown%2A>событийили вызовите метод и передайте целое число. <xref:System.Windows.Application.Exit?displayProperty=nameWithType> <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType>|
|Обнаружение необработанных исключений и реагирование на них|Обработайте <xref:System.Windows.Application.DispatcherUnhandledException> событие.|
|Получение и задание ресурсов области определения приложения|Используйте свойство <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.|
|Использование словаря ресурсов области определения приложения|См. раздел [Использование словаря ресурсов области приложения](how-to-use-an-application-scope-resource-dictionary.md).|
|Получение и задание свойств области определения приложения|Используйте свойство <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType>.|
|Получение и сохранение состояния приложения|См. раздел [Сохранение и восстановление свойств области приложения во всех сеансах приложения](persist-and-restore-application-scope-properties.md).|
|Управление файлами данных без кода, включая файлы ресурсов, файлы содержимого и файлы исходного сайта.|См. раздел [ресурс приложения WPF, содержимое и файлы данных](wpf-application-resource-content-and-data-files.md).|
|Управление окнами в автономных приложениях|См. раздел [Общие сведения об окнах WPF](wpf-windows-overview.md).|
|Отслеживание навигации и управление ею|См. раздел [Общие сведения о навигации](navigation-overview.md).|

<a name="The_Application_Definition"></a>

## <a name="the-application-definition"></a>Определение приложения

Чтобы использовать функциональные возможности <xref:System.Windows.Application> класса, необходимо реализовать определение приложения. Определение приложения WPF — это класс, производный от <xref:System.Windows.Application> и настроенный с помощью специального параметра MSBuild.

### <a name="implementing-an-application-definition"></a>Реализация определения приложения

Типичное определение приложения WPF реализуется с помощью разметки и кода программной части. Это позволяет использовать разметку для декларативного задания свойств и ресурсов приложения и регистрации событий, а обработку событий и поведение приложения реализовывать в коде программной части.

В следующем примере показано, как реализовать определение приложения с помощью разметки и кода программной части:

[!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]

[!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
[!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]

Для совместной работы файла разметки и файла кода программной части должны выполняться указанные ниже условия.

- В разметке `Application` элемент должен `x:Class` включать атрибут. `x:Class` При сборке приложения существование в файле разметки приводит к тому, что MSBuild `partial` создает класс, производный от <xref:System.Windows.Application> , и `x:Class` имеет имя, заданное атрибутом. Для этого требуется добавить объявление пространства имен XML для схемы XAML (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).

- В коде программной части класс должен быть `partial` классом с тем же именем, которое задано `x:Class` атрибутом в разметке и должен быть производным от <xref:System.Windows.Application>. Это позволяет связать файл кода программной части с `partial` классом, созданным для файла разметки при сборке приложения (см. раздел [Создание приложения WPF](building-a-wpf-application-wpf.md)).

> [!NOTE]
> При создании нового проекта приложения WPF или проекта приложения браузера WPF с помощью Visual Studio определение приложения включается по умолчанию и определяется с помощью разметки и кода программной части.

Этот код является минимумом, необходимым для реализации определения приложения. Однако перед сборкой и запуском приложения необходимо внести в определение приложения дополнительную конфигурацию MSBuild.

### <a name="configuring-the-application-definition-for-msbuild"></a>Настройка определения приложения для MSBuild

Для работы автономных приложений и приложений браузера XAML (XBAP) требуется реализация определенного уровня инфраструктуры. Наиболее важной частью этой инфраструктуры является точка входа. При запуске приложения пользователем операционная система вызывает точку входа, которая является известной функцией для запуска приложений.

Обычно разработчикам требовалось писать весь этот код или его часть самостоятельно в зависимости от технологии. Однако WPF создает этот код, если файл разметки определения приложения настроен в качестве элемента MSBuild `ApplicationDefinition` , как показано в следующем файле проекта MSBuild:

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

Поскольку файл кода программной части содержит код, он помечается как элемент `Compile` MSBuild, как обычная.

Применение этих конфигураций MSBuild к файлам разметки и кода программной части определения приложения приводит к тому, что MSBuild создает код, подобный следующему:

[!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
[!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]

Результирующий код дополняет определение приложения с помощью дополнительного кода инфраструктуры, который включает в себя метод `Main`точки входа. <xref:System.STAThreadAttribute> Атрибут применяется `Main` к методу, чтобы указать, что основной поток пользовательского интерфейса для приложения WPF является потоком STA, который необходим для приложений WPF. При вызове `Main` `InitializeComponent` метод создает новый экземпляр класса `App` перед вызовом метода для регистрации событий и задания свойств, которые реализуются в разметке. Поскольку `InitializeComponent` создается автоматически, вам не нужно явно вызывать `InitializeComponent` из определения приложения, как и <xref:System.Windows.Window> для <xref:System.Windows.Controls.Page> реализаций. Наконец, <xref:System.Windows.Application.Run%2A> вызывается метод для запуска приложения.

<a name="Getting_the_Current_Application"></a>

## <a name="getting-the-current-application"></a>Получение текущего приложения

Поскольку функциональные возможности <xref:System.Windows.Application> класса являются общими для приложения, в каждый <xref:System.Windows.Application> <xref:System.AppDomain>из них может быть только один экземпляр класса. Для этого <xref:System.Windows.Application> класс реализуется как одноэлементный класс (см. [реализацию Singleton в C# ](https://go.microsoft.com/fwlink/?LinkId=100567)), который создает единственный экземпляр и предоставляет `static` <xref:System.Windows.Application.Current%2A> общий доступ к нему со свойством.

В следующем коде показано, как получить ссылку на <xref:System.Windows.Application> объект для текущего <xref:System.AppDomain>объекта.

[!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]

<xref:System.Windows.Application.Current%2A>Возвращает ссылку на экземпляр <xref:System.Windows.Application> класса. Если требуется ссылка на <xref:System.Windows.Application> производный класс, необходимо привести значение <xref:System.Windows.Application.Current%2A> свойства, как показано в следующем примере.

[!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
[!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]

Значение <xref:System.Windows.Application.Current%2A> можно проверить в любой момент времени существования <xref:System.Windows.Application> объекта. Однако следует соблюдать осторожность. После создания экземпляра <xref:System.Windows.Application> классасуществуетпериод,втечениекоторогосостояниеобъекта<xref:System.Windows.Application> не согласовано. В течение этого периода <xref:System.Windows.Application> времени выполняет различные задачи инициализации, необходимые для выполнения кода, включая установку инфраструктуры приложений, настройку свойств и регистрацию событий. Если вы попытаетесь использовать <xref:System.Windows.Application> объект в течение этого периода, код может иметь непредвиденные результаты, особенно если он зависит от различных <xref:System.Windows.Application> заданных свойств.

Когда <xref:System.Windows.Application> завершает работу инициализации, действительно начинается его время существования.

<a name="Application_Lifetime"></a>

## <a name="application-lifetime"></a>Время существования приложения

Время существования приложения WPF помечается несколькими событиями, которые вызываются <xref:System.Windows.Application> , чтобы сообщить, когда приложение запущено, было активировано и отключено, а также было завершено.

<a name="Splash_Screen"></a>

### <a name="splash-screen"></a>Заставка

Начиная с .NET Framework 3,5 с пакетом обновления 1 (SP1), можно указать изображение, которое будет использоваться в окне запуска или на *экране*-заставке. <xref:System.Windows.SplashScreen> Класс позволяет легко отображать окно запуска во время загрузки приложения. Окно создается и отображается перед <xref:System.Windows.Application.Run%2A> вызовом метода. <xref:System.Windows.SplashScreen> Дополнительные сведения см. в статьях [время запуска приложения](../advanced/application-startup-time.md) и [Добавление экрана-ЗАСТАВКИ в приложение WPF](how-to-add-a-splash-screen-to-a-wpf-application.md).

<a name="Starting_an_Application"></a>

### <a name="starting-an-application"></a>Запуск приложения

После <xref:System.Windows.Application.Run%2A> вызова и инициализации приложения приложение готово к выполнению. Этот момент означает, что <xref:System.Windows.Application.Startup> возникает событие:

[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]

На этом этапе существования приложения наиболее распространенной особенностью является отображение пользовательского интерфейса.

<a name="Showing_a_User_Interface"></a>

### <a name="showing-a-user-interface"></a>Отображение пользовательского интерфейса

Большинство автономных приложений Windows открывают, <xref:System.Windows.Window> когда они начинают работать. Обработчик <xref:System.Windows.Application.Startup> событий — это одно из расположений, из которого можно сделать это, как показано в следующем коде.

[!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]

[!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
[!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]

> [!NOTE]
> Первый <xref:System.Windows.Window> экземпляр, создаваемый в автономном приложении, по умолчанию превращается в основное окно приложения. На <xref:System.Windows.Window> этот объект ссылается <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> свойство. Значение <xref:System.Windows.Application.MainWindow%2A> свойства может быть изменено программным образом, если другое окно, отличное от первого <xref:System.Windows.Window> экземпляра, должно быть основным окном.

При первом запуске XBAP, скорее всего, будет выполнен переход к <xref:System.Windows.Controls.Page>. Это показано в приведенном ниже коде.

[!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]

[!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
[!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]

Если вы обрабатываете <xref:System.Windows.Application.Startup> только <xref:System.Windows.Window> открытие или переход к <xref:System.Windows.Controls.Page>, можно задать `StartupUri` атрибут в разметке.

В следующем примере показано, <xref:System.Windows.Application.StartupUri%2A> как использовать из автономного приложения для <xref:System.Windows.Window>открытия.

[!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]

В следующем примере показано, как использовать <xref:System.Windows.Application.StartupUri%2A> из XBAP для перехода <xref:System.Windows.Controls.Page>к.

[!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]

Эта разметка действует так же, как и предыдущий код для открытия окна.

> [!NOTE]
> Дополнительные сведения о навигации см. в разделе [Общие сведения о навигации](navigation-overview.md).

Необходимо обработать <xref:System.Windows.Application.Startup> событие, чтобы открыть, <xref:System.Windows.Window> если необходимо создать его экземпляр с помощью конструктора без параметров, или необходимо задать его свойства или подписываться на его события перед отображением, или же необходимо обработать аргументы командной строки. которые были предоставлены при запуске приложения.

<a name="Processing_Command_Line_Arguments"></a>

### <a name="processing-command-line-arguments"></a>Обработка аргументов командной строки

В Windows автономные приложения можно запускать из командной строки или с рабочего стола. В обоих случаях аргументы командной строки могут быть переданы приложению. В приведенном ниже примере показано приложение, которое запускается с одним аргументом командной строки /StartMinimized:

`wpfapplication.exe /StartMinimized`

Во время инициализации приложения WPF получает аргументы командной строки из операционной системы и передает их <xref:System.Windows.Application.Startup> обработчику событий <xref:System.Windows.StartupEventArgs.Args%2A> через свойство <xref:System.Windows.StartupEventArgs> параметра. Аргументы командной строки можно извлечь и сохранить с помощью приведенного ниже кода.

[!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]

[!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
[!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]

Код обрабатывает <xref:System.Windows.Application.Startup> , чтобы проверить, предоставлен ли аргумент командной строки **/StartMinimized** . Если да, то он открывает <xref:System.Windows.WindowState> главное <xref:System.Windows.WindowState.Minimized>окно с параметром. Обратите внимание, <xref:System.Windows.Window.WindowState%2A> что поскольку свойство должно быть задано программно, главное <xref:System.Windows.Window> необходимо открыть в коде явным образом.

XBAP не могут извлекать и обрабатывать аргументы командной строки, так как они запускаются с помощью развертывания ClickOnce (см. раздел [развертывание приложения WPF](deploying-a-wpf-application-wpf.md)). Однако они могут извлекать и обрабатывать строковые параметры запроса из URL-адресов, которые используются для их запуска.

<a name="Application_Activation_and_Deactivation"></a>

### <a name="application-activation-and-deactivation"></a>Активация и отключение приложения

Windows позволяет пользователям переключаться между приложениями. Наиболее простой способ — использовать клавиши ALT+TAB. Приложение может быть переключено на, только если оно видимо <xref:System.Windows.Window> , которое пользователь может выбрать. Выбранный <xref:System.Windows.Window> в данный момент объект является *активным окном* (также известным как *окно переднего плана*) и — это объект <xref:System.Windows.Window> , который получает входные данные пользователя. Приложение с активным окном — это *активное приложение* (или *Приложение переднего плана*). Приложение становится активным в указанных ниже случаях.

- Он запускается и отображает <xref:System.Windows.Window>.

- Пользователь переключается из другого приложения, выбирая <xref:System.Windows.Window> в приложении.

Можно определить, когда приложение станет активным, обрабатывая <xref:System.Windows.Application.Activated?displayProperty=nameWithType> событие.

Аналогичным образом приложение может стать неактивным в указанных ниже случаях.

- Пользователь переключается на другое приложение из текущего.

- Приложение завершает работу.

Можно определить, когда приложение станет неактивным, обрабатывая <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> событие.

В следующем коде показано, как управлять <xref:System.Windows.Application.Activated> событиями и <xref:System.Windows.Application.Deactivated> , чтобы определить, является ли приложение активным.

[!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]

[!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
[!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]

<xref:System.Windows.Window> Можно также активировать и деактивировать. Дополнительные сведения см. в разделах <xref:System.Windows.Window.Activated?displayProperty=nameWithType> и <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>.

> [!NOTE]
> Для XBAP <xref:System.Windows.Application.Activated?displayProperty=nameWithType>невызываетсяни, ни.<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>

<a name="Application_Shutdown"></a>

### <a name="application-shutdown"></a>Завершение работы приложения

Время существования приложения заканчивается, когда оно завершает работу, что может возникнуть по указанным ниже причинам.

- Пользователь закрывает каждое <xref:System.Windows.Window>.

- Пользователь закрывает основной <xref:System.Windows.Window>.

- Пользователь завершает сеанс Windows, выполнив выход из системы или завершая его работу.

- Выполнено специальное условие для приложения.

Чтобы упростить управление завершением работы приложения <xref:System.Windows.Application> , <xref:System.Windows.Application.Shutdown%2A> предоставляет метод, <xref:System.Windows.Application.ShutdownMode%2A> свойство и <xref:System.Windows.Application.SessionEnding> события и <xref:System.Windows.Application.Exit> .

> [!NOTE]
> <xref:System.Windows.Application.Shutdown%2A>может вызываться только из приложений, имеющих <xref:System.Security.Permissions.UIPermission>. Это разрешение всегда имеет автономные приложения WPF. Однако XBAP, работающие в изолированной среде безопасности с частичным доверием зоны Интернета, не имеют.

#### <a name="shutdown-mode"></a>Режим завершения работы

Большинство приложений завершают работу при закрытии главного окна или всех окон. Иногда, однако, другие условия конкретного приложения могут определить, когда приложение завершает работу. Можно указать условия, при которых приложение будет закрыто, задав <xref:System.Windows.Application.ShutdownMode%2A> одно из следующих <xref:System.Windows.ShutdownMode> значений перечисления:

- <xref:System.Windows.ShutdownMode.OnLastWindowClose>

- <xref:System.Windows.ShutdownMode.OnMainWindowClose>

- <xref:System.Windows.ShutdownMode.OnExplicitShutdown>

Значение <xref:System.Windows.Application.ShutdownMode%2A> по умолчанию — <xref:System.Windows.ShutdownMode.OnLastWindowClose>, то есть приложение автоматически завершает работу при закрытии пользователем последнего окна в приложении. Однако если при закрытии главного окна приложение должно завершить работу, WPF автоматически делает это, если задано значение <xref:System.Windows.Application.ShutdownMode%2A>. <xref:System.Windows.ShutdownMode.OnMainWindowClose> Эти действия показаны в следующем примере.

[!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]

При наличии условий завершения работы, зависящих от приложения, устанавливается <xref:System.Windows.Application.ShutdownMode%2A> значение <xref:System.Windows.ShutdownMode.OnExplicitShutdown>. В этом случае вы отвечаете за завершение работы приложения путем явного вызова <xref:System.Windows.Application.Shutdown%2A> метода. в противном случае приложение продолжит работать, даже если все окна закрыты. Обратите <xref:System.Windows.Application.Shutdown%2A> внимание, что вызывается неявно <xref:System.Windows.Application.ShutdownMode%2A> , если <xref:System.Windows.ShutdownMode.OnLastWindowClose> имеет <xref:System.Windows.ShutdownMode.OnMainWindowClose>значение или.

> [!NOTE]
> <xref:System.Windows.Application.ShutdownMode%2A>может быть задано из XBAP, но игнорируется; XBAP всегда завершает работу при переходе из в браузере или при закрытии браузера, на котором размещается XBAP. Дополнительные сведения см. в разделе [Общие сведения о переходах](navigation-overview.md).

#### <a name="session-ending"></a>Завершение сеанса

Условия завершения работы, описанные <xref:System.Windows.Application.ShutdownMode%2A> свойством, относятся к приложению. Однако в некоторых случаях приложение может завершить работу в результате выполнения внешнего условия. Наиболее распространенное внешнее условие возникает, когда пользователь завершает сеанс Windows с помощью следующих действий:

- выход из системы;

- завершение работы;

- перезапуск;

- спящий режим.

Чтобы определить время завершения сеанса Windows, можно выполнить обработку <xref:System.Windows.Application.SessionEnding> события, как показано в следующем примере.

[!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]

[!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
[!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]

В этом примере код проверяет <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> свойство, чтобы определить, как завершается сеанс Windows. Он использует это значение, чтобы отобразить сообщение подтверждения для пользователя. Если пользователь не хочет, чтобы сеанс закончится, код задает <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> для `true` значение, чтобы предотвратить завершение сеанса Windows.

> [!NOTE]
> <xref:System.Windows.Application.SessionEnding>не вызывается для XBAP.

#### <a name="exit"></a>Exit

При завершении работы приложения может возникнуть необходимость выполнить окончательную обработку, например сохранение состояния приложения. В таких ситуациях можно выполнить обработку <xref:System.Windows.Application.Exit> события, как это `App_Exit` делает обработчик событий в следующем примере. Он определяется как обработчик событий в файле *app. XAML* . Его реализация выделяется в файлах *app.XAML.CS* и *Application. XAML. vb* .

[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]

[!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
[!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]

Полный пример см. в разделе [Сохранение и восстановление свойств области приложения во всех сеансах приложения](persist-and-restore-application-scope-properties.md).

<xref:System.Windows.Application.Exit>может обрабатываться как автономными приложениями, так и XBAP. Для XBAP <xref:System.Windows.Application.Exit> вызывается в следующих случаях:

- Выполняется переход к XBAP из.

- В Internet Explorer, когда вкладка, на которой размещается XBAP, закрыта.

- Закрывается браузер.

#### <a name="exit-code"></a>Код выхода

Приложения, как правило, запускаются операционной системой в ответ на запрос пользователя. Однако приложение может быть запущено другим приложением для выполнения определенной задачи. При завершении работы запущенного приложения приложению, которое его запустило, может понадобиться выяснить условие, при котором запущенное приложение завершает работу. В таких ситуациях Windows позволяет приложениям возвращать код выхода приложения при завершении работы. По умолчанию приложения WPF возвращают значение кода выхода 0.

> [!NOTE]
> При отладке из Visual Studio код завершения приложения отображается в окне **вывода** при завершении работы приложения в сообщении, которое выглядит следующим образом:
>
> `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`
>
> Чтобы открыть окно **вывода** , щелкните **вывод** в меню **вид** .

Чтобы изменить код выхода, можно вызвать <xref:System.Windows.Application.Shutdown%28System.Int32%29> перегрузку, которая принимает целочисленный аргумент в качестве кода выхода:

[!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
[!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]

Можно определить значение кода выхода и изменить его, обрабатывая <xref:System.Windows.Application.Exit> событие. Обработчик событий передается, <xref:System.Windows.ExitEventArgs> который предоставляет доступ к коду выхода со <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> свойством. <xref:System.Windows.Application.Exit> Дополнительные сведения см. в разделе <xref:System.Windows.Application.Exit>.

> [!NOTE]
> Код выхода можно задать как в автономных приложениях, так и в XBAP. Однако значение кода выхода игнорируется для XBAP.

<a name="Unhandled_Exceptions"></a>

### <a name="unhandled-exceptions"></a>Необработанные исключения

Иногда приложение может завершить работу из-за неправильного состояния, например когда создается непредвиденное исключение. В этом случае в приложении может не быть кода для обнаружения и обработки исключения. Исключение такого типа является необработанным. Перед закрытием приложения выводится уведомление, похожее на показанное на рисунке ниже.

![Снимок экрана, на котором показано уведомление о необработанном исключении.](./media/application-management-overview/unhandled-exception-notification.png)

С точки зрения работы пользователя такое поведение приложения по умолчанию лучше переопределить, выполнив некоторые или все следующие действия:

- отображение понятных для пользователя сведений;

- попытка продолжить выполнение приложения;

- Запись подробных сведений об исключениях, понятных разработчикам, в журнале событий Windows.

Реализация этой поддержки зависит от возможности обнаружения необработанных исключений, о которых <xref:System.Windows.Application.DispatcherUnhandledException> вызывается событие.

[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]

[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]

Обработчику <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>событий передается параметр, содержащий контекстные сведения о необработанном исключении, включая само исключение (). <xref:System.Windows.Application.DispatcherUnhandledException> Эту информацию можно использовать для определения способа обработки исключений.

При обработке <xref:System.Windows.Application.DispatcherUnhandledException>необходимо <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> задать для `true`свойства значение; в противном случае WPF по-прежнему считает исключение необработанным и вернется к поведению по умолчанию, описанному выше. Если возникает необработанное исключение и <xref:System.Windows.Application.DispatcherUnhandledException> событие не обрабатывается, или событие обрабатывается и <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> имеет значение `false`, приложение немедленно завершает работу. Кроме того, другие <xref:System.Windows.Application> события не вызываются. Следовательно, необходимо выполнить обработку <xref:System.Windows.Application.DispatcherUnhandledException> , если в приложении есть код, который должен выполняться перед завершением работы приложения.

Хотя приложение может завершить работу в результате возникновения необработанного исключения, приложение обычно завершает работу в ответ на запрос пользователя, как описано в следующем разделе.

<a name="Application_Lifetime_Events"></a>

### <a name="application-lifetime-events"></a>Событий приложения

Автономные приложения и XBAP не имеют точно одинакового времени существования. На приведенном ниже рисунке продемонстрированы ключевые события времени существования автономного приложения и показана последовательность, в которой они создаются.

![Автономное приложение — события объекта Application](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")

Аналогично, на следующем рисунке показаны ключевые события времени существования XBAP и показана последовательность, в которой они создаются.

![XBAP — события объекта Application](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")

## <a name="see-also"></a>См. также

- <xref:System.Windows.Application>
- [Общие сведения об окнах WPF](wpf-windows-overview.md)
- [Общие сведения о переходах](navigation-overview.md)
- [Файлы ресурсов, содержимого и данных WPF-приложения](wpf-application-resource-content-and-data-files.md)
- [URI типа "pack" в WPF](pack-uris-in-wpf.md)
- [Модель приложения: Разделы руководства](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))
- [Разработка приложений](index.md)
