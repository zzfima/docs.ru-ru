---
title: Обзор Windows
ms.date: 03/30/2017
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
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145544"
---
# <a name="wpf-windows-overview"></a>Общие сведения об окнах WPF
Пользователи взаимодействуют с автономными приложениями Windows Presentation Foundation (WPF) через окна. Основная цель окна — разместить содержимое, которое визуализирует данные и позволяет пользователям взаимодействовать с ними. Автономные приложения WPF предоставляют свои <xref:System.Windows.Window> собственные окна с помощью класса. Эта тема <xref:System.Windows.Window> представляет перед охватом основы создания и управления окнами в автономных приложениях.  
  
> [!NOTE]
> Приложения WPF, размещенные в браузере, включая приложения [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для браузеров XAML (XBAPs) и свободные страницы, не предоставляют свои собственные окна. Вместо этого они размещаются в окнах, предоставляемых Windows Internet Explorer. Смотрите [обзор приложений для браузеров WPF XAML](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>Класс окна  
 Следующая цифра иллюстрирует составные части окна:  
  
 ![Скриншот, на который отображаны элементы окна.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Окно разделено на две области: неклиентскую и клиентскую.  
  
 Область *окна,* не являющаяся клиентом, реализуется WPF и включает в себя части окна, которые являются общими для большинства окон, включая следующие:  
  
- Граница.  
  
- Заголовок окна.  
  
- Значок.  
  
- Кнопки "Свернуть", "Развернуть" и "Восстановить".  
  
- Кнопка "Закрыть".  
  
- Системное меню с элементами, которые позволяют пользователям свернуть, развернуть, восстановить, перемещать, изменять размеры и закрыть окно.  
  
 *Область клиента* окна — это область в зоне неклиента окна и используется разработчиками для добавления содержимого приложения, например баров меню, баров инструментов и элементов управления.  
  
 В WPF окно инкапсулируется <xref:System.Windows.Window> классом, который используется для выполнения следующих  
  
- Отобразить окно.  
  
- Настроить размер, положение и внешний вид окна.  
  
- Разместить содержимое конкретного приложения.  
  
- Управлять временем существования окна.  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>Реализация окна  
 Реализация типичного окна включает в себя как внешний вид, так и поведение, где *внешний вид* определяет, как окно выглядит для пользователей, а *поведение* определяет способ взаимодействия оконного окна при взаимодействии пользователей с ним. В WPF можно реализовать внешний вид и поведение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] окна, используя код или разметку.  
  
 Однако в целом внешний вид окна [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализуется с помощью разметки, а его поведение реализуется с помощью кода сзади, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Для совместной работы файла [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки и файла с кодом требуется следующее:  
  
- В разметке `Window` элемент `x:Class` должен включать атрибут. Когда приложение построено, наличие `x:Class` в файле разметки приводит к тому, что движок сборки Microsoft (MSBuild) создает `partial` класс, который происходит от <xref:System.Windows.Window> и имеет имя, указанное `x:Class` атрибутом. Это требует добавления декларации пространства [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имен XML `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` для схемы (). Сгенерированный `partial` класс `InitializeComponent` реализует метод, который называется для регистрации событий и набора свойств, реализованных в разметке.  
  
- В коде позади, класс `partial` должен быть класс с тем `x:Class` же именем, которое <xref:System.Windows.Window>указано атрибутом в разметке, и он должен вытекать из . Это позволяет ассоциировать файл `partial` с кодом с классом, который генерируется для файла разметки при создании приложения (см. [Создание приложения WPF).](building-a-wpf-application-wpf.md)  
  
- В закодированном <xref:System.Windows.Window> классе должен быть реализован `InitializeComponent` конструктор, который вызывает метод. `InitializeComponent`реализуется сгенерированным `partial` классом файла разметки для регистрации событий и набора свойств, определенных в разметке.  
  
> [!NOTE]
> При добавлении <xref:System.Windows.Window> нового к проекту с <xref:System.Windows.Window> помощью Visual Studio, реализована с использованием как разметки, так и кода за спиной, и включает в себя необходимую конфигурацию для создания связи между разметкой и файлами, закоторыми кода, как описано здесь.  
  
 С помощью этой конфигурации можно сосредоточиться на определении внешнего вида окна в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке и реализации его поведения в коде сзади. В следующем примере показано окно [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с кнопкой, реализованной в разметке, и обработчик событий для <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события кнопки, реализованный в коде сзади.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>Настройка определения окна для MSBuild  
 Способ реализации окна определяет, как оно настроено для MSBuild. Для окна, которое [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] определяется с помощью как разметки, так и за кодом:  
  
- Файлы разметки XAML `Page` настроены как элементы MSBuild.  
  
- Файлы, стоящие за кодом, настраиваются как элементы MSBuild. `Compile`  
  
 Это показано в следующем файле проекта MSBuild.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 Для получения информации о создании [приложений](building-a-wpf-application-wpf.md)WPF см.  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>Время существования окна  
 Как и любой класс, окно имеет время существования, которое начинается с момента создания его экземпляра, после чего оно открывается, активируется, деактивируется и, в конечном счете, закрывается.  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>Открытие окна  
 Чтобы открыть окно, сначала создайте его экземпляр, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 В этом примере `MarkupAndCodeBehindWindow` моментируется при запуске приложения, <xref:System.Windows.Application.Startup> что происходит при поднятии события.  
  
 Когда окно мгновенно, ссылка на него автоматически добавляется в список окон, <xref:System.Windows.Application> управляемых <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>объектом (см.). Кроме того, первое окно, которое будет мгновенно, <xref:System.Windows.Application> по умолчанию установлено <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>в качестве основного окна приложения (см.).  
  
 Окно, наконец, открывается, вызывая <xref:System.Windows.Window.Show%2A> метод; результат показан на следующей цифре.  
  
 ![Окно, открытое по телефону Window.Show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Окно, открываемые вызовом, <xref:System.Windows.Window.Show%2A> является безрежимным окном, что означает, что приложение работает в режиме, который позволяет пользователям активировать другие окна в том же приложении.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>называется, чтобы открыть окна, такие как диалоговые окна модально. Для получения дополнительной информации смотрите [обзор Dialog Boxes.](dialog-boxes-overview.md)  
  
 При <xref:System.Windows.Window.Show%2A> вызове окно выполняет работу инициализации перед тем, как будет показано создание инфраструктуры, позволяющей ему получать пользовательский ввод. Когда окно инициализировано, <xref:System.Windows.Window.SourceInitialized> событие поднимается и окно отображается.  
  
 В качестве ярлыка можно установить первое окно, <xref:System.Windows.Application.StartupUri%2A> которое открывается автоматически при запуске приложения.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 Когда приложение запускается, окно, указанное <xref:System.Windows.Application.StartupUri%2A> значением, открывается бесрежимно; внутри, окно открывается, вызывая его <xref:System.Windows.Window.Show%2A> метод.  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>Владение окном  
 Окно, открываемые <xref:System.Windows.Window.Show%2A> с помощью метода, не имеет неявной связи с окном, которое его создало; пользователи могут взаимодействовать с любым окном независимо от другого, что означает, что любое окно может сделать следующее:  
  
- Обложка другой (если одно из <xref:System.Windows.Window.Topmost%2A> окон `true`имеет свое свойство установить).  
  
- Сворачиваться, разворачиваться и восстанавливаться без влияния на другое окно.  
  
 Для некоторых окон требуется связь с окном, которое их открывает. Например, приложение Integrated Development Environment (IDE) может открывать окна свойств и окна инструментов, типичное поведение которых заключается в том, чтобы покрыть окно, которое их создает. Кроме того, такие окна должны всегда закрываться, сворачиваться, разворачиваться и восстанавливаться вместе с окном, которое их создало. Такие отношения могут быть установлены *own* путем создания одного окна <xref:System.Windows.Window.Owner%2A> собственным другим, и достигается путем установки собственности *на принадлежащее окно* со ссылкой на окно *владельца*. Это показано в следующем примере.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 После установки владения:  
  
- Принадлежащее окно может ссылаться на окно своего <xref:System.Windows.Window.Owner%2A> владельца, проверяя стоимость его имущества.  
  
- Окно владельца может обнаружить все окна, которыми <xref:System.Windows.Window.OwnedWindows%2A> оно владеет, проинспектируя стоимость его имущества.  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>Предотвращение активации окна  
 Есть сценарии, в которых окна не должны быть активированы при отображев, например, окна разговоров приложения в стиле интернет-мессенджера или окна уведомлений приложения электронной почты.  
  
 Если в приложении есть окно, которое не должно быть <xref:System.Windows.Window.ShowActivated%2A> активировано при отображев, вы можете настроить его `false` свойство, прежде чем вызвать <xref:System.Windows.Window.Show%2A> метод в первый раз. Результат:  
  
- Окно не активируется.  
  
- <xref:System.Windows.Window.Activated> Событие окна не поднято.  
  
- Текущее активированное окно останется активным.  
  
 Однако окно активируется, если пользователь щелкнет его неклиентскую или клиентскую область. В данном случае:  
  
- Окно активируется.  
  
- <xref:System.Windows.Window.Activated> Событие окна поднято.  
  
- Ранее активированное окно деактивируется.  
  
- Окно <xref:System.Windows.Window.Deactivated> и <xref:System.Windows.Window.Activated> события впоследствии поднимаются, как и ожидалось, в ответ на действия пользователя.  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>Активация окна  
 Когда окно впервые открывается, оно становится активным окном `false`(если оно не отображается с <xref:System.Windows.Window.ShowActivated%2A> набором). *Активное окно* — это окно, которое в настоящее время захватывает пользовательские входные данные, такие как штрихи клавиш и клики мыши. Когда окно становится активным, <xref:System.Windows.Window.Activated> оно поднимает событие.  
  
> [!NOTE]
> Когда окно впервые открывается, события <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.Window.ContentRendered> <xref:System.Windows.Window.Activated> события поднимаются только после поднятия события. Имея это в виду, окно может <xref:System.Windows.Window.ContentRendered> быть эффективно считается открытым, когда поднимается.  
  
 После активизации окна пользователь может активировать другое окно в том же приложении или активировать другое приложение. Когда это происходит, действующее в настоящее <xref:System.Windows.Window.Deactivated> время окно отключается и поднимает событие. Аналогичным образом, когда пользователь выбирает в настоящее время отключенное <xref:System.Windows.Window.Activated> окно, окно снова становится активным и поднимается.  
  
 Одной из распространенных причин для обработки <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> является включение и отключение функциональности, которая может работать только при активной обработке окна. Например, некоторые окна отображают интерактивное содержимое, которое требует постоянного ввода данных или внимания пользователя, включая игры и видеопроигрыватели. Следующим примером является упрощенный видеоплеер, <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> который демонстрирует, как обрабатывать и реализовывать это поведение.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Другие типы приложений могут выполнять код в фоновом режиме, когда окно деактивировано. Например, почтовый клиент может продолжать опрашивать почтовый сервер, пока пользователь работает с другими приложениями. Такие приложения часто обеспечивают другое или дополнительное поведение, когда главное окно не активно. В случае почтовой программы это может означать как добавление нового почтового элемента в папку "Входящие", так и добавление значка уведомления на панель задач. Значок уведомлений должен отображаться только в том случае, если почтовое <xref:System.Windows.Window.IsActive%2A> окно не работает, что может быть определено путем проверки свойства.  
  
 Если фоновая задача завершена, окно может захотеть <xref:System.Windows.Window.Activate%2A> более срочно уведомить пользователя методом вызова. Если пользователь взаимодействует с другим приложением, активированным при <xref:System.Windows.Window.Activate%2A> вызове, мигает кнопка панели задач окна. Если пользователь взаимодействует с текущим <xref:System.Windows.Window.Activate%2A> приложением, вызов выведет окно на передний план.  
  
> [!NOTE]
> Вы можете обрабатывать активацию <xref:System.Windows.Application.Activated?displayProperty=nameWithType> приложения <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> с помощью событий и событий.  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>Закрытие окна  
 Время существования окна заканчивается, когда пользователь его закрывает. Окно может быть закрыто с помощью элементов в неклиентской области, включая следующие:  
  
- **Закрыть** элемент меню **Системы.**  
  
- Нажатие клавиш ALT+F4.  
  
- Нажатие кнопки **"Закрыть".**  
  
 Можно указать дополнительные способы закрытия окна для клиентской области, к наиболее типичным из которых относятся следующие:  
  
- Элемент **выхода** в меню **файла,** как правило, для основных окон приложения.  
  
- **Элемент «Закрыть»** в меню **«Файл»,** обычно в окне вторичного приложения.  
  
- Кнопка **«Отмена»,** как правило, в модальном диалоговом поле.  
  
- **Кнопка "Закрыть",** как правило, на безспособном диалоговом ящике.  
  
 Чтобы закрыть окно в ответ на один из этих пользовательских механизмов, необходимо вызвать <xref:System.Windows.Window.Close%2A> метод. Следующий пример реализует возможность закрыть окно, выбрав **меню «Выход»** в меню **«Файл».**  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Когда окно закрывается, оно поднимает <xref:System.Windows.Window.Closing> <xref:System.Windows.Window.Closed>два события: и .  
  
 <xref:System.Windows.Window.Closing>поднимается до закрытия окна, и он обеспечивает механизм, с помощью которого закрытие окна может быть предотвращено. Одна из распространенных причин, препятствующих закрытию окна, заключается в том, что содержимое окна содержит измененные данные. В этой ситуации <xref:System.Windows.Window.Closing> событие может быть обработано, чтобы определить, являются ли данные грязными, и, если да, спросить пользователя, следует ли продолжать закрывать окно без сохранения данных или отменять закрытие окна. Ниже приводится следующий пример <xref:System.Windows.Window.Closing>ключевых аспектов обработки.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Обработчик <xref:System.Windows.Window.Closing> событий <xref:System.ComponentModel.CancelEventArgs>передается , `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> который реализует свойство, которое вы установили, чтобы `true` предотвратить закрытие окна.  
  
 Если <xref:System.Windows.Window.Closing> не обрабатывается или она обрабатывается, но не отменяется, окно закрывается. Непосредственно перед окном на <xref:System.Windows.Window.Closed> самом деле закрывается, поднимается. На этом этапе невозможно предотвратить закрытие окна.  
  
> [!NOTE]
> Приложение может быть настроено для автоматического выключения при <xref:System.Windows.Application.MainWindow%2A>закрытии либо основного окна приложения (см.), либо закроется последнее окно. Дополнительные сведения см. в разделе <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 В то время как окно может быть явно закрыто через механизмы, предоставляемые в неклиентных и клиентских областях, окно также может быть неявно закрыто в результате поведения в других частях приложения или Windows, включая следующие:  
  
- Пользователь выключает или выключает Windows.  
  
- Владелец окна закрывается (см.). <xref:System.Windows.Window.Owner%2A>  
  
- Основное окно приложения <xref:System.Windows.Application.ShutdownMode%2A> закрыто <xref:System.Windows.ShutdownMode.OnMainWindowClose>и находится в режиме .  
  
- Вызывается метод <xref:System.Windows.Application.Shutdown%2A>.  
  
> [!NOTE]
> После закрытия окно нельзя открыть повторно.  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>События времени существования окна  
 На следующей иллюстрации показана последовательность основных событий в течение всего срока службы окна:  
  
 ![Диаграмма, отображая события в жизни окна.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 Следующая иллюстрация показывает последовательность основных событий в жизни окна,<xref:System.Windows.Window.ShowActivated%2A> которое `false` отображается без активации (устанавливается до показа окна):  
  
 ![Диаграмма, отображая события в жизни окна без активации.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>Расположение окна  
 Когда окно открыто, оно располагается в координатах x и y относительно рабочего стола. Это местоположение может быть определено путем проверки <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> свойства, соответственно. Можно задать эти свойства, чтобы изменить расположение окна.  
  
 Можно также указать исходное местоположение, <xref:System.Windows.Window> когда <xref:System.Windows.Window.WindowStartupLocation%2A> оно впервые появится, установив свойство с одним из следующих <xref:System.Windows.WindowStartupLocation> значений перечисления:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (по умолчанию)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Если местоположение запуска указано <xref:System.Windows.WindowStartupLocation.Manual>как <xref:System.Windows.Window.Left%2A> , <xref:System.Windows.Window.Top%2A> а свойства и <xref:System.Windows.Window> свойства не были установлены, попросите Windows для размещения, чтобы появиться дюйма  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>Окна верхнего уровня и Z-порядок  
 Помимо расположения в координатах x и y, окно имеет координату по оси z, которая определяет его вертикальную позицию относительно других окон. Это называется z-порядком окна. Существует два типа: обычный z-порядок и верхний z-порядок. Местонахождение окна в *обычном z-заказе* определяется тем, активен оно в настоящее время или нет. По умолчанию окно находится в обычном z-порядке. Местонахождение окна в *верхнем z-заказе* также определяется тем, активен оно в настоящее время или нет. Кроме того, окна в самом верхнем z-порядке всегда расположены над окнами в обычном z-порядке. Окно расположено в верхнем z-заказе, установив его <xref:System.Windows.Window.Topmost%2A> свойство. `true`  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 В каждом z-порядке активное в данный момент окно появляется поверх всех других окон в том же z-порядке.  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>Размер окна  
 Помимо расположения рабочего стола, окно имеет размер, который определяется несколькими свойствами, включая различные свойства ширины и высоты и <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.MaxWidth%2A> используются для управления диапазоном ширины, что окно может иметь в течение своего срока службы, и настроены, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Высота окна <xref:System.Windows.FrameworkElement.MinHeight%2A>управляется, <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>и, и настроены, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Так как различные значения ширины и высоты определяют диапазон, то что ширина и высота изменяемого окна могут находиться в любом месте указанного диапазона для соответствующего измерения. Чтобы обнаружить его текущую <xref:System.Windows.FrameworkElement.ActualWidth%2A> <xref:System.Windows.FrameworkElement.ActualHeight%2A>ширину и высоту, проинспектировать и, соответственно.  
  
 Если вы хотите, чтобы ширина и высота окна имели размер, который соответствует размеру содержимого <xref:System.Windows.Window.SizeToContent%2A> окна, вы можете использовать свойство, которое имеет следующие значения:  
  
- <xref:System.Windows.SizeToContent.Manual>. Нет эффекта (по умолчанию).  
  
- <xref:System.Windows.SizeToContent.Width>. Подходит для ширины содержимого, что <xref:System.Windows.FrameworkElement.MinWidth%2A> имеет <xref:System.Windows.FrameworkElement.MaxWidth%2A> тот же эффект, как установка как и ширина содержимого.  
  
- <xref:System.Windows.SizeToContent.Height>. Подходит для содержания высоты, которая <xref:System.Windows.FrameworkElement.MinHeight%2A> имеет <xref:System.Windows.FrameworkElement.MaxHeight%2A> тот же эффект, как установка как и на высоту содержимого.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. Подходит для содержания ширины и высоты, <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> которая имеет тот же эффект, <xref:System.Windows.FrameworkElement.MinWidth%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> как установка и к высоте содержимого, и установка как и ширина содержимого.  
  
 В следующем примере показано окно, размеры которого автоматически устанавливаются равными его содержимому по вертикали и по горизонтали при первом отображении.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 В следующем примере показано, как установить <xref:System.Windows.Window.SizeToContent%2A> свойство в коде, чтобы указать, как окно изменяется в соответствии с его содержанием.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>Порядок приоритета для свойств размера  
 Различные свойства размеров окна объединяются для определения диапазона ширины и высоты окна изменяемого размера. Для обеспечения действительного <xref:System.Windows.Window> диапазона, оценивает значения размер свойства, используя следующие порядки приоритета.  
  
 **Для свойств высоты:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **Для свойств ширины:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 Порядок приоритета может также определить размер окна, когда оно максимизируется, которое управляется с свойством. <xref:System.Windows.Window.WindowState%2A>  
  
<a name="WindowState"></a>
## <a name="window-state"></a>Состояние окна  
 В течение времени существования окна изменяемого размера оно может иметь три состояния: обычное, свернутое и развернутое. Окно с *нормальным* состоянием — это состояние окна по умолчанию. Окно с этим состоянием позволяет пользователю перемещать его и изменять размер, используя захват для изменения размера или границу.  
  
 Окно с *сведенным минимумом* состояние мгновеется к кнопке панели задачи, если <xref:System.Windows.Window.ShowInTaskbar%2A> установлено на; `true` в противном случае, он разрушается до наименьшего размера, который может быть, и перемещается в левый нижний угол рабочего стола. Ни один из типов свернутого окна не может быть изменен с помощью границы или захвата для изменения размера, хотя свернутое окно, которое не отображается на панели задач, можно перетаскивать на рабочем столе.  
  
 Окно с *максимативным* состоянием расширяется до максимального размера, который <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>может <xref:System.Windows.Window.SizeToContent%2A> быть, который будет только таким большим, как его, и свойства диктуют. Как и для свернутого окна, размер развернутого окна нельзя изменить с помощью захвата для изменения размера или перетаскивания границы.  
  
> [!NOTE]
> <xref:System.Windows.Window.Top%2A>Значения, <xref:System.Windows.Window.Left%2A> <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.Height%2A> свойства окна всегда представляют значения для нормального состояния, даже если окно в настоящее время максимизировано или сведено к минимуму.  
  
 Состояние окна можно настроить путем настройки его <xref:System.Windows.Window.WindowState%2A> свойства, которое <xref:System.Windows.WindowState> может иметь одно из следующих значений перечисления:  
  
- <xref:System.Windows.WindowState.Normal> (по умолчанию)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 В следующем примере показано создание окна, которое отображается развернутым при его открытии.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 Как правило, необходимо <xref:System.Windows.Window.WindowState%2A> настроить начальное состояние окна. После отображения окна изменяемого размера пользователи могут нажимать кнопки свертывания, развертывания и восстановления на панели заголовка окна, чтобы изменить состояние окна.  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>Внешний вид окна  
 Можно изменить внешний вид клиентской области окна, добавляя в нее определенное содержимое, такое как кнопки, метки и текстовые поля. Для настройки области, не <xref:System.Windows.Window> являющаяся клиентом, предоставляется несколько свойств, которые включают в себя <xref:System.Windows.Window.Icon%2A> установку значка окна и <xref:System.Windows.Window.Title%2A> установление его названия.  
  
 Можно также изменить внешний вид и поведение границы неклиентской области, настраивая режим изменения размера окна, стиль окна и отображение в виде кнопки на панели задач рабочего стола.  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>Режим изменения размера  
 В зависимости <xref:System.Windows.Window.WindowStyle%2A> от свойства можно контролировать, как (и если) пользователи могут изменить размер окна. Выбор стиля окна влияет на то, может ли пользователь изменить размер окна, перетащив его границу с мышью, отображаются ли кнопки **«Минимизация»,** **«Максимизация»** и **«Изменение размера»** в области, не относящееся к клиенту, и, если они появляются, включены ли они.  
  
 Можно настроить, как окно изменяется, <xref:System.Windows.Window.ResizeMode%2A> установив его свойство, <xref:System.Windows.ResizeMode> которое может быть одним из следующих значений перечисления:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (по умолчанию)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Как <xref:System.Windows.Window.WindowStyle%2A>и в случае с режимом изменения размера окна, вряд ли изменится в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] течение его срока службы, а это означает, что вы, скорее всего, установите его из разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Обратите внимание, что можно определить, максимизируется ли окно, <xref:System.Windows.Window.WindowState%2A> минимизировано или восстановлено при проверке свойства.  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>Стиль окна  
 Граница, предоставляемая из неклиентской области окна, подходит для большинства приложений. Однако существуют ситуации, когда требуются различные типы границ либо границы вовсе не требуются, в зависимости от типа окна.  
  
 Чтобы контролировать, какой тип границы <xref:System.Windows.Window.WindowStyle%2A> получает окно, вы устанавливаете <xref:System.Windows.WindowStyle> его свойство одним из следующих значений перечисления:  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (по умолчанию)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Эффект этих стилей окна проиллюстрирован в следующем рисунке:  
  
 ![Иллюстрация стилей границы окон.](./media/wpf-windows-overview/window-border-styles.png)  
  
 Вы можете <xref:System.Windows.Window.WindowStyle%2A> установить с помощью разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] или кода; поскольку он вряд ли изменится в течение всего срока [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] службы окна, вы, скорее всего, наверстываете его с помощью разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Непрямоугольный стиль окна  
 Есть также ситуации, когда <xref:System.Windows.Window.WindowStyle%2A> границы стилей, что позволяет иметь не достаточно. Например, можно создать приложение с непрямоугольной границей, например, используется Microsoft Windows Media Player.  
  
 Например, рассмотрим окно пузыря речи, указанное на следующем рисунке:  
  
 ![Окно пузыря речи, которое говорит Перетащите меня.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Этот тип окна может быть <xref:System.Windows.Window.WindowStyle%2A> создан <xref:System.Windows.WindowStyle.None>путем установки свойства, и с помощью специальной поддержки, которая <xref:System.Windows.Window> имеет для прозрачности.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Это сочетание значений указывает, что окно отрисовывается полностью прозрачным. В этом состоянии нельзя использовать элементы оформления неклиентской области окна (кнопки "Закрыть", "Минимизировать", "Развернуть" и "Восстановить" и т. д.). Следовательно, необходимо предоставить свои собственные элементы.  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>Наличие панели задач  

Внешний вид окна по умолчанию включает кнопку панели задач, как и кнопку, показанную на следующем рисунке:

 ![Скриншот, на который отображается окно с кнопкой панели задач.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 Некоторые типы окон не имеют кнопки панели задач, такие как почтовые ящики и диалоговые [ящики (см. Обзор Dialog Boxes).](dialog-boxes-overview.md) Можно контролировать, отображается ли кнопка панели задач <xref:System.Windows.Window.ShowInTaskbar%2A> для`true` окна, установив свойство (по умолчанию).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>Соображения безопасности  
 <xref:System.Windows.Window>требует `UnmanagedCode` мгновенного разрешения на безопасность. Для приложений, установленных и запускаемых с локального компьютера, это включено в набор разрешений, предоставленных приложению.  
  
 Однако это не входит в набор разрешений, выданных приложениям, запускаемым из Интернета или локальной зоны интрасети с помощью ClickOnce. Следовательно, пользователи получат предупреждение о безопасности ClickOnce и должны будут повысить набор разрешений для приложения до полного доверия.  
  
 Кроме того, XBAPs не могут отображать окна или диалоговые окна по умолчанию. Для обсуждения автономных соображений безопасности приложений [см.](../wpf-security-strategy-platform-security.md)  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>Другие типы окон  
 <xref:System.Windows.Navigation.NavigationWindow>это окно, которое предназначено для размещения судоходного контента. Для получения дополнительной информации [см. Навигационный обзор).](navigation-overview.md)  
  
 Диалоговые окна — это окна, которые часто используются для сбора информации от пользователя для выполнения функции. Например, когда пользователь хочет открыть файл, диалоговое окно **Open File** обычно отображается приложением для получения имени файла от пользователя. Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Общие сведения о диалоговых окнах](dialog-boxes-overview.md)
- [Построение приложения WPF](building-a-wpf-application-wpf.md)
