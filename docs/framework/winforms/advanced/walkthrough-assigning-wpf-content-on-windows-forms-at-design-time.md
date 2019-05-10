---
title: Пошаговое руководство. Назначение содержимого WPF для формы Windows Forms во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211238"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="0a3de-102">Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="0a3de-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="0a3de-103">В этом пошаговом руководстве показано, как выбрать типы элементов управления Windows Presentation Foundation (WPF), которые будут отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="0a3de-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="0a3de-104">Можно выбрать любые типы элементов управления WPF, включенные в проект.</span><span class="sxs-lookup"><span data-stu-id="0a3de-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="0a3de-105">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="0a3de-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="0a3de-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="0a3de-106">Create the project.</span></span>

- <span data-ttu-id="0a3de-107">Создание типов элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="0a3de-107">Create the WPF control types.</span></span>

- <span data-ttu-id="0a3de-108">Выбор элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="0a3de-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a3de-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0a3de-109">Prerequisites</span></span>

<span data-ttu-id="0a3de-110">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0a3de-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="0a3de-111">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="0a3de-111">Create the project</span></span>

<span data-ttu-id="0a3de-112">Откройте Visual Studio и создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="0a3de-113">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0a3de-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="0a3de-114">Создание типов элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="0a3de-114">Create the WPF control types</span></span>

<span data-ttu-id="0a3de-115">После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="0a3de-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="0a3de-116">Создание типов элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="0a3de-116">Create WPF control types</span></span>

1. <span data-ttu-id="0a3de-117">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="0a3de-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="0a3de-118">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="0a3de-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="0a3de-119">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="0a3de-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="0a3de-120">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="0a3de-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="0a3de-121">Дополнительные сведения см. в разделе [Как Выберите и перемещать элементы в области конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0a3de-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="0a3de-122">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="0a3de-123">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content**.</span><span class="sxs-lookup"><span data-stu-id="0a3de-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="0a3de-124">Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="0a3de-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="0a3de-125">Используйте имя по умолчанию для этого типа элемента управления (`UserControl2.xaml`).</span><span class="sxs-lookup"><span data-stu-id="0a3de-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="0a3de-126">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="0a3de-127">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="0a3de-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="0a3de-128">**Примечание** в общем случае следует размещать более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="0a3de-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="0a3de-129">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="0a3de-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="0a3de-130">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="0a3de-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="0a3de-131">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="0a3de-131">Select WPF controls</span></span>

<span data-ttu-id="0a3de-132">Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="0a3de-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="0a3de-133">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0a3de-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="0a3de-134">В **элементов**, дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="0a3de-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="0a3de-135">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="0a3de-136">В панели смарт-тега для `elementHost1`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="0a3de-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="0a3de-137">Выберите **UserControl2** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="0a3de-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="0a3de-138">В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="0a3de-139">В **свойства** окна, убедитесь, что <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="0a3de-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="0a3de-140">Из **элементов**в **взаимодействие с WPF** группе, перетащите <xref:System.Windows.Forms.Integration.ElementHost> на форму.</span><span class="sxs-lookup"><span data-stu-id="0a3de-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="0a3de-141">Имя по умолчанию для нового элемента управления — `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="0a3de-142">В панели смарт-тега для `elementHost2`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="0a3de-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="0a3de-143">Выберите **UserControl1** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="0a3de-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="0a3de-144">В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="0a3de-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a3de-145">См. также</span><span class="sxs-lookup"><span data-stu-id="0a3de-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0a3de-146">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="0a3de-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="0a3de-147">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="0a3de-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="0a3de-148">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a3de-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
