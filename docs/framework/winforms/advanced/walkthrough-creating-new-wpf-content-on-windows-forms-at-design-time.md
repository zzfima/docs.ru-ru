---
title: Создание нового содержимого WPF на Windows Forms
titleSuffix: ''
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 69a0598b05d1b2bff84b203317d6d5a166ce109d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746386"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="0f3c6-102">Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="0f3c6-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="0f3c6-103">В этой статье показано, как создать элемент управления Windows Presentation Foundation (WPF) для использования в приложениях на основе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0f3c6-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="0f3c6-104">Prerequisites</span></span>

<span data-ttu-id="0f3c6-105">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0f3c6-106">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="0f3c6-106">Create the project</span></span>

<span data-ttu-id="0f3c6-107">Откройте Visual Studio и создайте новый проект **Windows Forms приложения (.NET Framework)** в Visual Basic или Visual C# с именем `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="0f3c6-108">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="0f3c6-109">Создание нового элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="0f3c6-109">Create a new WPF control</span></span>

<span data-ttu-id="0f3c6-110">Создать элемент управления WPF и добавить его в проект можно так же легко, как добавить в проект любой другой элемент.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="0f3c6-111">Конструктор Windows Forms работает с определенным видом элемента управления с именем *составного элемента*управления или *пользовательским элементом управления*.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="0f3c6-112">Подробнее о пользовательских элементах управления WPF см. в разделе <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="0f3c6-113">Тип <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> для элементов управления WPF отличается от типа пользовательских элементов управления, предоставляемого Windows Forms, который также называется <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="0f3c6-114">Чтобы создать новый элемент управления WPF, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="0f3c6-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="0f3c6-115">В **Обозреватель решений**добавьте в решение новый проект **библиотеки пользовательских элементов управления WPF (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="0f3c6-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="0f3c6-116">Используйте имя по умолчанию для библиотеки элементов управления (`WpfControlLibrary1`).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="0f3c6-117">Имя элемента управления по умолчанию — `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="0f3c6-118">Добавление нового элемента управления имеет следующие последствия.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="0f3c6-119">Добавляется файл UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="0f3c6-120">Добавлен файл UserControl1.xaml.cs (или UserControl1. XAML. vb).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="0f3c6-121">Этот файл содержит код программной части для обработчиков событий и иных реализованных компонентов.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="0f3c6-122">Добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="0f3c6-123">Файл UserControl1. XAML откроется в конструкторе WPF для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="0f3c6-124">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="0f3c6-125">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="0f3c6-126">Перетащите элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> из области **элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="0f3c6-127">В окне **Свойства** задайте для свойства <xref:System.Windows.Controls.TextBox.Text%2A> значение **размещенное содержимое**.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0f3c6-128">Обычно размещается более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="0f3c6-129">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="0f3c6-130">Постройте проект.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="0f3c6-131">Добавление элемента управления WPF в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f3c6-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="0f3c6-132">Новый элемент управления WPF готов к использованию в форме.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="0f3c6-133">Windows Forms использует элемент управления <xref:System.Windows.Forms.Integration.ElementHost> для размещения содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="0f3c6-134">Чтобы добавить элемент управления WPF в форму Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="0f3c6-135">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="0f3c6-136">На **панели элементов**найдите вкладку с надписью **впфусерконтроллибрари User Controls (пользовательские элементы управления WPF**).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="0f3c6-137">Перетащите экземпляр `UserControl1` в форму.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="0f3c6-138">Для размещения элемента управления WPF на форме будет автоматически создан элемент управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="0f3c6-139">Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> называется `elementHost1` и в окне **Свойства** можно увидеть, что его свойство <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> имеет значение **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="0f3c6-140">В проект добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="0f3c6-141">Элемент управления `elementHost1` имеет панель смарт-тегов, на которой приводятся имеющиеся параметры размещения.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="0f3c6-142">На панели смарт-тегов **Задачи ElementHost** выберите **закрепить в родительском контейнере**.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="0f3c6-143">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f3c6-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="0f3c6-144">Next steps</span></span>

<span data-ttu-id="0f3c6-145">Windows Forms и WPF — это разные технологии, но они предназначены для тесного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="0f3c6-146">Чтобы обеспечить расширенный внешний вид и поведение приложений, попробуйте выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="0f3c6-147">Размещение элемента управления Windows Forms на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="0f3c6-148">Дополнительные сведения см. [в разделе Пошаговое руководство. размещение элемента управления Windows Forms в WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="0f3c6-149">Применение стилей оформления Windows Forms к содержимому WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="0f3c6-150">Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="0f3c6-151">Изменение стиля оформления содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="0f3c6-151">Change the style of your WPF content.</span></span> <span data-ttu-id="0f3c6-152">Дополнительные сведения см. в разделе [Пошаговое руководство. стилизация содержимого WPF](walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="0f3c6-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f3c6-153">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f3c6-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0f3c6-154">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="0f3c6-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0f3c6-155">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="0f3c6-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="0f3c6-156">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0f3c6-156">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
