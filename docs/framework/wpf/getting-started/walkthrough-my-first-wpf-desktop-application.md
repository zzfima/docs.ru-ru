---
title: Создание приложения WPF в Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: 9d0abd18b2242ab21e8a915caac1ff9e3216acd0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617276"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="9f273-102">Пошаговое руководство. Создание классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="9f273-103">В этой статье показано, как для разработки классического приложения Windows Presentation Foundation (WPF), который содержит элементы, которые являются общими для большинства приложений WPF: Расширяемый язык разметки приложений (XAML) разметки, кода, определения приложений, элементы управления, макет, привязки данных и стили.</span><span class="sxs-lookup"><span data-stu-id="9f273-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="9f273-104">При разработке приложения, можно использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f273-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="9f273-105">В этом пошаговом руководстве включает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="9f273-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="9f273-106">Используйте XAML для разработки приложения пользовательского интерфейса (UI).</span><span class="sxs-lookup"><span data-stu-id="9f273-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="9f273-107">Напишите код для создания поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="9f273-108">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="9f273-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="9f273-109">Добавление элементов управления и создание макета для создания пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="9f273-110">Создания таблиц стилей для согласованное отображение пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="9f273-111">Привязка пользовательского интерфейса к данным, для заполнения пользовательского интерфейса на основе данных и хранить данные и пользовательский Интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9f273-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="9f273-112">В конце пошагового руководства будет создать автономное приложение Windows, которое позволяет пользователям просматривать отчеты о расходах для выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9f273-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="9f273-113">Приложение состоит из нескольких страниц WPF, размещаемых в окне обозревателя.</span><span class="sxs-lookup"><span data-stu-id="9f273-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="9f273-114">Пример кода, который используется в этом пошаговом руководстве доступен для обоих Visual Basic и C# в [код образца приложения WPF пошагового руководства](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="9f273-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="9f273-115">Можно переключать язык кода примера кода между C# и Visual Basic с помощью **\< />** раскрывающееся меню в верхней правой части в этой статье.</span><span class="sxs-lookup"><span data-stu-id="9f273-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9f273-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9f273-116">Prerequisites</span></span>

- <span data-ttu-id="9f273-117">Visual Studio 2017 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="9f273-117">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="9f273-118">Дополнительные сведения об установке последней версии Visual Studio, см. в разделе [установка Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9f273-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span> <span data-ttu-id="9f273-119">В этой статье используется Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="9f273-119">This article uses Visual Studio 2019.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="9f273-120">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="9f273-120">Create the application project</span></span>

<span data-ttu-id="9f273-121">Первым шагом является создание инфраструктуры приложений, который включает в себя определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9f273-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="9f273-122">Создание нового проекта приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="9f273-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="9f273-123">Откройте Visual Studio и выберите **файл** > **New** > **проекта**.</span><span class="sxs-lookup"><span data-stu-id="9f273-123">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="9f273-124">**Создайте новый проект** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9f273-124">The **Create a new project** dialog opens.</span></span>

      ![Создать диалоговое окно нового проекта](./media/gettingstartedfigure0a.png)

   2. <span data-ttu-id="9f273-126">В **языка** раскрывающемся списке выберите либо **C#** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="9f273-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="9f273-127">Выберите **приложение WPF (.NET Framework)** шаблона, а затем выберите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9f273-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
    
   4. <span data-ttu-id="9f273-128">Выберите **создайте новый проект**.</span><span class="sxs-lookup"><span data-stu-id="9f273-128">Select **Create a new project**.</span></span>

      <span data-ttu-id="9f273-129">**Настроить новый проект** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9f273-129">The **Configure a new project** dialog opens.</span></span>

      ![Настройте диалоговое окно нового проекта](./media/gettingstartedfigure0c.png)

   5. <span data-ttu-id="9f273-131">Введите имя проекта **`ExpenseIt`** , а затем выберите **создать**.</span><span class="sxs-lookup"><span data-stu-id="9f273-131">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      <span data-ttu-id="9f273-132">Visual Studio создаст проект и открывает конструктор для окна приложения по умолчанию с именем **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="9f273-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="9f273-133">Откройте *Application.xaml* (Visual Basic) или *App.xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="9f273-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="9f273-134">Этот файл XAML определяет WPF-приложение и все его ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9f273-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="9f273-135">Этот файл также используется для указания пользовательского интерфейса, в данном случае *MainWindow.xaml*, автоматически отображаемого при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="9f273-136">В XAML должен выглядеть как следующий код в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9f273-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="9f273-137">И, как показано ниже в C#:</span><span class="sxs-lookup"><span data-stu-id="9f273-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="9f273-138">Откройте *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="9f273-139">Этот файл XAML представляет главное окно приложения и отображает созданное содержимое страниц.</span><span class="sxs-lookup"><span data-stu-id="9f273-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="9f273-140"><xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер и значок и обрабатывает события, такие как открытие и закрытие окна.</span><span class="sxs-lookup"><span data-stu-id="9f273-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="9f273-141">Изменение <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>, как показано в следующем XAML:</span><span class="sxs-lookup"><span data-stu-id="9f273-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="9f273-142">Это приложение переходит к различному содержимому вводимых пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="9f273-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="9f273-143">Вот почему основной <xref:System.Windows.Window> должно быть изменено <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9f273-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="9f273-144"><xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="9f273-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="9f273-145"><xref:System.Windows.Navigation.NavigationWindow> В файле XAML создает экземпляр класса <xref:System.Windows.Navigation.NavigationWindow> класса.</span><span class="sxs-lookup"><span data-stu-id="9f273-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="9f273-146">Дополнительные сведения см. в разделе [Общие сведения о переходах](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="9f273-147">Удалить <xref:System.Windows.Controls.Grid> элементов из между <xref:System.Windows.Navigation.NavigationWindow> теги.</span><span class="sxs-lookup"><span data-stu-id="9f273-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="9f273-148">Измените следующие свойства в коде XAML для <xref:System.Windows.Navigation.NavigationWindow> элемент:</span><span class="sxs-lookup"><span data-stu-id="9f273-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="9f273-149">Задайте <xref:System.Windows.Window.Title%2A> свойства "`ExpenseIt`«.</span><span class="sxs-lookup"><span data-stu-id="9f273-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="9f273-150">Задайте <xref:System.Windows.FrameworkElement.Height%2A> свойство значение 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9f273-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="9f273-151">Задайте <xref:System.Windows.FrameworkElement.Width%2A> значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9f273-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="9f273-152">В XAML должен выглядеть как показано ниже для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9f273-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="9f273-153">И, как показано ниже для C#:</span><span class="sxs-lookup"><span data-stu-id="9f273-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="9f273-154">Откройте *MainWindow.xaml.vb* или *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f273-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="9f273-155">Этот файл является файлом кода, который содержит код для обработки событий, объявленных в *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="9f273-156">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="9f273-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="9f273-157">Если вы используете C#, изменить `MainWindow` класса для наследования от <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9f273-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="9f273-158">(В Visual Basic это происходит автоматически при изменении окна в XAML.) Ваш C# код теперь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9f273-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="9f273-159">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="9f273-159">Add files to the application</span></span>

<span data-ttu-id="9f273-160">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9f273-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="9f273-161">Добавьте новую страницу в проект и назовите его *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="9f273-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="9f273-162">В **обозревателе решений**, щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите **добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="9f273-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="9f273-163">В **Добавление нового элемента** диалоговое окно, **страницу (WPF)** шаблон уже выбран.</span><span class="sxs-lookup"><span data-stu-id="9f273-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="9f273-164">Введите имя **`ExpenseItHome`**, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="9f273-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="9f273-165">Эта страница является первой страницей, которое отображается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="9f273-166">Появится список пользователей для выбора, чтобы просмотреть отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="9f273-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="9f273-167">Откройте *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="9f273-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="9f273-168">Задайте <xref:System.Windows.Controls.Page.Title%2A> для "`ExpenseIt - Home`«.</span><span class="sxs-lookup"><span data-stu-id="9f273-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="9f273-169">Задайте `DesignHeight` и `DesignWidth` значения элементов до 300 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9f273-169">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="9f273-170">XAML теперь выглядит следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9f273-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="9f273-171">И, как показано ниже для C#:</span><span class="sxs-lookup"><span data-stu-id="9f273-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="9f273-172">Откройте *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="9f273-173">Добавить <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойства <xref:System.Windows.Navigation.NavigationWindow> элемент и задайте для него значение "`ExpenseItHome.xaml`«.</span><span class="sxs-lookup"><span data-stu-id="9f273-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="9f273-174">Этот параметр задает *`ExpenseItHome.xaml`* в качестве первой страницы, открываемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="9f273-175">Пример XAML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9f273-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="9f273-176">И в C#:</span><span class="sxs-lookup"><span data-stu-id="9f273-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="9f273-177">Можно также задать **источника** свойство в **Разное** категории **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="9f273-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Свойства Source в окно "Свойства"](./media/properties-source.png)

1. <span data-ttu-id="9f273-179">Добавьте другую новую страницу WPF в проект и назовите его *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="9f273-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="9f273-180">В **обозревателе решений**, щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите **добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="9f273-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="9f273-181">В **Добавление нового элемента** диалоговом окне выберите **страницу (WPF)** шаблона.</span><span class="sxs-lookup"><span data-stu-id="9f273-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="9f273-182">Введите имя **ExpenseReportPage**, а затем выберите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="9f273-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="9f273-183">Эта страница будет отображаться отчет по расходам для человека, выбранного на **`ExpenseItHome`** страницы.</span><span class="sxs-lookup"><span data-stu-id="9f273-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="9f273-184">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="9f273-185">Задайте <xref:System.Windows.Controls.Page.Title%2A> для "`ExpenseIt - View Expense`«.</span><span class="sxs-lookup"><span data-stu-id="9f273-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="9f273-186">Задайте `DesignHeight` и `DesignWidth` значения элементов до 300 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9f273-186">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="9f273-187">*ExpenseReportPage.xaml* теперь выглядит как следующий код в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9f273-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="9f273-188">И, как показано ниже в C#:</span><span class="sxs-lookup"><span data-stu-id="9f273-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="9f273-189">Откройте *ExpenseItHome.xaml.vb* и *ExpenseReportPage.xaml.vb*, или *ExpenseItHome.xaml.cs* и *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f273-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="9f273-190">При создании нового файла страницы Visual Studio автоматически создает его *кода* файл.</span><span class="sxs-lookup"><span data-stu-id="9f273-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="9f273-191">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="9f273-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="9f273-192">Код должен выглядеть, как показано ниже для **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="9f273-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="9f273-193">И, как показано ниже для **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="9f273-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="9f273-194">Добавить образ с именем *watermark.png* в проект.</span><span class="sxs-lookup"><span data-stu-id="9f273-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="9f273-195">Можно создать собственный образ, скопируйте файл из образца кода или его [здесь](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="9f273-195">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="9f273-196">Щелкните правой кнопкой мыши узел проекта и выберите **добавить** > **существующий элемент**, или нажмите клавишу **Shift**+**Alt** + **Объект**.</span><span class="sxs-lookup"><span data-stu-id="9f273-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="9f273-197">В **добавить существующий элемент** диалоговое окно, установить фильтр файлов **все файлы** или **файлы изображений**, перейдите к файлу образа, который вы хотите использовать, а затем выберите **добавить** .</span><span class="sxs-lookup"><span data-stu-id="9f273-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="9f273-198">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="9f273-198">Build and run the application</span></span>

1. <span data-ttu-id="9f273-199">Чтобы построить и запустить приложение, нажмите клавишу **F5** или выберите **начать отладку** из **Отладка** меню.</span><span class="sxs-lookup"><span data-stu-id="9f273-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="9f273-200">На следующем рисунке показано приложение с помощью <xref:System.Windows.Navigation.NavigationWindow> кнопки:</span><span class="sxs-lookup"><span data-stu-id="9f273-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Снимок экрана примера ExpenseIt](./media/gettingstartedfigure1.png)

2. <span data-ttu-id="9f273-202">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f273-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="9f273-203">Создание макета</span><span class="sxs-lookup"><span data-stu-id="9f273-203">Create the layout</span></span>

<span data-ttu-id="9f273-204">Макет позволяет упорядочивать размещение элементов пользовательского интерфейса и также управлять их размером и положением при изменении размера пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9f273-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="9f273-205">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="9f273-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="9f273-206"><xref:System.Windows.Controls.Canvas> -Определяет область, внутри которой можно явным образом разместить дочерние элементы, используя координаты относительно области полотна.</span><span class="sxs-lookup"><span data-stu-id="9f273-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="9f273-207"><xref:System.Windows.Controls.DockPanel> -Определяет область, где можно упорядочивать дочерние элементы горизонтально либо вертикально относительно друг друга.</span><span class="sxs-lookup"><span data-stu-id="9f273-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="9f273-208"><xref:System.Windows.Controls.Grid> -Определяет гибкую область сетки, состоящей из столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="9f273-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="9f273-209"><xref:System.Windows.Controls.StackPanel> -Дочерние элементы размещаются в одну линию, ориентированную горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="9f273-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="9f273-210"><xref:System.Windows.Controls.VirtualizingStackPanel> -Упорядочивает и виртуализирует содержимое на одной строке, ориентированную горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="9f273-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="9f273-211"><xref:System.Windows.Controls.WrapPanel> -Размещает дочерние элементы последовательно слева направо, перенося содержимое на следующую строку на границе содержащего поля.</span><span class="sxs-lookup"><span data-stu-id="9f273-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="9f273-212">Дальнейшее упорядочивание происходит последовательно сверху вниз или справа налево, в зависимости от значения свойства Orientation.</span><span class="sxs-lookup"><span data-stu-id="9f273-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="9f273-213">Каждая из этих элементов управления макетом поддерживает определенный тип макета дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="9f273-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="9f273-214">`ExpenseIt` размер страницы может быть изменен, и каждая страница имеет элементы, которые упорядочены по горизонтали и вертикали рядом с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="9f273-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="9f273-215">В этом примере <xref:System.Windows.Controls.Grid> используется как элемент макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="9f273-216">Дополнительные сведения о <xref:System.Windows.Controls.Panel> элементов, см. в разделе [Общие сведения о панелях](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="9f273-217">Дополнительные сведения о макете см. в разделе [макета](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="9f273-218">В этом разделе описано, создании одного столбца таблицы с тремя строками и полями шириной 10 пикселей путем добавления определений столбцов и строк для <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="9f273-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="9f273-219">В *`ExpenseItHome.xaml`*, задайте <xref:System.Windows.FrameworkElement.Margin%2A> свойство <xref:System.Windows.Controls.Grid> элемент «10,0,10,10», который соответствует слева, сверху, справа и нижнего полей:</span><span class="sxs-lookup"><span data-stu-id="9f273-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="9f273-220">Можно также задать **Margin** значения в **свойства** окна в разделе **макета** категории:</span><span class="sxs-lookup"><span data-stu-id="9f273-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения полей в окно "Свойства"](./media/properties-margin.png)

2. <span data-ttu-id="9f273-222">Добавьте следующий XAML между <xref:System.Windows.Controls.Grid> теги, чтобы создать определения строк и столбцов:</span><span class="sxs-lookup"><span data-stu-id="9f273-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="9f273-223"><xref:System.Windows.Controls.RowDefinition.Height%2A> Двух строк имеет значение <xref:System.Windows.GridLength.Auto%2A>, означающее, что размер строки на основе содержимого в строках.</span><span class="sxs-lookup"><span data-stu-id="9f273-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="9f273-224">Значение по умолчанию <xref:System.Windows.Controls.RowDefinition.Height%2A> является <xref:System.Windows.GridUnitType.Star> изменения размера, это означает, что высота строки — это взвешенная пропорция доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="9f273-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="9f273-225">Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> из «\*», каждый из них имеет высоту, половина доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="9f273-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="9f273-226">Ваш <xref:System.Windows.Controls.Grid> теперь должно содержать следующие XAML:</span><span class="sxs-lookup"><span data-stu-id="9f273-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="9f273-227">Добавление элементов управления</span><span class="sxs-lookup"><span data-stu-id="9f273-227">Add controls</span></span>

<span data-ttu-id="9f273-228">В этом разделе вы обновите на домашней странице пользовательский Интерфейс для отображения списка пользователей, где выбран один пользователь, для отображения отчета о расходах.</span><span class="sxs-lookup"><span data-stu-id="9f273-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="9f273-229">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="9f273-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="9f273-230">Более подробную информацию см. в разделе [Элементы управления](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="9f273-231">Чтобы создать этот пользовательский Интерфейс, нужно добавить следующие элементы для *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="9f273-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="9f273-232">Объект <xref:System.Windows.Controls.ListBox> (для списка пользователей).</span><span class="sxs-lookup"><span data-stu-id="9f273-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="9f273-233">Объект <xref:System.Windows.Controls.Label> (для заголовков списка).</span><span class="sxs-lookup"><span data-stu-id="9f273-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="9f273-234">Объект <xref:System.Windows.Controls.Button> (чтобы щелкните, чтобы просмотреть отчет по расходам для человека, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="9f273-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="9f273-235">Каждый элемент управления помещается в строке <xref:System.Windows.Controls.Grid> , задав <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вложенного свойства зависимостей.</span><span class="sxs-lookup"><span data-stu-id="9f273-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="9f273-236">Дополнительные сведения о вложенных свойствах см. в разделе [зависимостей](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="9f273-237">В *`ExpenseItHome.xaml`*, добавьте следующий XAML где-то между <xref:System.Windows.Controls.Grid> теги:</span><span class="sxs-lookup"><span data-stu-id="9f273-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="9f273-238">Также можно создать элементы управления, перетащив их из **элементов** окна в окне конструктора, а затем задав их свойства в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="9f273-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="9f273-239">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-239">Build and run the application.</span></span>

    <span data-ttu-id="9f273-240">На следующем рисунке показано элементы управления, что вы создали:</span><span class="sxs-lookup"><span data-stu-id="9f273-240">The following illustration shows the controls you created:</span></span>

    ![Снимок экрана примера ExpenseIt](./media/gettingstartedfigure2.png)

3. <span data-ttu-id="9f273-242">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f273-242">Close the application to return to Visual Studio.</span></span>

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="9f273-243">Добавить изображение и заголовок</span><span class="sxs-lookup"><span data-stu-id="9f273-243">Add an image and a title</span></span>

<span data-ttu-id="9f273-244">В этом разделе вы обновите интерфейсе пользователя домашней страницы изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="9f273-244">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="9f273-245">В *`ExpenseItHome.xaml`*, добавьте еще один столбец для <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей:</span><span class="sxs-lookup"><span data-stu-id="9f273-245">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="9f273-246">Добавить другую строку для <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, всего четыре строки:</span><span class="sxs-lookup"><span data-stu-id="9f273-246">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="9f273-247">Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойство в значение 1, в каждом из трех элементов управления (границы, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="9f273-247">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="9f273-248">Переместите каждый элемент управления вниз на одну строку, увеличивая его <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> значение на 1 для каждого из трех элементов управления (границы, ListBox и кнопка), а также для элемента.</span><span class="sxs-lookup"><span data-stu-id="9f273-248">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="9f273-249">XAML для трех элементов управления теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9f273-249">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="9f273-250">Задайте <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> свойства *watermark.png* файл изображения, добавив следующий XAML в любом месте между `<Grid>` и `</Grid>` теги:</span><span class="sxs-lookup"><span data-stu-id="9f273-250">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="9f273-251">Прежде чем <xref:System.Windows.Controls.Border> элемента, добавьте <xref:System.Windows.Controls.Label> с содержимым «View Expense Report».</span><span class="sxs-lookup"><span data-stu-id="9f273-251">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="9f273-252">Эта метка — это заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="9f273-252">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="9f273-253">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-253">Build and run the application.</span></span>

<span data-ttu-id="9f273-254">На следующем рисунке показано только что добавленную результаты:</span><span class="sxs-lookup"><span data-stu-id="9f273-254">The following illustration shows the results of what you just added:</span></span>

![Снимок экрана примера ExpenseIt](./media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="9f273-256">Добавьте код для обработки событий</span><span class="sxs-lookup"><span data-stu-id="9f273-256">Add code to handle events</span></span>

1. <span data-ttu-id="9f273-257">В *`ExpenseItHome.xaml`*, добавьте <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в обработчике событий <xref:System.Windows.Controls.Button> элемент.</span><span class="sxs-lookup"><span data-stu-id="9f273-257">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="9f273-258">Дополнительные сведения см. в разделе [Как Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9f273-258">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="9f273-259">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="9f273-259">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="9f273-260">Добавьте следующий код, чтобы `ExpenseItHome` класс, чтобы добавить кнопку обработчик события щелчка.</span><span class="sxs-lookup"><span data-stu-id="9f273-260">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="9f273-261">Обработчик событий открывает **ExpenseReportPage** страницы.</span><span class="sxs-lookup"><span data-stu-id="9f273-261">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="9f273-262">Создание пользовательского интерфейса для страницы ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="9f273-262">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="9f273-263">*ExpenseReportPage.xaml* отображается отчет по расходам для человека, выбранного на **`ExpenseItHome`** страницы.</span><span class="sxs-lookup"><span data-stu-id="9f273-263">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="9f273-264">В этом разделе вы создадите пользовательский Интерфейс для **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="9f273-264">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="9f273-265">Вы также добавите фона и цвета для различных элементов пользовательского интерфейса заливки.</span><span class="sxs-lookup"><span data-stu-id="9f273-265">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="9f273-266">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-266">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="9f273-267">Добавьте следующий XAML между <xref:System.Windows.Controls.Grid> теги:</span><span class="sxs-lookup"><span data-stu-id="9f273-267">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="9f273-268">Этот пользовательский Интерфейс аналогичен *`ExpenseItHome.xaml`*, за исключением, что данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="9f273-268">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="9f273-269">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-269">Build and run the application.</span></span>

4. <span data-ttu-id="9f273-270">Выберите **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="9f273-270">Select the **View** button.</span></span>

    <span data-ttu-id="9f273-271">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="9f273-271">The expense report page appears.</span></span> <span data-ttu-id="9f273-272">Также Обратите внимание на то, что кнопка возврата включено.</span><span class="sxs-lookup"><span data-stu-id="9f273-272">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="9f273-273">На следующем рисунке показан элементы пользовательского интерфейса, добавленные *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-273">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Снимок экрана примера ExpenseIt](./media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="9f273-275">Определение стиля элементов управления</span><span class="sxs-lookup"><span data-stu-id="9f273-275">Style controls</span></span>

<span data-ttu-id="9f273-276">Внешний вид различных элементов часто является одинаковым для всех элементов одного типа в пользовательском Интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9f273-276">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="9f273-277">Пользовательский Интерфейс использует [стили](../controls/styling-and-templating.md) чтобы варианты внешнего вида многократного использования для нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="9f273-277">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="9f273-278">Повторное использование стилей помогает упростить создание XAML и управление ими.</span><span class="sxs-lookup"><span data-stu-id="9f273-278">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="9f273-279">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="9f273-279">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="9f273-280">Откройте *Application.xaml* или *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-280">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="9f273-281">Добавьте следующий XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> теги:</span><span class="sxs-lookup"><span data-stu-id="9f273-281">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="9f273-282">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="9f273-282">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="9f273-283">`headerTextStyle`: Для форматирования заголовка страницы <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="9f273-283">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="9f273-284">`labelStyle`: Для форматирования <xref:System.Windows.Controls.Label> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9f273-284">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="9f273-285">`columnHeaderStyle`: Для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="9f273-285">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="9f273-286">`listHeaderStyle`: Форматирование заголовка списка <xref:System.Windows.Controls.Border> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9f273-286">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="9f273-287">`listHeaderTextStyle`: Форматирование заголовка списка <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="9f273-287">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="9f273-288">`buttonStyle`: Для форматирования <xref:System.Windows.Controls.Button> на `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9f273-288">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="9f273-289">Обратите внимание на то, что стили представляют собой ресурсы и являются дочерними <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемент свойства.</span><span class="sxs-lookup"><span data-stu-id="9f273-289">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="9f273-290">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="9f273-290">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="9f273-291">Пример использования ресурсов в приложении .NET, см. в разделе [использование ресурсов приложения](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-291">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="9f273-292">В *`ExpenseItHome.xaml`*, замените весь код между <xref:System.Windows.Controls.Grid> элементов при помощи следующих XAML:</span><span class="sxs-lookup"><span data-stu-id="9f273-292">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="9f273-293">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="9f273-293">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="9f273-294">Например `headerTextStyle` применяется к «View Expense Report» <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="9f273-294">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="9f273-295">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-295">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="9f273-296">Замените весь код между <xref:System.Windows.Controls.Grid> элементов при помощи следующих XAML:</span><span class="sxs-lookup"><span data-stu-id="9f273-296">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="9f273-297">Этот XAML добавлены стили <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border> элементы.</span><span class="sxs-lookup"><span data-stu-id="9f273-297">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="9f273-298">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-298">Build and run the application.</span></span> <span data-ttu-id="9f273-299">Внешний вид окна совпадает с ранее.</span><span class="sxs-lookup"><span data-stu-id="9f273-299">The window appearance is the same as previously.</span></span>

    ![Снимок экрана примера ExpenseIt](./media/gettingstartedfigure4.png)

7. <span data-ttu-id="9f273-301">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9f273-301">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="9f273-302">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="9f273-302">Bind data to a control</span></span>

<span data-ttu-id="9f273-303">В этом разделе вы создадите XML-данных, привязанный к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="9f273-303">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="9f273-304">В *`ExpenseItHome.xaml`*, открыв <xref:System.Windows.Controls.Grid> элемента, добавьте следующий XAML для создания <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="9f273-304">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="9f273-305">Данные создаются как <xref:System.Windows.Controls.Grid> ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9f273-305">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="9f273-306">Обычно эти данные могут загружаться как файл, но для простоты данные добавлены в код.</span><span class="sxs-lookup"><span data-stu-id="9f273-306">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="9f273-307">В рамках `<Grid.Resources>` элемента, добавьте следующий `<xref:System.Windows.DataTemplate>` элемент, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>после `<XmlDataProvider>` элемент:</span><span class="sxs-lookup"><span data-stu-id="9f273-307">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="9f273-308">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения о шаблонах данных](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-308">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="9f273-309">Замените существующий <xref:System.Windows.Controls.ListBox> с следующем XAML:</span><span class="sxs-lookup"><span data-stu-id="9f273-309">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="9f273-310">Этот XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных как <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9f273-310">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="9f273-311">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="9f273-311">Connect data to controls</span></span>

<span data-ttu-id="9f273-312">Далее добавим код для извлечения имени, выбранного на **`ExpenseItHome`** странице и передать его конструктору **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="9f273-312">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="9f273-313">**ExpenseReportPage** задает контекст данных для переданного элемента, который является то, что элементы управления, определенные в *ExpenseReportPage.xaml* привязки.</span><span class="sxs-lookup"><span data-stu-id="9f273-313">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="9f273-314">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="9f273-314">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="9f273-315">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9f273-315">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="9f273-316">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="9f273-316">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="9f273-317">Изменение <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий для вызова новый конструктор, передавая отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9f273-317">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="9f273-318">Стиль данных с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="9f273-318">Style data with data templates</span></span>

<span data-ttu-id="9f273-319">В этом разделе вы обновите пользовательский Интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="9f273-319">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="9f273-320">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9f273-320">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="9f273-321">Привяжите содержимое «Name» и «Отдел» <xref:System.Windows.Controls.Label> свойство источника элементов, соответствующих данных.</span><span class="sxs-lookup"><span data-stu-id="9f273-321">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="9f273-322">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9f273-322">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="9f273-323">После открывающего <xref:System.Windows.Controls.Grid> элемента, добавьте следующие шаблоны данных, которые определяют способ отображения данных отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="9f273-323">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="9f273-324">Замените <xref:System.Windows.Controls.DataGridTextColumn> элементов при помощи <xref:System.Windows.Controls.DataGridTemplateColumn> под <xref:System.Windows.Controls.DataGrid> элемента и примените шаблоны к ним.</span><span class="sxs-lookup"><span data-stu-id="9f273-324">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="9f273-325">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9f273-325">Build and run the application.</span></span>

6. <span data-ttu-id="9f273-326">Выберите "person", а затем выберите **представление** кнопки.</span><span class="sxs-lookup"><span data-stu-id="9f273-326">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="9f273-327">На следующем рисунке показан обе страницы `ExpenseIt` приложения с помощью элементов управления, макет, стили, привязку данных и примененными шаблонами данных:</span><span class="sxs-lookup"><span data-stu-id="9f273-327">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Снимки экрана примера ExpenseIt](./media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="9f273-329">В этом примере демонстрируется конкретная функциональная возможность WPF и не выполните все рекомендации по безопасности, локализации и специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="9f273-329">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="9f273-330">Исчерпывающая информация о WPF и рекомендации по разработке приложений .NET см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9f273-330">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="9f273-331">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="9f273-331">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="9f273-332">Безопасность</span><span class="sxs-lookup"><span data-stu-id="9f273-332">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="9f273-333">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-333">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="9f273-334">Производительности WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-334">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="9f273-335">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9f273-335">Next steps</span></span>

<span data-ttu-id="9f273-336">В этом пошаговом руководстве вы узнали ряд методов для создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9f273-336">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="9f273-337">Теперь вы должны основные стандартные блоки приложения .NET с данными.</span><span class="sxs-lookup"><span data-stu-id="9f273-337">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="9f273-338">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9f273-338">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="9f273-339">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-339">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="9f273-340">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9f273-340">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="9f273-341">Общие сведения о свойствах зависимостей</span><span class="sxs-lookup"><span data-stu-id="9f273-341">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="9f273-342">Макет</span><span class="sxs-lookup"><span data-stu-id="9f273-342">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="9f273-343">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9f273-343">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="9f273-344">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="9f273-344">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="9f273-345">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="9f273-345">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="9f273-346">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="9f273-346">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="9f273-347">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9f273-347">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="9f273-348">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-348">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="9f273-349">См. также</span><span class="sxs-lookup"><span data-stu-id="9f273-349">See also</span></span>

- [<span data-ttu-id="9f273-350">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="9f273-350">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="9f273-351">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="9f273-351">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="9f273-352">Построение приложения WPF</span><span class="sxs-lookup"><span data-stu-id="9f273-352">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="9f273-353">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="9f273-353">Styles and templates</span></span>](../controls/styles-and-templates.md)
