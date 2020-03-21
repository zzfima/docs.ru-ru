---
title: Создайте свое первое приложение WPF в Visual Studio 2019 - .NET Framework
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: 65b6fe31e86380162e90820c2cf118a9d1b96b4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186586"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="66aea-102">Учебник: Создайте свое первое приложение WPF в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="66aea-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="66aea-103">В этой статье показано, как разработать настольное приложение Windows Presentation Foundation (WPF), которое включает элементы, общие для большинства приложений WPF: разметка разметки «Расширяемый язык разметки» (XAML), код-за, определения приложений, элементы управления, макет, связывание данных и стили.</span><span class="sxs-lookup"><span data-stu-id="66aea-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="66aea-104">Для разработки приложения вы будете использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66aea-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="66aea-105">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="66aea-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="66aea-106">Создайте проект WPF.</span><span class="sxs-lookup"><span data-stu-id="66aea-106">Create a WPF project.</span></span>
> - <span data-ttu-id="66aea-107">Используйте XAML для разработки внешнего вида пользовательского интерфейса приложения (UI).</span><span class="sxs-lookup"><span data-stu-id="66aea-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="66aea-108">Напишите код для построения поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="66aea-109">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="66aea-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="66aea-110">Добавьте элементы управления и создайте макет для составления uI-има приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="66aea-111">Создавайте стили для последовательного внешнего вида на протяжении всего uI приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="66aea-112">Привязать uI к данным, как для заполнения uI из данных, так и для синхронизации данных и uI.</span><span class="sxs-lookup"><span data-stu-id="66aea-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="66aea-113">К концу учебника вы создали отдельное приложение Windows, которое позволяет пользователям просматривать отчеты о расходах для выбранных людей.</span><span class="sxs-lookup"><span data-stu-id="66aea-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="66aea-114">Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.</span><span class="sxs-lookup"><span data-stu-id="66aea-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="66aea-115">Образец кода, который используется в этом учебнике, доступен как для Visual Basic, так и для C- в [учебном коде WPF App Sample.](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)</span><span class="sxs-lookup"><span data-stu-id="66aea-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="66aea-116">Вы можете переключить кодовый язык кода образца между C и Visual Basic, используя селектор языка поверх этой страницы.</span><span class="sxs-lookup"><span data-stu-id="66aea-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66aea-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="66aea-117">Prerequisites</span></span>

- <span data-ttu-id="66aea-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой для **разработки рабочего стола .NET.**</span><span class="sxs-lookup"><span data-stu-id="66aea-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="66aea-119">Для получения дополнительной информации об установке последней версии Visual Studio, [см.](/visualstudio/install/install-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="66aea-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="66aea-120">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="66aea-120">Create the application project</span></span>

<span data-ttu-id="66aea-121">Первым шагом является создание инфраструктуры приложения, которая включает определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="66aea-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="66aea-122">Создайте новый проект приложения WPF в **`ExpenseIt`** Visual Basic или Visual C зпод названием:</span><span class="sxs-lookup"><span data-stu-id="66aea-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="66aea-123">Откройте Visual Studio и выберите **Создать новый проект** в меню **Get started.**</span><span class="sxs-lookup"><span data-stu-id="66aea-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="66aea-124">Открывается диалог **«Создание нового проекта».**</span><span class="sxs-lookup"><span data-stu-id="66aea-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="66aea-125">В выпадении **языка** выберите либо **C-** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="66aea-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="66aea-126">Выберите шаблон **приложения WPF (.NET Framework),** а затем выберите **следующий**.</span><span class="sxs-lookup"><span data-stu-id="66aea-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Диалоговое окно создания проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="66aea-128">Открывается новый диалог **проекта.**</span><span class="sxs-lookup"><span data-stu-id="66aea-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="66aea-129">Введите **`ExpenseIt`** имя проекта, а затем выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="66aea-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Настройка нового диалога проекта](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="66aea-131">Visual Studio создает проект и открывает дизайнердля окна приложения по умолчанию под названием **MainWindow.xaml.**</span><span class="sxs-lookup"><span data-stu-id="66aea-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="66aea-132">Открытое *приложение.xaml* (Visual Basic) или *App.xaml* (C).</span><span class="sxs-lookup"><span data-stu-id="66aea-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="66aea-133">Этот файл XAML определяет приложение WPF и любые ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="66aea-134">Вы также используете этот файл, чтобы указать uI, в данном случае *MainWindow.xaml*, который автоматически показывает, когда приложение начинается.</span><span class="sxs-lookup"><span data-stu-id="66aea-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="66aea-135">Ваш XAML должен выглядеть следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="66aea-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="66aea-136">И, как и следующие в C ':</span><span class="sxs-lookup"><span data-stu-id="66aea-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="66aea-137">Открыть *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="66aea-138">Этот файл XAML является основным окном вашего приложения и отображает содержимое, созданное на страницах.</span><span class="sxs-lookup"><span data-stu-id="66aea-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="66aea-139">Класс <xref:System.Windows.Window> определяет свойства окна, такие как его название, размер или значок, и обрабатывает события, такие как закрытие или сокрытие.</span><span class="sxs-lookup"><span data-stu-id="66aea-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="66aea-140">Измените <xref:System.Windows.Window> элемент <xref:System.Windows.Navigation.NavigationWindow>на , как показано в следующем XAML:</span><span class="sxs-lookup"><span data-stu-id="66aea-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="66aea-141">Это приложение переходит к другому содержимому в зависимости от ввода пользователя.</span><span class="sxs-lookup"><span data-stu-id="66aea-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="66aea-142">Вот почему главное <xref:System.Windows.Window> должно быть <xref:System.Windows.Navigation.NavigationWindow>изменено на .</span><span class="sxs-lookup"><span data-stu-id="66aea-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="66aea-143"><xref:System.Windows.Navigation.NavigationWindow>наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="66aea-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="66aea-144">Элемент <xref:System.Windows.Navigation.NavigationWindow> в файле XAML создает <xref:System.Windows.Navigation.NavigationWindow> экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="66aea-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="66aea-145">Для получения дополнительной информации смотрите [обзор навигации](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="66aea-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="66aea-146">Удалите <xref:System.Windows.Controls.Grid> элементы <xref:System.Windows.Navigation.NavigationWindow> между тегами.</span><span class="sxs-lookup"><span data-stu-id="66aea-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="66aea-147">Измените следующие свойства в коде <xref:System.Windows.Navigation.NavigationWindow> XAML для элемента:</span><span class="sxs-lookup"><span data-stu-id="66aea-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="66aea-148">Установите <xref:System.Windows.Window.Title%2A> свойство`ExpenseIt`на ".</span><span class="sxs-lookup"><span data-stu-id="66aea-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="66aea-149">Установите <xref:System.Windows.FrameworkElement.Height%2A> свойство до 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="66aea-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="66aea-150">Установите <xref:System.Windows.FrameworkElement.Width%2A> свойство до 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="66aea-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="66aea-151">Ваш XAML должен выглядеть следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="66aea-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="66aea-152">И, как и следующие для C '</span><span class="sxs-lookup"><span data-stu-id="66aea-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="66aea-153">Открыть *MainWindow.xaml.vb* или *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="66aea-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="66aea-154">Этот файл представляет собой файл с кодом, содержащий код для обработки событий, заявленных в *MainWindow.xaml.*</span><span class="sxs-lookup"><span data-stu-id="66aea-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="66aea-155">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="66aea-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="66aea-156">Если вы используете C-е, `MainWindow` измените <xref:System.Windows.Navigation.NavigationWindow>класс, чтобы извлечь из .</span><span class="sxs-lookup"><span data-stu-id="66aea-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="66aea-157">(В Visual Basic это происходит автоматически при изменении окна в XAML.) Ваш код C's теперь должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="66aea-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="66aea-158">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="66aea-158">Add files to the application</span></span>

<span data-ttu-id="66aea-159">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="66aea-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="66aea-160">Добавьте новую страницу в *`ExpenseItHome.xaml`* проект и назовите ее:</span><span class="sxs-lookup"><span data-stu-id="66aea-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="66aea-161">В **Solution Explorer**, правой кнопкой **`ExpenseIt`** мыши на узло проекта и выбрать **Добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="66aea-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="66aea-162">В диалоге **Добавить новый элемент** уже выбран шаблон **Страницы (WPF).**</span><span class="sxs-lookup"><span data-stu-id="66aea-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="66aea-163">Введите **`ExpenseItHome`** имя, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="66aea-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="66aea-164">Эта страница является первой страницей, отображаемыми при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="66aea-165">Он покажет список людей, которые можно выбрать из, чтобы показать отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="66aea-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="66aea-166">Открыто *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="66aea-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="66aea-167">Установить <xref:System.Windows.Controls.Page.Title%2A> на`ExpenseIt - Home`" "</span><span class="sxs-lookup"><span data-stu-id="66aea-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="66aea-168">Установите `DesignHeight` до 350 пикселей и `DesignWidth` до 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="66aea-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="66aea-169">XAML теперь отображается следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="66aea-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="66aea-170">И, как и следующие для C '</span><span class="sxs-lookup"><span data-stu-id="66aea-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="66aea-171">Открыть *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="66aea-172">Добавьте <xref:System.Windows.Navigation.NavigationWindow.Source%2A> свойство <xref:System.Windows.Navigation.NavigationWindow> к элементу`ExpenseItHome.xaml`и установите его на ".</span><span class="sxs-lookup"><span data-stu-id="66aea-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="66aea-173">Это *`ExpenseItHome.xaml`* наборы, чтобы быть первой страницей, открытой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="66aea-174">Пример XAML в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="66aea-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="66aea-175">И в C:</span><span class="sxs-lookup"><span data-stu-id="66aea-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="66aea-176">Вы также можете установить свойство **Source** в **разной** категории окна **Свойства.**</span><span class="sxs-lookup"><span data-stu-id="66aea-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Источник свойства в окне свойства](./media/properties-source.png)

1. <span data-ttu-id="66aea-178">Добавьте в проект еще одну новую страницу WPF и назовите ее *ExpenseReportPage.xaml::*</span><span class="sxs-lookup"><span data-stu-id="66aea-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="66aea-179">В **Solution Explorer**, правой кнопкой **`ExpenseIt`** мыши на узло проекта и выбрать **Добавить** > **страницы**.</span><span class="sxs-lookup"><span data-stu-id="66aea-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="66aea-180">В диалоге **Добавить новый элемент** выберите шаблон **Страницы (WPF).**</span><span class="sxs-lookup"><span data-stu-id="66aea-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="66aea-181">Введите имя **ExpenseReportPage,** а затем **выберите Добавить**.</span><span class="sxs-lookup"><span data-stu-id="66aea-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="66aea-182">На этой странице будет отображаться отчет о расходах для выбранного на **`ExpenseItHome`** странице лица.</span><span class="sxs-lookup"><span data-stu-id="66aea-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="66aea-183">Открыть *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="66aea-184">Установить <xref:System.Windows.Controls.Page.Title%2A> на`ExpenseIt - View Expense`" "</span><span class="sxs-lookup"><span data-stu-id="66aea-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="66aea-185">Установите `DesignHeight` до 350 пикселей и `DesignWidth` до 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="66aea-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="66aea-186">*ExpenseReportPage.xaml* теперь выглядит следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="66aea-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="66aea-187">И, как и следующие в C ':</span><span class="sxs-lookup"><span data-stu-id="66aea-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="66aea-188">Открыть *ExpenseItHome.xaml.vb* и *ExpenseReportPage.xaml.vb*, или *ExpenseItHome.xaml.cs* и *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="66aea-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="66aea-189">При создании нового файла Страницы Visual Studio автоматически создает свой *файл с кодом.*</span><span class="sxs-lookup"><span data-stu-id="66aea-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="66aea-190">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="66aea-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="66aea-191">Ваш код должен выглядеть **`ExpenseItHome`** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="66aea-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="66aea-192">И, как следующие для **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="66aea-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="66aea-193">Добавьте в проект изображение под названием *watermark.png.*</span><span class="sxs-lookup"><span data-stu-id="66aea-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="66aea-194">Вы можете создать свое собственное изображение, скопировать файл из кода образца или получить его из репозитория [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub.</span><span class="sxs-lookup"><span data-stu-id="66aea-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="66aea-195">Нажмите правой кнопкой мыши на узла проекта и выберите **Добавить** > **существующий элемент,** или нажмите **Shift**+**Alt**+**A.**</span><span class="sxs-lookup"><span data-stu-id="66aea-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="66aea-196">В диалоге **Добавить существующий элемент** установите фильтр файла либо для **всех файлов** или **файлов изображений,** просмотрите файл изображения, который вы хотите использовать, а затем выберите **Добавить.**</span><span class="sxs-lookup"><span data-stu-id="66aea-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="66aea-197">Создание и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="66aea-197">Build and run the application</span></span>

1. <span data-ttu-id="66aea-198">Чтобы создать и запустить приложение, нажмите **F5** или выберите **Start Debugging** из меню **Debug.**</span><span class="sxs-lookup"><span data-stu-id="66aea-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="66aea-199">На следующей иллюстрации <xref:System.Windows.Navigation.NavigationWindow> показано приложение с кнопками:</span><span class="sxs-lookup"><span data-stu-id="66aea-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Приложение после создания и запуска его.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="66aea-201">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66aea-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="66aea-202">Создание макета</span><span class="sxs-lookup"><span data-stu-id="66aea-202">Create the layout</span></span>

<span data-ttu-id="66aea-203">Layout предоставляет упорядоченный способ размещения элементов uI, а также управляет размером и положением этих элементов при повторном размере uI.</span><span class="sxs-lookup"><span data-stu-id="66aea-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="66aea-204">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="66aea-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="66aea-205"><xref:System.Windows.Controls.Canvas>- Определяет область, в которой вы можете явно позиционировать элементы ребенка, используя координаты, которые относятся к области Canvas.</span><span class="sxs-lookup"><span data-stu-id="66aea-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="66aea-206"><xref:System.Windows.Controls.DockPanel>- Определяет область, где вы можете расположить элементы ребенка либо горизонтально, либо вертикально, по отношению друг к другу.</span><span class="sxs-lookup"><span data-stu-id="66aea-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="66aea-207"><xref:System.Windows.Controls.Grid>- Определяет гибкую область сетки, которая состоит из столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="66aea-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="66aea-208"><xref:System.Windows.Controls.StackPanel>- Упорядочить элементы ребенка в одну линию, которая может быть ориентирована горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="66aea-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="66aea-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- Организует и виртуализирует контент на одной линии, которая ориентирована либо горизонтально, либо вертикально.</span><span class="sxs-lookup"><span data-stu-id="66aea-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="66aea-210"><xref:System.Windows.Controls.WrapPanel>- Позиции элементы ребенка в последовательном положении слева направо, нарушая содержимое следующей строки на краю содержащего окна.</span><span class="sxs-lookup"><span data-stu-id="66aea-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="66aea-211">Последующий заказ происходит последовательно сверху вниз или справа налево, в зависимости от стоимости свойства Ориентации.</span><span class="sxs-lookup"><span data-stu-id="66aea-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="66aea-212">Каждый из этих элементов расположения макета поддерживает определенный тип макета для своих элементов ребенка.</span><span class="sxs-lookup"><span data-stu-id="66aea-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="66aea-213">`ExpenseIt`страницы могут быть изменены, и каждая страница имеет элементы, которые расположены горизонтально и вертикально наряду с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="66aea-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="66aea-214">В этом примере используется элемент <xref:System.Windows.Controls.Grid> макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="66aea-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="66aea-215">Для получения <xref:System.Windows.Controls.Panel> дополнительной информации об элементах [см.](../controls/panels-overview.md)</span><span class="sxs-lookup"><span data-stu-id="66aea-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="66aea-216">Для получения дополнительной информации [Layout](../advanced/layout.md)о макете см.</span><span class="sxs-lookup"><span data-stu-id="66aea-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="66aea-217">В этом разделе создается таблица с одной колонкой с тремя рядами и 10-пиксельной маржой, добавляя определения столбца и строки <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="66aea-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="66aea-218">В *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> установить <xref:System.Windows.Controls.Grid> свойство на элементе "10,0,10,10", что соответствует левой, верхней, правой и нижней поля:</span><span class="sxs-lookup"><span data-stu-id="66aea-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="66aea-219">Вы также можете установить значения **маржи** в окне **свойств** под категорией **Layout:**</span><span class="sxs-lookup"><span data-stu-id="66aea-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения маржи в окне свойств](./media/properties-margin.png)

2. <span data-ttu-id="66aea-221">Добавьте следующие XAML между <xref:System.Windows.Controls.Grid> тегами, чтобы создать определения строки и столбца:</span><span class="sxs-lookup"><span data-stu-id="66aea-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="66aea-222">Двух <xref:System.Windows.Controls.RowDefinition.Height%2A> строк установлен, что <xref:System.Windows.GridLength.Auto%2A>означает, что ряды размером в зависимости от содержимого строк.</span><span class="sxs-lookup"><span data-stu-id="66aea-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="66aea-223">По <xref:System.Windows.Controls.RowDefinition.Height%2A> умолчанию размер, <xref:System.Windows.GridUnitType.Star> что означает, что высота строки представляет собой взвешенную долю доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="66aea-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="66aea-224">Например, если в двух <xref:System.Windows.Controls.RowDefinition.Height%2A> строках есть "к", каждый из них имеет высоту, которая составляет половину имеющегося пространства.</span><span class="sxs-lookup"><span data-stu-id="66aea-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="66aea-225">Теперь <xref:System.Windows.Controls.Grid> ваш должен содержать следующие XAML:</span><span class="sxs-lookup"><span data-stu-id="66aea-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="66aea-226">Добавление элементов управления</span><span class="sxs-lookup"><span data-stu-id="66aea-226">Add controls</span></span>

<span data-ttu-id="66aea-227">В этом разделе вы обновите ui-образного веб-страницы, чтобы показать список людей, где вы выбираете одного человека для отображения отчета о расходах.</span><span class="sxs-lookup"><span data-stu-id="66aea-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="66aea-228">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="66aea-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="66aea-229">Для получения дополнительной информации [см.](../controls/index.md)</span><span class="sxs-lookup"><span data-stu-id="66aea-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="66aea-230">Чтобы создать этот uI, вы добавите *`ExpenseItHome.xaml`* следующие элементы к:</span><span class="sxs-lookup"><span data-stu-id="66aea-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="66aea-231">A <xref:System.Windows.Controls.ListBox> (для списка людей).</span><span class="sxs-lookup"><span data-stu-id="66aea-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="66aea-232">A <xref:System.Windows.Controls.Label> (для заголовка списка).</span><span class="sxs-lookup"><span data-stu-id="66aea-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="66aea-233">A <xref:System.Windows.Controls.Button> (нажмите кнопку, чтобы просмотреть отчет о расходах для человека, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="66aea-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="66aea-234">Каждый элемент управления помещается <xref:System.Windows.Controls.Grid> в <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> ряд прилагаемого свойства.</span><span class="sxs-lookup"><span data-stu-id="66aea-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="66aea-235">Для получения дополнительной информации [Attached Properties Overview](../advanced/attached-properties-overview.md)о прилагаемых свойствах см.</span><span class="sxs-lookup"><span data-stu-id="66aea-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="66aea-236">В *`ExpenseItHome.xaml`*, добавить следующее XAML где-то между <xref:System.Windows.Controls.Grid> тегами:</span><span class="sxs-lookup"><span data-stu-id="66aea-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="66aea-237">Вы также можете создать элементы управления, перетащив их из окна **Toolbox** в окно проектирования, а затем установив их свойства в окне **Свойств.**</span><span class="sxs-lookup"><span data-stu-id="66aea-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="66aea-238">Выполните сборку и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="66aea-238">Build and run the application.</span></span>

    <span data-ttu-id="66aea-239">На следующей иллюстрации показаны созданные вами элементы управления:</span><span class="sxs-lookup"><span data-stu-id="66aea-239">The following illustration shows the controls you created:</span></span>

![Анализ скриншота ExpenseIt отображает список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="66aea-241">Добавление изображения и заголовка</span><span class="sxs-lookup"><span data-stu-id="66aea-241">Add an image and a title</span></span>

<span data-ttu-id="66aea-242">В этом разделе вы обновите uI домашней страницы с изображением и заголовком страницы.</span><span class="sxs-lookup"><span data-stu-id="66aea-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="66aea-243">В *`ExpenseItHome.xaml`*, добавить <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> еще один <xref:System.Windows.Controls.ColumnDefinition.Width%2A> столбец с фиксированной 230 пикселей:</span><span class="sxs-lookup"><span data-stu-id="66aea-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="66aea-244">Добавьте еще <xref:System.Windows.Controls.Grid.RowDefinitions%2A>один ряд в , в общей сложности четыре строки:</span><span class="sxs-lookup"><span data-stu-id="66aea-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="66aea-245">Переместите элементы управления <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> во второй столбец, установив свойство до 1 в каждом из трех элементов управления (граница, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="66aea-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="66aea-246">Переместите каждый элемент управления <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> вниз по ряду, прививего его значение на 1 для каждого из трех элементов управления (граница, ListBox и кнопка) и для элемента границы.</span><span class="sxs-lookup"><span data-stu-id="66aea-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="66aea-247">XAML для трех элементов управления теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="66aea-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="66aea-248">Установите <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> свойство к файлу изображения *watermark.png,* добавив следующее XAML где-нибудь между `<Grid>` тегами: `</Grid>`</span><span class="sxs-lookup"><span data-stu-id="66aea-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="66aea-249">Перед <xref:System.Windows.Controls.Border> элементом добавьте <xref:System.Windows.Controls.Label> с содержанием "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="66aea-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="66aea-250">Эта метка является названием страницы.</span><span class="sxs-lookup"><span data-stu-id="66aea-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="66aea-251">Выполните сборку и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="66aea-251">Build and run the application.</span></span>

<span data-ttu-id="66aea-252">Следующая иллюстрация показывает результаты того, что вы только что добавили:</span><span class="sxs-lookup"><span data-stu-id="66aea-252">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt образец скриншот с указанием нового фона изображения и название страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="66aea-254">Добавление кода для обработки событий</span><span class="sxs-lookup"><span data-stu-id="66aea-254">Add code to handle events</span></span>

1. <span data-ttu-id="66aea-255">В *`ExpenseItHome.xaml`* элементе <xref:System.Windows.Controls.Primitives.ButtonBase.Click> добавьте <xref:System.Windows.Controls.Button> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="66aea-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="66aea-256">Для получения дополнительной информации [см. Как: Создать простой обработчик событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="66aea-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="66aea-257">Открыть *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* или .</span><span class="sxs-lookup"><span data-stu-id="66aea-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="66aea-258">Добавьте следующий `ExpenseItHome` код в класс, чтобы добавить обработчик события кнопки.</span><span class="sxs-lookup"><span data-stu-id="66aea-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="66aea-259">Обработчик событий открывает страницу **ExpenseReportPage.**</span><span class="sxs-lookup"><span data-stu-id="66aea-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="66aea-260">Создание uii для ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="66aea-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="66aea-261">*ExpenseReportPage.xaml* отображает отчет о расходах для человека, **`ExpenseItHome`** выбранного на странице.</span><span class="sxs-lookup"><span data-stu-id="66aea-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="66aea-262">В этом разделе вы создадите ui ii для **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="66aea-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="66aea-263">Вы также добавите фон и заполните цвета различных элементов uI.</span><span class="sxs-lookup"><span data-stu-id="66aea-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="66aea-264">Открыть *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="66aea-265">Добавьте следующие XAML между <xref:System.Windows.Controls.Grid> тегами:</span><span class="sxs-lookup"><span data-stu-id="66aea-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="66aea-266">Этот uI похож *`ExpenseItHome.xaml`* на, за исключением отчета <xref:System.Windows.Controls.DataGrid>данные отображаются в .</span><span class="sxs-lookup"><span data-stu-id="66aea-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="66aea-267">Выполните сборку и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="66aea-267">Build and run the application.</span></span>

4. <span data-ttu-id="66aea-268">Выберите кнопку **«Вид».**</span><span class="sxs-lookup"><span data-stu-id="66aea-268">Select the **View** button.</span></span>

    <span data-ttu-id="66aea-269">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="66aea-269">The expense report page appears.</span></span> <span data-ttu-id="66aea-270">Также обратите внимание, что кнопка обратной навигации включена.</span><span class="sxs-lookup"><span data-stu-id="66aea-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="66aea-271">На следующей иллюстрации показаны элементы uI, добавленные в *ExpenseReportPage.xaml.*</span><span class="sxs-lookup"><span data-stu-id="66aea-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt образец скриншот с указанием uI только что созданный для ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="66aea-273">Элементы управления стилем</span><span class="sxs-lookup"><span data-stu-id="66aea-273">Style controls</span></span>

<span data-ttu-id="66aea-274">Появление различных элементов часто одинаково для всех элементов одного типа в uI.</span><span class="sxs-lookup"><span data-stu-id="66aea-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="66aea-275">UI использует [стили,](../controls/styling-and-templating.md) чтобы сделать выступления многоразовыми для нескольких элементов.</span><span class="sxs-lookup"><span data-stu-id="66aea-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="66aea-276">Повторное использование стилей помогает упростить создание и управление XAML.</span><span class="sxs-lookup"><span data-stu-id="66aea-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="66aea-277">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="66aea-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="66aea-278">Открытое *application.xaml* или *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="66aea-279">Добавьте следующие XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> тегами:</span><span class="sxs-lookup"><span data-stu-id="66aea-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="66aea-280">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="66aea-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="66aea-281">`headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;</span><span class="sxs-lookup"><span data-stu-id="66aea-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="66aea-282">`labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;</span><span class="sxs-lookup"><span data-stu-id="66aea-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="66aea-283">`columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;</span><span class="sxs-lookup"><span data-stu-id="66aea-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="66aea-284">`listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;</span><span class="sxs-lookup"><span data-stu-id="66aea-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="66aea-285">`listHeaderTextStyle`: Для формата <xref:System.Windows.Controls.Label>заголовка списка .</span><span class="sxs-lookup"><span data-stu-id="66aea-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="66aea-286">`buttonStyle`: Для <xref:System.Windows.Controls.Button> формата на `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="66aea-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="66aea-287">Обратите внимание, что стили <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> являются ресурсами и детьми элемента свойства.</span><span class="sxs-lookup"><span data-stu-id="66aea-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="66aea-288">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="66aea-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="66aea-289">Например, использование ресурсов в приложении .NET [см.](../advanced/how-to-use-application-resources.md)</span><span class="sxs-lookup"><span data-stu-id="66aea-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="66aea-290">В *`ExpenseItHome.xaml`*, заменить <xref:System.Windows.Controls.Grid> все между элементами со следующими XAML:</span><span class="sxs-lookup"><span data-stu-id="66aea-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="66aea-291">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="66aea-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="66aea-292">Например, `headerTextStyle` применяется к "Отчету <xref:System.Windows.Controls.Label>о расходах просмотра".</span><span class="sxs-lookup"><span data-stu-id="66aea-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="66aea-293">Открыть *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="66aea-294">Замените все <xref:System.Windows.Controls.Grid> между элементами следующимXAML:</span><span class="sxs-lookup"><span data-stu-id="66aea-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="66aea-295">Это XAML добавляет <xref:System.Windows.Controls.Label> стили к элементам и <xref:System.Windows.Controls.Border> элементам.</span><span class="sxs-lookup"><span data-stu-id="66aea-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="66aea-296">Выполните сборку и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="66aea-296">Build and run the application.</span></span> <span data-ttu-id="66aea-297">Внешний вид окна такой же, как и ранее.</span><span class="sxs-lookup"><span data-stu-id="66aea-297">The window appearance is the same as previously.</span></span>

    ![ExpenseIt образец скриншот с тем же внешним видом, как и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="66aea-299">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66aea-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="66aea-300">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="66aea-300">Bind data to a control</span></span>

<span data-ttu-id="66aea-301">В этом разделе вы создадите данные XML, которые привязаны к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="66aea-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="66aea-302">В *`ExpenseItHome.xaml`*, после <xref:System.Windows.Controls.Grid> открытия элемента, добавить следующий XAML <xref:System.Windows.Data.XmlDataProvider> создать, который содержит данные для каждого человека:</span><span class="sxs-lookup"><span data-stu-id="66aea-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="66aea-303">Данные создаются <xref:System.Windows.Controls.Grid> как ресурс.</span><span class="sxs-lookup"><span data-stu-id="66aea-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="66aea-304">Обычно эти данные загружаются как файл, но для простоты данные добавляются в строке.</span><span class="sxs-lookup"><span data-stu-id="66aea-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="66aea-305">В `<Grid.Resources>` элементе добавьте `<xref:System.Windows.DataTemplate>` следующий элемент, определяющий способ <xref:System.Windows.Controls.ListBox>отображения данных в элементе после элемента: `<XmlDataProvider>`</span><span class="sxs-lookup"><span data-stu-id="66aea-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="66aea-306">Для получения дополнительной информации [Data templating overview](../data/data-templating-overview.md)о шаблонах данных см.</span><span class="sxs-lookup"><span data-stu-id="66aea-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="66aea-307">Замените <xref:System.Windows.Controls.ListBox> существующий на следующий XAML:</span><span class="sxs-lookup"><span data-stu-id="66aea-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="66aea-308">Это XAML связывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> источника данных и применяет шаблон <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>данных в качестве .</span><span class="sxs-lookup"><span data-stu-id="66aea-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="66aea-309">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="66aea-309">Connect data to controls</span></span>

<span data-ttu-id="66aea-310">Далее вы добавите код для получения выбранного на **`ExpenseItHome`** странице имени и передадут его конструктору **ExpenseReportPage.**</span><span class="sxs-lookup"><span data-stu-id="66aea-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="66aea-311">**ExpenseReportPage** устанавливает свой контекст данных с пройденный элемент, который является то, что элемент, определенный в *ExpenseReportPage.xaml* связывать.</span><span class="sxs-lookup"><span data-stu-id="66aea-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="66aea-312">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="66aea-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="66aea-313">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="66aea-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="66aea-314">Открыть *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* или .</span><span class="sxs-lookup"><span data-stu-id="66aea-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="66aea-315">Измените <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий, чтобы вызвать новый конструктор, передающий данные отчета о расходах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="66aea-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="66aea-316">Данные о стиле с шаблонами данных</span><span class="sxs-lookup"><span data-stu-id="66aea-316">Style data with data templates</span></span>

<span data-ttu-id="66aea-317">В этом разделе вы будете обновлять ui для каждого элемента в списках, связанных с данными, с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="66aea-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="66aea-318">Открыть *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="66aea-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="66aea-319">Привязать содержимое элементов "Имя" <xref:System.Windows.Controls.Label> и "Департамент" к соответствующему свойству источника данных.</span><span class="sxs-lookup"><span data-stu-id="66aea-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="66aea-320">Для получения дополнительной информации [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md)о привязке данных см.</span><span class="sxs-lookup"><span data-stu-id="66aea-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="66aea-321">После открытия <xref:System.Windows.Controls.Grid> элемента добавьте следующие шаблоны данных, которые определяют, как отображать данные отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="66aea-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="66aea-322">Замените <xref:System.Windows.Controls.DataGridTextColumn> элементы <xref:System.Windows.Controls.DataGridTemplateColumn> <xref:System.Windows.Controls.DataGrid> под элементом и примените к ним шаблоны.</span><span class="sxs-lookup"><span data-stu-id="66aea-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="66aea-323">Выполните сборку и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="66aea-323">Build and run the application.</span></span>

6. <span data-ttu-id="66aea-324">Выберите человека, а затем выберите кнопку **«Вид».**</span><span class="sxs-lookup"><span data-stu-id="66aea-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="66aea-325">На следующей иллюстрации `ExpenseIt` показаны обе страницы приложения с элементами управления, макетом, стилями, привязкой данных и прикладными шаблонами данных:</span><span class="sxs-lookup"><span data-stu-id="66aea-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Обе страницы приложения, показывающие список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="66aea-327">Этот пример демонстрирует особенность WPF и не соответствует всем рекомендациям по таким вещам, как безопасность, локализация и доступность.</span><span class="sxs-lookup"><span data-stu-id="66aea-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="66aea-328">Для всестороннего охвата wPF и передового опыта разработки приложений .NET см.</span><span class="sxs-lookup"><span data-stu-id="66aea-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="66aea-329">Доступность</span><span class="sxs-lookup"><span data-stu-id="66aea-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="66aea-330">Безопасность</span><span class="sxs-lookup"><span data-stu-id="66aea-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="66aea-331">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="66aea-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="66aea-332">Производительность WPF</span><span class="sxs-lookup"><span data-stu-id="66aea-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="66aea-333">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="66aea-333">Next steps</span></span>

<span data-ttu-id="66aea-334">В этом пошаге вы узнали ряд методов для создания uI с помощью Windows Презентация фонда (WPF).</span><span class="sxs-lookup"><span data-stu-id="66aea-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="66aea-335">Теперь вы должны иметь базовое представление о строительных блоках приложения .NET, связанного с данными.</span><span class="sxs-lookup"><span data-stu-id="66aea-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="66aea-336">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="66aea-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="66aea-337">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="66aea-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="66aea-338">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="66aea-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="66aea-339">Обзор свойств зависимостей</span><span class="sxs-lookup"><span data-stu-id="66aea-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="66aea-340">Макет</span><span class="sxs-lookup"><span data-stu-id="66aea-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="66aea-341">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="66aea-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="66aea-342">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="66aea-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="66aea-343">Управление</span><span class="sxs-lookup"><span data-stu-id="66aea-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="66aea-344">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="66aea-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="66aea-345">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="66aea-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="66aea-346">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="66aea-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="66aea-347">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66aea-347">See also</span></span>

- [<span data-ttu-id="66aea-348">Обзор панелей</span><span class="sxs-lookup"><span data-stu-id="66aea-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="66aea-349">Обзор шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="66aea-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="66aea-350">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="66aea-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="66aea-351">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="66aea-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
