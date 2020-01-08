---
title: Руководство. Создание первого приложения WPF в Visual Studio 2019 — .NET Framework
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b5f74448ffce448740937c06a476a29c8659879
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75336811"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="9ef5b-102">Руководство. Создание первого приложения WPF в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="9ef5b-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="9ef5b-103">В этой статье показано, как разработать классическое приложение Windows Presentation Foundation (WPF), включающее элементы, которые являются общими для большинства приложений WPF: разметка XAML (XAML), код программной части, определения приложений, элементы управления, макет, привязка данных и стили.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="9ef5b-104">Для разработки приложения вы будете использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="9ef5b-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9ef5b-106">Создайте проект WPF.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-106">Create a WPF project.</span></span>
> - <span data-ttu-id="9ef5b-107">Используйте XAML для проектирования внешнего вида пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="9ef5b-108">Напишите код для создания поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="9ef5b-109">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="9ef5b-110">Добавьте элементы управления и создайте макет, чтобы составить пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="9ef5b-111">Создание стилей для согласованного внешнего вида в пользовательском интерфейсе приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="9ef5b-112">Привязка пользовательского интерфейса к данным для заполнения пользовательского интерфейса данными и синхронизации данных и пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="9ef5b-113">По завершении работы с этим руководством вы создадите автономное приложение Windows, которое позволит пользователям просматривать отчеты о расходах для выбранных лиц.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="9ef5b-114">Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="9ef5b-115">Пример кода, используемый в этом руководстве, доступен как для Visual Basic, так и C# в [руководстве по примерам кода приложения WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="9ef5b-116">Язык кода образца кода можно переключать между C# и Visual Basic с помощью селектора языка в верхней части этой страницы.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ef5b-117">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="9ef5b-117">Prerequisites</span></span>

- <span data-ttu-id="9ef5b-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой " **Разработка классических приложений .NET** ".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="9ef5b-119">Дополнительные сведения об установке последней версии Visual Studio см. в [статье Установка Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="9ef5b-120">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="9ef5b-120">Create the application project</span></span>

<span data-ttu-id="9ef5b-121">Первым шагом является создание инфраструктуры приложения, включающей определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="9ef5b-122">Создайте новый проект приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="9ef5b-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="9ef5b-123">Откройте Visual Studio и выберите **создать новый проект** в меню **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="9ef5b-124">Откроется диалоговое окно **Создание нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="9ef5b-125">В раскрывающемся списке **язык** выберите либо **C#** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="9ef5b-126">Выберите шаблон **приложения WPF (.NET Framework)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Диалоговое окно создания проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="9ef5b-128">Откроется диалоговое окно **Настройка нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="9ef5b-129">Введите имя проекта **`ExpenseIt`** а затем щелкните **создать**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Диалоговое окно "Настройка нового проекта"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="9ef5b-131">Visual Studio создаст проект и откроет конструктор для окна приложения по умолчанию с именем **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="9ef5b-132">Откройте *Application. XAML* (Visual Basic) или *app. XAML* (C#).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="9ef5b-133">Этот XAML-файл определяет приложение WPF и все ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="9ef5b-134">Этот файл также используется для указания пользовательского интерфейса, в данном случае *MainWindow. XAML*, который автоматически отображается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="9ef5b-135">КОД XAML должен выглядеть следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="9ef5b-136">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="9ef5b-137">Откройте файл *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="9ef5b-138">Этот XAML-файл является главным окном приложения и отображает содержимое, созданное на страницах.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="9ef5b-139">Класс <xref:System.Windows.Window> определяет свойства окна, такие как заголовок, размер или значок, а также обрабатывает события, такие как закрытие или скрытие.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="9ef5b-140">Измените элемент <xref:System.Windows.Window> на <xref:System.Windows.Navigation.NavigationWindow>, как показано в следующем коде XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="9ef5b-141">Это приложение переходит к другому содержимому в зависимости от введенных пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="9ef5b-142">Именно поэтому основное <xref:System.Windows.Window> необходимо изменить на <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="9ef5b-143"><xref:System.Windows.Navigation.NavigationWindow> наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="9ef5b-144">Элемент <xref:System.Windows.Navigation.NavigationWindow> в файле XAML создает экземпляр класса <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="9ef5b-145">Дополнительные сведения см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="9ef5b-146">Удалите элементы <xref:System.Windows.Controls.Grid> из тегов <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="9ef5b-147">Измените следующие свойства в коде XAML для элемента <xref:System.Windows.Navigation.NavigationWindow>:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="9ef5b-148">Задайте для свойства <xref:System.Windows.Window.Title%2A> значение "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="9ef5b-149">Задайте для свойства <xref:System.Windows.FrameworkElement.Height%2A> значение 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="9ef5b-150">Задайте для свойства <xref:System.Windows.FrameworkElement.Width%2A> значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="9ef5b-151">КОД XAML должен выглядеть следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="9ef5b-152">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="9ef5b-153">Откройте файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="9ef5b-154">Этот файл является файлом кода программной части, который содержит код для работы с событиями, объявленными в файле *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="9ef5b-155">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="9ef5b-156">Если вы используете C#, измените класс `MainWindow` на производный от <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="9ef5b-157">(В Visual Basic это происходит автоматически при изменении окна в XAML.) Теперь C# ваш код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="9ef5b-158">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="9ef5b-158">Add files to the application</span></span>

<span data-ttu-id="9ef5b-159">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="9ef5b-160">Добавьте в проект новую страницу и назовите ее *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="9ef5b-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="9ef5b-161">В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **`ExpenseIt`** и выберите пункт **добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="9ef5b-162">В диалоговом окне **Добавление нового элемента** шаблон **Page (WPF)** уже выбран.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="9ef5b-163">Введите имя **`ExpenseItHome`** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="9ef5b-164">Эта страница является первой страницей, отображаемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="9ef5b-165">Отобразится список людей для выбора, чтобы отобразить отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="9ef5b-166">Откройте *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="9ef5b-167">Задайте для <xref:System.Windows.Controls.Page.Title%2A> значение "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="9ef5b-168">Задайте для `DesignHeight` значение 350 пикселей, а `DesignWidth` — 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="9ef5b-169">Теперь XAML выглядит следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="9ef5b-170">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="9ef5b-171">Откройте файл *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="9ef5b-172">Добавьте свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A> в элемент <xref:System.Windows.Navigation.NavigationWindow> и задайте для него значение "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="9ef5b-173">Этот параметр задает *`ExpenseItHome.xaml`* первой страницей, открытой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="9ef5b-174">Пример XAML в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="9ef5b-175">И в C#:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="9ef5b-176">Также можно задать свойство **Source** в категории **Разное** в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Свойство Source в окно свойств](./media/properties-source.png)

1. <span data-ttu-id="9ef5b-178">Добавьте еще одну новую страницу WPF в проект и назовите ее *файл ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="9ef5b-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="9ef5b-179">В **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **`ExpenseIt`** и выберите пункт **добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="9ef5b-180">В диалоговом окне **Добавление нового элемента** выберите шаблон **Page (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="9ef5b-181">Введите имя **файл ExpenseReportPage**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="9ef5b-182">На этой странице отображается отчет о расходах для пользователя, выбранного на странице **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="9ef5b-183">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="9ef5b-184">Задайте для <xref:System.Windows.Controls.Page.Title%2A> значение "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="9ef5b-185">Задайте для `DesignHeight` значение 350 пикселей, а `DesignWidth` — 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="9ef5b-186">*Файл ExpenseReportPage. XAML* теперь выглядит следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="9ef5b-187">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="9ef5b-188">Откройте *ExpenseItHome. XAML. vb* и *файл ExpenseReportPage. XAML. vb*, а также *ExpenseItHome.XAML.CS* и *ExpenseReportPage.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="9ef5b-189">При создании нового файла подкачки Visual Studio автоматически создает свой файл *кода программной части* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="9ef5b-190">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="9ef5b-191">Код должен выглядеть следующим образом для **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="9ef5b-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="9ef5b-192">И, как и для **файл ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="9ef5b-193">Добавьте в проект образ с именем *водяной знак. png* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="9ef5b-194">Вы можете создать собственный образ, скопировать файл из примера кода или получить его из репозитория GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="9ef5b-195">Щелкните правой кнопкой мыши узел проекта и выберите **добавить** > **существующий элемент**или нажмите **SHIFT**+**ALT**+**A**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="9ef5b-196">В диалоговом окне **Добавление существующего элемента** задайте для фильтра файлов значение **все файлы** или **файлы изображений**, перейдите к файлу изображения, который необходимо использовать, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="9ef5b-197">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="9ef5b-197">Build and run the application</span></span>

1. <span data-ttu-id="9ef5b-198">Чтобы выполнить сборку и запуск приложения, нажмите клавишу **F5** или выберите **начать отладку** в меню **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="9ef5b-199">На следующем рисунке показано приложение с кнопками <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![После сборки и запуска приложения.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="9ef5b-201">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="9ef5b-202">Создание макета</span><span class="sxs-lookup"><span data-stu-id="9ef5b-202">Create the layout</span></span>

<span data-ttu-id="9ef5b-203">Макет предоставляет упорядоченный способ размещения элементов пользовательского интерфейса, а также управляет размером и положением этих элементов при изменении размера пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="9ef5b-204">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="9ef5b-205"><xref:System.Windows.Controls.Canvas> — определяет область, в которой можно явно располагать дочерние элементы с помощью координат, относящихся к области Canvas.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="9ef5b-206"><xref:System.Windows.Controls.DockPanel> — определяет область, в которой можно расположить дочерние элементы по горизонтали или по вертикали относительно друг друга.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="9ef5b-207"><xref:System.Windows.Controls.Grid> — определяет гибкую область сетки, состоящую из столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="9ef5b-208"><xref:System.Windows.Controls.StackPanel> — упорядочивает дочерние элементы в одну строку, которая может быть ориентирована горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="9ef5b-209"><xref:System.Windows.Controls.VirtualizingStackPanel> — упорядочивает и виртуализировать содержимое в одной строке, ориентированной либо горизонтально, либо вертикально.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="9ef5b-210"><xref:System.Windows.Controls.WrapPanel> размещает дочерние элементы в последовательном положении слева направо, разбивая содержимое на следующую строку на границе содержащего поля.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="9ef5b-211">Последующее упорядочение происходит последовательно сверху вниз или справа налево в зависимости от значения свойства Orientation.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="9ef5b-212">Каждый из этих элементов управления макета поддерживает определенный тип макета для своих дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="9ef5b-213">размеры страниц `ExpenseIt` можно изменять, и каждая страница содержит элементы, расположенные горизонтально и вертикально вместе с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="9ef5b-214">В этом примере <xref:System.Windows.Controls.Grid> используется в качестве элемента макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="9ef5b-215">Дополнительные сведения об элементах <xref:System.Windows.Controls.Panel> см. в разделе [Общие сведения о панелях](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="9ef5b-216">Дополнительные сведения о макете см. в разделе [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="9ef5b-217">В этом разделе вы создадите таблицу с одним столбцом с тремя строками и 10-пиксельным полем, добавив определения столбцов и строк в <xref:System.Windows.Controls.Grid> в *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="9ef5b-218">В *`ExpenseItHome.xaml`* задайте для свойства <xref:System.Windows.FrameworkElement.Margin%2A> элемента <xref:System.Windows.Controls.Grid> значение "10, 0, 10, 10", которое соответствует левому, верхнему, правому и нижнему полям:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="9ef5b-219">Можно также задать значения **полей** в окне **свойства** в категории **Макет** :</span><span class="sxs-lookup"><span data-stu-id="9ef5b-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения полей в окно свойств](./media/properties-margin.png)

2. <span data-ttu-id="9ef5b-221">Добавьте следующий код XAML между тегами <xref:System.Windows.Controls.Grid>, чтобы создать определения строк и столбцов:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="9ef5b-222"><xref:System.Windows.Controls.RowDefinition.Height%2A> двух строк имеет значение <xref:System.Windows.GridLength.Auto%2A>. Это означает, что размер строк зависит от содержимого строк.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="9ef5b-223"><xref:System.Windows.Controls.RowDefinition.Height%2A> по умолчанию — <xref:System.Windows.GridUnitType.Star> размер, что означает, что высота строки является взвешенной пропорциями доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="9ef5b-224">Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> "\*", каждая из них имеет высоту, которая является половиной доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="9ef5b-225">Теперь <xref:System.Windows.Controls.Grid> должен содержать следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="9ef5b-226">Добавление элементов управления</span><span class="sxs-lookup"><span data-stu-id="9ef5b-226">Add controls</span></span>

<span data-ttu-id="9ef5b-227">В этом разделе вы обновите пользовательский интерфейс домашней страницы, чтобы отобразить список людей, в которых вы выбрали одного пользователя для отображения отчета о расходах.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="9ef5b-228">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="9ef5b-229">Более подробную информацию см. в разделе [Элементы управления](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="9ef5b-230">Чтобы создать этот пользовательский интерфейс, добавьте в *`ExpenseItHome.xaml`* следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="9ef5b-231"><xref:System.Windows.Controls.ListBox> (для списка пользователей).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="9ef5b-232"><xref:System.Windows.Controls.Label> (для заголовка списка).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="9ef5b-233"><xref:System.Windows.Controls.Button> (щелкните, чтобы просмотреть отчет о расходах для пользователя, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="9ef5b-234">Каждый элемент управления помещается в строку <xref:System.Windows.Controls.Grid> путем установки присоединенного <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="9ef5b-235">Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="9ef5b-236">В *`ExpenseItHome.xaml`* добавьте в теги <xref:System.Windows.Controls.Grid> следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="9ef5b-237">Можно также создать элементы управления, перетащив их из окна **панель элементов** в окно конструктора, а затем задав их свойства в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="9ef5b-238">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-238">Build and run the application.</span></span>

    <span data-ttu-id="9ef5b-239">На следующем рисунке показаны созданные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-239">The following illustration shows the controls you created:</span></span>

![Пример снимка экрана ExpenseIt, отображающий список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="9ef5b-241">Добавление изображения и заголовка</span><span class="sxs-lookup"><span data-stu-id="9ef5b-241">Add an image and a title</span></span>

<span data-ttu-id="9ef5b-242">В этом разделе вы обновите пользовательский интерфейс домашней страницы, используя изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="9ef5b-243">В *`ExpenseItHome.xaml`* добавьте еще один столбец в <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> с фиксированной <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселей:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="9ef5b-244">Добавьте еще одну строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, чтобы всего четыре строки:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="9ef5b-245">Переместите элементы управления во второй столбец, задав для свойства <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> значение 1 в каждом из трех элементов управления (граница, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="9ef5b-246">Переместите каждый элемент управления по строке, увеличив значение <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> на 1 для каждого из трех элементов управления (границы, ListBox и Button) и для элемента Border.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="9ef5b-247">Теперь XAML для трех элементов управления выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="9ef5b-248">Задайте для свойства <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> файл изображения *водяного знака. png* , добавив следующий код XAML в любом месте между тегами `<Grid>` и `</Grid>`:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="9ef5b-249">Перед элементом <xref:System.Windows.Controls.Border> добавьте <xref:System.Windows.Controls.Label> с содержимым "Просмотр отчета о расходах".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="9ef5b-250">Эта метка является заголовком страницы.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="9ef5b-251">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-251">Build and run the application.</span></span>

<span data-ttu-id="9ef5b-252">На следующем рисунке показаны результаты только что добавленных элементов.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-252">The following illustration shows the results of what you just added:</span></span>

![Образец снимка экрана ExpenseIt, показывающий новый фон и заголовок страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="9ef5b-254">Добавление кода для обработчика событий</span><span class="sxs-lookup"><span data-stu-id="9ef5b-254">Add code to handle events</span></span>

1. <span data-ttu-id="9ef5b-255">В *`ExpenseItHome.xaml`* добавьте обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> в элемент <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="9ef5b-256">Дополнительные сведения см. [в разделе инструкции. Создание простого обработчика событий](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="9ef5b-257">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="9ef5b-258">Добавьте следующий код в класс `ExpenseItHome`, чтобы добавить обработчик событий нажатия кнопки.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="9ef5b-259">Обработчик событий открывает страницу **файл ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="9ef5b-260">Создание пользовательского интерфейса для файл ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="9ef5b-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="9ef5b-261">*Файл ExpenseReportPage. XAML* отображает отчет о расходах для пользователя, выбранного на странице **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="9ef5b-262">В этом разделе вы создадите пользовательский интерфейс для **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="9ef5b-263">Вы также добавите цвета фона и заливки в различные элементы пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="9ef5b-264">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="9ef5b-265">Добавьте следующий код XAML между тегами <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="9ef5b-266">Этот пользовательский интерфейс похож на *`ExpenseItHome.xaml`* , за исключением того, что данные отчета отображаются в <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="9ef5b-267">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-267">Build and run the application.</span></span>

4. <span data-ttu-id="9ef5b-268">Нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-268">Select the **View** button.</span></span>

    <span data-ttu-id="9ef5b-269">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-269">The expense report page appears.</span></span> <span data-ttu-id="9ef5b-270">Также обратите внимание, что кнопка обратной навигации включена.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="9ef5b-271">На следующем рисунке показаны элементы пользовательского интерфейса, добавленные в *файл ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Пример снимка экрана ExpenseIt, показывающий пользовательский интерфейс, созданный для файл ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="9ef5b-273">Элементы управления стиля</span><span class="sxs-lookup"><span data-stu-id="9ef5b-273">Style controls</span></span>

<span data-ttu-id="9ef5b-274">Внешний вид различных элементов часто одинаков для всех элементов одного типа в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="9ef5b-275">Пользовательский интерфейс использует [стили](../controls/styling-and-templating.md) для того, чтобы внешний вид можно было использовать в нескольких элементах.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="9ef5b-276">Многократное использование стилей помогает упростить создание XAML и управление им.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="9ef5b-277">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="9ef5b-278">Откройте *Application. XAML* или *app. XAML*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="9ef5b-279">Добавьте следующий код XAML между тегами <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="9ef5b-280">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="9ef5b-281">`headerTextStyle`для форматирования заголовка страницы <xref:System.Windows.Controls.Label>;</span><span class="sxs-lookup"><span data-stu-id="9ef5b-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="9ef5b-282">`labelStyle`для форматирования элементов управления <xref:System.Windows.Controls.Label> ;</span><span class="sxs-lookup"><span data-stu-id="9ef5b-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="9ef5b-283">`columnHeaderStyle`для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>;</span><span class="sxs-lookup"><span data-stu-id="9ef5b-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="9ef5b-284">`listHeaderStyle`для форматирования элементов управления <xref:System.Windows.Controls.Border> заголовков списка;</span><span class="sxs-lookup"><span data-stu-id="9ef5b-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="9ef5b-285">`listHeaderTextStyle`: для форматирования <xref:System.Windows.Controls.Label>заголовка списка.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="9ef5b-286">`buttonStyle`: для форматирования <xref:System.Windows.Controls.Button> на `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="9ef5b-287">Обратите внимание, что стили являются ресурсами и дочерними элементами элемента свойства <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="9ef5b-288">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="9ef5b-289">Пример использования ресурсов в приложении .NET см. в разделе [использование ресурсов приложения](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="9ef5b-290">В *`ExpenseItHome.xaml`* замените все между элементами <xref:System.Windows.Controls.Grid> следующим кодом XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="9ef5b-291">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="9ef5b-292">Например, `headerTextStyle` применяется к <xref:System.Windows.Controls.Label>"Просмотр отчета о расходах".</span><span class="sxs-lookup"><span data-stu-id="9ef5b-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="9ef5b-293">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="9ef5b-294">Замените все элементы <xref:System.Windows.Controls.Grid> элементами следующим кодом XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="9ef5b-295">Этот XAML добавляет стили к элементам <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="9ef5b-296">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-296">Build and run the application.</span></span> <span data-ttu-id="9ef5b-297">Внешний вид окна такой же, как и ранее.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-297">The window appearance is the same as previously.</span></span>

    ![Пример снимка экрана ExpenseIt с тем же видом, что и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="9ef5b-299">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="9ef5b-300">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="9ef5b-300">Bind data to a control</span></span>

<span data-ttu-id="9ef5b-301">В этом разделе вы создадите XML-данные, привязанные к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="9ef5b-302">В *`ExpenseItHome.xaml`* после открытия элемента <xref:System.Windows.Controls.Grid> добавьте следующий код XAML, чтобы создать <xref:System.Windows.Data.XmlDataProvider>, содержащий данные для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="9ef5b-303">Данные создаются в качестве <xref:System.Windows.Controls.Grid> ресурса.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="9ef5b-304">Обычно эти данные загружаются в виде файла, но для простоты данные добавляются встроенным образом.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="9ef5b-305">В элементе `<Grid.Resources>` добавьте следующий элемент `<xref:System.Windows.DataTemplate>`, который определяет способ отображения данных в <xref:System.Windows.Controls.ListBox>после элемента `<XmlDataProvider>`:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="9ef5b-306">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения](../data/data-templating-overview.md)о создании шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="9ef5b-307">Замените существующий <xref:System.Windows.Controls.ListBox> следующим кодом XAML:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="9ef5b-308">Этот XAML привязывает свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> к источнику данных и применяет шаблон данных в качестве <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="9ef5b-309">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="9ef5b-309">Connect data to controls</span></span>

<span data-ttu-id="9ef5b-310">Далее предстоит добавить код для получения имени, выбранного на странице **`ExpenseItHome`** , и передать его конструктору **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="9ef5b-311">**Файл ExpenseReportPage** устанавливает в качестве контекста данных переданный элемент, который является элементом управления, определенным в привязке *файл ExpenseReportPage. XAML* к.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="9ef5b-312">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="9ef5b-313">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="9ef5b-314">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="9ef5b-315">Измените обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, чтобы вызвать новый конструктор, передающий данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="9ef5b-316">Применение стилей к данным с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="9ef5b-316">Style data with data templates</span></span>

<span data-ttu-id="9ef5b-317">В этом разделе вы обновите пользовательский интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="9ef5b-318">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="9ef5b-319">Привяжите содержимое элементов "Name" и "Department" <xref:System.Windows.Controls.Label> к соответствующему свойству источника данных.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="9ef5b-320">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="9ef5b-321">После открытия элемента <xref:System.Windows.Controls.Grid> добавьте следующие шаблоны данных, определяющие способ отображения данных отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="9ef5b-322">Замените элементы <xref:System.Windows.Controls.DataGridTextColumn> <xref:System.Windows.Controls.DataGridTemplateColumn> в элементе <xref:System.Windows.Controls.DataGrid> и примените к ним шаблоны.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="9ef5b-323">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-323">Build and run the application.</span></span>

6. <span data-ttu-id="9ef5b-324">Выберите пользователя и нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="9ef5b-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="9ef5b-325">На следующем рисунке показаны страницы `ExpenseIt`ного приложения с элементами управления, макетом, стилями, привязкой данных и применяемыми шаблонами данных:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![На обеих страницах приложения отображается список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="9ef5b-327">В этом примере демонстрируется конкретная функция WPF, которая не соответствует всем рекомендациям, таким как безопасность, локализация и специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="9ef5b-328">Полный охват WPF и рекомендации по разработке приложений .NET см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="9ef5b-329">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="9ef5b-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="9ef5b-330">Security</span><span class="sxs-lookup"><span data-stu-id="9ef5b-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="9ef5b-331">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="9ef5b-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="9ef5b-332">Производительность WPF</span><span class="sxs-lookup"><span data-stu-id="9ef5b-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="9ef5b-333">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9ef5b-333">Next steps</span></span>

<span data-ttu-id="9ef5b-334">В этом пошаговом руководстве вы узнали о ряде методов создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9ef5b-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="9ef5b-335">Теперь у вас должно быть базовое представление о стандартных блоках приложений .NET с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="9ef5b-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="9ef5b-336">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="9ef5b-337">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="9ef5b-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="9ef5b-338">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9ef5b-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="9ef5b-339">Общие сведения о свойствах зависимостей</span><span class="sxs-lookup"><span data-stu-id="9ef5b-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="9ef5b-340">Макет</span><span class="sxs-lookup"><span data-stu-id="9ef5b-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="9ef5b-341">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="9ef5b-342">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="9ef5b-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="9ef5b-343">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="9ef5b-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="9ef5b-344">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="9ef5b-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9ef5b-345">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9ef5b-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="9ef5b-346">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="9ef5b-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="9ef5b-347">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ef5b-347">See also</span></span>

- [<span data-ttu-id="9ef5b-348">Обзор панелей</span><span class="sxs-lookup"><span data-stu-id="9ef5b-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="9ef5b-349">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="9ef5b-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="9ef5b-350">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="9ef5b-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="9ef5b-351">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="9ef5b-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
