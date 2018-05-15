---
title: Пошаговое руководство. Создание кнопки с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 6d41d0894aa85f342deafb77434771b2c89e4150
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="30dc1-102">Пошаговое руководство. Создание кнопки с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="30dc1-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="30dc1-103">Цель данного руководства является создание анимированной кнопки для использования в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="30dc1-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="30dc1-104">В этом пошаговом руководстве используется стиль и шаблон для создания ресурса пользовательской кнопки, которая позволяет повторно использовать код и разделять логику от объявления кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="30dc1-105">В этом пошаговом руководстве приведено полностью в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30dc1-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30dc1-106">В этом пошаговом руководстве поможет выполнить шаги для создания приложения путем ввода или копирования и вставки [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30dc1-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="30dc1-107">Если вы предпочитаете узнать, как использовать средство разработки (Microsoft Expression Blend) для создания того же приложения см. в разделе [Создание кнопки с помощью Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="30dc1-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="30dc1-108">На следующем рисунке показана созданные кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="30dc1-109">![Настраиваемые кнопки, созданные с помощью XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="30dc1-109">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="30dc1-110">Создание простых кнопок</span><span class="sxs-lookup"><span data-stu-id="30dc1-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="30dc1-111">Начнем с создания проекта и добавления нескольких кнопок в окно.</span><span class="sxs-lookup"><span data-stu-id="30dc1-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="30dc1-112">Чтобы создать новый проект WPF и добавить кнопки в окно</span><span class="sxs-lookup"><span data-stu-id="30dc1-112">To create a new WPF project and add buttons to the window</span></span>  
  
1.  <span data-ttu-id="30dc1-113">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="30dc1-113">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="30dc1-114">**Создайте новый проект WPF:** на **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**.</span><span class="sxs-lookup"><span data-stu-id="30dc1-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="30dc1-115">Найти **приложения Windows (WPF)** шаблон и имя проекта «AnimatedButton».</span><span class="sxs-lookup"><span data-stu-id="30dc1-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="30dc1-116">Это создает основу для приложения.</span><span class="sxs-lookup"><span data-stu-id="30dc1-116">This will create the skeleton for the application.</span></span>  
  
3.  <span data-ttu-id="30dc1-117">**Добавление кнопок basic по умолчанию:** все файлы, необходимые для этого пошагового руководства включенных в шаблон.</span><span class="sxs-lookup"><span data-stu-id="30dc1-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="30dc1-118">Откройте файл Window1.xaml, дважды щелкнув его в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="30dc1-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="30dc1-119">По умолчанию — <xref:System.Windows.Controls.Grid> элемент в Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="30dc1-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="30dc1-120">Удалить <xref:System.Windows.Controls.Grid> элемент и добавьте несколько кнопок для [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы путем ввода или копирования и вставки в Window1.xaml следующий выделенный код:</span><span class="sxs-lookup"><span data-stu-id="30dc1-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     <span data-ttu-id="30dc1-121">Нажмите клавишу F5 для запуска приложения; Вы увидите набор кнопок, который выглядит как на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="30dc1-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="30dc1-122">![Три основные кнопки](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="30dc1-122">![Three basic buttons](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="30dc1-123">После создания простых кнопок вы закончили работу в файле Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="30dc1-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="30dc1-124">Остальная часть пошагового руководства основное внимание уделяется файл app.xaml, определять стили и шаблон для кнопок.</span><span class="sxs-lookup"><span data-stu-id="30dc1-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="30dc1-125">Набор основных свойств</span><span class="sxs-lookup"><span data-stu-id="30dc1-125">Set Basic Properties</span></span>  
 <span data-ttu-id="30dc1-126">Далее зададим некоторые свойства этих кнопок, определяющие внешний вид кнопки и макет.</span><span class="sxs-lookup"><span data-stu-id="30dc1-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="30dc1-127">Вместо того чтобы задавать свойства для кнопок по отдельности, будет использовать ресурсы для определения свойств кнопки для всего приложения.</span><span class="sxs-lookup"><span data-stu-id="30dc1-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="30dc1-128">Ресурсы приложений похожи на внешние [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] для веб-страниц; Однако ресурсы являются гораздо эффективнее, чем [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], как можно будет увидеть в конце данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="30dc1-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="30dc1-129">Дополнительные сведения о ресурсах см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="30dc1-129">To learn more about resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="30dc1-130">Чтобы использовать стили для установки основных свойств кнопок</span><span class="sxs-lookup"><span data-stu-id="30dc1-130">To use styles to set basic properties on the buttons</span></span>  
  
1.  <span data-ttu-id="30dc1-131">**Определение блока ресурсы приложения:** откройте файл app.xaml и добавьте следующую выделенную разметку, если он еще не существует:</span><span class="sxs-lookup"><span data-stu-id="30dc1-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
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
  
     <span data-ttu-id="30dc1-132">Область ресурса определяется где определить ресурс.</span><span class="sxs-lookup"><span data-stu-id="30dc1-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="30dc1-133">Определение ресурсов в `Application.Resources` в файле app.xaml файл позволяет ресурса для использования в любом месте в приложении.</span><span class="sxs-lookup"><span data-stu-id="30dc1-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="30dc1-134">Дополнительные сведения об определении области ресурсов см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="30dc1-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
2.  <span data-ttu-id="30dc1-135">**Создание стиля и определять значения свойств основных с ним:** добавьте следующую разметку, чтобы `Application.Resources` блока.</span><span class="sxs-lookup"><span data-stu-id="30dc1-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="30dc1-136">Эта разметка создает <xref:System.Windows.Style> , применяется для всех кнопок в приложении, устанавливая <xref:System.Windows.FrameworkElement.Width%2A> кнопок на 90 и <xref:System.Windows.FrameworkElement.Margin%2A> до 10:</span><span class="sxs-lookup"><span data-stu-id="30dc1-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="30dc1-137"><xref:System.Windows.Style.TargetType%2A> Свойство указывает, что стиль применяется ко всем объектам типа <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="30dc1-138">Каждый <xref:System.Windows.Setter> задает другое значение свойства для <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="30dc1-139">Поэтому в этот момент все кнопки в приложении имеет шириной равной 90 и границей 10.</span><span class="sxs-lookup"><span data-stu-id="30dc1-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="30dc1-140">Если нажать клавишу F5 для запуска приложения, вы увидите следующее окно.</span><span class="sxs-lookup"><span data-stu-id="30dc1-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="30dc1-141">![Кнопки с шириной равной 90 и границей 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="30dc1-141">![Buttons with a width of 90 and a margin of 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="30dc1-142">Есть намного больше, можно сделать с помощью стилей, включая различные способы настройки целевых объектах, указание сложных значений свойств и даже использование стилей в качестве входных данных для других стилей.</span><span class="sxs-lookup"><span data-stu-id="30dc1-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="30dc1-143">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="30dc1-143">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
3.  <span data-ttu-id="30dc1-144">**Задайте значение свойства стиля для ресурса:** ресурсы позволяют простой способ повторного использования часто определяемых объектов и значений.</span><span class="sxs-lookup"><span data-stu-id="30dc1-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="30dc1-145">Это особенно полезно для определения сложных значений с помощью ресурсов, чтобы сделать код более удобным.</span><span class="sxs-lookup"><span data-stu-id="30dc1-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="30dc1-146">Добавьте следующую выделенную разметку в файл app.xaml.</span><span class="sxs-lookup"><span data-stu-id="30dc1-146">Add the following highlighted markup to app.xaml.</span></span>  
  
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
  
     <span data-ttu-id="30dc1-147">Непосредственно под `Application.Resources` блок, вы создали ресурсу с именем «GrayBlueGradientBrush».</span><span class="sxs-lookup"><span data-stu-id="30dc1-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="30dc1-148">Этот ресурс определяет горизонтальный градиент.</span><span class="sxs-lookup"><span data-stu-id="30dc1-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="30dc1-149">Этот ресурс можно использовать в качестве значения свойства из любого места в приложении, в том числе внутри метода задания стиля кнопки для <xref:System.Windows.Controls.Control.Background%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="30dc1-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="30dc1-150">Теперь все кнопки имеют <xref:System.Windows.Controls.Control.Background%2A> значение свойства для этого градиента.</span><span class="sxs-lookup"><span data-stu-id="30dc1-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="30dc1-151">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="30dc1-151">Press F5 to run the application.</span></span> <span data-ttu-id="30dc1-152">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="30dc1-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="30dc1-153">![Кнопки с фоновым градиентом](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="30dc1-153">![Buttons with a gradient background](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="30dc1-154">Создание шаблона, который определяет внешний вид кнопки</span><span class="sxs-lookup"><span data-stu-id="30dc1-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="30dc1-155">В этом разделе создайте шаблон, который настраивает внешний вид (представление) кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="30dc1-156">Представление кнопки состоит из нескольких объектов, включая прямоугольники и другие компоненты для предоставления уникальный вид кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="30dc1-157">На данный момент управления видом кнопок в приложении выполнялось с помощью изменения свойств кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="30dc1-158">Что делать, если вы хотите внести кардинально изменить внешний вид кнопки?</span><span class="sxs-lookup"><span data-stu-id="30dc1-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="30dc1-159">Шаблоны включают мощным средством управления представлением объекта.</span><span class="sxs-lookup"><span data-stu-id="30dc1-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="30dc1-160">Поскольку шаблоны могут использоваться в стилях, можно применить шаблон ко всем объектам, применяется стиль (в этом пошаговом руководстве, кнопки).</span><span class="sxs-lookup"><span data-stu-id="30dc1-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="30dc1-161">Чтобы использовать шаблон для определения внешнего вида кнопки</span><span class="sxs-lookup"><span data-stu-id="30dc1-161">To use the template to define the look of the button</span></span>  
  
1.  <span data-ttu-id="30dc1-162">**Настройка шаблона:** так, как элементы управления, например <xref:System.Windows.Controls.Button> имеют <xref:System.Windows.Controls.Control.Template%2A> можно определить значение свойства шаблона так же, как и другие значения свойств, заданных в <xref:System.Windows.Style> с помощью <xref:System.Windows.Setter>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="30dc1-163">Добавьте следующую выделенную разметку в стиль кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-163">Add the following highlighted markup to your button style.</span></span>  
  
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
  
2.  <span data-ttu-id="30dc1-164">**ALTER презентации кнопки:** на этом этапе необходимо определить шаблон.</span><span class="sxs-lookup"><span data-stu-id="30dc1-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="30dc1-165">Добавьте следующую выделенную разметку.</span><span class="sxs-lookup"><span data-stu-id="30dc1-165">Add the following highlighted markup.</span></span> <span data-ttu-id="30dc1-166">Эта разметка задает два <xref:System.Windows.Shapes.Rectangle> элементы со скругленными краями, за которым следует <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="30dc1-167"><xref:System.Windows.Controls.DockPanel> Используется для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="30dc1-168">Объект <xref:System.Windows.Controls.ContentPresenter> отображает содержимое кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="30dc1-169">В этом пошаговом руководстве содержимым является текст («Button 1», «Button 2», «Button 3»).</span><span class="sxs-lookup"><span data-stu-id="30dc1-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="30dc1-170">Все компоненты шаблона (прямоугольники и <xref:System.Windows.Controls.DockPanel>) располагаются внутри <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
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
  
     <span data-ttu-id="30dc1-171">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="30dc1-171">Press F5 to run the application.</span></span> <span data-ttu-id="30dc1-172">Он должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="30dc1-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="30dc1-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="30dc1-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3.  <span data-ttu-id="30dc1-174">**Добавление прозрачности в шаблон:** мы добавим стекла.</span><span class="sxs-lookup"><span data-stu-id="30dc1-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="30dc1-175">Сначала создать ресурсы, которые создают эффект градиента прозрачности.</span><span class="sxs-lookup"><span data-stu-id="30dc1-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="30dc1-176">Добавьте эти градиентные ресурсы в любом месте в пределах `Application.Resources` блока:</span><span class="sxs-lookup"><span data-stu-id="30dc1-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     <span data-ttu-id="30dc1-177">Эти ресурсы используются как <xref:System.Windows.Shapes.Shape.Fill%2A> для прямоугольника, который вставляется в <xref:System.Windows.Controls.Grid> шаблона кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="30dc1-178">Добавьте следующую выделенную разметку в шаблон.</span><span class="sxs-lookup"><span data-stu-id="30dc1-178">Add the following highlighted markup to the template.</span></span>  
  
    ```  
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
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     <span data-ttu-id="30dc1-179">Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольника с `x:Name` свойство «glassCube» задано значение 0, поэтому при выполнении примера, вы не видите прозрачного прямоугольника в верхней части.</span><span class="sxs-lookup"><span data-stu-id="30dc1-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="30dc1-180">Это потому, что впоследствии будет происходить добавление триггеров в шаблон для взаимодействия пользователя с помощью кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="30dc1-181">Тем не менее, вы увидите, что эта кнопка выглядит теперь изменив <xref:System.Windows.UIElement.Opacity%2A> значение 1, а также выполнение приложения.</span><span class="sxs-lookup"><span data-stu-id="30dc1-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="30dc1-182">См. следующий рисунок.</span><span class="sxs-lookup"><span data-stu-id="30dc1-182">See the following figure.</span></span> <span data-ttu-id="30dc1-183">Прежде чем переходить к следующему шагу изменить <xref:System.Windows.UIElement.Opacity%2A> значение 0.</span><span class="sxs-lookup"><span data-stu-id="30dc1-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="30dc1-184">![Настраиваемые кнопки, созданные с помощью XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="30dc1-184">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="30dc1-185">Создать интерактивную кнопку</span><span class="sxs-lookup"><span data-stu-id="30dc1-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="30dc1-186">В этом разделе вы создадите свойство триггеров и триггеров событий для изменения значений свойств и выполнения анимации в ответ на действия пользователя, например Наведение указателя мыши на кнопку и нажав кнопку.</span><span class="sxs-lookup"><span data-stu-id="30dc1-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="30dc1-187">Простой способ добавления интерактивности (указатель, оставьте мыши, нажмите кнопку и т. д.) является определение триггеров в шаблоне или стиле.</span><span class="sxs-lookup"><span data-stu-id="30dc1-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="30dc1-188">Для создания <xref:System.Windows.Trigger>, определять свойство «условие», такие как: кнопки <xref:System.Windows.UIElement.IsMouseOver%2A> значение свойства равно `true`.</span><span class="sxs-lookup"><span data-stu-id="30dc1-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="30dc1-189">Затем предстоит определить элементы Setter (действия), выполняемые при условия триггера.</span><span class="sxs-lookup"><span data-stu-id="30dc1-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="30dc1-190">Чтобы создать интерактивную кнопку</span><span class="sxs-lookup"><span data-stu-id="30dc1-190">To create button interactivity</span></span>  
  
1.  <span data-ttu-id="30dc1-191">**Добавить триггеры шаблона:** добавьте выделенную разметку в шаблон.</span><span class="sxs-lookup"><span data-stu-id="30dc1-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
    ```  
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
  
2.  <span data-ttu-id="30dc1-192">**Добавить триггеры свойств:** добавьте выделенную разметку для `ControlTemplate.Triggers` блока:</span><span class="sxs-lookup"><span data-stu-id="30dc1-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="30dc1-193">Нажмите клавишу F5, чтобы запустить приложение и увидеть эффект при запуске указатель мыши над кнопками.</span><span class="sxs-lookup"><span data-stu-id="30dc1-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3.  <span data-ttu-id="30dc1-194">**Добавление триггера фокус:** Далее мы добавим некоторые аналогичные методы задания для обработки случая, когда кнопка имеет фокус (например, при нажатии ее).</span><span class="sxs-lookup"><span data-stu-id="30dc1-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
    ```  
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
  
     <span data-ttu-id="30dc1-195">Нажмите клавишу F5 для запуска приложения и выберите одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="30dc1-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="30dc1-196">Обратите внимание, что кнопка остается выделенной после нажатия, поскольку она по-прежнему имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="30dc1-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="30dc1-197">Если щелкнуть еще одну кнопку «Создать» получает фокус, во время его утрачивает последним.</span><span class="sxs-lookup"><span data-stu-id="30dc1-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4.  <span data-ttu-id="30dc1-198">**Добавление анимации для** <xref:System.Windows.UIElement.MouseEnter> **и** <xref:System.Windows.UIElement.MouseLeave> **:** Далее будет добавлена анимация к триггерам.  </span><span class="sxs-lookup"><span data-stu-id="30dc1-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="30dc1-199">Добавьте следующую разметку в любое место `ControlTemplate.Triggers` блока.</span><span class="sxs-lookup"><span data-stu-id="30dc1-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="30dc1-200">Прозрачный прямоугольник уменьшается, когда указатель мыши перемещается над кнопкой и возвращает в исходное состояние, когда указатель мыши покидает.</span><span class="sxs-lookup"><span data-stu-id="30dc1-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="30dc1-201">Существуют две анимации, которые запускаются при наведении указателя мыши на кнопку (<xref:System.Windows.UIElement.MouseEnter> события).</span><span class="sxs-lookup"><span data-stu-id="30dc1-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="30dc1-202">Эти анимации сжимают прозрачный прямоугольник вдоль оси X и Y.</span><span class="sxs-lookup"><span data-stu-id="30dc1-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="30dc1-203">Обратите внимание на <xref:System.Windows.Media.Animation.DoubleAnimation> элементов — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="30dc1-204"><xref:System.Windows.Media.Animation.Timeline.Duration%2A> Указывает, что анимация выполняется через полсекунды, а <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> указывает, что прозрачный элемент сжимается на 10%.</span><span class="sxs-lookup"><span data-stu-id="30dc1-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="30dc1-205">Второй триггер события (<xref:System.Windows.UIElement.MouseLeave>) просто останавливает первое из них.</span><span class="sxs-lookup"><span data-stu-id="30dc1-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="30dc1-206">При остановке <xref:System.Windows.Media.Animation.Storyboard>, все анимированные свойства возвращаются к значениям по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="30dc1-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="30dc1-207">Таким образом когда пользователь перемещает указатель мыши за границы кнопки, кнопки возвращается так, как оно было до перемещения указателя мыши на кнопку.</span><span class="sxs-lookup"><span data-stu-id="30dc1-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="30dc1-208">Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="30dc1-208">For more information about animations, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
5.  <span data-ttu-id="30dc1-209">**Добавление анимации, при щелчке кнопки:** последний шаг — добавить триггер для при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="30dc1-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="30dc1-210">Добавьте следующую разметку в любое место `ControlTemplate.Triggers` блока:</span><span class="sxs-lookup"><span data-stu-id="30dc1-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
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
  
     <span data-ttu-id="30dc1-211">Нажмите клавишу F5, чтобы запустить приложение и щелкните одну из кнопок.</span><span class="sxs-lookup"><span data-stu-id="30dc1-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="30dc1-212">При нажатии кнопки вращаться прозрачного прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="30dc1-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="30dc1-213">Сводка</span><span class="sxs-lookup"><span data-stu-id="30dc1-213">Summary</span></span>  
 <span data-ttu-id="30dc1-214">В этом пошаговом руководстве вы выполнили следующие упражнения:</span><span class="sxs-lookup"><span data-stu-id="30dc1-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="30dc1-215">Целевые <xref:System.Windows.Style> к типу объекта (<xref:System.Windows.Controls.Button>).</span><span class="sxs-lookup"><span data-stu-id="30dc1-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="30dc1-216">Управление основными свойствами кнопок в всего приложения с помощью <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="30dc1-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="30dc1-217">Создать ресурсы, такие как градиенты, для использования в качестве значений свойств для <xref:System.Windows.Style> задания.</span><span class="sxs-lookup"><span data-stu-id="30dc1-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="30dc1-218">Настройка внешнего вида кнопок во всем приложении путем применения шаблона к кнопкам.</span><span class="sxs-lookup"><span data-stu-id="30dc1-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="30dc1-219">Настройка поведения для кнопок в ответ на действия пользователя (например, <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, и <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), которые включены эффекты анимации.</span><span class="sxs-lookup"><span data-stu-id="30dc1-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dc1-220">См. также</span><span class="sxs-lookup"><span data-stu-id="30dc1-220">See Also</span></span>  
 [<span data-ttu-id="30dc1-221">Создание кнопки с помощью Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="30dc1-221">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [<span data-ttu-id="30dc1-222">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="30dc1-222">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="30dc1-223">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="30dc1-223">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="30dc1-224">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="30dc1-224">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="30dc1-225">Общие сведения об эффектах для точечных рисунков</span><span class="sxs-lookup"><span data-stu-id="30dc1-225">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
