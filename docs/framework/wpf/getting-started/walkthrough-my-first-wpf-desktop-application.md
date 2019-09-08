---
title: Учебник. Создание первого приложения WPF в Visual Studio 2019 — .NET Framework
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: vs-dotnet
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8b7f6f3bdbf3adc7c355e88cfe1f569cc0cb76f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799340"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="d6d9c-102">Учебник. Создание первого приложения WPF в Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="d6d9c-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="d6d9c-103">В этой статье показано, как разработать классическое приложение Windows Presentation Foundation (WPF), включающее элементы, которые являются общими для большинства приложений WPF: Разметка XAML (XAML), код программной части, определения приложений, элементы управления, макет, привязка данных и стили.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="d6d9c-104">Для разработки приложения вы будете использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="d6d9c-105">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="d6d9c-106">Создайте проект WPF.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-106">Create a WPF project.</span></span>
> - <span data-ttu-id="d6d9c-107">Используйте XAML для проектирования внешнего вида пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="d6d9c-108">Напишите код для создания поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="d6d9c-109">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="d6d9c-110">Добавьте элементы управления и создайте макет, чтобы составить пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="d6d9c-111">Создание стилей для согласованного внешнего вида в пользовательском интерфейсе приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="d6d9c-112">Привязка пользовательского интерфейса к данным для заполнения пользовательского интерфейса данными и синхронизации данных и пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="d6d9c-113">По завершении работы с этим руководством вы создадите автономное приложение Windows, которое позволит пользователям просматривать отчеты о расходах для выбранных лиц.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="d6d9c-114">Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="d6d9c-115">Пример кода, используемый в этом руководстве, доступен как для Visual Basic, так и C# в [руководстве по примерам кода приложения WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="d6d9c-116">Язык кода образца кода можно переключать между C# и Visual Basic с помощью селектора языка в верхней части этой страницы.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6d9c-117">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d6d9c-117">Prerequisites</span></span>

- <span data-ttu-id="d6d9c-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой " **Разработка классических приложений .NET** ".</span><span class="sxs-lookup"><span data-stu-id="d6d9c-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="d6d9c-119">Дополнительные сведения об установке последней версии Visual Studio см. в [статье Установка Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="d6d9c-120">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="d6d9c-120">Create the application project</span></span>

<span data-ttu-id="d6d9c-121">Первым шагом является создание инфраструктуры приложения, включающей определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="d6d9c-122">Создайте новый проект приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="d6d9c-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="d6d9c-123">Откройте Visual Studio и выберите **создать новый проект** в меню **Приступая к работе** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="d6d9c-124">Откроется диалоговое окно **Создание нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="d6d9c-125">В раскрывающемся списке **язык** выберите либо **C#** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="d6d9c-126">Выберите шаблон **приложения WPF (.NET Framework)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Диалоговое окно создания нового проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="d6d9c-128">Откроется диалоговое окно **Настройка нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="d6d9c-129">Введите имя **`ExpenseIt`** проекта и нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Диалоговое окно "Настройка нового проекта"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="d6d9c-131">Visual Studio создаст проект и откроет конструктор для окна приложения по умолчанию с именем **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="d6d9c-132">Откройте *Application. XAML* (Visual Basic) или *app. XAML* (C#).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="d6d9c-133">Этот XAML-файл определяет приложение WPF и все ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="d6d9c-134">Этот файл также используется для указания пользовательского интерфейса, в данном случае *MainWindow. XAML*, который автоматически отображается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="d6d9c-135">КОД XAML должен выглядеть следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="d6d9c-136">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="d6d9c-137">Откройте файл *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="d6d9c-138">Этот XAML-файл является главным окном приложения и отображает содержимое, созданное на страницах.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="d6d9c-139"><xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер или значок, а также обрабатывает события, такие как закрытие или скрытие.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="d6d9c-140"><xref:System.Windows.Window> Измените элемент<xref:System.Windows.Navigation.NavigationWindow>на, как показано в следующем коде XAML:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="d6d9c-141">Это приложение переходит к другому содержимому в зависимости от введенных пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="d6d9c-142">Именно поэтому необходимо изменить основное <xref:System.Windows.Window> значение <xref:System.Windows.Navigation.NavigationWindow>на.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="d6d9c-143"><xref:System.Windows.Navigation.NavigationWindow>наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="d6d9c-144">Элемент в файле XAML создает экземпляр <xref:System.Windows.Navigation.NavigationWindow> класса. <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="d6d9c-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="d6d9c-145">Дополнительные сведения см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="d6d9c-146">Удалите элементы из между <xref:System.Windows.Navigation.NavigationWindow>тегами. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="d6d9c-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="d6d9c-147">Измените следующие свойства в коде XAML для <xref:System.Windows.Navigation.NavigationWindow> элемента:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="d6d9c-148">`ExpenseIt`Присвойте <xref:System.Windows.Window.Title%2A> свойству значение "".</span><span class="sxs-lookup"><span data-stu-id="d6d9c-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="d6d9c-149">Задайте для <xref:System.Windows.FrameworkElement.Height%2A> свойства значение 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="d6d9c-150">Задайте для <xref:System.Windows.FrameworkElement.Width%2A> свойства значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="d6d9c-151">КОД XAML должен выглядеть следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="d6d9c-152">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="d6d9c-153">Откройте файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="d6d9c-154">Этот файл является файлом кода программной части, который содержит код для работы с событиями, объявленными в файле *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="d6d9c-155">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="d6d9c-156">Если вы используете C#, измените `MainWindow` класс на производный от <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="d6d9c-157">(В Visual Basic это происходит автоматически при изменении окна в XAML.) Теперь C# ваш код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="d6d9c-158">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="d6d9c-158">Add files to the application</span></span>

<span data-ttu-id="d6d9c-159">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="d6d9c-160">Добавьте в проект новую страницу и назовите ее *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="d6d9c-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="d6d9c-161">В **Обозреватель решений**щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите команду **Добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="d6d9c-162">В диалоговом окне **Добавление нового элемента** шаблон **Page (WPF)** уже выбран.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="d6d9c-163">Введите имя **`ExpenseItHome`** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="d6d9c-164">Эта страница является первой страницей, отображаемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="d6d9c-165">Отобразится список людей для выбора, чтобы отобразить отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="d6d9c-166">Откройте *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="d6d9c-167">Присвойте свойству`ExpenseIt - Home`значение "". <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="d6d9c-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="d6d9c-168">Задайте для `DesignHeight` параметра значение 350 пикселей, `DesignWidth` а для параметра — значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="d6d9c-169">Теперь XAML выглядит следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="d6d9c-170">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="d6d9c-171">Откройте файл *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="d6d9c-172">Добавьте свойство в элемент и задайте для него значение "`ExpenseItHome.xaml`". <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow.Source%2A></span><span class="sxs-lookup"><span data-stu-id="d6d9c-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="d6d9c-173">Этот набор *`ExpenseItHome.xaml`* устанавливается в качестве первой страницы, открытой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="d6d9c-174">Пример XAML в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="d6d9c-175">И в C#:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="d6d9c-176">Также можно задать свойство **Source** в категории **Разное** в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Свойство Source в окно свойств](./media/properties-source.png)

1. <span data-ttu-id="d6d9c-178">Добавьте еще одну новую страницу WPF в проект и назовите ее *файл ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="d6d9c-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="d6d9c-179">В **Обозреватель решений**щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите команду **Добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="d6d9c-180">В диалоговом окне **Добавление нового элемента** выберите шаблон **Page (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="d6d9c-181">Введите имя **файл ExpenseReportPage**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="d6d9c-182">На этой странице отображается отчет о расходах для пользователя, выбранного на **`ExpenseItHome`** странице.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="d6d9c-183">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="d6d9c-184">Присвойте свойству`ExpenseIt - View Expense`значение "". <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="d6d9c-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="d6d9c-185">Задайте для `DesignHeight` параметра значение 350 пикселей, `DesignWidth` а для параметра — значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="d6d9c-186">*Файл ExpenseReportPage. XAML* теперь выглядит следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="d6d9c-187">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="d6d9c-188">Откройте *ExpenseItHome. XAML. vb* и *файл ExpenseReportPage. XAML. vb*, а также *ExpenseItHome.XAML.CS* и *ExpenseReportPage.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="d6d9c-189">При создании нового файла подкачки Visual Studio автоматически создает свой файл *кода программной части* .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="d6d9c-190">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="d6d9c-191">Код должен выглядеть следующим **`ExpenseItHome`** образом:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="d6d9c-192">И, как и для **файл ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="d6d9c-193">Добавьте в проект образ с именем *водяной знак. png* .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="d6d9c-194">Вы можете создать собственный образ, скопировать файл из примера кода или получить его из репозитория GitHub [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="d6d9c-195">Щелкните правой кнопкой мыши узел проекта и выберите команду **Добавить** > **существующий элемент**или нажмите клавиши **SHIFT**+**ALT**+**A**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="d6d9c-196">В диалоговом окне **Добавление существующего элемента** задайте для фильтра файлов значение **все файлы** или **файлы изображений**, перейдите к файлу изображения, который необходимо использовать, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="d6d9c-197">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="d6d9c-197">Build and run the application</span></span>

1. <span data-ttu-id="d6d9c-198">Чтобы выполнить сборку и запуск приложения, нажмите клавишу **F5** или выберите **начать отладку** в меню **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="d6d9c-199">На следующем рисунке показано приложение с <xref:System.Windows.Navigation.NavigationWindow> кнопками:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![После сборки и запуска приложения.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="d6d9c-201">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="d6d9c-202">Создание макета</span><span class="sxs-lookup"><span data-stu-id="d6d9c-202">Create the layout</span></span>

<span data-ttu-id="d6d9c-203">Макет предоставляет упорядоченный способ размещения элементов пользовательского интерфейса, а также управляет размером и положением этих элементов при изменении размера пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="d6d9c-204">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="d6d9c-205"><xref:System.Windows.Controls.Canvas>— Определяет область, в которой можно явно располагать дочерние элементы с помощью координат, относящихся к области Canvas.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="d6d9c-206"><xref:System.Windows.Controls.DockPanel>— Определяет область, в которой можно расположить дочерние элементы по горизонтали или по вертикали относительно друг друга.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="d6d9c-207"><xref:System.Windows.Controls.Grid>— Определяет гибкую область сетки, состоящую из столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="d6d9c-208"><xref:System.Windows.Controls.StackPanel>— Упорядочивает дочерние элементы в одну строку, которая может быть ориентирована горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="d6d9c-209"><xref:System.Windows.Controls.VirtualizingStackPanel>— Упорядочивает и виртуализировать содержимое в одной строке, ориентированной горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="d6d9c-210"><xref:System.Windows.Controls.WrapPanel>— Размещает дочерние элементы в последовательном положении слева направо, разбивая содержимое на следующую строку на границе содержащего поля.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="d6d9c-211">Последующее упорядочение происходит последовательно сверху вниз или справа налево в зависимости от значения свойства Orientation.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="d6d9c-212">Каждый из этих элементов управления макета поддерживает определенный тип макета для своих дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="d6d9c-213">`ExpenseIt`размеры страниц можно изменять, и каждая страница содержит элементы, расположенные горизонтально и вертикально рядом с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="d6d9c-214">В этом примере <xref:System.Windows.Controls.Grid> используется как элемент макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="d6d9c-215">Дополнительные сведения об элементах см. в разделе <xref:System.Windows.Controls.Panel> [Общие сведения о панелях](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="d6d9c-216">Дополнительные сведения о макете см. в разделе [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="d6d9c-217">В этом разделе вы создадите таблицу с одним столбцом с тремя строками и 10-пиксельным полем, добавив определения <xref:System.Windows.Controls.Grid> столбцов и строк в в. *`ExpenseItHome.xaml`*</span><span class="sxs-lookup"><span data-stu-id="d6d9c-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="d6d9c-218">В *`ExpenseItHome.xaml`* Задайтедля<xref:System.Windows.Controls.Grid>свойстваэлемента значение "10, 0, 10, 10", которое соответствует левому, верхнему, правому и нижнему полям: <xref:System.Windows.FrameworkElement.Margin%2A></span><span class="sxs-lookup"><span data-stu-id="d6d9c-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="d6d9c-219">Можно также задать значения **полей** в окне **свойства** в категории **Макет** :</span><span class="sxs-lookup"><span data-stu-id="d6d9c-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения полей в окно свойств](./media/properties-margin.png)

2. <span data-ttu-id="d6d9c-221">Добавьте следующий код XAML между <xref:System.Windows.Controls.Grid> тегами, чтобы создать определения строк и столбцов:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="d6d9c-222">Для двух строк <xref:System.Windows.GridLength.Auto%2A>устанавливается значение, которое означает, что размер строк зависит от содержимого строк. <xref:System.Windows.Controls.RowDefinition.Height%2A></span><span class="sxs-lookup"><span data-stu-id="d6d9c-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="d6d9c-223">По <xref:System.Windows.Controls.RowDefinition.Height%2A> умолчанию <xref:System.Windows.GridUnitType.Star> используется размер, что означает, что высота строки является взвешенной пропорциями доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="d6d9c-224">Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> "\*", каждая из них имеет высоту, равную половине доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="d6d9c-225">Теперь <xref:System.Windows.Controls.Grid> должен содержаться следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="d6d9c-226">Добавить элементы управления</span><span class="sxs-lookup"><span data-stu-id="d6d9c-226">Add controls</span></span>

<span data-ttu-id="d6d9c-227">В этом разделе вы обновите пользовательский интерфейс домашней страницы, чтобы отобразить список людей, в которых вы выбрали одного пользователя для отображения отчета о расходах.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="d6d9c-228">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="d6d9c-229">Более подробную информацию см. в разделе [Элементы управления](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="d6d9c-230">Чтобы создать этот пользовательский интерфейс, добавьте следующие элементы в *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="d6d9c-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="d6d9c-231">A <xref:System.Windows.Controls.ListBox> (для списка пользователей).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="d6d9c-232">A <xref:System.Windows.Controls.Label> (для заголовка списка).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="d6d9c-233">A <xref:System.Windows.Controls.Button> (щелкните, чтобы просмотреть отчет о расходах для пользователя, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="d6d9c-234">Каждый элемент управления помещается в строку объекта <xref:System.Windows.Controls.Grid> путем <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> установки присоединенного свойства.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="d6d9c-235">Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения о вложенных свойствах](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="d6d9c-236">В *`ExpenseItHome.xaml`* добавьте в <xref:System.Windows.Controls.Grid> тег следующий код XAML между тегами:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="d6d9c-237">Можно также создать элементы управления, перетащив их из окна **панель элементов** в окно конструктора, а затем задав их свойства в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="d6d9c-238">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-238">Build and run the application.</span></span>

    <span data-ttu-id="d6d9c-239">На следующем рисунке показаны созданные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-239">The following illustration shows the controls you created:</span></span>

![Пример снимка экрана ExpenseIt, отображающий список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="d6d9c-241">Добавление изображения и заголовка</span><span class="sxs-lookup"><span data-stu-id="d6d9c-241">Add an image and a title</span></span>

<span data-ttu-id="d6d9c-242">В этом разделе вы обновите пользовательский интерфейс домашней страницы, используя изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="d6d9c-243">В *`ExpenseItHome.xaml`* добавьте еще один столбец <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> в с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселов:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="d6d9c-244">Добавьте еще одну строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, чтобы всего четыре строки:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="d6d9c-245">Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойству значение 1 в каждом из трех элементов управления (граница, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="d6d9c-246">Переместите каждый элемент управления по строке, увеличив его <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> значение на 1 для каждого из трех элементов управления (границы, ListBox и Button) и для элемента Border.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="d6d9c-247">Теперь XAML для трех элементов управления выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="d6d9c-248">Задайте для `<Grid>` `</Grid>` свойства файл изображения *водяного знака. png* , добавив следующий код XAML в любом месте между тегами и: <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d6d9c-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="d6d9c-249"><xref:System.Windows.Controls.Border> Перед элементом<xref:System.Windows.Controls.Label> добавьте с содержимым "Просмотр отчета о расходах".</span><span class="sxs-lookup"><span data-stu-id="d6d9c-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="d6d9c-250">Эта метка является заголовком страницы.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="d6d9c-251">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-251">Build and run the application.</span></span>

<span data-ttu-id="d6d9c-252">На следующем рисунке показаны результаты только что добавленных элементов.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-252">The following illustration shows the results of what you just added:</span></span>

![Образец снимка экрана ExpenseIt, показывающий новый фон и заголовок страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="d6d9c-254">Добавление кода для обработчика событий</span><span class="sxs-lookup"><span data-stu-id="d6d9c-254">Add code to handle events</span></span>

1. <span data-ttu-id="d6d9c-255">В *`ExpenseItHome.xaml`* добавьтек<xref:System.Windows.Controls.Button> элементу обработчик событий.<xref:System.Windows.Controls.Primitives.ButtonBase.Click></span><span class="sxs-lookup"><span data-stu-id="d6d9c-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="d6d9c-256">Дополнительные сведения см. в разделе [Практическое руководство. Создайте простой обработчик](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))событий.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="d6d9c-257">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="d6d9c-258">Добавьте следующий код в `ExpenseItHome` класс, чтобы добавить обработчик событий нажатия кнопки.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="d6d9c-259">Обработчик событий открывает страницу **файл ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="d6d9c-260">Создание пользовательского интерфейса для файл ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="d6d9c-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="d6d9c-261">*Файл ExpenseReportPage. XAML* отображает отчет о расходах для пользователя, выбранного на **`ExpenseItHome`** странице.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="d6d9c-262">В этом разделе вы создадите пользовательский интерфейс для **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="d6d9c-263">Вы также добавите цвета фона и заливки в различные элементы пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="d6d9c-264">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="d6d9c-265">Добавьте следующий код XAML между <xref:System.Windows.Controls.Grid> тегами:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="d6d9c-266">Этот пользовательский интерфейс аналогичен *`ExpenseItHome.xaml`* , за исключением того, что данные отчета <xref:System.Windows.Controls.DataGrid>отображаются в.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="d6d9c-267">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-267">Build and run the application.</span></span>

4. <span data-ttu-id="d6d9c-268">Нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-268">Select the **View** button.</span></span>

    <span data-ttu-id="d6d9c-269">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-269">The expense report page appears.</span></span> <span data-ttu-id="d6d9c-270">Также обратите внимание, что кнопка обратной навигации включена.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="d6d9c-271">На следующем рисунке показаны элементы пользовательского интерфейса, добавленные в *файл ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Пример снимка экрана ExpenseIt, показывающий пользовательский интерфейс, созданный для файл ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="d6d9c-273">Элементы управления стиля</span><span class="sxs-lookup"><span data-stu-id="d6d9c-273">Style controls</span></span>

<span data-ttu-id="d6d9c-274">Внешний вид различных элементов часто одинаков для всех элементов одного типа в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="d6d9c-275">Пользовательский интерфейс использует [стили](../controls/styling-and-templating.md) для того, чтобы внешний вид можно было использовать в нескольких элементах.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="d6d9c-276">Многократное использование стилей помогает упростить создание XAML и управление им.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="d6d9c-277">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="d6d9c-278">Откройте *Application. XAML* или *app. XAML*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="d6d9c-279">Добавьте следующий код XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> тегами:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="d6d9c-280">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="d6d9c-281">`headerTextStyle`: Для форматирования заголовка <xref:System.Windows.Controls.Label>страницы.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="d6d9c-282">`labelStyle`: Для форматирования <xref:System.Windows.Controls.Label> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="d6d9c-283">`columnHeaderStyle`: Для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="d6d9c-284">`listHeaderStyle`: Для форматирования элементов управления " <xref:System.Windows.Controls.Border> заголовок списка".</span><span class="sxs-lookup"><span data-stu-id="d6d9c-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="d6d9c-285">`listHeaderTextStyle`: Для форматирования заголовка <xref:System.Windows.Controls.Label>списка.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="d6d9c-286">`buttonStyle`: Для форматирования <xref:System.Windows.Controls.Button>. `ExpenseItHome.xaml`</span><span class="sxs-lookup"><span data-stu-id="d6d9c-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="d6d9c-287">Обратите внимание, что стили являются ресурсами и дочерними элементами <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемента Property.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="d6d9c-288">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="d6d9c-289">Пример использования ресурсов в приложении .NET см. в разделе [использование ресурсов приложения](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="d6d9c-290">В *`ExpenseItHome.xaml`* замените все <xref:System.Windows.Controls.Grid> между элементами следующим кодом XAML:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="d6d9c-291">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="d6d9c-292">Например, `headerTextStyle` применяется к «Просмотр отчета о расходах» <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="d6d9c-293">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="d6d9c-294">Замените все <xref:System.Windows.Controls.Grid> элементы на следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="d6d9c-295">Этот XAML добавляет стили в <xref:System.Windows.Controls.Label> элементы и. <xref:System.Windows.Controls.Border></span><span class="sxs-lookup"><span data-stu-id="d6d9c-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="d6d9c-296">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-296">Build and run the application.</span></span> <span data-ttu-id="d6d9c-297">Внешний вид окна такой же, как и ранее.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-297">The window appearance is the same as previously.</span></span>

    ![Пример снимка экрана ExpenseIt с тем же видом, что и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="d6d9c-299">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="d6d9c-300">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="d6d9c-300">Bind data to a control</span></span>

<span data-ttu-id="d6d9c-301">В этом разделе вы создадите XML-данные, привязанные к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="d6d9c-302">В *`ExpenseItHome.xaml`* после открывающего <xref:System.Windows.Controls.Grid> элемента добавьте следующий код XAML, чтобы создать объект <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="d6d9c-303">Данные создаются в виде <xref:System.Windows.Controls.Grid> ресурса.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="d6d9c-304">Обычно эти данные загружаются в виде файла, но для простоты данные добавляются встроенным образом.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="d6d9c-305">В элементе добавьте следующий `<xref:System.Windows.DataTemplate>` элемент, определяющий способ <xref:System.Windows.Controls.ListBox>отображения данных `<XmlDataProvider>` в, после элемента: `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="d6d9c-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="d6d9c-306">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения](../data/data-templating-overview.md)о создании шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="d6d9c-307">Замените существующий <xref:System.Windows.Controls.ListBox> код XAML следующим:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="d6d9c-308">Этот XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> объекта к источнику данных и применяет шаблон данных в качестве <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="d6d9c-309">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="d6d9c-309">Connect data to controls</span></span>

<span data-ttu-id="d6d9c-310">Далее предстоит добавить код для получения имени, выбранного на **`ExpenseItHome`** странице, и передачи его конструктору **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="d6d9c-311">**Файл ExpenseReportPage** устанавливает в качестве контекста данных переданный элемент, который является элементом управления, определенным в привязке *файл ExpenseReportPage. XAML* к.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="d6d9c-312">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="d6d9c-313">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="d6d9c-314">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="d6d9c-315">Измените обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий, чтобы вызвать новый конструктор, передающий данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="d6d9c-316">Применение стилей к данным с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="d6d9c-316">Style data with data templates</span></span>

<span data-ttu-id="d6d9c-317">В этом разделе вы обновите пользовательский интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="d6d9c-318">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="d6d9c-319">Привяжите содержимое элементов "Name" и "Department" <xref:System.Windows.Controls.Label> к соответствующему свойству источника данных.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="d6d9c-320">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-320">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="d6d9c-321">После открывающего <xref:System.Windows.Controls.Grid> элемента добавьте следующие шаблоны данных, определяющие способ отображения данных отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="d6d9c-322"><xref:System.Windows.Controls.DataGridTextColumn> Замените элементыэлементом<xref:System.Windows.Controls.DataGrid>вэлементе и примените к ним шаблоны. <xref:System.Windows.Controls.DataGridTemplateColumn></span><span class="sxs-lookup"><span data-stu-id="d6d9c-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="d6d9c-323">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-323">Build and run the application.</span></span>

6. <span data-ttu-id="d6d9c-324">Выберите пользователя и нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="d6d9c-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="d6d9c-325">На следующем рисунке показаны обе страницы `ExpenseIt` приложения с примененными элементами управления, макет, стили, привязка данных и шаблоны данных:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![На обеих страницах приложения отображается список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="d6d9c-327">В этом примере демонстрируется конкретная функция WPF, которая не соответствует всем рекомендациям, таким как безопасность, локализация и специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="d6d9c-328">Полный охват WPF и рекомендации по разработке приложений .NET см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="d6d9c-329">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="d6d9c-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="d6d9c-330">Безопасность</span><span class="sxs-lookup"><span data-stu-id="d6d9c-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="d6d9c-331">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="d6d9c-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="d6d9c-332">Производительность WPF</span><span class="sxs-lookup"><span data-stu-id="d6d9c-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="d6d9c-333">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d6d9c-333">Next steps</span></span>

<span data-ttu-id="d6d9c-334">В этом пошаговом руководстве вы узнали о ряде методов создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d6d9c-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="d6d9c-335">Теперь у вас должно быть базовое представление о стандартных блоках приложений .NET с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="d6d9c-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="d6d9c-336">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="d6d9c-337">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="d6d9c-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="d6d9c-338">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d6d9c-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="d6d9c-339">Общие сведения о свойствах зависимостей</span><span class="sxs-lookup"><span data-stu-id="d6d9c-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="d6d9c-340">Макет</span><span class="sxs-lookup"><span data-stu-id="d6d9c-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="d6d9c-341">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d6d9c-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="d6d9c-342">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="d6d9c-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="d6d9c-343">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="d6d9c-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="d6d9c-344">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="d6d9c-344">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="d6d9c-345">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d6d9c-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="d6d9c-346">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="d6d9c-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="d6d9c-347">См. также</span><span class="sxs-lookup"><span data-stu-id="d6d9c-347">See also</span></span>

- [<span data-ttu-id="d6d9c-348">Обзор панелей</span><span class="sxs-lookup"><span data-stu-id="d6d9c-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="d6d9c-349">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="d6d9c-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="d6d9c-350">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="d6d9c-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="d6d9c-351">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="d6d9c-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
