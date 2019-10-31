---
title: Пошаговое руководство. Применение стилей к содержимому WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8b9e2c5c05f1a4b263890c2d8ca8474abe07d836
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197410"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="3287f-102">Пошаговое руководство. стиль содержимого WPF</span><span class="sxs-lookup"><span data-stu-id="3287f-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="3287f-103">В этой статье показано, как применять стили к элементу управления Windows Presentation Foundation (WPF), размещенному в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3287f-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3287f-104">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="3287f-104">Prerequisites</span></span>

<span data-ttu-id="3287f-105">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3287f-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="3287f-106">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="3287f-106">Create the project</span></span>

<span data-ttu-id="3287f-107">Откройте Visual Studio и создайте новый проект Windows Forms приложения в Visual Basic или Visual C# с именем `StylingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="3287f-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="3287f-108">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3287f-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="3287f-109">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="3287f-109">Create the WPF control types</span></span>

<span data-ttu-id="3287f-110">После добавления в проект типа элемента управления WPF можно разместить его в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="3287f-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="3287f-111">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="3287f-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="3287f-112">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="3287f-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="3287f-113">Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="3287f-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="3287f-114">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="3287f-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="3287f-115">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="3287f-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="3287f-116">Добавьте элемент управления <xref:System.Windows.Controls.Button?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.ContentControl.Content%2A> значение **Cancel**.</span><span class="sxs-lookup"><span data-stu-id="3287f-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="3287f-117">Добавьте второй элемент управления <xref:System.Windows.Controls.Button?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.ContentControl.Content%2A> значение **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3287f-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="3287f-118">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="3287f-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="3287f-119">Применение стиля к элементу управления WPF</span><span class="sxs-lookup"><span data-stu-id="3287f-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="3287f-120">Для изменения внешнего вида и поведения элемента управления WPF к нему можно применить различные стили.</span><span class="sxs-lookup"><span data-stu-id="3287f-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="3287f-121">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3287f-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="3287f-122">На **панели элементов**дважды щелкните `UserControl1`, чтобы создать экземпляр `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="3287f-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="3287f-123">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="3287f-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="3287f-124">На панели смарт-тегов для `elementHost1`щелкните **Изменить размещенное содержимое** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="3287f-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="3287f-125">`UserControl1` откроется в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="3287f-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="3287f-126">В представлении XAML вставьте следующий код XAML после открывающего тега `<UserControl>` .</span><span class="sxs-lookup"><span data-stu-id="3287f-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="3287f-127">Этот код XAML создает градиент с контрастной градиентной границей.</span><span class="sxs-lookup"><span data-stu-id="3287f-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="3287f-128">При нажатии на элемент управления градиенты изменяются, формируя образ нажатой кнопки.</span><span class="sxs-lookup"><span data-stu-id="3287f-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="3287f-129">Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="3287f-129">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. <span data-ttu-id="3287f-130">Примените стиль `SimpleButton`, определенный на предыдущем шаге, к кнопке Отмена, вставив следующий код XAML в тег `<Button>` кнопки **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="3287f-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="3287f-131">Объявление кнопки будет похоже на следующий XAML:</span><span class="sxs-lookup"><span data-stu-id="3287f-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="3287f-132">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="3287f-132">Build the project.</span></span>

1. <span data-ttu-id="3287f-133">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3287f-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="3287f-134">Новый стиль применяется для элемента управления button.</span><span class="sxs-lookup"><span data-stu-id="3287f-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="3287f-135">В меню **Отладка** выберите команду **начать отладку** , чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="3287f-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="3287f-136">Нажмите кнопки **ОК** и **Отмена** и просмотрите различия.</span><span class="sxs-lookup"><span data-stu-id="3287f-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="3287f-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3287f-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3287f-138">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="3287f-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="3287f-139">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="3287f-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="3287f-140">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3287f-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="3287f-141">Общие сведения о языке XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="3287f-141">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="3287f-142">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="3287f-142">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
