---
title: Создание приложения WPF в Visual Studio
ms.date: 04/12/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8f806a1f1f7840f21e82d77d1b639b9318259e7
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271394"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="743a5-102">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="743a5-103">В этой статье показано, как разработать простое приложение Windows Presentation Foundation (WPF), которое включает элементы, которые являются общими для большинства приложений WPF: разметку расширяемого языка разметки приложений (XAML), кода, определения приложения элементы управления, макет, привязку данных и стили.</span><span class="sxs-lookup"><span data-stu-id="743a5-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="743a5-104">В этом пошаговом руководстве включает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="743a5-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="743a5-105">Используйте XAML для разработки приложения пользовательского интерфейса (UI).</span><span class="sxs-lookup"><span data-stu-id="743a5-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="743a5-106">Напишите код для создания поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="743a5-107">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="743a5-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="743a5-108">Добавление элементов управления и создание макета для создания пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="743a5-109">Создания таблиц стилей для согласованное отображение пользовательского интерфейса в приложении.</span><span class="sxs-lookup"><span data-stu-id="743a5-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="743a5-110">Пользовательский Интерфейс привязку к данным для заполнения пользовательского интерфейса на основе данных и сохранить данные и пользовательский Интерфейс.</span><span class="sxs-lookup"><span data-stu-id="743a5-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="743a5-111">В конце пошагового руководства будет создать автономное приложение Windows, которое позволяет пользователям просматривать отчеты о расходах для выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="743a5-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="743a5-112">Приложение состоит из нескольких страниц WPF, размещаемых в окне обозревателя.</span><span class="sxs-lookup"><span data-stu-id="743a5-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="743a5-113">Пример кода, который используется в этом пошаговом руководстве доступен для Visual Basic и C# в [Общие сведения о сборке приложений WPF](https://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="743a5-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="743a5-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="743a5-114">Prerequisites</span></span>

- <span data-ttu-id="743a5-115">Visual Studio 2012 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="743a5-115">Visual Studio 2012 or later</span></span>

<span data-ttu-id="743a5-116">Дополнительные сведения об установке последней версии Visual Studio, см. в разделе [установка Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="743a5-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="743a5-117">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="743a5-117">Create the application project</span></span>

<span data-ttu-id="743a5-118">Первым шагом является создание инфраструктуры приложений, который включает в себя определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="743a5-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="743a5-119">Создание нового проекта приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="743a5-119">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="743a5-120">Откройте Visual Studio и выберите **файл** > **New** > **проекта**.</span><span class="sxs-lookup"><span data-stu-id="743a5-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="743a5-121">**Новый проект** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="743a5-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="743a5-122">В разделе **установленные** категории, разверните **Visual C#** или **Visual Basic** узел, а затем выберите **классический рабочий стол Windows**.</span><span class="sxs-lookup"><span data-stu-id="743a5-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Classic Desktop**.</span></span>

   3. <span data-ttu-id="743a5-123">Выберите **приложение WPF (.NET Framework)** шаблона.</span><span class="sxs-lookup"><span data-stu-id="743a5-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="743a5-124">Введите имя **`ExpenseIt`** , а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="743a5-124">Enter the name **`ExpenseIt`** and then select **OK**.</span></span>

      ![Диалоговое окно нового проекта с помощью выбранного приложения WPF](media/new-project-dialog.png)

      <span data-ttu-id="743a5-126">Visual Studio создаст проект и открывает конструктор для окна приложения по умолчанию с именем **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="743a5-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="743a5-127">В этом пошаговом руководстве использует <xref:System.Windows.Controls.DataGrid> элемент управления, доступных в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="743a5-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="743a5-128">Быть в том, что проект предназначен для .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="743a5-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="743a5-129">Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="743a5-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="743a5-130">Откройте *Application.xaml* (Visual Basic) или *App.xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="743a5-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="743a5-131">Этот файл XAML определяет WPF-приложение и все его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="743a5-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="743a5-132">Этот файл также используется для указания пользовательского интерфейса, автоматически отображаемого при запуске приложения; в этом случае *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="743a5-133">В Visual Basic в XAML должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="743a5-134">В C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="743a5-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="743a5-135">Откройте *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="743a5-136">Этот файл XAML представляет главное окно приложения и отображает созданное содержимое страниц.</span><span class="sxs-lookup"><span data-stu-id="743a5-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="743a5-137"><xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер и значок и обрабатывает события, такие как открытие и закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="743a5-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="743a5-138">Изменение <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>, как показано в следующем XAML:</span><span class="sxs-lookup"><span data-stu-id="743a5-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="743a5-139">Это приложение переходит к различному содержимому вводимых пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="743a5-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="743a5-140">Вот почему основной <xref:System.Windows.Window> должно быть изменено <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="743a5-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="743a5-141"><xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="743a5-141"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="743a5-142"><xref:System.Windows.Navigation.NavigationWindow> В файле XAML создает экземпляр класса <xref:System.Windows.Navigation.NavigationWindow> класса.</span><span class="sxs-lookup"><span data-stu-id="743a5-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="743a5-143">Дополнительные сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-143">For more information, see [Navigation overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="743a5-144">Измените следующие свойства на <xref:System.Windows.Navigation.NavigationWindow> элемент:</span><span class="sxs-lookup"><span data-stu-id="743a5-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="743a5-145">Задайте <xref:System.Windows.Window.Title%2A> свойства "`ExpenseIt`«.</span><span class="sxs-lookup"><span data-stu-id="743a5-145">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="743a5-146">Задайте <xref:System.Windows.FrameworkElement.Width%2A> значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="743a5-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="743a5-147">Задайте <xref:System.Windows.FrameworkElement.Height%2A> свойство значение 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="743a5-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="743a5-148">Удалить <xref:System.Windows.Controls.Grid> элементов между <xref:System.Windows.Navigation.NavigationWindow> теги.</span><span class="sxs-lookup"><span data-stu-id="743a5-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="743a5-149">В Visual Basic в XAML должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="743a5-150">В C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="743a5-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="743a5-151">Откройте *MainWindow.xaml.vb* или *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="743a5-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="743a5-152">Этот файл является файлом кода, который содержит код для обработки событий, объявленных в *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="743a5-153">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="743a5-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="743a5-154">Если вы используете C#, измените `MainWindow` класса для наследования от <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="743a5-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="743a5-155">(В Visual Basic это происходит автоматически при изменении окна в XAML.)</span><span class="sxs-lookup"><span data-stu-id="743a5-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="743a5-156">Код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="743a5-157">Можно переключать язык кода примера кода между C# и Visual Basic в **языка** раскрывающееся меню в верхней правой части в этой статье.</span><span class="sxs-lookup"><span data-stu-id="743a5-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="743a5-158">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="743a5-158">Add files to the application</span></span>

<span data-ttu-id="743a5-159">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="743a5-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="743a5-160">Добавьте новую страницу WPF в проект и назовите его *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="743a5-160">Add a new WPF page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="743a5-161">В **обозревателе решений**, щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите **добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="743a5-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="743a5-162">В **Добавление нового элемента** диалоговое окно, **страницу (WPF)** шаблон уже выбран.</span><span class="sxs-lookup"><span data-stu-id="743a5-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="743a5-163">Введите имя **`ExpenseItHome`**, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="743a5-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="743a5-164">Эта страница является первой страницей, которое отображается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="743a5-165">Появится список пользователей для выбора, чтобы просмотреть отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="743a5-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="743a5-166">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-166">Open *`ExpenseItHome.xaml`*.</span></span>

3. <span data-ttu-id="743a5-167">Задайте <xref:System.Windows.Controls.Page.Title%2A> для "`ExpenseIt - Home`«.</span><span class="sxs-lookup"><span data-stu-id="743a5-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

    <span data-ttu-id="743a5-168">В Visual Basic в XAML должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="743a5-169">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="743a5-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="743a5-170">Откройте *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="743a5-171">Задайте <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойство <xref:System.Windows.Navigation.NavigationWindow> для "`ExpenseItHome.xaml`«.</span><span class="sxs-lookup"><span data-stu-id="743a5-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="743a5-172">Этот параметр задает *`ExpenseItHome.xaml`* в качестве первой страницы, открываемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> <span data-ttu-id="743a5-173">В Visual Basic в XAML должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="743a5-174">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="743a5-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="743a5-175">Можно также задать **источника** свойство в **Разное** категории **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="743a5-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Свойства Source в окно "Свойства"](media/properties-source.png)

6. <span data-ttu-id="743a5-177">Добавьте другую новую страницу WPF в проект и назовите его *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="743a5-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="743a5-178">В **обозревателе решений**, щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите **добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="743a5-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="743a5-179">В **Добавление нового элемента** диалоговое окно, **страницу (WPF)** шаблон уже выбран.</span><span class="sxs-lookup"><span data-stu-id="743a5-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="743a5-180">Введите имя **ExpenseReportPage**, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="743a5-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="743a5-181">Эта страница будет отображаться отчет по расходам для человека, выбранного на **`ExpenseItHome`** страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

7. <span data-ttu-id="743a5-182">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="743a5-183">Задайте <xref:System.Windows.Controls.Page.Title%2A> для "`ExpenseIt - View Expense`«.</span><span class="sxs-lookup"><span data-stu-id="743a5-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

    <span data-ttu-id="743a5-184">В Visual Basic в XAML должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="743a5-185">А в C# он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="743a5-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="743a5-186">Откройте *ExpenseItHome.xaml.vb* и *ExpenseReportPage.xaml.vb*, или *ExpenseItHome.xaml.cs* и *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="743a5-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="743a5-187">При создании нового файла страницы Visual Studio автоматически создает *кода* файл.</span><span class="sxs-lookup"><span data-stu-id="743a5-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="743a5-188">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="743a5-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="743a5-189">Код должен выглядеть следующим образом для **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="743a5-189">Your code should look like this for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="743a5-190">И следующим образом для **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="743a5-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="743a5-191">Добавить образ с именем *watermark.png* в проект.</span><span class="sxs-lookup"><span data-stu-id="743a5-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="743a5-192">Можно создать собственный образ, скопируйте файл из образца кода или его [здесь](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span><span class="sxs-lookup"><span data-stu-id="743a5-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span></span>

   1. <span data-ttu-id="743a5-193">Щелкните правой кнопкой мыши узел проекта и выберите **добавить** > **существующий элемент**, или нажмите клавишу **Shift**+**Alt** + **Объект**.</span><span class="sxs-lookup"><span data-stu-id="743a5-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

   2. <span data-ttu-id="743a5-194">В **добавить существующий элемент** диалоговое окно, перейдите к файлу изображения, который вы хотите использовать, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="743a5-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="743a5-195">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="743a5-195">Build and run the application</span></span>

1. <span data-ttu-id="743a5-196">Чтобы построить и запустить приложение, нажмите клавишу **F5** или выберите **начать отладку** из **Отладка** меню.</span><span class="sxs-lookup"><span data-stu-id="743a5-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="743a5-197">На следующем рисунке показано приложение с помощью <xref:System.Windows.Navigation.NavigationWindow> кнопки:</span><span class="sxs-lookup"><span data-stu-id="743a5-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. <span data-ttu-id="743a5-199">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="743a5-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="743a5-200">Создание макета</span><span class="sxs-lookup"><span data-stu-id="743a5-200">Create the layout</span></span>

<span data-ttu-id="743a5-201">Макет позволяет упорядочивать размещение элементов пользовательского интерфейса и также управлять их размером и положением при изменении размера пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="743a5-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="743a5-202">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="743a5-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="743a5-203">Каждый из этих элементов управления макетом поддерживает специальный тип макета дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="743a5-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="743a5-204">`ExpenseIt` размер страницы может быть изменен, и каждая страница имеет элементы, которые упорядочены по горизонтали и вертикали рядом с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="743a5-204">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="743a5-205">Следовательно <xref:System.Windows.Controls.Grid> является идеальным элементом макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="743a5-206">Дополнительные сведения о <xref:System.Windows.Controls.Panel> элементов, см. в разделе [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="743a5-207">Дополнительные сведения о макете см. в разделе [макета](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-207">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span>

<span data-ttu-id="743a5-208">В разделе создается таблица с одним столбцом с тремя строками и полями шириной 10 пикселей путем добавления определений столбцов и строк для <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="743a5-209">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-209">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="743a5-210">Задайте <xref:System.Windows.FrameworkElement.Margin%2A> свойство <xref:System.Windows.Controls.Grid> элемент «10,0,10,10», который соответствует слева, сверху, справа и нижнего полей:</span><span class="sxs-lookup"><span data-stu-id="743a5-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="743a5-211">Можно также задать **Margin** значения в **свойства** окна в разделе **макета** категории:</span><span class="sxs-lookup"><span data-stu-id="743a5-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения полей в окно "Свойства"](media/properties-margin.png)

3. <span data-ttu-id="743a5-213">Добавьте следующий XAML между <xref:System.Windows.Controls.Grid> теги, чтобы создать определения строк и столбцов:</span><span class="sxs-lookup"><span data-stu-id="743a5-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="743a5-214"><xref:System.Windows.Controls.RowDefinition.Height%2A> Двух строк имеет значение <xref:System.Windows.GridLength.Auto%2A>, что означает, что строки имеют размер базового содержимого в строках.</span><span class="sxs-lookup"><span data-stu-id="743a5-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized base on the content in the rows.</span></span> <span data-ttu-id="743a5-215">Значение по умолчанию <xref:System.Windows.Controls.RowDefinition.Height%2A> является <xref:System.Windows.GridUnitType.Star> изменения размера, это означает, что высота строки — это взвешенная пропорция доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="743a5-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="743a5-216">Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> из «\*», каждый из них имеет высоту, половина доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="743a5-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="743a5-217">Ваш <xref:System.Windows.Controls.Grid> теперь должен выглядеть как следующий XAML:</span><span class="sxs-lookup"><span data-stu-id="743a5-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="743a5-218">Добавление элементов управления</span><span class="sxs-lookup"><span data-stu-id="743a5-218">Add controls</span></span>

<span data-ttu-id="743a5-219">В этом разделе вы обновите пользовательский Интерфейс для отображения списка пользователей, для которых пользователь может выводиться отчет по расходам для домашней страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="743a5-220">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="743a5-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="743a5-221">Более подробную информацию см. в разделе [Элементы управления](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-221">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span>

<span data-ttu-id="743a5-222">Чтобы создать этот пользовательский Интерфейс, нужно добавить следующие элементы для *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="743a5-222">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="743a5-223"><xref:System.Windows.Controls.ListBox> (для получения списка пользователей).</span><span class="sxs-lookup"><span data-stu-id="743a5-223"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="743a5-224"><xref:System.Windows.Controls.Label> (для заголовков списка).</span><span class="sxs-lookup"><span data-stu-id="743a5-224"><xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="743a5-225"><xref:System.Windows.Controls.Button> (чтобы щелкните, чтобы просмотреть отчет по расходам для человека, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="743a5-225"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="743a5-226">Каждый элемент управления помещается в строке <xref:System.Windows.Controls.Grid> , задав <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вложенного свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="743a5-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="743a5-227">Дополнительные сведения о вложенных свойствах см. в разделе [зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-227">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="743a5-228">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-228">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="743a5-229">Добавьте следующий XAML где-то между <xref:System.Windows.Controls.Grid> теги:</span><span class="sxs-lookup"><span data-stu-id="743a5-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="743a5-230">Также можно создать элементы управления, перетащив их из **элементов** окна в окне конструктора, а затем задав их свойства в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="743a5-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="743a5-231">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-231">Build and run the application.</span></span>

<span data-ttu-id="743a5-232">На следующем рисунке показано элементы управления, что вы только что создали:</span><span class="sxs-lookup"><span data-stu-id="743a5-232">The following illustration shows the controls you just created:</span></span>

![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="743a5-234">Добавить изображение и заголовок</span><span class="sxs-lookup"><span data-stu-id="743a5-234">Add an image and a title</span></span>

<span data-ttu-id="743a5-235">В этом разделе вы обновите интерфейсе пользователя домашней страницы изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="743a5-236">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-236">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="743a5-237">Добавьте еще один столбец для <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей:</span><span class="sxs-lookup"><span data-stu-id="743a5-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="743a5-238">Добавить другую строку для <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, всего четыре строки:</span><span class="sxs-lookup"><span data-stu-id="743a5-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="743a5-239">Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойство в значение 1, в каждом из трех элементов управления (границы, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="743a5-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="743a5-240">Переместите каждый элемент управления вниз на одну строку, увеличивая его <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> значение на 1.</span><span class="sxs-lookup"><span data-stu-id="743a5-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="743a5-241">XAML для трех элементов управления теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="743a5-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="743a5-242">Задайте <xref:System.Windows.Controls.Panel.Background%2A> из <xref:System.Windows.Controls.Grid> быть *watermark.png* файл изображения, добавив следующий XAML где-то между `<Grid>` и `</Grid>` теги:</span><span class="sxs-lookup"><span data-stu-id="743a5-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="743a5-243">Прежде чем <xref:System.Windows.Controls.Border> элемента, добавьте <xref:System.Windows.Controls.Label> с содержимым «View Expense Report».</span><span class="sxs-lookup"><span data-stu-id="743a5-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="743a5-244">Это заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="743a5-245">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-245">Build and run the application.</span></span>

<span data-ttu-id="743a5-246">На следующем рисунке показано только что добавленную результаты:</span><span class="sxs-lookup"><span data-stu-id="743a5-246">The following illustration shows the results of what you just added:</span></span>

![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="743a5-248">Добавьте код для обработки событий</span><span class="sxs-lookup"><span data-stu-id="743a5-248">Add code to handle events</span></span>

1. <span data-ttu-id="743a5-249">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-249">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="743a5-250">Добавить <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в обработчике событий <xref:System.Windows.Controls.Button> элемент.</span><span class="sxs-lookup"><span data-stu-id="743a5-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="743a5-251">Дополнительные сведения см. в разделе [как: создание простого обработчика событий](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="743a5-251">For more information, see [How to: Create a simple event handler](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="743a5-252">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-252">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="743a5-253">Добавьте следующий код, чтобы `ExpenseItHome` класс, чтобы добавить кнопку обработчик события щелчка.</span><span class="sxs-lookup"><span data-stu-id="743a5-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="743a5-254">Обработчик событий открывает **ExpenseReportPage** страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="743a5-255">Создание пользовательского интерфейса для страницы ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="743a5-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="743a5-256">*ExpenseReportPage.xaml* отображается отчет по расходам для человека, выбранного на **`ExpenseItHome`** страницы.</span><span class="sxs-lookup"><span data-stu-id="743a5-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="743a5-257">В этом разделе вы создадите пользовательский Интерфейс для **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="743a5-257">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="743a5-258">Вы также добавите фона и цвета для различных элементов пользовательского интерфейса заливки.</span><span class="sxs-lookup"><span data-stu-id="743a5-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="743a5-259">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="743a5-260">Добавьте следующий XAML между <xref:System.Windows.Controls.Grid> теги:</span><span class="sxs-lookup"><span data-stu-id="743a5-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="743a5-261">Этот пользовательский Интерфейс аналогичен *`ExpenseItHome.xaml`*, за исключением, что данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="743a5-261">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="743a5-262">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="743a5-263">Если отобразится сообщение об ошибке, <xref:System.Windows.Controls.DataGrid> не найден или не существует, убедитесь, что ваш проект предназначен для .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="743a5-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="743a5-264">Дополнительные сведения см. в [практическом руководстве по настройке конкретной версии .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="743a5-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="743a5-265">Выберите **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="743a5-265">Select the **View** button.</span></span>

    <span data-ttu-id="743a5-266">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="743a5-266">The expense report page appears.</span></span> <span data-ttu-id="743a5-267">Также Обратите внимание на то, что кнопка возврата включено.</span><span class="sxs-lookup"><span data-stu-id="743a5-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="743a5-268">На следующем рисунке показан элементы пользовательского интерфейса, добавленные *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Снимок экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="743a5-270">Определение стиля элементов управления</span><span class="sxs-lookup"><span data-stu-id="743a5-270">Style controls</span></span>

<span data-ttu-id="743a5-271">Внешний вид различных элементов часто является одинаковым для всех элементов одного типа в пользовательском Интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="743a5-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="743a5-272">Пользовательский Интерфейс использует [стили](../../../../docs/framework/wpf/controls/styling-and-templating.md) чтобы варианты внешнего вида многократного использования для нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="743a5-272">UI uses [styles](../../../../docs/framework/wpf/controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="743a5-273">Повторное использование стилей помогает упростить создание XAML и управление ими.</span><span class="sxs-lookup"><span data-stu-id="743a5-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="743a5-274">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="743a5-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="743a5-275">Откройте *Application.xaml* или *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="743a5-276">Добавьте следующий XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> теги:</span><span class="sxs-lookup"><span data-stu-id="743a5-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="743a5-277">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="743a5-277">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="743a5-278">`headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;</span><span class="sxs-lookup"><span data-stu-id="743a5-278">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="743a5-279">`labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;</span><span class="sxs-lookup"><span data-stu-id="743a5-279">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="743a5-280">`columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;</span><span class="sxs-lookup"><span data-stu-id="743a5-280">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="743a5-281">`listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;</span><span class="sxs-lookup"><span data-stu-id="743a5-281">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="743a5-282">`listHeaderTextStyle`Для форматирования заголовка списка <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="743a5-282">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="743a5-283">`buttonStyle`Для форматирования <xref:System.Windows.Controls.Button> на `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="743a5-283">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="743a5-284">Обратите внимание на то, что стили представляют собой ресурсы и являются дочерними <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемент свойства.</span><span class="sxs-lookup"><span data-stu-id="743a5-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="743a5-285">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="743a5-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="743a5-286">Пример использования ресурсов в приложении .NET Framework, см. в разделе [использование ресурсов приложения](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="743a5-287">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-287">Open *`ExpenseItHome.xaml`*.</span></span>

4. <span data-ttu-id="743a5-288">Замените весь код между <xref:System.Windows.Controls.Grid> элементов при помощи следующих XAML:</span><span class="sxs-lookup"><span data-stu-id="743a5-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="743a5-289">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="743a5-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="743a5-290">Например `headerTextStyle` применяется к «View Expense Report» <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="743a5-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="743a5-291">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="743a5-292">Замените весь код между <xref:System.Windows.Controls.Grid> элементов при помощи следующих XAML:</span><span class="sxs-lookup"><span data-stu-id="743a5-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="743a5-293">В элементы <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border> будут добавлены стили.</span><span class="sxs-lookup"><span data-stu-id="743a5-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="743a5-294">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="743a5-294">Bind data to a control</span></span>

<span data-ttu-id="743a5-295">В этом разделе вы создадите XML-данных, привязанный к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="743a5-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="743a5-296">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-296">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="743a5-297">После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующий XAML для создания <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="743a5-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="743a5-298">Данные создаются как <xref:System.Windows.Controls.Grid> ресурсов.</span><span class="sxs-lookup"><span data-stu-id="743a5-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="743a5-299">Обычно такие данные загружаются в виде файла, но для простоты в этом примере они добавляются в коде.</span><span class="sxs-lookup"><span data-stu-id="743a5-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="743a5-300">В рамках `<Grid.Resources>` элемента, добавьте следующий <xref:System.Windows.DataTemplate>, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="743a5-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="743a5-301">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-301">For more information about data templates, see [Data templating overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="743a5-302">Замените существующий <xref:System.Windows.Controls.ListBox> с следующем XAML:</span><span class="sxs-lookup"><span data-stu-id="743a5-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="743a5-303">Этот XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="743a5-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="743a5-304">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="743a5-304">Connect data to controls</span></span>

<span data-ttu-id="743a5-305">Далее добавим код для извлечения имени, выбранного на **`ExpenseItHome`** странице и передать его конструктору **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="743a5-305">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="743a5-306">**ExpenseReportPage** задает контекст данных для переданного элемента, который является то, что элементы управления, определенные в *ExpenseReportPage.xaml* привязки.</span><span class="sxs-lookup"><span data-stu-id="743a5-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="743a5-307">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="743a5-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="743a5-308">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="743a5-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="743a5-309">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="743a5-309">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="743a5-310">Изменение <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий для вызова новый конструктор, передавая отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="743a5-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="743a5-311">Стиль данных с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="743a5-311">Style data with data templates</span></span>

<span data-ttu-id="743a5-312">В этом разделе вы обновите пользовательский Интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="743a5-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="743a5-313">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="743a5-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="743a5-314">Привяжите содержимое «Name» и «Отдел» <xref:System.Windows.Controls.Label> свойство источника элементов, соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="743a5-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="743a5-315">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="743a5-315">For more information about data binding, see [Data binding overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="743a5-316">После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующие шаблоны данных, которые определяют способ отображения данных отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="743a5-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="743a5-317">Замените <xref:System.Windows.Controls.DataGridTextColumn> элементов при помощи <xref:System.Windows.Controls.DataGridTemplateColumn> под <xref:System.Windows.Controls.DataGrid> элемента и примените шаблоны к ним.</span><span class="sxs-lookup"><span data-stu-id="743a5-317">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="743a5-318">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="743a5-318">Build and run the application.</span></span>

6. <span data-ttu-id="743a5-319">Выберите "person", а затем выберите **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="743a5-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="743a5-320">На следующем рисунке показан обе страницы `ExpenseIt` приложения с помощью элементов управления, макет, стили, привязку данных и примененными шаблонами данных:</span><span class="sxs-lookup"><span data-stu-id="743a5-320">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Снимки экрана примера ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="743a5-322">В этом примере демонстрируется конкретная функциональная возможность WPF и не выполните все рекомендации по безопасности, локализации и специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="743a5-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="743a5-323">Исчерпывающая информация о WPF и рекомендации по разработке приложений .NET Framework см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="743a5-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="743a5-324">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="743a5-324">Accessibility</span></span>](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="743a5-325">Безопасность</span><span class="sxs-lookup"><span data-stu-id="743a5-325">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
>
> - [<span data-ttu-id="743a5-326">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-326">WPF globalization and localization</span></span>](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="743a5-327">Производительности WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-327">WPF performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="743a5-328">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="743a5-328">Next steps</span></span>

<span data-ttu-id="743a5-329">В этом пошаговом руководстве вы узнали ряд методов для создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="743a5-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="743a5-330">Теперь вы должны основные стандартные блоки приложения .NET Framework с данными.</span><span class="sxs-lookup"><span data-stu-id="743a5-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="743a5-331">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="743a5-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="743a5-332">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-332">WPF architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [<span data-ttu-id="743a5-333">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="743a5-333">XAML overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="743a5-334">Общие сведения о свойствах зависимостей</span><span class="sxs-lookup"><span data-stu-id="743a5-334">Dependency properties overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="743a5-335">Макет</span><span class="sxs-lookup"><span data-stu-id="743a5-335">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)

<span data-ttu-id="743a5-336">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="743a5-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="743a5-337">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="743a5-337">Application development</span></span>](../../../../docs/framework/wpf/app-development/index.md)
- [<span data-ttu-id="743a5-338">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="743a5-338">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="743a5-339">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="743a5-339">Data binding overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="743a5-340">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="743a5-340">Graphics and multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="743a5-341">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-341">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="743a5-342">См. также</span><span class="sxs-lookup"><span data-stu-id="743a5-342">See also</span></span>

- [<span data-ttu-id="743a5-343">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="743a5-343">Panels overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="743a5-344">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="743a5-344">Data templating overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="743a5-345">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="743a5-345">Build a WPF application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="743a5-346">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="743a5-346">Styles and templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
