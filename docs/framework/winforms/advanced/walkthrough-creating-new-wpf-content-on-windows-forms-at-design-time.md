---
title: Пошаговое руководство. Создание содержимого WPF для формы Windows Forms во время разработки
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 889e81053d4e2264755468446a4e1681216ae22e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040378"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="94507-102">Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="94507-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="94507-103">В этой статье показано, как создать элемент управления Windows Presentation Foundation (WPF) для использования в приложениях на основе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94507-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="94507-104">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="94507-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="94507-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="94507-105">Create the project.</span></span>

- <span data-ttu-id="94507-106">создание элемента управления WPF;</span><span class="sxs-lookup"><span data-stu-id="94507-106">Create a new WPF control.</span></span>

- <span data-ttu-id="94507-107">добавление нового элемента управления WPF в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94507-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="94507-108">Элемент управления WPF размещается в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="94507-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94507-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="94507-109">Prerequisites</span></span>

<span data-ttu-id="94507-110">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="94507-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="94507-111">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94507-111">Visual Studio</span></span>

## <a name="create-the-project"></a><span data-ttu-id="94507-112">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="94507-112">Create the project</span></span>

<span data-ttu-id="94507-113">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94507-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="94507-114">Откройте Visual Studio и создайте новый проект **Windows Forms приложения (.NET Framework)** в Visual Basic или Visual C# с именем `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="94507-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="94507-115">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="94507-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="94507-116">Создание нового элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="94507-116">Create a new WPF control</span></span>

<span data-ttu-id="94507-117">Создать элемент управления WPF и добавить его в проект можно так же легко, как добавить в проект любой другой элемент.</span><span class="sxs-lookup"><span data-stu-id="94507-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="94507-118">Конструктор Windows Forms работает с определенным видом элемента управления с именем *составного элемента*управления или *пользовательским элементом управления*.</span><span class="sxs-lookup"><span data-stu-id="94507-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="94507-119">Подробнее о пользовательских элементах управления WPF см. в разделе <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="94507-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="94507-120">Тип <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> для элементов управления WPF отличается от типа пользовательских элементов управления, предоставляемого Windows Forms, который также называется <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94507-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="94507-121">Чтобы создать новый элемент управления WPF, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="94507-121">To create a new WPF control:</span></span>

1. <span data-ttu-id="94507-122">В **Обозреватель решений**добавьте в решение новый проект **библиотеки пользовательских элементов управления WPF (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="94507-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="94507-123">Используйте имя по умолчанию для библиотеки элементов управления (`WpfControlLibrary1`).</span><span class="sxs-lookup"><span data-stu-id="94507-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="94507-124">Имя элемента управления по умолчанию — `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="94507-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="94507-125">Добавление нового элемента управления имеет следующие последствия.</span><span class="sxs-lookup"><span data-stu-id="94507-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="94507-126">Добавляется файл UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="94507-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="94507-127">Добавляется файл UserControl1.xaml.cs или UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="94507-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="94507-128">Этот файл содержит код программной части для обработчиков событий и иных реализованных компонентов.</span><span class="sxs-lookup"><span data-stu-id="94507-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="94507-129">Добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="94507-130">Файл UserControl1.xaml открывается в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94507-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="94507-131">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="94507-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="94507-132">Дополнительные сведения см. в разделе [Практическое руководство. Выберите и переместите элементы в область конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="94507-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="94507-133">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="94507-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="94507-134">Перетащите<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> элемент управления из области **элементов**в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="94507-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="94507-135">В окне **Свойства** присвойте <xref:System.Windows.Controls.TextBox.Text%2A> свойству значение **размещенное содержимое**.</span><span class="sxs-lookup"><span data-stu-id="94507-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94507-136">Обычно размещается более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="94507-137">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="94507-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="94507-138">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="94507-138">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="94507-139">Добавление элемента управления WPF в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94507-139">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="94507-140">Новый элемент управления WPF готов к использованию в форме.</span><span class="sxs-lookup"><span data-stu-id="94507-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="94507-141">Windows Forms использует <xref:System.Windows.Forms.Integration.ElementHost> элемент управления для размещения содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="94507-142">Чтобы добавить элемент управления WPF в форму Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="94507-142">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="94507-143">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94507-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="94507-144">На **панели элементов**найдите вкладку с надписью **впфусерконтроллибрари User Controls (пользовательские элементы управления WPF**).</span><span class="sxs-lookup"><span data-stu-id="94507-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="94507-145">Перетащите экземпляр `UserControl1` в форму.</span><span class="sxs-lookup"><span data-stu-id="94507-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="94507-146">Для размещения элемента управления WPF на форме будет автоматически создан элемент управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="94507-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="94507-147"><xref:System.Windows.Forms.Integration.ElementHost.Child%2A> Элемент управления называется, и в окне Свойства можно увидеть, что его свойство имеет значение UserControl1. `elementHost1` <xref:System.Windows.Forms.Integration.ElementHost></span><span class="sxs-lookup"><span data-stu-id="94507-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="94507-148">В проект добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="94507-149">Элемент управления `elementHost1` имеет панель смарт-тегов, на которой приводятся имеющиеся параметры размещения.</span><span class="sxs-lookup"><span data-stu-id="94507-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="94507-150">На панели смарт-тегов **Задачи ElementHost** выберите закрепить **в родительском контейнере**.</span><span class="sxs-lookup"><span data-stu-id="94507-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="94507-151">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="94507-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94507-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="94507-152">Next steps</span></span>

<span data-ttu-id="94507-153">Windows Forms и WPF — это разные технологии, но они предназначены для тесного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="94507-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="94507-154">Чтобы обеспечить расширенный внешний вид и поведение приложений, попробуйте выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="94507-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="94507-155">Размещение элемента управления Windows Forms на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="94507-156">Дополнительные сведения см. в разделе [Пошаговое руководство: Размещение элемента управления Windows Forms в WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="94507-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="94507-157">Применение стилей оформления Windows Forms к содержимому WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="94507-158">Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)приложении.</span><span class="sxs-lookup"><span data-stu-id="94507-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="94507-159">Изменение стиля оформления содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-159">Change the style of your WPF content.</span></span> <span data-ttu-id="94507-160">Дополнительные сведения см. в разделе [Пошаговое руководство: Стилизация содержимого](walkthrough-styling-wpf-content.md)WPF.</span><span class="sxs-lookup"><span data-stu-id="94507-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94507-161">См. также</span><span class="sxs-lookup"><span data-stu-id="94507-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="94507-162">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="94507-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="94507-163">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="94507-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="94507-164">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94507-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
