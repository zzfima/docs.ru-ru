---
title: Пошаговое руководство. Создание кнопки с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 6738b9e66c1223ea4ec50c070a421d119fd30bc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458693"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="a5943-102">Пошаговое руководство. Создание кнопки с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="a5943-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="a5943-103">Цель этого пошагового руководства — научиться создавать анимированную кнопку для использования в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="a5943-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="a5943-104">В этом пошаговом руководстве используются стили и шаблон для создания настраиваемого ресурса кнопки, который позволяет повторно использовать код и разделение логики кнопки из объявления кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="a5943-105">Это пошаговое руководство написано полностью в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5943-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5943-106">В этом пошаговом руководстве описано, как создать приложение, введя или скопировав и вставляя [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5943-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="a5943-107">Если вы предпочитаете использовать конструктор для создания того же приложения, см. раздел [Создание кнопки с помощью Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="a5943-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="a5943-108">На следующем рисунке показаны готовые кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="a5943-109">![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="a5943-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="a5943-110">Создание основных кнопок</span><span class="sxs-lookup"><span data-stu-id="a5943-110">Create Basic Buttons</span></span>

<span data-ttu-id="a5943-111">Начнем с создания нового проекта и добавления нескольких кнопок в окно.</span><span class="sxs-lookup"><span data-stu-id="a5943-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="a5943-112">Создание нового проекта WPF и добавление в него кнопок</span><span class="sxs-lookup"><span data-stu-id="a5943-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="a5943-113">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5943-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="a5943-114">**Создайте новый проект WPF:** В меню **файл** наведите указатель мыши на пункт **создать**и выберите пункт **проект**.</span><span class="sxs-lookup"><span data-stu-id="a5943-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="a5943-115">Найдите шаблон **Windows Application (WPF)** и назовите проект «аниматедбуттон».</span><span class="sxs-lookup"><span data-stu-id="a5943-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="a5943-116">Это приведет к созданию каркаса для приложения.</span><span class="sxs-lookup"><span data-stu-id="a5943-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="a5943-117">**Добавить основные кнопки по умолчанию:** Все файлы, необходимые для этого пошагового руководства, предоставляются шаблоном.</span><span class="sxs-lookup"><span data-stu-id="a5943-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="a5943-118">Откройте файл Window1. XAML, дважды щелкнув его в обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="a5943-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="a5943-119">По умолчанию в Window1. XAML присутствует элемент <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="a5943-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="a5943-120">Удалите элемент <xref:System.Windows.Controls.Grid> и добавьте несколько кнопок на страницу [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], введя или скопировав и вставляя следующий выделенный код в Window1. XAML:</span><span class="sxs-lookup"><span data-stu-id="a5943-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="a5943-121">Нажмите клавишу F5, чтобы запустить приложение. Вы увидите набор кнопок, которые выглядят как на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a5943-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="a5943-122">![Три основные кнопки](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="a5943-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="a5943-123">Теперь, когда основные кнопки созданы, вы завершили работу в файле Window1. XAML.</span><span class="sxs-lookup"><span data-stu-id="a5943-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="a5943-124">Остальная часть пошагового руководства посвящена файлу app. XAML, определяющему стили и шаблон для кнопок.</span><span class="sxs-lookup"><span data-stu-id="a5943-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="a5943-125">Задание основных свойств</span><span class="sxs-lookup"><span data-stu-id="a5943-125">Set Basic Properties</span></span>

<span data-ttu-id="a5943-126">Теперь давайте настроим некоторые свойства на этих кнопках, чтобы управлять внешним видом и макетом кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="a5943-127">Вместо того чтобы устанавливать свойства на кнопки по отдельности, вы будете использовать ресурсы для определения свойств кнопки для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="a5943-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="a5943-128">Ресурсы приложения концептуально похожи на внешние каскадные таблицы стилей (CSS) для веб-страниц. Тем не менее ресурсы являются гораздо более мощными, чем каскадные таблицы стилей (CSS), как вы увидите в конце этого пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="a5943-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="a5943-129">Дополнительные сведения о ресурсах см. в разделе [ресурсы XAML](../advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a5943-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="a5943-130">Использование стилей для задания основных свойств кнопок</span><span class="sxs-lookup"><span data-stu-id="a5943-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="a5943-131">**Определите блок Application. Resources:** Откройте App. XAML и добавьте следующую выделенную разметку, если она еще не существует:</span><span class="sxs-lookup"><span data-stu-id="a5943-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="a5943-132">Область ресурсов определяется местом, где определяется ресурс.</span><span class="sxs-lookup"><span data-stu-id="a5943-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="a5943-133">Определение ресурсов в `Application.Resources` в файле App. XAML позволяет использовать ресурс из любого места в приложении.</span><span class="sxs-lookup"><span data-stu-id="a5943-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="a5943-134">Дополнительные сведения об определении области ресурсов см. в разделе [ресурсы XAML](../advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a5943-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

2. <span data-ttu-id="a5943-135">**Создайте стиль и определите в нем основные значения свойств:** Добавьте следующую разметку в блок `Application.Resources`.</span><span class="sxs-lookup"><span data-stu-id="a5943-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="a5943-136">Эта разметка создает <xref:System.Windows.Style>, который применяется ко всем кнопкам в приложении, настроив <xref:System.Windows.FrameworkElement.Width%2A> кнопок на 90, а <xref:System.Windows.FrameworkElement.Margin%2A> — на 10:</span><span class="sxs-lookup"><span data-stu-id="a5943-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="a5943-137">Свойство <xref:System.Windows.Style.TargetType%2A> указывает, что стиль применяется ко всем объектам типа <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="a5943-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="a5943-138">Каждый <xref:System.Windows.Setter> задает другое значение свойства для <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="a5943-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="a5943-139">Таким образом, на этом этапе каждая кнопка в приложении имеет ширину 90 и поле, равное 10.</span><span class="sxs-lookup"><span data-stu-id="a5943-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="a5943-140">Если нажать клавишу F5 для запуска приложения, появится следующее окно.</span><span class="sxs-lookup"><span data-stu-id="a5943-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="a5943-141">![Кнопки с шириной 90 и полем, равным 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="a5943-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="a5943-142">С помощью стилей можно выполнять множество других задач, в том числе различные способы точной настройки объектов, указания сложных значений свойств и даже использования стилей в качестве входных данных для других стилей.</span><span class="sxs-lookup"><span data-stu-id="a5943-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="a5943-143">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5943-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="a5943-144">**Задайте ресурсу значение свойства Style:** Ресурсы обеспечивают простой способ повторного использования часто заданных объектов и значений.</span><span class="sxs-lookup"><span data-stu-id="a5943-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="a5943-145">Особенно полезно определить сложные значения с помощью ресурсов, чтобы сделать код более модульным.</span><span class="sxs-lookup"><span data-stu-id="a5943-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="a5943-146">Добавьте следующую выделенную разметку в App. XAML.</span><span class="sxs-lookup"><span data-stu-id="a5943-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="a5943-147">Непосредственно в блоке `Application.Resources` вы создали ресурс с именем «Грайблуеградиентбруш».</span><span class="sxs-lookup"><span data-stu-id="a5943-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="a5943-148">Этот ресурс определяет горизонтальный градиент.</span><span class="sxs-lookup"><span data-stu-id="a5943-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="a5943-149">Этот ресурс можно использовать как значение свойства из любого места в приложении, включая внутри метода задания стиля кнопки для свойства <xref:System.Windows.Controls.Control.Background%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5943-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="a5943-150">Теперь все кнопки имеют значение свойства <xref:System.Windows.Controls.Control.Background%2A> этого градиента.</span><span class="sxs-lookup"><span data-stu-id="a5943-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="a5943-151">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a5943-151">Press F5 to run the application.</span></span> <span data-ttu-id="a5943-152">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a5943-152">It should look like the following.</span></span>

     <span data-ttu-id="a5943-153">![Кнопки с градиентным фоном](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="a5943-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="a5943-154">Создание шаблона, определяющего вид кнопки</span><span class="sxs-lookup"><span data-stu-id="a5943-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="a5943-155">В этом разделе вы создадите шаблон, который настраивает внешний вид (представление) кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="a5943-156">Кнопка презентации состоит из нескольких объектов, включая прямоугольники и другие компоненты, чтобы дать кнопке уникальный вид.</span><span class="sxs-lookup"><span data-stu-id="a5943-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="a5943-157">До сих пор Управление тем, как выглядят кнопки в приложении, было ограничено изменением свойств кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="a5943-158">Что делать, если вы хотите внести более коренные изменения в внешний вид кнопки?</span><span class="sxs-lookup"><span data-stu-id="a5943-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="a5943-159">Шаблоны обеспечивают мощный контроль над представлением объекта.</span><span class="sxs-lookup"><span data-stu-id="a5943-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="a5943-160">Поскольку шаблоны можно использовать в стилях, можно применить шаблон ко всем объектам, к которым применяется стиль (в этом пошаговом руководстве это кнопка).</span><span class="sxs-lookup"><span data-stu-id="a5943-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="a5943-161">Использование шаблона для определения вида кнопки</span><span class="sxs-lookup"><span data-stu-id="a5943-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="a5943-162">**Настройте шаблон:** Так как элементы управления, такие как <xref:System.Windows.Controls.Button>, имеют свойство <xref:System.Windows.Controls.Control.Template%2A>, можно определить значение свойства шаблона так же, как и другие значения свойств, заданные в <xref:System.Windows.Style> с помощью <xref:System.Windows.Setter>.</span><span class="sxs-lookup"><span data-stu-id="a5943-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="a5943-163">Добавьте следующую выделенную разметку в стиль кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="a5943-164">**Изменить представление кнопки:** На этом этапе необходимо определить шаблон.</span><span class="sxs-lookup"><span data-stu-id="a5943-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="a5943-165">Добавьте следующую выделенную разметку.</span><span class="sxs-lookup"><span data-stu-id="a5943-165">Add the following highlighted markup.</span></span> <span data-ttu-id="a5943-166">Эта разметка определяет два элемента <xref:System.Windows.Shapes.Rectangle> с закругленными краями, за которыми следует <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="a5943-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="a5943-167"><xref:System.Windows.Controls.DockPanel> используется для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="a5943-168"><xref:System.Windows.Controls.ContentPresenter> отображает содержимое кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="a5943-169">В этом пошаговом руководстве содержимое является текстом ("Кнопка 1", "Кнопка 2", "Кнопка 3").</span><span class="sxs-lookup"><span data-stu-id="a5943-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="a5943-170">Все компоненты шаблона (прямоугольники и <xref:System.Windows.Controls.DockPanel>) размещаются внутри <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="a5943-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="a5943-171">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a5943-171">Press F5 to run the application.</span></span> <span data-ttu-id="a5943-172">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a5943-172">It should look like the following.</span></span>

     ![Окно с тремя кнопками](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="a5943-174">**Добавьте глассеффект в шаблон:** Далее вы добавите стекло.</span><span class="sxs-lookup"><span data-stu-id="a5943-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="a5943-175">Сначала необходимо создать ресурсы, которые создают эффект прозрачного градиента.</span><span class="sxs-lookup"><span data-stu-id="a5943-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="a5943-176">Добавьте эти ресурсы градиента в любое место в блоке `Application.Resources`:</span><span class="sxs-lookup"><span data-stu-id="a5943-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="a5943-177">Эти ресурсы используются в качестве <xref:System.Windows.Shapes.Shape.Fill%2A> для прямоугольника, который мы вставляем в <xref:System.Windows.Controls.Grid> шаблона кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="a5943-178">Добавьте в шаблон следующую выделенную разметку.</span><span class="sxs-lookup"><span data-stu-id="a5943-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="a5943-179">Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольника со свойством `x:Name` "Гласскубе" равно 0, поэтому при выполнении образца не отображается стеклянный прямоугольник, наложенный сверху.</span><span class="sxs-lookup"><span data-stu-id="a5943-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="a5943-180">Это связано с тем, что позже мы добавим триггеры к шаблону, когда пользователь взаимодействует с кнопкой.</span><span class="sxs-lookup"><span data-stu-id="a5943-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="a5943-181">Однако можно увидеть, как выглядит кнопка, изменив значение <xref:System.Windows.UIElement.Opacity%2A> на 1 и запустив приложение.</span><span class="sxs-lookup"><span data-stu-id="a5943-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="a5943-182">См. следующий рисунок.</span><span class="sxs-lookup"><span data-stu-id="a5943-182">See the following figure.</span></span> <span data-ttu-id="a5943-183">Прежде чем перейти к следующему шагу, измените значение <xref:System.Windows.UIElement.Opacity%2A> обратно на 0.</span><span class="sxs-lookup"><span data-stu-id="a5943-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="a5943-184">![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="a5943-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="a5943-185">Взаимодействие кнопки "создать"</span><span class="sxs-lookup"><span data-stu-id="a5943-185">Create Button Interactivity</span></span>

<span data-ttu-id="a5943-186">В этом разделе вы создадите триггеры свойств и триггеры событий для изменения значений свойств и запуска анимации в ответ на действия пользователя, такие как перемещение указателя мыши над кнопкой и нажатие кнопки.</span><span class="sxs-lookup"><span data-stu-id="a5943-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="a5943-187">Простой способ добавления интерактивности (нажатие кнопки мыши, выхода из мыши, щелчка и т. д.) заключается в определении триггеров в шаблоне или стиле.</span><span class="sxs-lookup"><span data-stu-id="a5943-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="a5943-188">Чтобы создать <xref:System.Windows.Trigger>, определите свойство "Condition", например: кнопка <xref:System.Windows.UIElement.IsMouseOver%2A> значение свойства равно `true`.</span><span class="sxs-lookup"><span data-stu-id="a5943-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="a5943-189">Затем определяются методы задания (Actions), которые выполняются, когда условие триггера имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="a5943-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="a5943-190">Создание интерактивной активности кнопки</span><span class="sxs-lookup"><span data-stu-id="a5943-190">To create button interactivity</span></span>

1. <span data-ttu-id="a5943-191">**Добавить триггеры шаблона:** Добавьте выделенную разметку в шаблон.</span><span class="sxs-lookup"><span data-stu-id="a5943-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="a5943-192">**Добавить триггеры свойств:** Добавьте выделенную разметку в блок `ControlTemplate.Triggers`:</span><span class="sxs-lookup"><span data-stu-id="a5943-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="a5943-193">Нажмите клавишу F5, чтобы запустить приложение и увидеть результат при выполнении указателя мыши над кнопками.</span><span class="sxs-lookup"><span data-stu-id="a5943-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="a5943-194">**Добавить триггер фокуса:** Далее мы добавим несколько аналогичных методов задания, которые будут обработаны, когда кнопка будет иметь фокус (например, после того, как пользователь щелкнет его).</span><span class="sxs-lookup"><span data-stu-id="a5943-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="a5943-195">Нажмите клавишу F5, чтобы запустить приложение, и нажмите одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="a5943-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="a5943-196">Обратите внимание, что кнопка остается выделенной после ее нажатия, так как она по-прежнему имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a5943-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="a5943-197">Если щелкнуть другую кнопку, кнопка Создать получит фокус, а последний теряет ее.</span><span class="sxs-lookup"><span data-stu-id="a5943-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="a5943-198">**Добавьте анимацию для**  <xref:System.Windows.UIElement.MouseEnter> **и** <xref:System.Windows.UIElement.MouseLeave> **.** далее мы добавим несколько анимаций к триггерам.</span><span class="sxs-lookup"><span data-stu-id="a5943-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="a5943-199">Добавьте следующую разметку в любое место внутри блока `ControlTemplate.Triggers`.</span><span class="sxs-lookup"><span data-stu-id="a5943-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="a5943-200">Прозрачный прямоугольник сжимается при наведении указателя мыши на кнопку и возвращается к нормальному размеру, когда указатель покидает.</span><span class="sxs-lookup"><span data-stu-id="a5943-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="a5943-201">Существует две анимации, которые запускаются при наведении указателя мыши на кнопку (возникает событие<xref:System.Windows.UIElement.MouseEnter>).</span><span class="sxs-lookup"><span data-stu-id="a5943-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="a5943-202">Эти анимации сжимают стеклянный прямоугольник вдоль осей X и Y.</span><span class="sxs-lookup"><span data-stu-id="a5943-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="a5943-203">Обратите внимание на свойства элементов <xref:System.Windows.Media.Animation.DoubleAnimation> — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5943-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="a5943-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A> указывает, что анимация выполняется в течение половины секунды, а <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> указывает, что стекло сжимается на 10%.</span><span class="sxs-lookup"><span data-stu-id="a5943-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="a5943-205">Второй триггер события (<xref:System.Windows.UIElement.MouseLeave>) просто останавливает первый из них.</span><span class="sxs-lookup"><span data-stu-id="a5943-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="a5943-206">Когда вы останавливаете <xref:System.Windows.Media.Animation.Storyboard>, все анимированные свойства возвращают значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a5943-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="a5943-207">Таким образом, когда пользователь перемещает указатель мыши за пределы кнопки, кнопка возвращается к способу, который находился перед перемещением курсора по кнопке.</span><span class="sxs-lookup"><span data-stu-id="a5943-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="a5943-208">Дополнительные сведения о анимациях см. в разделе [Общие сведения об анимации](../graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a5943-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="a5943-209">**Добавить анимацию при нажатии кнопки:** Последним шагом является добавление триггера для, когда пользователь нажимает кнопку.</span><span class="sxs-lookup"><span data-stu-id="a5943-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="a5943-210">Добавьте следующую разметку в любое место внутри блока `ControlTemplate.Triggers`:</span><span class="sxs-lookup"><span data-stu-id="a5943-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="a5943-211">Нажмите клавишу F5, чтобы запустить приложение, и нажмите одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="a5943-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="a5943-212">При нажатии кнопки прозрачный прямоугольник вращается вокруг.</span><span class="sxs-lookup"><span data-stu-id="a5943-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="a5943-213">Сводка</span><span class="sxs-lookup"><span data-stu-id="a5943-213">Summary</span></span>
 <span data-ttu-id="a5943-214">В этом пошаговом руководстве вы выполнили следующие упражнения:</span><span class="sxs-lookup"><span data-stu-id="a5943-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="a5943-215">Нацелен на <xref:System.Windows.Style> типа объекта (<xref:System.Windows.Controls.Button>).</span><span class="sxs-lookup"><span data-stu-id="a5943-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="a5943-216">Контролируемые основные свойства кнопок во всем приложении, использующих <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="a5943-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="a5943-217">Созданные ресурсы, такие как градиенты, используемые для значений свойств <xref:System.Windows.Style> методов задания.</span><span class="sxs-lookup"><span data-stu-id="a5943-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="a5943-218">Настройка вида кнопок во всем приложении путем применения шаблона к кнопкам.</span><span class="sxs-lookup"><span data-stu-id="a5943-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="a5943-219">Настраиваемое поведение кнопок в ответ на действия пользователя (например, <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>и <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), которые включают эффекты анимации.</span><span class="sxs-lookup"><span data-stu-id="a5943-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5943-220">См. также</span><span class="sxs-lookup"><span data-stu-id="a5943-220">See also</span></span>

- [<span data-ttu-id="a5943-221">Создание кнопки с помощью Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="a5943-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="a5943-222">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="a5943-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a5943-223">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="a5943-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="a5943-224">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="a5943-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="a5943-225">Общие сведения об эффектах для точечных рисунков</span><span class="sxs-lookup"><span data-stu-id="a5943-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
