---
title: Пошаговое руководство. Создание первого классического приложения WPF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: 71
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3725e96b514b0204f10f6b5c45ed2bbec1d892de
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="9a3ac-102">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="9a3ac-102">Walkthrough: My first WPF desktop application</span></span>
<span data-ttu-id="9a3ac-103">В этом пошаговом руководстве представляет собой введение в разработку [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] приложения, которое содержит элементы, которые являются общими для большинства [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложений: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметки, кода, определения приложения, элементы управления, макет, Привязка данных и стили.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-103">This walkthrough provides an introduction to the development of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application that includes the elements that are common to most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> 
  
<span data-ttu-id="9a3ac-104">Пошаговом руководстве описывается разработка простого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-104">This walkthrough guides you through the development of a simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application using the following steps.</span></span> 
  
-   <span data-ttu-id="9a3ac-105">Определение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] на внешний вид приложения [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-105">Defining [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to design the appearance of the application's [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="9a3ac-106">Написание кода для создания модели поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-106">Writing code to build the application's behavior.</span></span> 
  
-   <span data-ttu-id="9a3ac-107">Создание управляющих определений приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-107">Creating an application definition to manage the application.</span></span> 
  
-   <span data-ttu-id="9a3ac-108">Добавление элементов управления и создание макета, входящих в состав приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-108">Adding controls and creating the layout to compose the application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="9a3ac-109">Создание стилей, обеспечивающих унифицированный внешний вид компонентов приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-109">Creating styles to create a consistent appearance throughout an application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="9a3ac-110">Привязка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с данными для заполнения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из данных и синхронизации данных и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] синхронизированы.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-110">Binding the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to data to both populate the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] from data and keep the data and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronized.</span></span> 
  
<span data-ttu-id="9a3ac-111">В конце данного пошагового руководства вы сможете создать автономный [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] приложение, которое позволяет пользователям просматривать отчеты о расходах для выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-111">By the end of the walkthrough, you will have built a standalone [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="9a3ac-112">Приложение будет состоять из нескольких [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] страницы, размещенные в окне обозревателя.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-112">The application will be composed of several [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pages that are hosted in a browser-style window.</span></span> 
  
<span data-ttu-id="9a3ac-113">Пример кода, который используется в этом пошаговом руководстве, доступен как для [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] и [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] в [введение в построение приложений WPF](http://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-113">The sample code that is used to build this walkthrough is available for both [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] and [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] at  [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="9a3ac-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9a3ac-114">Prerequisites</span></span>  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="9a3ac-115"> или более поздняя версия</span><span class="sxs-lookup"><span data-stu-id="9a3ac-115"> or later</span></span>

<span data-ttu-id="9a3ac-116">Дополнительные сведения об установке последней версии Visual Studio см. в разделе [установите Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>
  
## <a name="creating-the-application-project"></a><span data-ttu-id="9a3ac-117">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="9a3ac-117">Creating the application project</span></span>  
<span data-ttu-id="9a3ac-118">В этом разделе вы создадите инфраструктуру приложения, включающую в себя определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-118">In this section, you create the application infrastructure, which includes an application definition, two pages, and an image.</span></span> 
  
1. <span data-ttu-id="9a3ac-119">Создайте проект приложения WPF на Visual Basic или Visual C# с именем `ExpenseIt`.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-119">Create a new WPF Application project in Visual Basic or Visual C# named `ExpenseIt`.</span></span> <span data-ttu-id="9a3ac-120">Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-120">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="9a3ac-121">В этом пошаговом руководстве используется <xref:System.Windows.Controls.DataGrid> управления, доступных в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-121">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4.</span></span> <span data-ttu-id="9a3ac-122">Быть в том, что проект предназначен для .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-122">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="9a3ac-123">Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-123">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
2. <span data-ttu-id="9a3ac-124">Откройте файл Application.xaml (Visual Basic) или файл App.xaml (C#).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-124">Open Application.xaml (Visual Basic) or App.xaml (C#).</span></span> 
  
     <span data-ttu-id="9a3ac-125">Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл определяет [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения и все его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-125">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file defines a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application and any application resources.</span></span> <span data-ttu-id="9a3ac-126">Этот файл также используется для указания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , будет автоматически отображаться при запуске приложения; в этом случае файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-126">You also use this file to specify the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that automatically shows when the application starts; in this case, MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="9a3ac-127">Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-127">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     <span data-ttu-id="9a3ac-128">В C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-128">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. <span data-ttu-id="9a3ac-129">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-129">Open MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="9a3ac-130">Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл главного окна приложения, который отображает содержимое, созданное в страницах.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-130">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="9a3ac-131"><xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер и значок и обрабатывает события, такие как открытие и закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-131">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span> 
  
4. <span data-ttu-id="9a3ac-132">Изменение <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-132">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="9a3ac-133">Приложение будет переходить к различному содержимому согласно действиям пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-133">This application will navigate to different content depending on the user interaction.</span></span> <span data-ttu-id="9a3ac-134">Поэтому главное <xref:System.Windows.Window> должно быть изменено <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-134">Therefore, the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="9a3ac-135"><xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-135"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="9a3ac-136"><xref:System.Windows.Navigation.NavigationWindow> Элемент файла XAML создает экземпляр <xref:System.Windows.Navigation.NavigationWindow> класса.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-136">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="9a3ac-137">Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-137">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span> 
  
5. <span data-ttu-id="9a3ac-138">Измените следующие свойства на <xref:System.Windows.Navigation.NavigationWindow> элемента:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-138">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>  
  
    -   <span data-ttu-id="9a3ac-139">Задать <xref:System.Windows.Window.Title%2A> свойства «ExpenseIt».</span><span class="sxs-lookup"><span data-stu-id="9a3ac-139">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span> 
  
    -   <span data-ttu-id="9a3ac-140">Задать <xref:System.Windows.FrameworkElement.Width%2A> свойство до 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-140">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span> 
  
    -   <span data-ttu-id="9a3ac-141">Задать <xref:System.Windows.FrameworkElement.Height%2A> свойство до 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-141">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span> 
  
    -   <span data-ttu-id="9a3ac-142">Удалить <xref:System.Windows.Controls.Grid> элементов между <xref:System.Windows.Navigation.NavigationWindow> тегов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-142">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span> 
  
     <span data-ttu-id="9a3ac-143">Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-143">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     <span data-ttu-id="9a3ac-144">В C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-144">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. <span data-ttu-id="9a3ac-145">Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-145">Open MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span> 
  
     <span data-ttu-id="9a3ac-146">В этом файле кода программной части содержится код обработки событий, объявленных в файле MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-146">This file is a code-behind file that contains code to handle the events declared in MainWindow.xaml.</span></span> <span data-ttu-id="9a3ac-147">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-147">This file contains a partial class for the window defined in XAML.</span></span> 
  
7. <span data-ttu-id="9a3ac-148">Если вы используете C#, измените `MainWindow` являются производными от класса <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-148">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="9a3ac-149">В Visual Basic это выполняется автоматически при изменении окна в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-149">In Visual Basic, this happens automatically when you change the window in XAML.</span></span> 
  
     <span data-ttu-id="9a3ac-150">Код должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-150">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a><span data-ttu-id="9a3ac-151">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="9a3ac-151">Adding files to the application</span></span>  
<span data-ttu-id="9a3ac-152">В этом разделе в приложение добавляются две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-152">In this section, you add two pages and an image to the application.</span></span> 
  
1. <span data-ttu-id="9a3ac-153">Добавление новой страницы (WPF) в проект с именем `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-153">Add a new Page (WPF) to the project named `ExpenseItHome.xaml`.</span></span> <span data-ttu-id="9a3ac-154">Дополнительные сведения см. в разделе [как: Добавление новых элементов в проект WPF](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-154">For more information, see [How to: Add New Items to a WPF Project](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span></span> 
  
     <span data-ttu-id="9a3ac-155">Эта страница отображается первой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-155">This page is the first page that is displayed when the application is launched.</span></span> <span data-ttu-id="9a3ac-156">На ней выводится список, в котором можно выбрать человека и просмотреть отчет о его затратах.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-156">It will show a list of people from which a user can select a person to show an expense report for.</span></span> 
  
2. <span data-ttu-id="9a3ac-157">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-157">Open ExpenseItHome.xaml.</span></span> 
  
3. <span data-ttu-id="9a3ac-158">Задать <xref:System.Windows.Controls.Page.Title%2A> для «ExpenseIt — Домашняя».</span><span class="sxs-lookup"><span data-stu-id="9a3ac-158">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span> 
  
     <span data-ttu-id="9a3ac-159">Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-159">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     <span data-ttu-id="9a3ac-160">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-160">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. <span data-ttu-id="9a3ac-161">Откройте файл MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-161">Open MainWindow.xaml.</span></span> 
  
5. <span data-ttu-id="9a3ac-162">Задать <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойство <xref:System.Windows.Navigation.NavigationWindow> для «ExpenseItHome.xaml».</span><span class="sxs-lookup"><span data-stu-id="9a3ac-162">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span> 
  
     <span data-ttu-id="9a3ac-163">В результате ExpenseItHome.xaml будет первой страницей, открываемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-163">This sets ExpenseItHome.xaml to be the first page opened when the application starts.</span></span> <span data-ttu-id="9a3ac-164">Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-164">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     <span data-ttu-id="9a3ac-165">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-165">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. <span data-ttu-id="9a3ac-166">Добавление новой страницы (WPF) в проект с именем `ExpenseReportPage.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-166">Add a new Page (WPF) to the project named `ExpenseReportPage.xaml`.</span></span> 
  
     <span data-ttu-id="9a3ac-167">На этой странице будет выводиться отчет по расходам для человека, выбранного на странице ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-167">This page will show the expense report for the person that is selected on ExpenseItHome.xaml.</span></span> 
  
7. <span data-ttu-id="9a3ac-168">Откройте файл ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-168">Open ExpenseReportPage.xaml.</span></span> 
  
8. <span data-ttu-id="9a3ac-169">Задать <xref:System.Windows.Controls.Page.Title%2A> для «ExpenseIt — Просмотр расходов».</span><span class="sxs-lookup"><span data-stu-id="9a3ac-169">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span> 
  
     <span data-ttu-id="9a3ac-170">Ваш [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в Visual Basic должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-170">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     <span data-ttu-id="9a3ac-171">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-171">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. <span data-ttu-id="9a3ac-172">Откройте файлы ExpenseItHome.xaml.vb и ExpenseReportPage.xaml.vb (или ExpenseItHome.xaml.cs и ExpenseReportPage.xaml.cs).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-172">Open ExpenseItHome.xaml.vb and ExpenseReportPage.xaml.vb, or ExpenseItHome.xaml.cs and ExpenseReportPage.xaml.cs.</span></span> 
  
     <span data-ttu-id="9a3ac-173">При создании нового файла страницы Visual Studio автоматически создает файл кода программной части.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-173">When you create a new Page file, Visual Studio automatically creates a code behind file.</span></span> <span data-ttu-id="9a3ac-174">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-174">These code-behind files handle the logic for responding to user input.</span></span> 
  
     <span data-ttu-id="9a3ac-175">Код должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-175">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. <span data-ttu-id="9a3ac-176">Добавьте изображение с именем *watermark.png* в проект.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-176">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="9a3ac-177">Можно создать собственное изображение или скопировать файл из образца кода.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-177">You can either create your own image, or copy the file from the sample code.</span></span> <span data-ttu-id="9a3ac-178">Дополнительные сведения см. в разделе [как: Добавление существующих элементов в проект](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-178">For more information, see [How to: Add Existing Items to a Project](/previous-versions/visualstudio/visual-studio-2008/9f4t9t92(v=vs.90)).</span></span> 

## <a name="building-and-running-the-application"></a><span data-ttu-id="9a3ac-179">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="9a3ac-179">Building and running the application</span></span>  
<span data-ttu-id="9a3ac-180">В этом разделе выполняются сборка и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-180">In this section, you build and run the application.</span></span> 
  
1. <span data-ttu-id="9a3ac-181">Построение и запуск приложения нажатием клавиши F5 или выбрав **начать отладку** из **отладки** меню.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-181">Build and run the application by pressing F5 or selecting **Start Debugging** from the **Debug** menu.</span></span> 
  
     <span data-ttu-id="9a3ac-182">На следующем рисунке показано приложение с <xref:System.Windows.Navigation.NavigationWindow> кнопки.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-182">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons.</span></span> 
  
     <span data-ttu-id="9a3ac-183">![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span><span class="sxs-lookup"><span data-stu-id="9a3ac-183">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span></span>  
  
2. <span data-ttu-id="9a3ac-184">Закройте приложение, чтобы вернуться к [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-184">Close the application to return to [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> 
  
## <a name="creating-the-layout"></a><span data-ttu-id="9a3ac-185">Создание макета</span><span class="sxs-lookup"><span data-stu-id="9a3ac-185">Creating the layout</span></span>  
<span data-ttu-id="9a3ac-186">Макет позволяет упорядочивать для размещения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов, а также управление размером и положением при [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] изменяется.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-186">Layout provides an ordered way to place [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements, and also manages the size and position of those elements when a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is resized.</span></span> <span data-ttu-id="9a3ac-187">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-187">You typically create a layout with one of the following layout controls:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
<span data-ttu-id="9a3ac-188">Каждый из этих элементов управления макетом поддерживает специальный тип макета дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-188">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="9a3ac-189">Размер страниц приложения ExpenseIt может быть изменен. На каждой странице представлены элементы, которые упорядочены по горизонтали и вертикали рядом с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-189">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="9a3ac-190">Следовательно <xref:System.Windows.Controls.Grid> является идеальным элементом макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-190">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="9a3ac-191">Дополнительные сведения о <xref:System.Windows.Controls.Panel> см [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-191">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="9a3ac-192">Дополнительные сведения о макете см. в разделе [макета](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-192">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span> 
  
<span data-ttu-id="9a3ac-193">В разделе, создании одного столбца таблицы с тремя строками и 10 пикселей путем добавления определений столбцов и строк для <xref:System.Windows.Controls.Grid> в ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-193">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span></span> 
  
1. <span data-ttu-id="9a3ac-194">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-194">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-195">Задать <xref:System.Windows.FrameworkElement.Margin%2A> свойства <xref:System.Windows.Controls.Grid> элемента «10,0,10,10», который соответствует слева, сверху, справа и нижнего полей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-195">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10" which corresponds to left, top, right and bottom margins.</span></span> 
  
3. <span data-ttu-id="9a3ac-196">Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] между <xref:System.Windows.Controls.Grid> теги, чтобы создать определения строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-196">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions.</span></span> 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <span data-ttu-id="9a3ac-197"><xref:System.Windows.Controls.RowDefinition.Height%2A> Две строки имеет значение <xref:System.Windows.GridLength.Auto%2A> что означает, что строки будет изменяться размер основан на содержимое в строках.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-197">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A> which means that the rows will be sized base on the content in the rows.</span></span> <span data-ttu-id="9a3ac-198">Значение по умолчанию <xref:System.Windows.Controls.RowDefinition.Height%2A> — <xref:System.Windows.GridUnitType.Star> изменения размера, это означает, что строки будут пропорционально изменяющегося доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-198">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row will be a weighted proportion of the available space.</span></span> <span data-ttu-id="9a3ac-199">Например, если каждая из двух строк имеет высоту "\*", высота каждой из них будет равна половине имеющегося свободного места.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-199">For example if two rows each have a height of "\*", they will each have a height that is half of the available space.</span></span>  
  
     <span data-ttu-id="9a3ac-200">Ваш <xref:System.Windows.Controls.Grid> должен выглядеть так, следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-200">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a><span data-ttu-id="9a3ac-201">Добавление элементов управления</span><span class="sxs-lookup"><span data-stu-id="9a3ac-201">Adding controls</span></span>  
<span data-ttu-id="9a3ac-202">В этом разделе, на домашней странице [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] обновляется для отображения списка людей, пользователи могут выбрать, чтобы отобразить отчет по расходам для выбранного пользователя из.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-202">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated to show a list of people that users can select from to show the expense report for a selected person.</span></span> <span data-ttu-id="9a3ac-203">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-203">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="9a3ac-204">Более подробную информацию см. в разделе [Элементы управления](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-204">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span> 
  
<span data-ttu-id="9a3ac-205">Для создания этого [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], ExpenseItHome.xaml добавляются следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-205">To create this [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the following elements are added to ExpenseItHome.xaml:</span></span>  
  
-   <span data-ttu-id="9a3ac-206"><xref:System.Windows.Controls.ListBox> (для список людей).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-206"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span> 
  
-   <span data-ttu-id="9a3ac-207"><xref:System.Windows.Controls.Label> (для заголовков списка).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-207"><xref:System.Windows.Controls.Label> (for the list header).</span></span> 
  
-   <span data-ttu-id="9a3ac-208"><xref:System.Windows.Controls.Button> (чтобы щелкните, чтобы просмотреть отчет по расходам для человека, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-208"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span> 
  
<span data-ttu-id="9a3ac-209">Каждый элемент управления помещается в строку <xref:System.Windows.Controls.Grid> , установив <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вложенное свойство.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-209">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="9a3ac-210">Дополнительные сведения о вложенных свойствах см. в разделе [зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-210">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span> 
  
1. <span data-ttu-id="9a3ac-211">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-211">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-212">Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] между <xref:System.Windows.Controls.Grid> тегов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-212">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. <span data-ttu-id="9a3ac-213">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-213">Build and run the application.</span></span> 
  
<span data-ttu-id="9a3ac-214">На следующем рисунке показаны элементы управления, созданные с помощью кода XAML в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-214">The following illustration shows the controls that are created by the XAML in this section.</span></span> 
  
<span data-ttu-id="9a3ac-215">![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span><span class="sxs-lookup"><span data-stu-id="9a3ac-215">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span></span>  
  
## <a name="adding-an-image-and-a-title"></a><span data-ttu-id="9a3ac-216">Добавление изображения и заголовка</span><span class="sxs-lookup"><span data-stu-id="9a3ac-216">Adding an image and a title</span></span>  
<span data-ttu-id="9a3ac-217">В этом разделе, на домашней странице [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] обновляется изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-217">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated with an image and a page title.</span></span> 
  
1. <span data-ttu-id="9a3ac-218">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-218">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-219">Добавьте еще один столбец для <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-219">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels.</span></span> 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. <span data-ttu-id="9a3ac-220">Добавьте строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-220">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span></span> 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. <span data-ttu-id="9a3ac-221">Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> значение 1.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-221">Move the controls to the second column by setting <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> to 1.</span></span> <span data-ttu-id="9a3ac-222">Переместите каждый элемент управления в одну строку вниз, увеличив <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> на 1.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-222">Move each control down a row, by increasing the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> by 1.</span></span> 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. <span data-ttu-id="9a3ac-223">Задать <xref:System.Windows.Controls.Panel.Background%2A> из <xref:System.Windows.Controls.Grid> watermark.png файлом изображения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-223">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the watermark.png image file.</span></span> 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. <span data-ttu-id="9a3ac-224">Прежде чем <xref:System.Windows.Controls.Border>, добавьте <xref:System.Windows.Controls.Label> с содержимым «Просмотреть отчет о расходах» в заголовке страницы.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-224">Before the <xref:System.Windows.Controls.Border>, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report" to be the title of the page.</span></span> 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. <span data-ttu-id="9a3ac-225">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-225">Build and run the application.</span></span> 
  
<span data-ttu-id="9a3ac-226">На следующем рисунке показаны результаты действий из этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-226">The following illustration shows the results of this section.</span></span> 
  
<span data-ttu-id="9a3ac-227">![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span><span class="sxs-lookup"><span data-stu-id="9a3ac-227">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span></span>  
  
## <a name="adding-code-to-handle-events"></a><span data-ttu-id="9a3ac-228">Добавление кода для обработки событий</span><span class="sxs-lookup"><span data-stu-id="9a3ac-228">Adding code to handle events</span></span>  
  
1. <span data-ttu-id="9a3ac-229">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-229">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-230">Добавить <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий <xref:System.Windows.Controls.Button> элемента.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-230">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="9a3ac-231">Дополнительные сведения см. в разделе [как: создание простого обработчика событий](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-231">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span> 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. <span data-ttu-id="9a3ac-232">Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-232">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="9a3ac-233">Добавьте следующий код в <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, который вызывает окно, чтобы перейти к файлу ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-233">Add the following code to the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler, which causes the window to navigate to the ExpenseReportPage.xaml file.</span></span> 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a><span data-ttu-id="9a3ac-234">Создание пользовательского интерфейса для страницы ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="9a3ac-234">Creating the UI for ExpenseReportPage</span></span>  
<span data-ttu-id="9a3ac-235">На странице ExpenseReportPage.xaml отображается отчет о расходах для человека, выбранного на странице ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-235">ExpenseReportPage.xaml displays the expense report for the person that was selected on the ExpenseItHome.xaml.</span></span> <span data-ttu-id="9a3ac-236">Добавляет элементы управления в этом разделе и создает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-236">This section adds controls and creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for ExpenseReportPage.xaml.</span></span> <span data-ttu-id="9a3ac-237">В этом разделе также добавляется фона и цвета заливки на разные [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-237">This section also adds background and fill colors to the various [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> 
  
1. <span data-ttu-id="9a3ac-238">Откройте файл ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-238">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-239">Добавьте следующий XAML-код между тегами <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-239">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
     <span data-ttu-id="9a3ac-240">Этот пользовательский Интерфейс аналогичен Интерфейсу, созданному в ExpenseItHome.xaml, за исключением того, данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-240">This UI is similar to the UI created on ExpenseItHome.xaml except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span> 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. <span data-ttu-id="9a3ac-241">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-241">Build and run the application.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="9a3ac-242">Если вы получаете сообщение об <xref:System.Windows.Controls.DataGrid> не найден или не существует, убедитесь, что проект ориентирован на .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-242">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="9a3ac-243">Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-243">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
4. <span data-ttu-id="9a3ac-244">Нажмите кнопку **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-244">Click the **View** button.</span></span> 
  
     <span data-ttu-id="9a3ac-245">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-245">The expense report page appears.</span></span> 
  
<span data-ttu-id="9a3ac-246">На следующем рисунке показана [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы, добавленные ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-246">The following illustration shows the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements added to ExpenseReportPage.xaml.</span></span> <span data-ttu-id="9a3ac-247">Обратите внимание на то, что кнопка возврата активна.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-247">Notice that the back navigation button is enabled.</span></span> 
  
<span data-ttu-id="9a3ac-248">![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span><span class="sxs-lookup"><span data-stu-id="9a3ac-248">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span></span>  
  
## <a name="styling-controls"></a><span data-ttu-id="9a3ac-249">Настройка стиля элементов управления</span><span class="sxs-lookup"><span data-stu-id="9a3ac-249">Styling controls</span></span>  
<span data-ttu-id="9a3ac-250">Внешний вид различных элементов часто могут совпадать для всех элементов одного типа в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-250">The appearance of various elements can often be the same for all elements of the same type in a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<span data-ttu-id="9a3ac-251"> использует стили, чтобы варианты внешнего вида можно было многократно использовать для нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-251"> uses styles to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="9a3ac-252">Повторное использование стилей помогает упростить [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Создание и управление ими.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-252">The reusability of styles helps to simplify [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creation and management.</span></span> <span data-ttu-id="9a3ac-253">Дополнительные сведения о стилях см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-253">For more information about styles, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span> <span data-ttu-id="9a3ac-254">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-254">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span> 
  
1. <span data-ttu-id="9a3ac-255">Откройте файл Application.xaml или App.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-255">Open Application.xaml or App.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-256">Добавьте следующий код XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> теги:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-256">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     <span data-ttu-id="9a3ac-257">Это [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-257">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] adds the following styles:</span></span>  
  
    -  <span data-ttu-id="9a3ac-258">`headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;</span><span class="sxs-lookup"><span data-stu-id="9a3ac-258">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="9a3ac-259">`labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;</span><span class="sxs-lookup"><span data-stu-id="9a3ac-259">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span> 
  
    -  <span data-ttu-id="9a3ac-260">`columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;</span><span class="sxs-lookup"><span data-stu-id="9a3ac-260">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span> 
  
    -  <span data-ttu-id="9a3ac-261">`listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;</span><span class="sxs-lookup"><span data-stu-id="9a3ac-261">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span> 
  
    -  <span data-ttu-id="9a3ac-262">`listHeaderTextStyle`Для форматирования заголовка списка <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-262">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="9a3ac-263">`buttonStyle`Для форматирования <xref:System.Windows.Controls.Button> на ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-263">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span> 
  
     <span data-ttu-id="9a3ac-264">Обратите внимание, что стили, ресурсы и дочерних элементов <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемент свойства.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-264">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="9a3ac-265">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-265">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="9a3ac-266">Пример использования ресурсов в [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] приложения, в разделе [использования ресурсов приложения](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-266">For an example of using resources in a [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span> 
  
3. <span data-ttu-id="9a3ac-267">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-267">Open ExpenseItHome.xaml.</span></span> 
  
4. <span data-ttu-id="9a3ac-268">Замените весь код между <xref:System.Windows.Controls.Grid> элементы следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-268">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     <span data-ttu-id="9a3ac-269">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-269">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="9a3ac-270">Например `headerTextStyle` применяется к «View Expense Report» <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-270">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span> 
  
5. <span data-ttu-id="9a3ac-271">Откройте файл ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-271">Open ExpenseReportPage.xaml.</span></span> 
  
6. <span data-ttu-id="9a3ac-272">Замените весь код между <xref:System.Windows.Controls.Grid> элементы следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-272">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     <span data-ttu-id="9a3ac-273">В элементы <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border> будут добавлены стили.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-273">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span> 
  
7. <span data-ttu-id="9a3ac-274">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-274">Build and run the application.</span></span> 
  
     <span data-ttu-id="9a3ac-275">После добавления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в этом разделе приложение выглядит так же, как и перед обновлением с использованием стилей.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-275">After adding the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in this section, the application looks the same as it did before being updated with styles.</span></span> 
  
## <a name="binding-data-to-a-control"></a><span data-ttu-id="9a3ac-276">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="9a3ac-276">Binding data to a control</span></span>  
<span data-ttu-id="9a3ac-277">В этом разделе создайте [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] данные, привязанные к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-277">In this section, you create the [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] data that is bound to various controls.</span></span> 
  
1. <span data-ttu-id="9a3ac-278">Откройте файл ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-278">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-279">После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующий код XAML для создания <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-279">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person.</span></span> 
  
     <span data-ttu-id="9a3ac-280">Данные создаются в виде <xref:System.Windows.Controls.Grid> ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-280">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="9a3ac-281">Обычно такие данные загружаются в виде файла, но для простоты в этом примере они добавляются в коде.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-281">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. <span data-ttu-id="9a3ac-282">В <xref:System.Windows.Controls.Grid> ресурсов, добавьте следующий <xref:System.Windows.DataTemplate>, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-282">In the <xref:System.Windows.Controls.Grid> resource, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="9a3ac-283">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-283">For more information about data templates, see [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. <span data-ttu-id="9a3ac-284">Заменить существующий <xref:System.Windows.Controls.ListBox> следующим кодом XAML.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-284">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     <span data-ttu-id="9a3ac-285">Этот код XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-285">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span> 
  
## <a name="connecting-data-to-controls"></a><span data-ttu-id="9a3ac-286">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="9a3ac-286">Connecting data to controls</span></span>  
<span data-ttu-id="9a3ac-287">В этом разделе, можно написать код, который получает текущий элемент, выбранный в списке людей на странице ExpenseItHome.xaml и передается ссылка на конструктор `ExpenseReportPage` во время создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-287">In this section, you write the code that retrieves the current item that is selected in the list of people on the ExpenseItHome.xaml page, and passes its reference to the constructor of `ExpenseReportPage` during instantiation.</span></span> <span data-ttu-id="9a3ac-288">`ExpenseReportPage` задает контекст данных для переданного элемента, к которому будут привязаны элементы управления, определенные в файле ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-288">`ExpenseReportPage` sets its data context with the passed item, which is what the controls defined in ExpenseReportPage.xaml will bind to.</span></span> 
  
1. <span data-ttu-id="9a3ac-289">Откройте файл ExpenseReportPage.xaml.vb или ExpenseReportPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-289">Open ExpenseReportPage.xaml.vb or ExpenseReportPage.xaml.cs.</span></span> 
  
2. <span data-ttu-id="9a3ac-290">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-290">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. <span data-ttu-id="9a3ac-291">Откройте файл ExpenseItHome.xaml.vb или ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-291">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="9a3ac-292">Изменение <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий для вызова нового конструктора, передавая данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-292">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a><span data-ttu-id="9a3ac-293">Стили данных с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="9a3ac-293">Styling data with data templates</span></span>  
<span data-ttu-id="9a3ac-294">В этом разделе обновления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для каждого элемента данных, привязанного к списков с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-294">In this section, you update the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for each item in the data bound lists by using data templates.</span></span> 
  
1. <span data-ttu-id="9a3ac-295">Откройте файл ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-295">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="9a3ac-296">Привяжите содержимое «Name» и «Отдел» <xref:System.Windows.Controls.Label> свойство source элементов, соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-296">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="9a3ac-297">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9a3ac-297">For more information about data binding, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. <span data-ttu-id="9a3ac-298">После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующие шаблоны данных, определяющие способ отображения данных отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-298">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data.</span></span>  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. <span data-ttu-id="9a3ac-299">Применять шаблоны для <xref:System.Windows.Controls.DataGrid> столбцы, которые отображают расход данные отчета.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-299">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span> 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. <span data-ttu-id="9a3ac-300">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-300">Build and run the application.</span></span> 
  
6. <span data-ttu-id="9a3ac-301">Выберите человека и нажмите кнопку **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-301">Select a person and click the **View** button.</span></span> 
  
 <span data-ttu-id="9a3ac-302">На рисунке ниже показаны обе страницы приложения ExpenseIt с элементами управления, макетом, стилями, привязкой данных и примененными шаблонами данных.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-302">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied.</span></span> 
  
 <span data-ttu-id="9a3ac-303">![Снимки экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span><span class="sxs-lookup"><span data-stu-id="9a3ac-303">![ExpenseIt sample screen shots](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="9a3ac-304">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="9a3ac-304">Best practices</span></span>  
<span data-ttu-id="9a3ac-305">В этом примере демонстрируется конкретная функциональная возможность WPF, поэтому рекомендации по разработке приложений не соблюдаются.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-305">This sample demonstrates a specific feature of WPF and, consequently, does not follow application development best practices.</span></span> <span data-ttu-id="9a3ac-306">Полное описание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] лучшие методики разработки приложений, в следующих разделах соответствующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-306">For comprehensive coverage of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application development best practices, see the following topics as appropriate:</span></span>  
  
-   <span data-ttu-id="9a3ac-307">Специальные возможности: [Рекомендации по специальным возможностям](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="9a3ac-307">Accessibility - [Accessibility Best Practices](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span></span>  
  
-   <span data-ttu-id="9a3ac-308">Безопасность — [безопасности](../../../../docs/framework/wpf/security-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="9a3ac-308">Security - [Security](../../../../docs/framework/wpf/security-wpf.md)</span></span>  
  
-   <span data-ttu-id="9a3ac-309">Локализация: [Общие сведения о глобализации и локализации WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9a3ac-309">Localization - [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span></span>  
  
-   <span data-ttu-id="9a3ac-310">Производительность [Улучшение производительности приложений WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span><span class="sxs-lookup"><span data-stu-id="9a3ac-310">Performance - [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span></span>  
  
## <a name="whats-next"></a><span data-ttu-id="9a3ac-311">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="9a3ac-311">What's next</span></span>  
<span data-ttu-id="9a3ac-312">Теперь у вас есть несколько способов в вашем распоряжении для создания [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] с помощью [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a3ac-312">You now have a number of techniques at your disposal for creating a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] using [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span> <span data-ttu-id="9a3ac-313">Теперь вы получите более основательно изучить основные стандартные блоки, привязкой данных [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-313">You should now have a broad understanding of the basic building blocks of a data-bound [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application.</span></span> <span data-ttu-id="9a3ac-314">Информация в этом разделе ни в коем случае не является исчерпывающей, но мы надеемся, что у вас также есть теперь некоторое представление о возможностях, которые вы можете изучить самостоятельно, помимо рассмотренных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9a3ac-314">This topic is by no means exhaustive, but hopefully you also now have a sense of some of the possibilities you might discover on your own beyond the techniques in this topic.</span></span> 
  
 <span data-ttu-id="9a3ac-315">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-315">For more information about the WPF architecture and programming models, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9a3ac-316">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="9a3ac-316">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [<span data-ttu-id="9a3ac-317">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9a3ac-317">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [<span data-ttu-id="9a3ac-318">Общие сведения о свойствах зависимости</span><span class="sxs-lookup"><span data-stu-id="9a3ac-318">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [<span data-ttu-id="9a3ac-319">Макет</span><span class="sxs-lookup"><span data-stu-id="9a3ac-319">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
  
 <span data-ttu-id="9a3ac-320">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9a3ac-320">For more information about creating applications, see the following topics:</span></span>  
  
-   [<span data-ttu-id="9a3ac-321">Разработка приложения</span><span class="sxs-lookup"><span data-stu-id="9a3ac-321">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [<span data-ttu-id="9a3ac-322">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="9a3ac-322">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
  
-   [<span data-ttu-id="9a3ac-323">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="9a3ac-323">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [<span data-ttu-id="9a3ac-324">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9a3ac-324">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [<span data-ttu-id="9a3ac-325">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="9a3ac-325">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a3ac-326">См. также</span><span class="sxs-lookup"><span data-stu-id="9a3ac-326">See also</span></span>  
 [<span data-ttu-id="9a3ac-327">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="9a3ac-327">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="9a3ac-328">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="9a3ac-328">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="9a3ac-329">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="9a3ac-329">Building a WPF Application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="9a3ac-330">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="9a3ac-330">Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
