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
ms.openlocfilehash: 9d5b5b8a479efd3918dc23616aa331cc07a901ac
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972120"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="1f880-102">Пошаговое руководство. Создание классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="1f880-103">В этой статье показано, как разработать классическое приложение Windows Presentation Foundation (WPF), включающее элементы, которые являются общими для большинства приложений WPF: Разметка XAML (XAML), код программной части, определения приложений, элементы управления, макет, привязка данных и стили.</span><span class="sxs-lookup"><span data-stu-id="1f880-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="1f880-104">Для разработки приложения вы будете использовать Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f880-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="1f880-105">Это пошаговое руководство включает следующие шаги:</span><span class="sxs-lookup"><span data-stu-id="1f880-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="1f880-106">Используйте XAML для проектирования внешнего вида пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="1f880-107">Напишите код для создания поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="1f880-108">Создайте определение приложения для управления приложением.</span><span class="sxs-lookup"><span data-stu-id="1f880-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="1f880-109">Добавьте элементы управления и создайте макет, чтобы составить пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="1f880-110">Создание стилей для согласованного внешнего вида в пользовательском интерфейсе приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="1f880-111">Привязка пользовательского интерфейса к данным для заполнения пользовательского интерфейса данными и синхронизации данных и пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1f880-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="1f880-112">По завершении работы с пошаговым руководством вы создадите автономное приложение Windows, позволяющее пользователям просматривать отчеты о расходах для выбранных лиц.</span><span class="sxs-lookup"><span data-stu-id="1f880-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="1f880-113">Приложение состоит из нескольких страниц WPF, размещенных в окне в стиле браузера.</span><span class="sxs-lookup"><span data-stu-id="1f880-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="1f880-114">Пример кода, который используется для построения этого пошагового руководства, доступен как для C# Visual Basic, так и в пошаговом [руководстве по примерам кода приложения WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="1f880-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="1f880-115">Язык кода образца кода можно переключать между C# и Visual Basic с помощью **\< />** раскрывающегося списка в правой верхней части этой статьи.</span><span class="sxs-lookup"><span data-stu-id="1f880-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1f880-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1f880-116">Prerequisites</span></span>

- <span data-ttu-id="1f880-117">Visual Studio 2017 или более поздней версии (в этой статье используется Visual Studio 2019)</span><span class="sxs-lookup"><span data-stu-id="1f880-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="1f880-118">Дополнительные сведения об установке последней версии Visual Studio см. в [статье Установка Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1f880-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="1f880-119">Создание проекта приложения</span><span class="sxs-lookup"><span data-stu-id="1f880-119">Create the application project</span></span>

<span data-ttu-id="1f880-120">Первым шагом является создание инфраструктуры приложения, включающей определение приложения, две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="1f880-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="1f880-121">Создайте новый проект приложения WPF в Visual Basic или Visual C# с именем **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="1f880-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="1f880-122">Откройте Visual Studio и выберите **создать новый проект** в меню Приступая к **работе** .</span><span class="sxs-lookup"><span data-stu-id="1f880-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="1f880-123">Откроется диалоговое окно **Создание нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="1f880-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="1f880-124">В раскрывающемся списке **язык** выберите либо **C#** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="1f880-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="1f880-125">Выберите шаблон **приложения WPF (.NET Framework)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="1f880-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Диалоговое окно создания нового проекта](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="1f880-127">Откроется диалоговое окно **Настройка нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="1f880-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="1f880-128">Введите имя **`ExpenseIt`** проекта и нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="1f880-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Диалоговое окно "Настройка нового проекта"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="1f880-130">Visual Studio создаст проект и откроет конструктор для окна приложения по умолчанию с именем **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="1f880-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="1f880-131">Откройте *Application. XAML* (Visual Basic) или *app. XAML* (C#).</span><span class="sxs-lookup"><span data-stu-id="1f880-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="1f880-132">Этот XAML-файл определяет приложение WPF и все ресурсы приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="1f880-133">Этот файл также используется для указания пользовательского интерфейса, в данном случае *MainWindow. XAML*, который автоматически отображается при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="1f880-134">КОД XAML должен выглядеть следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1f880-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="1f880-135">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="1f880-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="1f880-136">Откройте файл *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="1f880-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="1f880-137">Этот XAML-файл является главным окном приложения и отображает содержимое, созданное на страницах.</span><span class="sxs-lookup"><span data-stu-id="1f880-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="1f880-138"><xref:System.Windows.Window> Класс определяет свойства окна, такие как заголовок, размер или значок, а также обрабатывает события, такие как закрытие или скрытие.</span><span class="sxs-lookup"><span data-stu-id="1f880-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="1f880-139"><xref:System.Windows.Window> Измените элемент<xref:System.Windows.Navigation.NavigationWindow>на, как показано в следующем коде XAML:</span><span class="sxs-lookup"><span data-stu-id="1f880-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="1f880-140">Это приложение переходит к другому содержимому в зависимости от введенных пользователем данных.</span><span class="sxs-lookup"><span data-stu-id="1f880-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="1f880-141">Именно поэтому необходимо изменить основное <xref:System.Windows.Window> значение <xref:System.Windows.Navigation.NavigationWindow>на.</span><span class="sxs-lookup"><span data-stu-id="1f880-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1f880-142"><xref:System.Windows.Navigation.NavigationWindow>наследует все свойства <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="1f880-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1f880-143">Элемент в файле XAML создает экземпляр <xref:System.Windows.Navigation.NavigationWindow> класса. <xref:System.Windows.Navigation.NavigationWindow></span><span class="sxs-lookup"><span data-stu-id="1f880-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="1f880-144">Дополнительные сведения см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f880-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="1f880-145">Удалите элементы из между <xref:System.Windows.Navigation.NavigationWindow>тегами. <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="1f880-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="1f880-146">Измените следующие свойства в коде XAML для <xref:System.Windows.Navigation.NavigationWindow> элемента:</span><span class="sxs-lookup"><span data-stu-id="1f880-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="1f880-147">`ExpenseIt`Присвойте <xref:System.Windows.Window.Title%2A> свойству значение "".</span><span class="sxs-lookup"><span data-stu-id="1f880-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="1f880-148">Задайте для <xref:System.Windows.FrameworkElement.Height%2A> свойства значение 350 пикселей.</span><span class="sxs-lookup"><span data-stu-id="1f880-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="1f880-149">Задайте для <xref:System.Windows.FrameworkElement.Width%2A> свойства значение 500 пикселей.</span><span class="sxs-lookup"><span data-stu-id="1f880-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="1f880-150">КОД XAML должен выглядеть следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1f880-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="1f880-151">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="1f880-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="1f880-152">Откройте файл *MainWindow. XAML. vb* или *MainWindow.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="1f880-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="1f880-153">Этот файл является файлом кода программной части, который содержит код для работы с событиями, объявленными в файле *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="1f880-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="1f880-154">Этот файл содержит разделяемый класс для окна, определенного в XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="1f880-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="1f880-155">Если вы используете C#, измените `MainWindow` класс на производный от <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="1f880-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1f880-156">(В Visual Basic это происходит автоматически при изменении окна в XAML.) Теперь C# ваш код должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f880-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="1f880-157">Добавление файлов в приложение</span><span class="sxs-lookup"><span data-stu-id="1f880-157">Add files to the application</span></span>

<span data-ttu-id="1f880-158">В этом разделе вы добавите в приложение две страницы и изображение.</span><span class="sxs-lookup"><span data-stu-id="1f880-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="1f880-159">Добавьте в проект новую страницу и назовите ее *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="1f880-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="1f880-160">В **Обозреватель решений**щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите команду **Добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="1f880-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1f880-161">В диалоговом окне **Добавление нового элемента** шаблон **Page (WPF)** уже выбран.</span><span class="sxs-lookup"><span data-stu-id="1f880-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="1f880-162">Введите имя **`ExpenseItHome`** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="1f880-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="1f880-163">Эта страница является первой страницей, отображаемой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="1f880-164">Отобразится список людей для выбора, чтобы отобразить отчет о расходах для.</span><span class="sxs-lookup"><span data-stu-id="1f880-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="1f880-165">Откройте *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="1f880-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1f880-166">Присвойте свойству`ExpenseIt - Home`значение "". <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="1f880-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="1f880-167">Установите значения элементов `DesignWidth`иравными 300 пикселам. `DesignHeight`</span><span class="sxs-lookup"><span data-stu-id="1f880-167">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="1f880-168">Теперь XAML выглядит следующим образом для Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1f880-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="1f880-169">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="1f880-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="1f880-170">Откройте файл *MainWindow. XAML*.</span><span class="sxs-lookup"><span data-stu-id="1f880-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="1f880-171">Добавьте свойство в элемент и задайте для него значение "`ExpenseItHome.xaml`". <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow.Source%2A></span><span class="sxs-lookup"><span data-stu-id="1f880-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="1f880-172">Этот набор *`ExpenseItHome.xaml`* устанавливается в качестве первой страницы, открытой при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="1f880-173">Пример XAML в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1f880-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="1f880-174">И в C#:</span><span class="sxs-lookup"><span data-stu-id="1f880-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="1f880-175">Также можно задать свойство **Source** в категории Разное в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="1f880-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Свойство Source в окно свойств](./media/properties-source.png)

1. <span data-ttu-id="1f880-177">Добавьте еще одну новую страницу WPF в проект и назовите ее *файл ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="1f880-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="1f880-178">В **Обозреватель решений**щелкните правой кнопкой мыши **`ExpenseIt`** узел проекта и выберите команду **Добавить** > **страницу**.</span><span class="sxs-lookup"><span data-stu-id="1f880-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1f880-179">В диалоговом окне **Добавление нового элемента** выберите шаблон **Page (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="1f880-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="1f880-180">Введите имя **файл ExpenseReportPage**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1f880-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="1f880-181">На этой странице отображается отчет о расходах для пользователя, выбранного на **`ExpenseItHome`** странице.</span><span class="sxs-lookup"><span data-stu-id="1f880-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="1f880-182">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1f880-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="1f880-183">Присвойте свойству`ExpenseIt - View Expense`значение "". <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="1f880-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="1f880-184">Установите значения элементов `DesignWidth`иравными 300 пикселам. `DesignHeight`</span><span class="sxs-lookup"><span data-stu-id="1f880-184">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="1f880-185">*Файл ExpenseReportPage. XAML* теперь выглядит следующим образом в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1f880-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="1f880-186">И следующим образом C#:</span><span class="sxs-lookup"><span data-stu-id="1f880-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="1f880-187">Откройте *ExpenseItHome. XAML. vb* и *файл ExpenseReportPage. XAML. vb*, а также *ExpenseItHome.XAML.CS* и *ExpenseReportPage.XAML.CS*.</span><span class="sxs-lookup"><span data-stu-id="1f880-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="1f880-188">При создании нового файла подкачки Visual Studio автоматически создает свой файл *кода программной части* .</span><span class="sxs-lookup"><span data-stu-id="1f880-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="1f880-189">Эти файлы кода программной части обрабатывают логику, реагирующую на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="1f880-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="1f880-190">Код должен выглядеть следующим **`ExpenseItHome`** образом:</span><span class="sxs-lookup"><span data-stu-id="1f880-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="1f880-191">И, как и для **файл ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="1f880-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="1f880-192">Добавьте в проект образ с именем *водяной знак. png* .</span><span class="sxs-lookup"><span data-stu-id="1f880-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="1f880-193">Можно создать собственный образ, скопировать файл из образца кода или получить его [здесь](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png).</span><span class="sxs-lookup"><span data-stu-id="1f880-193">You can create your own image, copy the file from the sample code, or get it [here](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png).</span></span>

    1. <span data-ttu-id="1f880-194">Щелкните правой кнопкой мыши узел проекта и выберите команду **Добавить** > **существующий элемент**или нажмите клавиши **SHIFT**+**ALT**+**A**.</span><span class="sxs-lookup"><span data-stu-id="1f880-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="1f880-195">В диалоговом окне **Добавление существующего элемента** задайте для фильтра файлов значение **все файлы** или **файлы изображений**, перейдите к файлу изображения, который необходимо использовать, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="1f880-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="1f880-196">Построение и запуск приложения</span><span class="sxs-lookup"><span data-stu-id="1f880-196">Build and run the application</span></span>

1. <span data-ttu-id="1f880-197">Чтобы выполнить сборку и запуск приложения, нажмите клавишу **F5** или выберите **начать отладку** в меню **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="1f880-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="1f880-198">На следующем рисунке показано приложение с <xref:System.Windows.Navigation.NavigationWindow> кнопками:</span><span class="sxs-lookup"><span data-stu-id="1f880-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![После сборки и запуска приложения.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="1f880-200">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f880-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="1f880-201">Создание макета</span><span class="sxs-lookup"><span data-stu-id="1f880-201">Create the layout</span></span>

<span data-ttu-id="1f880-202">Макет предоставляет упорядоченный способ размещения элементов пользовательского интерфейса, а также управляет размером и положением этих элементов при изменении размера пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1f880-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="1f880-203">Обычно макет создается с одним из следующих элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="1f880-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="1f880-204"><xref:System.Windows.Controls.Canvas>— Определяет область, в которой можно явно располагать дочерние элементы с помощью координат, относящихся к области Canvas.</span><span class="sxs-lookup"><span data-stu-id="1f880-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="1f880-205"><xref:System.Windows.Controls.DockPanel>— Определяет область, в которой можно расположить дочерние элементы по горизонтали или по вертикали относительно друг друга.</span><span class="sxs-lookup"><span data-stu-id="1f880-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="1f880-206"><xref:System.Windows.Controls.Grid>— Определяет гибкую область сетки, состоящую из столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="1f880-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="1f880-207"><xref:System.Windows.Controls.StackPanel>— Упорядочивает дочерние элементы в одну строку, которая может быть ориентирована горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="1f880-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="1f880-208"><xref:System.Windows.Controls.VirtualizingStackPanel>— Упорядочивает и виртуализировать содержимое в одной строке, ориентированной горизонтально или вертикально.</span><span class="sxs-lookup"><span data-stu-id="1f880-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="1f880-209"><xref:System.Windows.Controls.WrapPanel>— Размещает дочерние элементы в последовательном положении слева направо, разбивая содержимое на следующую строку на границе содержащего поля.</span><span class="sxs-lookup"><span data-stu-id="1f880-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="1f880-210">Последующее упорядочение происходит последовательно сверху вниз или справа налево в зависимости от значения свойства Orientation.</span><span class="sxs-lookup"><span data-stu-id="1f880-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="1f880-211">Каждый из этих элементов управления макета поддерживает определенный тип макета для своих дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="1f880-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="1f880-212">`ExpenseIt`размеры страниц можно изменять, и каждая страница содержит элементы, расположенные горизонтально и вертикально рядом с другими элементами.</span><span class="sxs-lookup"><span data-stu-id="1f880-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="1f880-213">В этом примере <xref:System.Windows.Controls.Grid> используется как элемент макета для приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="1f880-214">Дополнительные сведения об элементах см. в разделе <xref:System.Windows.Controls.Panel> [Общие сведения](../controls/panels-overview.md)о панелях.</span><span class="sxs-lookup"><span data-stu-id="1f880-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="1f880-215">Дополнительные сведения о макете см. в разделе [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="1f880-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="1f880-216">В этом разделе вы создадите таблицу с одним столбцом с тремя строками и 10-пиксельным полем, добавив определения <xref:System.Windows.Controls.Grid> столбцов и строк в в. *`ExpenseItHome.xaml`*</span><span class="sxs-lookup"><span data-stu-id="1f880-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1f880-217">В *`ExpenseItHome.xaml`* Задайтедля<xref:System.Windows.Controls.Grid>свойстваэлемента значение "10, 0, 10, 10", которое соответствует левому, верхнему, правому и нижнему полям: <xref:System.Windows.FrameworkElement.Margin%2A></span><span class="sxs-lookup"><span data-stu-id="1f880-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="1f880-218">Можно также задать значения **полей** в окне **свойства** в категории **Макет** :</span><span class="sxs-lookup"><span data-stu-id="1f880-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Значения полей в окно свойств](./media/properties-margin.png)

2. <span data-ttu-id="1f880-220">Добавьте следующий код XAML между <xref:System.Windows.Controls.Grid> тегами, чтобы создать определения строк и столбцов:</span><span class="sxs-lookup"><span data-stu-id="1f880-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="1f880-221">Для двух строк <xref:System.Windows.GridLength.Auto%2A>устанавливается значение, которое означает, что размер строк зависит от содержимого строк. <xref:System.Windows.Controls.RowDefinition.Height%2A></span><span class="sxs-lookup"><span data-stu-id="1f880-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="1f880-222">По <xref:System.Windows.Controls.RowDefinition.Height%2A> умолчанию <xref:System.Windows.GridUnitType.Star> используется размер, что означает, что высота строки является взвешенной пропорциями доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="1f880-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="1f880-223">Например, если две строки имеют <xref:System.Windows.Controls.RowDefinition.Height%2A> "\*", каждая из них имеет высоту, равную половине доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="1f880-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="1f880-224">Теперь <xref:System.Windows.Controls.Grid> должен содержаться следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="1f880-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="1f880-225">Добавить элементы управления</span><span class="sxs-lookup"><span data-stu-id="1f880-225">Add controls</span></span>

<span data-ttu-id="1f880-226">В этом разделе вы обновите пользовательский интерфейс домашней страницы, чтобы отобразить список людей, в которых вы выбрали одного пользователя для отображения отчета о расходах.</span><span class="sxs-lookup"><span data-stu-id="1f880-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="1f880-227">Элементы управления — это объекты пользовательского интерфейса, позволяющие пользователям взаимодействовать с приложением.</span><span class="sxs-lookup"><span data-stu-id="1f880-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="1f880-228">Более подробную информацию см. в разделе [Элементы управления](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f880-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="1f880-229">Чтобы создать этот пользовательский интерфейс, добавьте следующие элементы в *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="1f880-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="1f880-230">A <xref:System.Windows.Controls.ListBox> (для списка пользователей).</span><span class="sxs-lookup"><span data-stu-id="1f880-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="1f880-231">A <xref:System.Windows.Controls.Label> (для заголовка списка).</span><span class="sxs-lookup"><span data-stu-id="1f880-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="1f880-232">A <xref:System.Windows.Controls.Button> (щелкните, чтобы просмотреть отчет о расходах для пользователя, выбранного в списке).</span><span class="sxs-lookup"><span data-stu-id="1f880-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="1f880-233">Каждый элемент управления помещается в строку объекта <xref:System.Windows.Controls.Grid> путем <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> установки присоединенного свойства.</span><span class="sxs-lookup"><span data-stu-id="1f880-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="1f880-234">Дополнительные сведения о вложенных свойствах см. в разделе [Общие сведения](../advanced/attached-properties-overview.md)о вложенных свойствах.</span><span class="sxs-lookup"><span data-stu-id="1f880-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="1f880-235">В *`ExpenseItHome.xaml`* добавьте в <xref:System.Windows.Controls.Grid> тег следующий код XAML между тегами:</span><span class="sxs-lookup"><span data-stu-id="1f880-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="1f880-236">Можно также создать элементы управления, перетащив их из окна **панель элементов** в окно конструктора, а затем задав их свойства в окне **свойства** .</span><span class="sxs-lookup"><span data-stu-id="1f880-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="1f880-237">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-237">Build and run the application.</span></span>

    <span data-ttu-id="1f880-238">На следующем рисунке показаны созданные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="1f880-238">The following illustration shows the controls you created:</span></span>

![Пример снимка экрана ExpenseIt, отображающий список имен](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="1f880-240">Добавление изображения и заголовка</span><span class="sxs-lookup"><span data-stu-id="1f880-240">Add an image and a title</span></span>

<span data-ttu-id="1f880-241">В этом разделе вы обновите пользовательский интерфейс домашней страницы, используя изображение и заголовок страницы.</span><span class="sxs-lookup"><span data-stu-id="1f880-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="1f880-242">В *`ExpenseItHome.xaml`* добавьте еще один столбец <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> в с фиксированным <xref:System.Windows.Controls.ColumnDefinition.Width%2A> 230 пикселов:</span><span class="sxs-lookup"><span data-stu-id="1f880-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="1f880-243">Добавьте еще одну строку в <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, чтобы всего четыре строки:</span><span class="sxs-lookup"><span data-stu-id="1f880-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="1f880-244">Переместите элементы управления во второй столбец, задав <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> свойству значение 1 в каждом из трех элементов управления (граница, ListBox и кнопка).</span><span class="sxs-lookup"><span data-stu-id="1f880-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="1f880-245">Переместите каждый элемент управления по строке, увеличив его <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> значение на 1 для каждого из трех элементов управления (границы, ListBox и Button) и для элемента Border.</span><span class="sxs-lookup"><span data-stu-id="1f880-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="1f880-246">Теперь XAML для трех элементов управления выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f880-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="1f880-247">Задайте для `<Grid>` `</Grid>` свойства файл изображения *водяного знака. png* , добавив следующий код XAML в любом месте между тегами и: <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1f880-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="1f880-248"><xref:System.Windows.Controls.Border> Перед элементом<xref:System.Windows.Controls.Label> добавьте с содержимым "Просмотр отчета о расходах".</span><span class="sxs-lookup"><span data-stu-id="1f880-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="1f880-249">Эта метка является заголовком страницы.</span><span class="sxs-lookup"><span data-stu-id="1f880-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="1f880-250">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-250">Build and run the application.</span></span>

<span data-ttu-id="1f880-251">На следующем рисунке показаны результаты только что добавленных элементов.</span><span class="sxs-lookup"><span data-stu-id="1f880-251">The following illustration shows the results of what you just added:</span></span>

![Образец снимка экрана ExpenseIt, показывающий новый фон и заголовок страницы](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="1f880-253">Добавление кода для обработчика событий</span><span class="sxs-lookup"><span data-stu-id="1f880-253">Add code to handle events</span></span>

1. <span data-ttu-id="1f880-254">В *`ExpenseItHome.xaml`* добавьтек<xref:System.Windows.Controls.Button> элементу обработчик событий.<xref:System.Windows.Controls.Primitives.ButtonBase.Click></span><span class="sxs-lookup"><span data-stu-id="1f880-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="1f880-255">Дополнительные сведения см. в разделе [Практическое руководство. Создайте простой обработчик](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))событий.</span><span class="sxs-lookup"><span data-stu-id="1f880-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="1f880-256">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="1f880-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="1f880-257">Добавьте следующий код в `ExpenseItHome` класс, чтобы добавить обработчик событий нажатия кнопки.</span><span class="sxs-lookup"><span data-stu-id="1f880-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="1f880-258">Обработчик событий открывает страницу **файл ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="1f880-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="1f880-259">Создание пользовательского интерфейса для файл ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="1f880-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="1f880-260">*Файл ExpenseReportPage. XAML* отображает отчет о расходах для пользователя, выбранного на **`ExpenseItHome`** странице.</span><span class="sxs-lookup"><span data-stu-id="1f880-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="1f880-261">В этом разделе вы создадите пользовательский интерфейс для **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="1f880-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="1f880-262">Вы также добавите цвета фона и заливки в различные элементы пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="1f880-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="1f880-263">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1f880-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1f880-264">Добавьте следующий код XAML между <xref:System.Windows.Controls.Grid> тегами:</span><span class="sxs-lookup"><span data-stu-id="1f880-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="1f880-265">Этот пользовательский интерфейс аналогичен *`ExpenseItHome.xaml`* , за исключением того, что данные отчета <xref:System.Windows.Controls.DataGrid>отображаются в.</span><span class="sxs-lookup"><span data-stu-id="1f880-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="1f880-266">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-266">Build and run the application.</span></span>

4. <span data-ttu-id="1f880-267">Нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="1f880-267">Select the **View** button.</span></span>

    <span data-ttu-id="1f880-268">Появится страница отчета по расходам.</span><span class="sxs-lookup"><span data-stu-id="1f880-268">The expense report page appears.</span></span> <span data-ttu-id="1f880-269">Также обратите внимание, что кнопка обратной навигации включена.</span><span class="sxs-lookup"><span data-stu-id="1f880-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="1f880-270">На следующем рисунке показаны элементы пользовательского интерфейса, добавленные в *файл ExpenseReportPage. XAML*.</span><span class="sxs-lookup"><span data-stu-id="1f880-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Пример снимка экрана ExpenseIt, показывающий пользовательский интерфейс, созданный для файл ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="1f880-272">Элементы управления стиля</span><span class="sxs-lookup"><span data-stu-id="1f880-272">Style controls</span></span>

<span data-ttu-id="1f880-273">Внешний вид различных элементов часто одинаков для всех элементов одного типа в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="1f880-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="1f880-274">Пользовательский интерфейс использует [стили](../controls/styling-and-templating.md) для того, чтобы внешний вид можно было использовать в нескольких элементах.</span><span class="sxs-lookup"><span data-stu-id="1f880-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="1f880-275">Многократное использование стилей помогает упростить создание XAML и управление им.</span><span class="sxs-lookup"><span data-stu-id="1f880-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="1f880-276">В этом разделе атрибуты, установленные ранее для каждого элемента, заменяются стилями.</span><span class="sxs-lookup"><span data-stu-id="1f880-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="1f880-277">Откройте *Application. XAML* или *app. XAML*.</span><span class="sxs-lookup"><span data-stu-id="1f880-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="1f880-278">Добавьте следующий код XAML между <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> тегами:</span><span class="sxs-lookup"><span data-stu-id="1f880-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="1f880-279">Этот код XAML добавляет следующие стили:</span><span class="sxs-lookup"><span data-stu-id="1f880-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="1f880-280">`headerTextStyle`: Для форматирования заголовка <xref:System.Windows.Controls.Label>страницы.</span><span class="sxs-lookup"><span data-stu-id="1f880-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1f880-281">`labelStyle`: Для форматирования <xref:System.Windows.Controls.Label> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1f880-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="1f880-282">`columnHeaderStyle`: Для форматирования <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="1f880-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="1f880-283">`listHeaderStyle`: Для форматирования элементов управления " <xref:System.Windows.Controls.Border> заголовок списка".</span><span class="sxs-lookup"><span data-stu-id="1f880-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="1f880-284">`listHeaderTextStyle`: Для форматирования заголовка <xref:System.Windows.Controls.Label>списка.</span><span class="sxs-lookup"><span data-stu-id="1f880-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1f880-285">`buttonStyle`: Для форматирования <xref:System.Windows.Controls.Button>. `ExpenseItHome.xaml`</span><span class="sxs-lookup"><span data-stu-id="1f880-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="1f880-286">Обратите внимание, что стили являются ресурсами и дочерними элементами <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> элемента Property.</span><span class="sxs-lookup"><span data-stu-id="1f880-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="1f880-287">Здесь стили применяются ко всем элементам в приложении.</span><span class="sxs-lookup"><span data-stu-id="1f880-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="1f880-288">Пример использования ресурсов в приложении .NET см. в разделе [использование ресурсов приложения](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="1f880-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="1f880-289">В *`ExpenseItHome.xaml`* замените все <xref:System.Windows.Controls.Grid> между элементами следующим кодом XAML:</span><span class="sxs-lookup"><span data-stu-id="1f880-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="1f880-290">Свойства, определяющие внешний вид элементов управления, такие как <xref:System.Windows.VerticalAlignment> и <xref:System.Windows.Media.FontFamily> , при применении стилей удаляются и заменяются.</span><span class="sxs-lookup"><span data-stu-id="1f880-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="1f880-291">Например, `headerTextStyle` применяется к «Просмотр отчета о расходах» <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="1f880-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="1f880-292">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1f880-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="1f880-293">Замените все <xref:System.Windows.Controls.Grid> элементы на следующий код XAML:</span><span class="sxs-lookup"><span data-stu-id="1f880-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="1f880-294">Этот XAML добавляет стили в <xref:System.Windows.Controls.Label> элементы и. <xref:System.Windows.Controls.Border></span><span class="sxs-lookup"><span data-stu-id="1f880-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="1f880-295">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-295">Build and run the application.</span></span> <span data-ttu-id="1f880-296">Внешний вид окна такой же, как и ранее.</span><span class="sxs-lookup"><span data-stu-id="1f880-296">The window appearance is the same as previously.</span></span>

    ![Пример снимка экрана ExpenseIt с тем же видом, что и в последнем разделе.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="1f880-298">Закройте приложение, чтобы вернуться в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1f880-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="1f880-299">Привязка данных к элементу управления</span><span class="sxs-lookup"><span data-stu-id="1f880-299">Bind data to a control</span></span>

<span data-ttu-id="1f880-300">В этом разделе вы создадите XML-данные, привязанные к различным элементам управления.</span><span class="sxs-lookup"><span data-stu-id="1f880-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="1f880-301">В *`ExpenseItHome.xaml`* после открывающего <xref:System.Windows.Controls.Grid> элемента добавьте следующий код XAML, чтобы создать объект <xref:System.Windows.Data.XmlDataProvider> , содержащий данные для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="1f880-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="1f880-302">Данные создаются в виде <xref:System.Windows.Controls.Grid> ресурса.</span><span class="sxs-lookup"><span data-stu-id="1f880-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="1f880-303">Обычно эти данные загружаются в виде файла, но для простоты данные добавляются встроенным образом.</span><span class="sxs-lookup"><span data-stu-id="1f880-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="1f880-304">В элементе добавьте следующий `<xref:System.Windows.DataTemplate>` элемент, определяющий способ <xref:System.Windows.Controls.ListBox>отображения данных `<XmlDataProvider>` в, после элемента: `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="1f880-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="1f880-305">Дополнительные сведения о шаблонах данных см. в разделе [Общие сведения](../data/data-templating-overview.md)о создании шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="1f880-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="1f880-306">Замените существующий <xref:System.Windows.Controls.ListBox> код XAML следующим:</span><span class="sxs-lookup"><span data-stu-id="1f880-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="1f880-307">Этот XAML привязывает <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> свойство <xref:System.Windows.Controls.ListBox> объекта к источнику данных и применяет шаблон данных в качестве <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="1f880-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="1f880-308">Подключение данных к элементам управления</span><span class="sxs-lookup"><span data-stu-id="1f880-308">Connect data to controls</span></span>

<span data-ttu-id="1f880-309">Далее предстоит добавить код для получения имени, выбранного на **`ExpenseItHome`** странице, и передачи его конструктору **файл ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="1f880-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="1f880-310">**Файл ExpenseReportPage** устанавливает в качестве контекста данных переданный элемент, который является элементом управления, определенным в привязке *файл ExpenseReportPage. XAML* к.</span><span class="sxs-lookup"><span data-stu-id="1f880-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="1f880-311">Откройте файл *ExpenseReportPage.xaml.vb* или *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1f880-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="1f880-312">Добавьте конструктор, принимающий объект, чтобы можно было передавать данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="1f880-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="1f880-313">Откройте *`ExpenseItHome.xaml.vb`* или *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="1f880-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="1f880-314">Измените обработчик <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событий, чтобы вызвать новый конструктор, передающий данные отчета о затратах выбранного человека.</span><span class="sxs-lookup"><span data-stu-id="1f880-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="1f880-315">Применение стилей к данным с помощью шаблонов данных</span><span class="sxs-lookup"><span data-stu-id="1f880-315">Style data with data templates</span></span>

<span data-ttu-id="1f880-316">В этом разделе вы обновите пользовательский интерфейс для каждого элемента в списках с привязкой к данным с помощью шаблонов данных.</span><span class="sxs-lookup"><span data-stu-id="1f880-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="1f880-317">Откройте файл *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1f880-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1f880-318">Привяжите содержимое элементов "Name" и "Department" <xref:System.Windows.Controls.Label> к соответствующему свойству источника данных.</span><span class="sxs-lookup"><span data-stu-id="1f880-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="1f880-319">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f880-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="1f880-320">После открывающего <xref:System.Windows.Controls.Grid> элемента добавьте следующие шаблоны данных, определяющие способ отображения данных отчета о расходах:</span><span class="sxs-lookup"><span data-stu-id="1f880-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="1f880-321"><xref:System.Windows.Controls.DataGridTextColumn> Замените элементыэлементом<xref:System.Windows.Controls.DataGrid>вэлементе и примените к ним шаблоны. <xref:System.Windows.Controls.DataGridTemplateColumn></span><span class="sxs-lookup"><span data-stu-id="1f880-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="1f880-322">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1f880-322">Build and run the application.</span></span>

6. <span data-ttu-id="1f880-323">Выберите пользователя и нажмите кнопку **Просмотр** .</span><span class="sxs-lookup"><span data-stu-id="1f880-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="1f880-324">На следующем рисунке показаны обе страницы `ExpenseIt` приложения с примененными элементами управления, макет, стили, привязка данных и шаблоны данных:</span><span class="sxs-lookup"><span data-stu-id="1f880-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![На обеих страницах приложения отображается список имен и отчет о расходах.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="1f880-326">В этом примере демонстрируется конкретная функция WPF, которая не соответствует всем рекомендациям, таким как безопасность, локализация и специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="1f880-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="1f880-327">Полный охват WPF и рекомендации по разработке приложений .NET см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1f880-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="1f880-328">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="1f880-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="1f880-329">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1f880-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="1f880-330">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="1f880-331">Производительность WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="1f880-332">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="1f880-332">Next steps</span></span>

<span data-ttu-id="1f880-333">В этом пошаговом руководстве вы узнали о ряде методов создания пользовательского интерфейса с помощью Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="1f880-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="1f880-334">Теперь у вас должно быть базовое представление о стандартных блоках приложений .NET с привязкой к данным.</span><span class="sxs-lookup"><span data-stu-id="1f880-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="1f880-335">Более подробную информацию об архитектуре и моделях программирования WPF см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1f880-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="1f880-336">Архитектура WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="1f880-337">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="1f880-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="1f880-338">Общие сведения о свойствах зависимостей</span><span class="sxs-lookup"><span data-stu-id="1f880-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="1f880-339">Макет</span><span class="sxs-lookup"><span data-stu-id="1f880-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="1f880-340">Более подробную информацию о создании приложений см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="1f880-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="1f880-341">Разработка приложений</span><span class="sxs-lookup"><span data-stu-id="1f880-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="1f880-342">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="1f880-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="1f880-343">Общие сведения о привязке данных</span><span class="sxs-lookup"><span data-stu-id="1f880-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="1f880-344">Графика и мультимедиа</span><span class="sxs-lookup"><span data-stu-id="1f880-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="1f880-345">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="1f880-346">См. также</span><span class="sxs-lookup"><span data-stu-id="1f880-346">See also</span></span>

- [<span data-ttu-id="1f880-347">Обзор панелей</span><span class="sxs-lookup"><span data-stu-id="1f880-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="1f880-348">Общие сведения о шаблонах данных</span><span class="sxs-lookup"><span data-stu-id="1f880-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="1f880-349">Создание приложения WPF</span><span class="sxs-lookup"><span data-stu-id="1f880-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="1f880-350">Стили и шаблоны</span><span class="sxs-lookup"><span data-stu-id="1f880-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
