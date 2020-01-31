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
ms.openlocfilehash: 17582192fabf85777bba250f6f53047a84f264b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742361"
---
# <a name="wpf-windows-overview"></a>Общие сведения об окнах WPF
Пользователи взаимодействуют с автономными приложениями Windows Presentation Foundation (WPF) через Windows. Основная цель окна — разместить содержимое, которое визуализирует данные и позволяет пользователям взаимодействовать с ними. Автономные приложения WPF предоставляют собственные окна с помощью класса <xref:System.Windows.Window>. В этом разделе представлены <xref:System.Windows.Window>, прежде чем изобретаться основы создания и управления окнами в автономных приложениях.  
  
> [!NOTE]
> Размещенные в браузере приложения WPF, включая приложения браузера XAML (XBAP) и свободные [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы, не предоставляют собственные окна. Вместо этого они размещаются в Windows, предоставляемых Windows Internet Explorer. См. раздел [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md).  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a>Класс окна  
 На следующем рисунке показаны составные части окна:  
  
 ![Снимок экрана, на котором показаны элементы окна.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 Окно разделено на две области: неклиентскую и клиентскую.  
  
 *Неклиентская область* окна реализуется WPF и включает части окна, которые являются общими для большинства окон, в том числе следующие:  
  
- Граница.  
  
- Заголовок окна.  
  
- Значок.  
  
- Кнопки "Свернуть", "Развернуть" и "Восстановить".  
  
- Кнопка "Закрыть".  
  
- Системное меню с элементами, которые позволяют пользователям свернуть, развернуть, восстановить, перемещать, изменять размеры и закрыть окно.  
  
 *Клиентская область* окна — это область внутри неклиентской области окна, которая используется разработчиками для добавления содержимого, зависящего от приложения, таких как строки меню, панели инструментов и элементы управления.  
  
 В WPF окно инкапсулируется классом <xref:System.Windows.Window>, который используется для следующих действий:  
  
- Отобразить окно.  
  
- Настроить размер, положение и внешний вид окна.  
  
- Разместить содержимое конкретного приложения.  
  
- Управлять временем существования окна.  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a>Реализация окна  
 Реализация типичного окна состоит как из внешнего вида, так и поведения, где *внешний вид* определяет, как окно будет выглядеть для пользователей и их *поведение* определяет способ работы окна при взаимодействии пользователей с ним. В WPF можно реализовать внешний вид и поведение окна с помощью кода или [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 Однако в общем случае внешний вид окна реализуется с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки, а его поведение реализуется с помощью кода программной части, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 Чтобы включить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл разметки и файл кода программной части для совместной работы, необходимо выполнить следующие действия.  
  
- В разметке элемент `Window` должен включать атрибут `x:Class`. При построении приложения существование `x:Class` в файле разметки приводит к тому, что Microsoft Build Engine (MSBuild) создает класс `partial`, производный от <xref:System.Windows.Window>, и имеет имя, заданное атрибутом `x:Class`. Для этого требуется добавить объявление пространства имен XML для схемы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`). Созданный класс `partial` реализует метод `InitializeComponent`, который вызывается для регистрации событий и задания свойств, реализованных в разметке.  
  
- В коде программной части класс должен быть классом `partial` с тем же именем, которое задано атрибутом `x:Class` в разметке и должен быть производным от <xref:System.Windows.Window>. Это позволяет связать файл кода программной части с классом `partial`, созданным для файла разметки при сборке приложения (см. раздел [Создание приложения WPF](building-a-wpf-application-wpf.md)).  
  
- В коде программной части класс <xref:System.Windows.Window> должен реализовывать конструктор, который вызывает метод `InitializeComponent`. `InitializeComponent` реализуется с помощью созданного `partial` класса файла разметки для регистрации событий и задания свойств, определенных в разметке.  
  
> [!NOTE]
> При добавлении нового <xref:System.Windows.Window> в проект с помощью Visual Studio <xref:System.Windows.Window> реализуется с помощью разметки и кода программной части, а также включает необходимую конфигурацию для создания связи между файлами разметки и кода программной части, как описано здесь.  
  
 С этой конфигурацией можно сосредоточиться на определении внешнего вида окна в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке и реализации его поведения в коде программной части. В следующем примере показано окно с кнопкой, реализованной в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке, и обработчиком событий для события <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки, реализованного в коде программной части.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a>Настройка определения окна для MSBuild  
 Реализация окна определяет, как оно настроено для MSBuild. Для окна, которое определено с использованием как [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки, так и кода программной части:  
  
- Файлы разметки XAML настраиваются как элементы MSBuild `Page`.  
  
- Файлы кода программной части настраиваются как элементы MSBuild `Compile`.  
  
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
  
 Сведения о создании приложений WPF см. [в разделе Создание приложения WPF](building-a-wpf-application-wpf.md).  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a>Время существования окна  
 Как и любой класс, окно имеет время существования, которое начинается с момента создания его экземпляра, после чего оно открывается, активируется, деактивируется и, в конечном счете, закрывается.  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a>Открытие окна  
 Чтобы открыть окно, сначала создайте его экземпляр, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 В этом примере создается экземпляр `MarkupAndCodeBehindWindow` при запуске приложения, которое происходит при возникновении события <xref:System.Windows.Application.Startup>.  
  
 При создании экземпляра окна ссылка на него автоматически добавляется в список окон, управляемых объектом <xref:System.Windows.Application> (см. <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>). Кроме того, первое окно, для которого создается экземпляр, по умолчанию устанавливается по <xref:System.Windows.Application> в качестве главного окна приложения (см. <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).  
  
 После этого окно открывается путем вызова метода <xref:System.Windows.Window.Show%2A>; Результат показан на следующем рисунке.  
  
 ![Окно, открытое при вызове Window. показывать](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 Окно, которое открывается путем вызова <xref:System.Windows.Window.Show%2A>, является немодальным окном, что означает, что приложение работает в режиме, позволяющем пользователям активировать другие окна в одном приложении.  
  
> [!NOTE]
> для открытия окон, таких как модальные диалоговые окна, вызывается <xref:System.Windows.Window.ShowDialog%2A>. Дополнительные сведения см. в разделе [Обзор диалоговых](dialog-boxes-overview.md) окон.  
  
 При вызове <xref:System.Windows.Window.Show%2A> окно выполняет инициализацию перед отображением, чтобы установить инфраструктуру, позволяющую принимать входные данные пользователя. При инициализации окна возникает событие <xref:System.Windows.Window.SourceInitialized> и отображается окно.  
  
 В качестве ярлыка <xref:System.Windows.Application.StartupUri%2A> можно задать, чтобы указать первое окно, которое автоматически открывается при запуске приложения.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 При запуске приложения окно, заданное значением <xref:System.Windows.Application.StartupUri%2A>, открывается немодально; на внутреннем уровне окно открывается путем вызова метода <xref:System.Windows.Window.Show%2A>.  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a>Владение окном  
 Окно, открываемое с помощью метода <xref:System.Windows.Window.Show%2A>, не имеет неявной связи с окном, которое его создало. Пользователи могут взаимодействовать с любым окном независимо друг от друга. Это означает, что одно из окон может сделать следующее:  
  
- Охватывает другой (за исключением случаев, когда для одного из окон свойству <xref:System.Windows.Window.Topmost%2A> задано значение `true`).  
  
- Сворачиваться, разворачиваться и восстанавливаться без влияния на другое окно.  
  
 Для некоторых окон требуется связь с окном, которое их открывает. Например, приложение интегрированной среды разработки (IDE) может открывать окна свойств и окна инструментов, в которых типичное поведение заключается в покрытии окна, которое их создает. Кроме того, такие окна должны всегда закрываться, сворачиваться, разворачиваться и восстанавливаться вместе с окном, которое их создало. Такая связь может быть установлена путем создания одного *окна другим и* достигается путем установки свойства <xref:System.Windows.Window.Owner%2A> *принадлежащего окна* со ссылкой на *окно владельца*. Эти действия показаны в следующем примере.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 После установки владения:  
  
- Принадлежащее окно может ссылаться на окно его владельца путем проверки значения его свойства <xref:System.Windows.Window.Owner%2A>.  
  
- Окно "владелец" может обнаружить все окна, которыми он владеет, проверив значение его свойства <xref:System.Windows.Window.OwnedWindows%2A>.  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a>Предотвращение активации окна  
 Существуют ситуации, когда не следует активировать Windows при отображении, например в окнах беседы приложения электронной почты в стиле Internet Messenger или окна уведомлений.  
  
 Если в приложении есть окно, которое не должно быть активировано при отображении, можно задать для его свойства <xref:System.Windows.Window.ShowActivated%2A> значение `false` перед первым вызовом метода <xref:System.Windows.Window.Show%2A>. Результат:  
  
- Окно не активируется.  
  
- Событие <xref:System.Windows.Window.Activated> окна не возникает.  
  
- Текущее активированное окно останется активным.  
  
 Однако окно активируется, если пользователь щелкнет его неклиентскую или клиентскую область. В этом случае:  
  
- Окно активируется.  
  
- Вызывается событие <xref:System.Windows.Window.Activated> окна.  
  
- Ранее активированное окно деактивируется.  
  
- События <xref:System.Windows.Window.Deactivated> и <xref:System.Windows.Window.Activated> окна впоследствии вызываются в ответ на действия пользователя.  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a>Активация окна  
 При первом открытии окна он становится активным окном (если для параметра <xref:System.Windows.Window.ShowActivated%2A> задано значение `false`). *Активное окно* — это окно, которое в данный момент захватывает ввод пользователя, например, нажатие клавиш и щелчки мышью. Когда окно активируется, оно вызывает событие <xref:System.Windows.Window.Activated>.  
  
> [!NOTE]
> При первом открытии окна события <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.Window.ContentRendered> вызываются только после возникновения события <xref:System.Windows.Window.Activated>. Учитывая это, окно может считаться открытым при возникновении <xref:System.Windows.Window.ContentRendered>.  
  
 После активизации окна пользователь может активировать другое окно в том же приложении или активировать другое приложение. В этом случае активное в настоящий момент окно отключается и вызывает событие <xref:System.Windows.Window.Deactivated>. Аналогично, когда пользователь выбирает неактивное окно, окно снова становится активным, а <xref:System.Windows.Window.Activated> вызывается.  
  
 Одной из распространенных причин для обработки <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> является включение и отключение функций, которые могут выполняться только при активном окне. Например, некоторые окна отображают интерактивное содержимое, которое требует постоянного ввода данных или внимания пользователя, включая игры и видеопроигрыватели. Ниже приведен пример упрощенного видеопроигрывателя, демонстрирующий обработку <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> для реализации такого поведения.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 Другие типы приложений могут выполнять код в фоновом режиме, когда окно деактивировано. Например, почтовый клиент может продолжать опрашивать почтовый сервер, пока пользователь работает с другими приложениями. Такие приложения часто обеспечивают другое или дополнительное поведение, когда главное окно не активно. В случае почтовой программы это может означать как добавление нового почтового элемента в папку "Входящие", так и добавление значка уведомления на панель задач. Значок уведомления должен отображаться только в том случае, если окно почты не активно, которое можно определить с помощью проверки свойства <xref:System.Windows.Window.IsActive%2A>.  
  
 Если фоновая задача завершается, в окне может потребоваться более срочно уведомлять пользователя, вызывая метод <xref:System.Windows.Window.Activate%2A>. Если пользователь взаимодействует с другим приложением, активированным при вызове <xref:System.Windows.Window.Activate%2A>, кнопка панели задач окна отображается. Если пользователь взаимодействует с текущим приложением, вызов <xref:System.Windows.Window.Activate%2A> приведет к переводу окна на передний план.  
  
> [!NOTE]
> Активацию области действия приложения можно выполнять с помощью событий <xref:System.Windows.Application.Activated?displayProperty=nameWithType> и <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a>Закрытие окна  
 Время существования окна заканчивается, когда пользователь его закрывает. Окно может быть закрыто с помощью элементов в неклиентской области, включая следующие:  
  
- Элемент **закрытия** **системного** меню.  
  
- Нажатие клавиш ALT+F4.  
  
- Нажмите кнопку **Закрыть** .  
  
 Можно указать дополнительные способы закрытия окна для клиентской области, к наиболее типичным из которых относятся следующие:  
  
- Элемент **Exit** в меню **файл** , обычно для основных окон приложений.  
  
- Элемент **закрытия** в меню **файл** , обычно в дополнительном окне приложения.  
  
- Кнопка **Отмена** , обычно в модальном диалоговом окне.  
  
- Кнопка " **Закрыть** " (обычно в немодальном диалоговом окне).  
  
 Чтобы закрыть окно в ответ на один из этих пользовательских механизмов, необходимо вызвать метод <xref:System.Windows.Window.Close%2A>. В следующем примере реализуется возможность закрытия окна с помощью команды **выход** в меню **файл** .  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 Когда окно закрывается, оно вызывает два события: <xref:System.Windows.Window.Closing> и <xref:System.Windows.Window.Closed>.  
  
 <xref:System.Windows.Window.Closing> возникает перед закрытием окна и предоставляет механизм, с помощью которого можно предотвратить закрытие окна. Одна из распространенных причин, препятствующих закрытию окна, заключается в том, что содержимое окна содержит измененные данные. В этом случае событие <xref:System.Windows.Window.Closing> может быть обработано, чтобы определить, являются ли данные "грязными", и, если да, попросить пользователя либо продолжить закрытие окна без сохранения данных, либо отменить закрытие окна. В следующем примере показаны ключевые аспекты обработки <xref:System.Windows.Window.Closing>.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 Обработчику <xref:System.Windows.Window.Closing> событий передается <xref:System.ComponentModel.CancelEventArgs>, который реализует свойство `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, для которого задано значение `true`, чтобы предотвратить закрытие окна.  
  
 Если <xref:System.Windows.Window.Closing> не обрабатывается или обрабатывается, но не отменяется, окно будет закрыто. Непосредственно перед закрытием окна возникает <xref:System.Windows.Window.Closed>. На этом этапе невозможно предотвратить закрытие окна.  
  
> [!NOTE]
> Приложение может быть настроено на автоматическое завершение работы при закрытии главного окна приложения (см. <xref:System.Windows.Application.MainWindow%2A>) или при закрытии последнего окна. Дополнительные сведения см. в разделе <xref:System.Windows.Application.ShutdownMode%2A>.  
  
 Хотя окно может быть явно закрыто с помощью механизмов, предоставленных в неклиентской и клиентской областях, окно также может быть неявно закрыто в результате поведения в других частях приложения или окна, включая следующие:  
  
- Пользователь выходит из системы или завершает работу Windows.  
  
- Владелец окна закрывается (см. <xref:System.Windows.Window.Owner%2A>).  
  
- Главное окно приложения закрывается, и <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnMainWindowClose>.  
  
- вызывается метод <xref:System.Windows.Application.Shutdown%2A>;  
  
> [!NOTE]
> После закрытия окно нельзя открыть повторно.  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a>События времени существования окна  
 На следующем рисунке показана последовательность основных событий во время существования окна:  
  
 ![Схема, показывающая события в течение времени существования окна.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 На следующем рисунке показана последовательность основных событий во время существования окна, которое отображается без активации (<xref:System.Windows.Window.ShowActivated%2A> устанавливается в `false` до отображения окна):  
  
 ![Схема, показывающая события в течение времени существования окна без активации.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a>Расположение окна  
 Когда окно открыто, оно располагается в координатах x и y относительно рабочего стола. Это расположение можно определить с помощью проверки свойств <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> соответственно. Можно задать эти свойства, чтобы изменить расположение окна.  
  
 Можно также указать начальное расположение <xref:System.Windows.Window> при первом отображении, задав для свойства <xref:System.Windows.Window.WindowStartupLocation%2A> одно из следующих значений перечисления <xref:System.Windows.WindowStartupLocation>:  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner> (по умолчанию)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 Если в качестве расположения запуска указано <xref:System.Windows.WindowStartupLocation.Manual>, а свойства <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> не заданы, <xref:System.Windows.Window> запросит в Windows расположение, в котором будет размещаться.  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a>Окна верхнего уровня и Z-порядок  
 Помимо расположения в координатах x и y, окно имеет координату по оси z, которая определяет его вертикальную позицию относительно других окон. Это называется z-порядком окна. Существует два типа: обычный z-порядок и верхний z-порядок. Расположение окна в *стандартном z-порядке* определяется тем, активно ли оно в данный момент. По умолчанию окно находится в обычном z-порядке. Расположение окна в *верхнем z-порядке* также определяется тем, активно ли оно в данный момент. Кроме того, окна в самом верхнем z-порядке всегда расположены над окнами в обычном z-порядке. Окно находится в верхнем z-порядке, присвоив свойству <xref:System.Windows.Window.Topmost%2A> значение `true`.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 В каждом z-порядке активное в данный момент окно появляется поверх всех других окон в том же z-порядке.  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a>Размер окна  
 Помимо расположения рабочего стола, размер окна определяется несколькими свойствами, включая различные свойства Width и Height, а также <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.MaxWidth%2A> используются для управления диапазоном ширины, который может иметь окно в течение своего времени существования, и настраивается, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 Высота окна управляется <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>и <xref:System.Windows.FrameworkElement.MaxHeight%2A>и настраивается, как показано в следующем примере.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 Так как различные значения ширины и высоты определяют диапазон, то что ширина и высота изменяемого окна могут находиться в любом месте указанного диапазона для соответствующего измерения. Чтобы определить текущую ширину и высоту, проверьте <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A>соответственно.  
  
 Если вы хотите, чтобы ширина и высота окна имели размер, соответствующий размеру содержимого окна, можно использовать свойство <xref:System.Windows.Window.SizeToContent%2A>, которое имеет следующие значения:  
  
- <xref:System.Windows.SizeToContent.Manual>. Нет эффекта (по умолчанию).  
  
- <xref:System.Windows.SizeToContent.Width>. По ширине содержимого, что оказывает тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> ширины содержимого.  
  
- <xref:System.Windows.SizeToContent.Height>. По высоте содержимого, что оказывает тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> к высоте содержимого.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. По ширине и высоте содержимого, которая имеет тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> к высоте содержимого, и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> ширины содержимого.  
  
 В следующем примере показано окно, размеры которого автоматически устанавливаются равными его содержимому по вертикали и по горизонтали при первом отображении.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 В следующем примере показано, как задать свойство <xref:System.Windows.Window.SizeToContent%2A> в коде, чтобы указать, как размер окна изменяется в соответствии с содержимым.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a>Порядок приоритета для свойств размера  
 Различные свойства размеров окна объединяются для определения диапазона ширины и высоты окна изменяемого размера. Чтобы обеспечить соблюдение допустимого диапазона, <xref:System.Windows.Window> вычисляет значения свойств размера с помощью следующих порядков приоритета.  
  
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
  
 Порядок приоритета также может определять размер окна, когда оно развернуто, которое управляется с помощью свойства <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="WindowState"></a>   
## <a name="window-state"></a>Состояние окна  
 В течение времени существования окна изменяемого размера оно может иметь три состояния: обычное, свернутое и развернутое. Окно с *нормальным* состоянием является состоянием окна по умолчанию. Окно с этим состоянием позволяет пользователю перемещать его и изменять размер, используя захват для изменения размера или границу.  
  
 Окно с *свернутым* состоянием сворачивается в кнопку панели задач, если <xref:System.Windows.Window.ShowInTaskbar%2A> имеет значение `true`. в противном случае он сворачивается до наименьшего возможного размера, который может быть и перемещается в левый нижний угол рабочего стола. Ни один из типов свернутого окна не может быть изменен с помощью границы или захвата для изменения размера, хотя свернутое окно, которое не отображается на панели задач, можно перетаскивать на рабочем столе.  
  
 Окно с *развернутым* состоянием разворачивается до максимального размера, который может быть только большим, чем его <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, а <xref:System.Windows.Window.SizeToContent%2A> свойства определяются. Как и для свернутого окна, размер развернутого окна нельзя изменить с помощью захвата для изменения размера или перетаскивания границы.  
  
> [!NOTE]
> Значения свойств <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.Height%2A> окна всегда представляют значения для нормального состояния, даже если окно в данный момент развернуто или уменьшено.  
  
 Состояние окна можно настроить, задав его свойство <xref:System.Windows.Window.WindowState%2A>, которое может иметь одно из следующих <xref:System.Windows.WindowState> перечисляемых значений:  
  
- <xref:System.Windows.WindowState.Normal> (по умолчанию)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 В следующем примере показано создание окна, которое отображается развернутым при его открытии.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 В общем случае следует задать <xref:System.Windows.Window.WindowState%2A>, чтобы настроить начальное состояние окна. После отображения окна изменяемого размера пользователи могут нажимать кнопки свертывания, развертывания и восстановления на панели заголовка окна, чтобы изменить состояние окна.  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a>Внешний вид окна  
 Можно изменить внешний вид клиентской области окна, добавляя в нее определенное содержимое, такое как кнопки, метки и текстовые поля. Чтобы настроить неклиентскую область, <xref:System.Windows.Window> предоставляет несколько свойств, в том числе <xref:System.Windows.Window.Icon%2A> для установки значка окна и <xref:System.Windows.Window.Title%2A> для задания его заголовка.  
  
 Можно также изменить внешний вид и поведение границы неклиентской области, настраивая режим изменения размера окна, стиль окна и отображение в виде кнопки на панели задач рабочего стола.  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a>Режим изменения размера  
 В зависимости от свойства <xref:System.Windows.Window.WindowStyle%2A> можно управлять тем, как пользователи могут изменять размер окна (и, если). Выбранный стиль окна влияет на то, может ли пользователь изменять размер окна, перетаскивая его границу с помощью мыши, появляются ли кнопки **сворачивания**, **развернуть**и **изменить размер** в неклиентской области и, если они отображаются, включены ли они.  
  
 Можно настроить изменение размера окна, задав его свойство <xref:System.Windows.Window.ResizeMode%2A>, которое может быть одним из следующих <xref:System.Windows.ResizeMode> перечисляемых значений:  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize> (по умолчанию)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 Как и в случае с <xref:System.Windows.Window.WindowStyle%2A>, режим изменения размера окна вряд ли изменится во время его существования. Это означает, что скорее всего, вы задаете его из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 Обратите внимание, что можно определить, является ли окно развернутым, минимальным или восстанавливаемым, проверив свойство <xref:System.Windows.Window.WindowState%2A>.  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a>Стиль окна  
 Граница, предоставляемая из неклиентской области окна, подходит для большинства приложений. Однако существуют ситуации, когда требуются различные типы границ либо границы вовсе не требуются, в зависимости от типа окна.  
  
 Чтобы управлять тем, какой тип границы получает окно, задайте для свойства <xref:System.Windows.Window.WindowStyle%2A> одно из следующих значений перечисления <xref:System.Windows.WindowStyle>.  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow> (по умолчанию)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 Эффект этих стилей окна показан на следующем рисунке:  
  
 ![Иллюстрация стилей границ окна.](./media/wpf-windows-overview/window-border-styles.png)  
  
 <xref:System.Windows.Window.WindowStyle%2A> можно задать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки или кода. так как маловероятно изменить время существования окна, скорее всего, он будет настроен с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>Непрямоугольный стиль окна  
 Существуют также ситуации, когда стили границ, которые <xref:System.Windows.Window.WindowStyle%2A> позволяют, недостаточно. Например, может потребоваться создать приложение с непрямоугольной границей, например с помощью проигрывателя Microsoft Windows Media.  
  
 Например, рассмотрим всплывающее окно распознавания речи, показанное на следующем рисунке:  
  
 ![Всплывающее окно речевого ввода, говорящее на перетаскивание.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 Этот тип окна можно создать, задав для свойства <xref:System.Windows.Window.WindowStyle%2A> значение <xref:System.Windows.WindowStyle.None>и используя специальную поддержку, <xref:System.Windows.Window> для прозрачности.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 Это сочетание значений указывает, что окно отрисовывается полностью прозрачным. В этом состоянии нельзя использовать элементы оформления неклиентской области окна (кнопки "Закрыть", "Минимизировать", "Развернуть" и "Восстановить" и т. д.). Следовательно, необходимо предоставить свои собственные элементы.  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a>Наличие панели задач  

Внешний вид окна по умолчанию включает кнопку панели задач, как показано на следующем рисунке.

 ![Снимок экрана, на котором показано окно с кнопкой на панели задач.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 У некоторых типов окон нет кнопки панели задач, например окон сообщений и диалоговых окон (см. [Обзор диалоговых окон](dialog-boxes-overview.md)). Можно указать, отображается ли кнопка панели задач для окна, задав свойство <xref:System.Windows.Window.ShowInTaskbar%2A> (по умолчанию`true`).  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a>Вопросы безопасности  
 <xref:System.Windows.Window> требует создания экземпляра разрешения `UnmanagedCode` безопасности. Для приложений, установленных и запускаемых с локального компьютера, это включено в набор разрешений, предоставленных приложению.  
  
 Однако это выходит за рамки набора разрешений, предоставленных приложениям, которые запускаются из зоны Интернета или местной интрасети с помощью ClickOnce. Следовательно, пользователи получат предупреждение системы безопасности ClickOnce и потребуют повысить уровень разрешений приложения до полного доверия.  
  
 Кроме того, XBAP не может отображать окна или диалоговые окна по умолчанию. Обсуждение вопросов безопасности отдельных приложений см. в разделе [стратегия безопасности WPF — безопасность платформы](../wpf-security-strategy-platform-security.md).  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a>Другие типы окон  
 <xref:System.Windows.Navigation.NavigationWindow> — это окно, предназначенное для размещения содержимого с возможностью навигации. Дополнительные сведения см. в разделе [Общие сведения о навигации](navigation-overview.md).  
  
 Диалоговые окна — это окна, которые часто используются для сбора информации от пользователя для выполнения функции. Например, когда пользователь хочет открыть файл, диалоговое окно **Открытие файла** обычно отображается приложением для получения имени файла от пользователя. Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](dialog-boxes-overview.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [Общие сведения о диалоговых окнах](dialog-boxes-overview.md)
- [Построение приложения WPF](building-a-wpf-application-wpf.md)
