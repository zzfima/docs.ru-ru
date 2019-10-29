---
title: Общие сведения об окнах WPF
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
ms.openlocfilehash: e62825a88858a63984860cbc8a1c570f784f663f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040863"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="a5fe1-102">Общие сведения об окнах WPF</span><span class="sxs-lookup"><span data-stu-id="a5fe1-102">WPF Windows Overview</span></span>
<span data-ttu-id="a5fe1-103">Пользователи взаимодействуют с автономными приложениями Windows Presentation Foundation (WPF) через Windows.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-103">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="a5fe1-104">Основная цель окна — разместить содержимое, которое визуализирует данные и позволяет пользователям взаимодействовать с ними.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-104">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="a5fe1-105">Автономные [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения предоставляют собственные окна с помощью класса <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-105">Standalone [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="a5fe1-106">В этом разделе представлены <xref:System.Windows.Window>, прежде чем изобретаться основы создания и управления окнами в автономных приложениях.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-106">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-107">Размещенные в браузере [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, в том числе [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и свободные [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы, не предоставляют собственные окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-107">Browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="a5fe1-108">Вместо этого они размещаются в Windows, предоставляемых Windows Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-108">Instead, they are hosted in windows provided by Windows Internet Explorer.</span></span> <span data-ttu-id="a5fe1-109">См. раздел [Общие сведения о приложениях браузера WPF XAML](wpf-xaml-browser-applications-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-109">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>   
## <a name="the-window-class"></a><span data-ttu-id="a5fe1-110">Класс окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-110">The Window Class</span></span>  
 <span data-ttu-id="a5fe1-111">На следующем рисунке показаны составные части окна:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-111">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![Снимок экрана, на котором показаны элементы окна.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="a5fe1-113">Окно разделено на две области: неклиентскую и клиентскую.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-113">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="a5fe1-114">*Неклиентская область* окна реализуется [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и включает части окна, которые являются общими для большинства окон, в том числе следующие:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-114">The *non-client area* of a window is implemented by [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
- <span data-ttu-id="a5fe1-115">Граница.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-115">A border.</span></span>  
  
- <span data-ttu-id="a5fe1-116">Заголовок окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-116">A title bar.</span></span>  
  
- <span data-ttu-id="a5fe1-117">Значок.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-117">An icon.</span></span>  
  
- <span data-ttu-id="a5fe1-118">Кнопки "Свернуть", "Развернуть" и "Восстановить".</span><span class="sxs-lookup"><span data-stu-id="a5fe1-118">Minimize, Maximize, and Restore buttons.</span></span>  
  
- <span data-ttu-id="a5fe1-119">Кнопка "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="a5fe1-119">A Close button.</span></span>  
  
- <span data-ttu-id="a5fe1-120">Системное меню с элементами, которые позволяют пользователям свернуть, развернуть, восстановить, перемещать, изменять размеры и закрыть окно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-120">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="a5fe1-121">*Клиентская область* окна — это область внутри неклиентской области окна, которая используется разработчиками для добавления содержимого, зависящего от приложения, таких как строки меню, панели инструментов и элементы управления.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-121">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="a5fe1-122">В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]окно инкапсулируется классом <xref:System.Windows.Window>, который используется для следующих действий:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-122">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
- <span data-ttu-id="a5fe1-123">Отобразить окно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-123">Display a window.</span></span>  
  
- <span data-ttu-id="a5fe1-124">Настроить размер, положение и внешний вид окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-124">Configure the size, position, and appearance of a window.</span></span>  
  
- <span data-ttu-id="a5fe1-125">Разместить содержимое конкретного приложения.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-125">Host application-specific content.</span></span>  
  
- <span data-ttu-id="a5fe1-126">Управлять временем существования окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-126">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>   
## <a name="implementing-a-window"></a><span data-ttu-id="a5fe1-127">Реализация окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-127">Implementing a Window</span></span>  
 <span data-ttu-id="a5fe1-128">Реализация типичного окна состоит как из внешнего вида, так и поведения, где *внешний вид* определяет, как окно будет выглядеть для пользователей и их *поведение* определяет способ работы окна при взаимодействии пользователей с ним.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-128">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="a5fe1-129">В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]можно реализовать внешний вид и поведение окна, используя либо код, либо [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметку.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-129">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="a5fe1-130">Однако в общем случае внешний вид окна реализуется с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки, а его поведение реализуется с помощью кода программной части, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-130">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="a5fe1-131">Чтобы включить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл разметки и файл кода программной части для совместной работы, необходимо выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-131">To enable a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
- <span data-ttu-id="a5fe1-132">В разметке элемент `Window` должен включать атрибут `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-132">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="a5fe1-133">При построении приложения существование `x:Class` в файле разметки приводит к тому, что Microsoft Build Engine (MSBuild) создает класс `partial`, производный от <xref:System.Windows.Window>, и имеет имя, заданное атрибутом `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-133">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="a5fe1-134">Для этого требуется добавить [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] объявление пространства имен для схемы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-134">This requires the addition of an [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="a5fe1-135">Созданный класс `partial` реализует метод `InitializeComponent`, который вызывается для регистрации событий и задания свойств, реализованных в разметке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-135">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
- <span data-ttu-id="a5fe1-136">В коде программной части класс должен быть классом `partial` с тем же именем, которое задано атрибутом `x:Class` в разметке и должен быть производным от <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-136">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="a5fe1-137">Это позволяет связать файл кода программной части с классом `partial`, созданным для файла разметки при сборке приложения (см. раздел [Создание приложения WPF](building-a-wpf-application-wpf.md)).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-137">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
- <span data-ttu-id="a5fe1-138">В коде программной части класс <xref:System.Windows.Window> должен реализовывать конструктор, который вызывает метод `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-138">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="a5fe1-139">`InitializeComponent` реализуется с помощью созданного `partial` класса файла разметки для регистрации событий и задания свойств, определенных в разметке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-139">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-140">При добавлении нового <xref:System.Windows.Window> в проект с помощью Visual Studio <xref:System.Windows.Window> реализуется с помощью разметки и кода программной части, а также включает необходимую конфигурацию для создания связи между файлами разметки и кода программной части, как описано здесь.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-140">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="a5fe1-141">С этой конфигурацией можно сосредоточиться на определении внешнего вида окна в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке и реализации его поведения в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-141">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="a5fe1-142">В следующем примере показано окно с кнопкой, реализованной в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметке, и обработчиком событий для события <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки, реализованного в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-142">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>   
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="a5fe1-143">Настройка определения окна для MSBuild</span><span class="sxs-lookup"><span data-stu-id="a5fe1-143">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="a5fe1-144">Реализация окна определяет, как оно настроено для MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-144">How you implement your window determines how it is configured for MSBuild.</span></span> <span data-ttu-id="a5fe1-145">Для окна, которое определено с использованием как [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки, так и кода программной части:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-145">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
- <span data-ttu-id="a5fe1-146">Файлы разметки XAML настраиваются как элементы MSBuild `Page`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-146">XAML markup files are configured as MSBuild `Page` items.</span></span>  
  
- <span data-ttu-id="a5fe1-147">Файлы кода программной части настраиваются как элементы MSBuild `Compile`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-147">Code-behind files are configured as MSBuild `Compile` items.</span></span>  
  
 <span data-ttu-id="a5fe1-148">Это показано в следующем файле проекта MSBuild.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-148">This is shown in the following MSBuild project file.</span></span>  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="a5fe1-149">Сведения о создании [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений см. [в разделе Создание приложения WPF](building-a-wpf-application-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-149">For information about building [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>   
## <a name="window-lifetime"></a><span data-ttu-id="a5fe1-150">Время существования окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-150">Window Lifetime</span></span>  
 <span data-ttu-id="a5fe1-151">Как и любой класс, окно имеет время существования, которое начинается с момента создания его экземпляра, после чего оно открывается, активируется, деактивируется и, в конечном счете, закрывается.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-151">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>   
### <a name="opening-a-window"></a><span data-ttu-id="a5fe1-152">Открытие окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-152">Opening a Window</span></span>  
 <span data-ttu-id="a5fe1-153">Чтобы открыть окно, сначала создайте его экземпляр, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-153">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="a5fe1-154">В этом примере создается экземпляр `MarkupAndCodeBehindWindow` при запуске приложения, которое происходит при возникновении события <xref:System.Windows.Application.Startup>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-154">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="a5fe1-155">При создании экземпляра окна ссылка на него автоматически добавляется в список окон, управляемых объектом <xref:System.Windows.Application> (см. <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-155">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="a5fe1-156">Кроме того, первое окно, для которого создается экземпляр, по умолчанию устанавливается по <xref:System.Windows.Application> в качестве главного окна приложения (см. <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-156">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="a5fe1-157">После этого окно открывается путем вызова метода <xref:System.Windows.Window.Show%2A>; Результат показан на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-157">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![Окно, открытое при вызове Window. показывать](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="a5fe1-159">Окно, которое открывается путем вызова <xref:System.Windows.Window.Show%2A>, является немодальным окном, что означает, что приложение работает в режиме, позволяющем пользователям активировать другие окна в одном приложении.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-159">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-160">для открытия окон, таких как модальные диалоговые окна, вызывается <xref:System.Windows.Window.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-160"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="a5fe1-161">Дополнительные сведения см. в разделе [Обзор диалоговых](dialog-boxes-overview.md) окон.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-161">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="a5fe1-162">При вызове <xref:System.Windows.Window.Show%2A> окно выполняет инициализацию перед отображением, чтобы установить инфраструктуру, позволяющую принимать входные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-162">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="a5fe1-163">При инициализации окна возникает событие <xref:System.Windows.Window.SourceInitialized> и отображается окно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-163">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="a5fe1-164">В качестве ярлыка <xref:System.Windows.Application.StartupUri%2A> можно задать, чтобы указать первое окно, которое автоматически открывается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-164">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="a5fe1-165">При запуске приложения окно, заданное значением <xref:System.Windows.Application.StartupUri%2A>, открывается немодально; на внутреннем уровне окно открывается путем вызова метода <xref:System.Windows.Window.Show%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-165">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>   
#### <a name="window-ownership"></a><span data-ttu-id="a5fe1-166">Владение окном</span><span class="sxs-lookup"><span data-stu-id="a5fe1-166">Window Ownership</span></span>  
 <span data-ttu-id="a5fe1-167">Окно, открываемое с помощью метода <xref:System.Windows.Window.Show%2A>, не имеет неявной связи с окном, которое его создало. Пользователи могут взаимодействовать с любым окном независимо друг от друга. Это означает, что одно из окон может сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-167">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
- <span data-ttu-id="a5fe1-168">Охватывает другой (за исключением случаев, когда для одного из окон свойству <xref:System.Windows.Window.Topmost%2A> задано значение `true`).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-168">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
- <span data-ttu-id="a5fe1-169">Сворачиваться, разворачиваться и восстанавливаться без влияния на другое окно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-169">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="a5fe1-170">Для некоторых окон требуется связь с окном, которое их открывает.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-170">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="a5fe1-171">Например, приложение интегрированной среды разработки (IDE) может открывать окна свойств и окна инструментов, в которых типичное поведение заключается в покрытии окна, которое их создает.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-171">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="a5fe1-172">Кроме того, такие окна должны всегда закрываться, сворачиваться, разворачиваться и восстанавливаться вместе с окном, которое их создало.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-172">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="a5fe1-173">Такая связь может быть установлена путем создания одного *окна другим и* достигается путем установки свойства <xref:System.Windows.Window.Owner%2A> *принадлежащего окна* со ссылкой на *окно владельца*.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-173">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="a5fe1-174">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-174">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="a5fe1-175">После установки владения:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-175">After ownership is established:</span></span>  
  
- <span data-ttu-id="a5fe1-176">Принадлежащее окно может ссылаться на окно его владельца путем проверки значения его свойства <xref:System.Windows.Window.Owner%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-176">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
- <span data-ttu-id="a5fe1-177">Окно "владелец" может обнаружить все окна, которыми он владеет, проверив значение его свойства <xref:System.Windows.Window.OwnedWindows%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-177">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>   
#### <a name="preventing-window-activation"></a><span data-ttu-id="a5fe1-178">Предотвращение активации окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-178">Preventing Window Activation</span></span>  
 <span data-ttu-id="a5fe1-179">Существуют ситуации, когда не следует активировать Windows при отображении, например в окнах беседы приложения электронной почты в стиле Internet Messenger или окна уведомлений.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-179">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="a5fe1-180">Если в приложении есть окно, которое не должно быть активировано при отображении, можно задать для его свойства <xref:System.Windows.Window.ShowActivated%2A> значение `false` перед первым вызовом метода <xref:System.Windows.Window.Show%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-180">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="a5fe1-181">Результат:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-181">As a consequence:</span></span>  
  
- <span data-ttu-id="a5fe1-182">Окно не активируется.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-182">The window is not activated.</span></span>  
  
- <span data-ttu-id="a5fe1-183">Событие <xref:System.Windows.Window.Activated> окна не возникает.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-183">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
- <span data-ttu-id="a5fe1-184">Текущее активированное окно останется активным.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-184">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="a5fe1-185">Однако окно активируется, если пользователь щелкнет его неклиентскую или клиентскую область.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-185">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="a5fe1-186">В этом случае:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-186">In this case:</span></span>  
  
- <span data-ttu-id="a5fe1-187">Окно активируется.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-187">The window is activated.</span></span>  
  
- <span data-ttu-id="a5fe1-188">Вызывается событие <xref:System.Windows.Window.Activated> окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-188">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
- <span data-ttu-id="a5fe1-189">Ранее активированное окно деактивируется.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-189">The previously activated window is deactivated.</span></span>  
  
- <span data-ttu-id="a5fe1-190">События <xref:System.Windows.Window.Deactivated> и <xref:System.Windows.Window.Activated> окна впоследствии вызываются в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-190">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>   
### <a name="window-activation"></a><span data-ttu-id="a5fe1-191">Активация окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-191">Window Activation</span></span>  
 <span data-ttu-id="a5fe1-192">При первом открытии окна он становится активным окном (если для параметра <xref:System.Windows.Window.ShowActivated%2A> задано значение `false`).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-192">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="a5fe1-193">*Активное окно* — это окно, которое в данный момент захватывает ввод пользователя, например, нажатие клавиш и щелчки мышью.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-193">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="a5fe1-194">Когда окно активируется, оно вызывает событие <xref:System.Windows.Window.Activated>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-194">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-195">При первом открытии окна события <xref:System.Windows.FrameworkElement.Loaded> и <xref:System.Windows.Window.ContentRendered> вызываются только после возникновения события <xref:System.Windows.Window.Activated>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-195">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="a5fe1-196">Учитывая это, окно может считаться открытым при возникновении <xref:System.Windows.Window.ContentRendered>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-196">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="a5fe1-197">После активизации окна пользователь может активировать другое окно в том же приложении или активировать другое приложение.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-197">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="a5fe1-198">В этом случае активное в настоящий момент окно отключается и вызывает событие <xref:System.Windows.Window.Deactivated>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-198">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="a5fe1-199">Аналогично, когда пользователь выбирает неактивное окно, окно снова становится активным, а <xref:System.Windows.Window.Activated> вызывается.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-199">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="a5fe1-200">Одной из распространенных причин для обработки <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> является включение и отключение функций, которые могут выполняться только при активном окне.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-200">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="a5fe1-201">Например, некоторые окна отображают интерактивное содержимое, которое требует постоянного ввода данных или внимания пользователя, включая игры и видеопроигрыватели.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-201">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="a5fe1-202">Ниже приведен пример упрощенного видеопроигрывателя, демонстрирующий обработку <xref:System.Windows.Window.Activated> и <xref:System.Windows.Window.Deactivated> для реализации такого поведения.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-202">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="a5fe1-203">Другие типы приложений могут выполнять код в фоновом режиме, когда окно деактивировано.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-203">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="a5fe1-204">Например, почтовый клиент может продолжать опрашивать почтовый сервер, пока пользователь работает с другими приложениями.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-204">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="a5fe1-205">Такие приложения часто обеспечивают другое или дополнительное поведение, когда главное окно не активно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-205">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="a5fe1-206">В случае почтовой программы это может означать как добавление нового почтового элемента в папку "Входящие", так и добавление значка уведомления на панель задач.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-206">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="a5fe1-207">Значок уведомления должен отображаться только в том случае, если окно почты не активно, которое можно определить с помощью проверки свойства <xref:System.Windows.Window.IsActive%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-207">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="a5fe1-208">Если фоновая задача завершается, в окне может потребоваться более срочно уведомлять пользователя, вызывая метод <xref:System.Windows.Window.Activate%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-208">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="a5fe1-209">Если пользователь взаимодействует с другим приложением, активированным при вызове <xref:System.Windows.Window.Activate%2A>, кнопка панели задач окна отображается.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-209">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="a5fe1-210">Если пользователь взаимодействует с текущим приложением, вызов <xref:System.Windows.Window.Activate%2A> приведет к переводу окна на передний план.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-210">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-211">Активацию области действия приложения можно выполнять с помощью событий <xref:System.Windows.Application.Activated?displayProperty=nameWithType> и <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-211">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>   
### <a name="closing-a-window"></a><span data-ttu-id="a5fe1-212">Закрытие окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-212">Closing a Window</span></span>  
 <span data-ttu-id="a5fe1-213">Время существования окна заканчивается, когда пользователь его закрывает.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-213">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="a5fe1-214">Окно может быть закрыто с помощью элементов в неклиентской области, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-214">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
- <span data-ttu-id="a5fe1-215">Элемент **закрытия** **системного** меню.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-215">The **Close** item of the **System** menu.</span></span>  
  
- <span data-ttu-id="a5fe1-216">Нажатие клавиш ALT+F4.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-216">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="a5fe1-217">Нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="a5fe1-217">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="a5fe1-218">Можно указать дополнительные способы закрытия окна для клиентской области, к наиболее типичным из которых относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-218">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
- <span data-ttu-id="a5fe1-219">Элемент **Exit** в меню **файл** , обычно для основных окон приложений.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-219">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
- <span data-ttu-id="a5fe1-220">Элемент **закрытия** в меню **файл** , обычно в дополнительном окне приложения.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-220">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
- <span data-ttu-id="a5fe1-221">Кнопка **Отмена** , обычно в модальном диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-221">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
- <span data-ttu-id="a5fe1-222">Кнопка " **Закрыть** " (обычно в немодальном диалоговом окне).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-222">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="a5fe1-223">Чтобы закрыть окно в ответ на один из этих пользовательских механизмов, необходимо вызвать метод <xref:System.Windows.Window.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-223">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="a5fe1-224">В следующем примере реализуется возможность закрытия окна с помощью команды **выход** в меню **файл** .</span><span class="sxs-lookup"><span data-stu-id="a5fe1-224">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="a5fe1-225">Когда окно закрывается, оно вызывает два события: <xref:System.Windows.Window.Closing> и <xref:System.Windows.Window.Closed>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-225">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="a5fe1-226"><xref:System.Windows.Window.Closing> возникает перед закрытием окна и предоставляет механизм, с помощью которого можно предотвратить закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-226"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="a5fe1-227">Одна из распространенных причин, препятствующих закрытию окна, заключается в том, что содержимое окна содержит измененные данные.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-227">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="a5fe1-228">В этом случае событие <xref:System.Windows.Window.Closing> может быть обработано, чтобы определить, являются ли данные "грязными", и, если да, попросить пользователя либо продолжить закрытие окна без сохранения данных, либо отменить закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-228">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="a5fe1-229">В следующем примере показаны ключевые аспекты обработки <xref:System.Windows.Window.Closing>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-229">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="a5fe1-230">Обработчику <xref:System.Windows.Window.Closing> событий передается <xref:System.ComponentModel.CancelEventArgs>, который реализует свойство `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>, для которого задано значение `true`, чтобы предотвратить закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-230">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="a5fe1-231">Если <xref:System.Windows.Window.Closing> не обрабатывается или обрабатывается, но не отменяется, окно будет закрыто.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-231">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="a5fe1-232">Непосредственно перед закрытием окна возникает <xref:System.Windows.Window.Closed>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-232">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="a5fe1-233">На этом этапе невозможно предотвратить закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-233">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-234">Приложение может быть настроено на автоматическое завершение работы при закрытии главного окна приложения (см. <xref:System.Windows.Application.MainWindow%2A>) или при закрытии последнего окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-234">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="a5fe1-235">Дополнительные сведения см. в разделе <xref:System.Windows.Application.ShutdownMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-235">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="a5fe1-236">Хотя окно может быть явно закрыто с помощью механизмов, предоставленных в неклиентской и клиентской областях, окно также может быть неявно закрыто в результате поведения в других частях приложения или окна, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-236">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>  
  
- <span data-ttu-id="a5fe1-237">Пользователь выходит из системы или завершает работу Windows.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-237">A user logs off or shuts down Windows.</span></span>  
  
- <span data-ttu-id="a5fe1-238">Владелец окна закрывается (см. <xref:System.Windows.Window.Owner%2A>).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-238">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
- <span data-ttu-id="a5fe1-239">Главное окно приложения закрывается, и <xref:System.Windows.Application.ShutdownMode%2A> <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-239">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
- <span data-ttu-id="a5fe1-240">вызывается метод <xref:System.Windows.Application.Shutdown%2A>;</span><span class="sxs-lookup"><span data-stu-id="a5fe1-240"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-241">После закрытия окно нельзя открыть повторно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-241">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>   
### <a name="window-lifetime-events"></a><span data-ttu-id="a5fe1-242">События времени существования окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-242">Window Lifetime Events</span></span>  
 <span data-ttu-id="a5fe1-243">На следующем рисунке показана последовательность основных событий во время существования окна:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-243">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![Схема, показывающая события в течение времени существования окна.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="a5fe1-245">На следующем рисунке показана последовательность основных событий во время существования окна, которое отображается без активации (<xref:System.Windows.Window.ShowActivated%2A> устанавливается в `false` до отображения окна):</span><span class="sxs-lookup"><span data-stu-id="a5fe1-245">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![Схема, показывающая события в течение времени существования окна без активации.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>   
## <a name="window-location"></a><span data-ttu-id="a5fe1-247">Расположение окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-247">Window Location</span></span>  
 <span data-ttu-id="a5fe1-248">Когда окно открыто, оно располагается в координатах x и y относительно рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-248">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="a5fe1-249">Это расположение можно определить с помощью проверки свойств <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> соответственно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-249">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="a5fe1-250">Можно задать эти свойства, чтобы изменить расположение окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-250">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="a5fe1-251">Можно также указать начальное расположение <xref:System.Windows.Window> при первом отображении, задав для свойства <xref:System.Windows.Window.WindowStartupLocation%2A> одно из следующих значений перечисления <xref:System.Windows.WindowStartupLocation>:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-251">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
- <span data-ttu-id="a5fe1-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a5fe1-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="a5fe1-253">Если в качестве расположения запуска указано <xref:System.Windows.WindowStartupLocation.Manual>, а свойства <xref:System.Windows.Window.Left%2A> и <xref:System.Windows.Window.Top%2A> не заданы, <xref:System.Windows.Window> запросит в Windows расположение, в котором будет размещаться.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-253">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>   
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="a5fe1-254">Окна верхнего уровня и Z-порядок</span><span class="sxs-lookup"><span data-stu-id="a5fe1-254">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="a5fe1-255">Помимо расположения в координатах x и y, окно имеет координату по оси z, которая определяет его вертикальную позицию относительно других окон.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-255">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="a5fe1-256">Это называется z-порядком окна. Существует два типа: обычный z-порядок и верхний z-порядок.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-256">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="a5fe1-257">Расположение окна в *стандартном z-порядке* определяется тем, активно ли оно в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-257">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="a5fe1-258">По умолчанию окно находится в обычном z-порядке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-258">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="a5fe1-259">Расположение окна в *верхнем z-порядке* также определяется тем, активно ли оно в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-259">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="a5fe1-260">Кроме того, окна в самом верхнем z-порядке всегда расположены над окнами в обычном z-порядке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-260">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="a5fe1-261">Окно находится в верхнем z-порядке, присвоив свойству <xref:System.Windows.Window.Topmost%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-261">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-262">В каждом z-порядке активное в данный момент окно появляется поверх всех других окон в том же z-порядке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-262">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>   
## <a name="window-size"></a><span data-ttu-id="a5fe1-263">Размер окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-263">Window Size</span></span>  
 <span data-ttu-id="a5fe1-264">Помимо расположения рабочего стола, размер окна определяется несколькими свойствами, включая различные свойства Width и Height, а также <xref:System.Windows.Window.SizeToContent%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-264">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="a5fe1-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.MaxWidth%2A> используются для управления диапазоном ширины, который может иметь окно в течение своего времени существования, и настраивается, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-266">Высота окна управляется <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>и <xref:System.Windows.FrameworkElement.MaxHeight%2A>и настраивается, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-266">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-267">Так как различные значения ширины и высоты определяют диапазон, то что ширина и высота изменяемого окна могут находиться в любом месте указанного диапазона для соответствующего измерения.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-267">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="a5fe1-268">Чтобы определить текущую ширину и высоту, проверьте <xref:System.Windows.FrameworkElement.ActualWidth%2A> и <xref:System.Windows.FrameworkElement.ActualHeight%2A>соответственно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-268">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="a5fe1-269">Если вы хотите, чтобы ширина и высота окна имели размер, соответствующий размеру содержимого окна, можно использовать свойство <xref:System.Windows.Window.SizeToContent%2A>, которое имеет следующие значения:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-269">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
- <span data-ttu-id="a5fe1-270"><xref:System.Windows.SizeToContent.Manual></span><span class="sxs-lookup"><span data-stu-id="a5fe1-270"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="a5fe1-271">Нет эффекта (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-271">No effect (default).</span></span>  
  
- <span data-ttu-id="a5fe1-272"><xref:System.Windows.SizeToContent.Width></span><span class="sxs-lookup"><span data-stu-id="a5fe1-272"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="a5fe1-273">По ширине содержимого, что оказывает тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> ширины содержимого.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-273">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
- <span data-ttu-id="a5fe1-274"><xref:System.Windows.SizeToContent.Height></span><span class="sxs-lookup"><span data-stu-id="a5fe1-274"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="a5fe1-275">По высоте содержимого, что оказывает тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> к высоте содержимого.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-275">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
- <span data-ttu-id="a5fe1-276"><xref:System.Windows.SizeToContent.WidthAndHeight></span><span class="sxs-lookup"><span data-stu-id="a5fe1-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="a5fe1-277">По ширине и высоте содержимого, которая имеет тот же результат, что и установка <xref:System.Windows.FrameworkElement.MinHeight%2A> и <xref:System.Windows.FrameworkElement.MaxHeight%2A> к высоте содержимого, и установка <xref:System.Windows.FrameworkElement.MinWidth%2A> и <xref:System.Windows.FrameworkElement.MaxWidth%2A> ширины содержимого.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-277">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="a5fe1-278">В следующем примере показано окно, размеры которого автоматически устанавливаются равными его содержимому по вертикали и по горизонтали при первом отображении.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-278">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-279">В следующем примере показано, как задать свойство <xref:System.Windows.Window.SizeToContent%2A> в коде, чтобы указать, как размер окна изменяется в соответствии с содержимым.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-279">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>   
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="a5fe1-280">Порядок приоритета для свойств размера</span><span class="sxs-lookup"><span data-stu-id="a5fe1-280">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="a5fe1-281">Различные свойства размеров окна объединяются для определения диапазона ширины и высоты окна изменяемого размера.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-281">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="a5fe1-282">Чтобы обеспечить соблюдение допустимого диапазона, <xref:System.Windows.Window> вычисляет значения свойств размера с помощью следующих порядков приоритета.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-282">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="a5fe1-283">**Для свойств высоты:**</span><span class="sxs-lookup"><span data-stu-id="a5fe1-283">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="a5fe1-284">**Для свойств ширины:**</span><span class="sxs-lookup"><span data-stu-id="a5fe1-284">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="a5fe1-285">Порядок приоритета также может определять размер окна, когда оно развернуто, которое управляется с помощью свойства <xref:System.Windows.Window.WindowState%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-285">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>   
## <a name="window-state"></a><span data-ttu-id="a5fe1-286">Состояние окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-286">Window State</span></span>  
 <span data-ttu-id="a5fe1-287">В течение времени существования окна изменяемого размера оно может иметь три состояния: обычное, свернутое и развернутое.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-287">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="a5fe1-288">Окно с *нормальным* состоянием является состоянием окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-288">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="a5fe1-289">Окно с этим состоянием позволяет пользователю перемещать его и изменять размер, используя захват для изменения размера или границу.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-289">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="a5fe1-290">Окно с *свернутым* состоянием сворачивается в кнопку панели задач, если <xref:System.Windows.Window.ShowInTaskbar%2A> имеет значение `true`. в противном случае он сворачивается до наименьшего возможного размера, который может быть и перемещается в левый нижний угол рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-290">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="a5fe1-291">Ни один из типов свернутого окна не может быть изменен с помощью границы или захвата для изменения размера, хотя свернутое окно, которое не отображается на панели задач, можно перетаскивать на рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-291">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="a5fe1-292">Окно с *развернутым* состоянием разворачивается до максимального размера, который может быть только большим, чем его <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, а <xref:System.Windows.Window.SizeToContent%2A> свойства определяются.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-292">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="a5fe1-293">Как и для свернутого окна, размер развернутого окна нельзя изменить с помощью захвата для изменения размера или перетаскивания границы.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-293">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5fe1-294">Значения свойств <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>и <xref:System.Windows.FrameworkElement.Height%2A> окна всегда представляют значения для нормального состояния, даже если окно в данный момент развернуто или уменьшено.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-294">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="a5fe1-295">Состояние окна можно настроить, задав его свойство <xref:System.Windows.Window.WindowState%2A>, которое может иметь одно из следующих <xref:System.Windows.WindowState> перечисляемых значений:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-295">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
- <span data-ttu-id="a5fe1-296"><xref:System.Windows.WindowState.Normal> (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a5fe1-296"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="a5fe1-297">В следующем примере показано создание окна, которое отображается развернутым при его открытии.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-297">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-298">В общем случае следует задать <xref:System.Windows.Window.WindowState%2A>, чтобы настроить начальное состояние окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-298">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="a5fe1-299">После отображения окна изменяемого размера пользователи могут нажимать кнопки свертывания, развертывания и восстановления на панели заголовка окна, чтобы изменить состояние окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-299">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>   
## <a name="window-appearance"></a><span data-ttu-id="a5fe1-300">Внешний вид окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-300">Window Appearance</span></span>  
 <span data-ttu-id="a5fe1-301">Можно изменить внешний вид клиентской области окна, добавляя в нее определенное содержимое, такое как кнопки, метки и текстовые поля.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-301">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="a5fe1-302">Чтобы настроить неклиентскую область, <xref:System.Windows.Window> предоставляет несколько свойств, в том числе <xref:System.Windows.Window.Icon%2A> для установки значка окна и <xref:System.Windows.Window.Title%2A> для задания его заголовка.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-302">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="a5fe1-303">Можно также изменить внешний вид и поведение границы неклиентской области, настраивая режим изменения размера окна, стиль окна и отображение в виде кнопки на панели задач рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-303">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>   
### <a name="resize-mode"></a><span data-ttu-id="a5fe1-304">Режим изменения размера</span><span class="sxs-lookup"><span data-stu-id="a5fe1-304">Resize Mode</span></span>  
 <span data-ttu-id="a5fe1-305">В зависимости от свойства <xref:System.Windows.Window.WindowStyle%2A> можно управлять тем, как пользователи могут изменять размер окна (и, если).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-305">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="a5fe1-306">Выбранный стиль окна влияет на то, может ли пользователь изменять размер окна, перетаскивая его границу мышью, отображаются ли кнопки **сворачивания**, **развернуть**и **изменить размер** в неклиентской области, и если они отображаются, то доступной.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-306">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="a5fe1-307">Можно настроить изменение размера окна, задав его свойство <xref:System.Windows.Window.ResizeMode%2A>, которое может быть одним из следующих <xref:System.Windows.ResizeMode> перечисляемых значений:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-307">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <span data-ttu-id="a5fe1-308"><xref:System.Windows.ResizeMode.CanResize> (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a5fe1-308"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="a5fe1-309">Как и в случае с <xref:System.Windows.Window.WindowStyle%2A>, режим изменения размера окна вряд ли изменится во время его существования. Это означает, что скорее всего, вы задаете его из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-309">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-310">Обратите внимание, что можно определить, является ли окно развернутым, минимальным или восстанавливаемым, проверив свойство <xref:System.Windows.Window.WindowState%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-310">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>   
### <a name="window-style"></a><span data-ttu-id="a5fe1-311">Стиль окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-311">Window Style</span></span>  
 <span data-ttu-id="a5fe1-312">Граница, предоставляемая из неклиентской области окна, подходит для большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-312">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="a5fe1-313">Однако существуют ситуации, когда требуются различные типы границ либо границы вовсе не требуются, в зависимости от типа окна.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-313">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="a5fe1-314">Чтобы управлять тем, какой тип границы получает окно, задайте для свойства <xref:System.Windows.Window.WindowStyle%2A> одно из следующих значений перечисления <xref:System.Windows.WindowStyle>.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-314">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <span data-ttu-id="a5fe1-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="a5fe1-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="a5fe1-316">Эффект этих стилей окна показан на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-316">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![Иллюстрация стилей границ окна.](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="a5fe1-318"><xref:System.Windows.Window.WindowStyle%2A> можно задать с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки или кода. так как маловероятно изменить время существования окна, скорее всего, он будет настроен с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-318">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="a5fe1-319">Непрямоугольный стиль окна</span><span class="sxs-lookup"><span data-stu-id="a5fe1-319">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="a5fe1-320">Существуют также ситуации, когда стили границ, которые <xref:System.Windows.Window.WindowStyle%2A> позволяют, недостаточно.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-320">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="a5fe1-321">Например, может потребоваться создать приложение с непрямоугольной границей, например с помощью проигрывателя Microsoft Windows Media.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-321">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>  
  
 <span data-ttu-id="a5fe1-322">Например, рассмотрим всплывающее окно распознавания речи, показанное на следующем рисунке:</span><span class="sxs-lookup"><span data-stu-id="a5fe1-322">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 ![Всплывающее окно речевого ввода, говорящее на перетаскивание.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="a5fe1-324">Этот тип окна можно создать, задав для свойства <xref:System.Windows.Window.WindowStyle%2A> значение <xref:System.Windows.WindowStyle.None>и используя специальную поддержку, <xref:System.Windows.Window> для прозрачности.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-324">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="a5fe1-325">Это сочетание значений указывает, что окно отрисовывается полностью прозрачным.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-325">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="a5fe1-326">В этом состоянии нельзя использовать элементы оформления неклиентской области окна (кнопки "Закрыть", "Минимизировать", "Развернуть" и "Восстановить" и т. д.).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-326">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="a5fe1-327">Следовательно, необходимо предоставить свои собственные элементы.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-327">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>   
### <a name="task-bar-presence"></a><span data-ttu-id="a5fe1-328">Наличие панели задач</span><span class="sxs-lookup"><span data-stu-id="a5fe1-328">Task Bar Presence</span></span>  

<span data-ttu-id="a5fe1-329">Внешний вид окна по умолчанию включает кнопку панели задач, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-329">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![Снимок экрана, на котором показано окно с кнопкой на панели задач.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="a5fe1-331">У некоторых типов окон нет кнопки панели задач, например окон сообщений и диалоговых окон (см. [Обзор диалоговых окон](dialog-boxes-overview.md)).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-331">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="a5fe1-332">Можно указать, отображается ли кнопка панели задач для окна, задав свойство <xref:System.Windows.Window.ShowInTaskbar%2A> (по умолчанию`true`).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-332">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations"></a><span data-ttu-id="a5fe1-333">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="a5fe1-333">Security Considerations</span></span>  
 <span data-ttu-id="a5fe1-334"><xref:System.Windows.Window> требует создания экземпляра разрешения `UnmanagedCode` безопасности.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-334"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="a5fe1-335">Для приложений, установленных и запускаемых с локального компьютера, это включено в набор разрешений, предоставленных приложению.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-335">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="a5fe1-336">Однако это выходит за рамки набора разрешений, предоставленных приложениям, которые запускаются из зоны Интернета или местной интрасети с помощью ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-336">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using ClickOnce.</span></span> <span data-ttu-id="a5fe1-337">Следовательно, пользователи получат предупреждение системы безопасности ClickOnce и потребуют повысить уровень разрешений приложения до полного доверия.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-337">Consequently, users will receive a ClickOnce security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="a5fe1-338">Кроме того, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] не может отображать окна или диалоговые окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-338">Additionally, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="a5fe1-339">Обсуждение вопросов безопасности отдельных приложений см. в разделе [стратегия безопасности WPF — безопасность платформы](../wpf-security-strategy-platform-security.md).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-339">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>   
## <a name="other-types-of-windows"></a><span data-ttu-id="a5fe1-340">Другие типы окон</span><span class="sxs-lookup"><span data-stu-id="a5fe1-340">Other Types of Windows</span></span>  
 <span data-ttu-id="a5fe1-341"><xref:System.Windows.Navigation.NavigationWindow> — это окно, предназначенное для размещения содержимого с возможностью навигации.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-341"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="a5fe1-342">Дополнительные сведения см. в разделе [Общие сведения о навигации](navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-342">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="a5fe1-343">Диалоговые окна — это окна, которые часто используются для сбора информации от пользователя для выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-343">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="a5fe1-344">Например, когда пользователь хочет открыть файл, диалоговое окно **Открытие файла** обычно отображается приложением для получения имени файла от пользователя.</span><span class="sxs-lookup"><span data-stu-id="a5fe1-344">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="a5fe1-345">Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](dialog-boxes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5fe1-345">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fe1-346">См. также</span><span class="sxs-lookup"><span data-stu-id="a5fe1-346">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="a5fe1-347">Общие сведения о диалоговых окнах</span><span class="sxs-lookup"><span data-stu-id="a5fe1-347">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="a5fe1-348">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="a5fe1-348">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
