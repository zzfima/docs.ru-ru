---
title: Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0c1e0c91b7ab8bded677a86b597b02b9cb442d98
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460675"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="48f61-102">Пошаговое руководство. Назначение содержимого WPF на Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="48f61-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="48f61-103">В этой статье показано, как выбрать типы элементов управления Windows Presentation Foundation (WPF), которые должны отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="48f61-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="48f61-104">Можно выбрать любые типы элементов управления WPF, включенные в проект.</span><span class="sxs-lookup"><span data-stu-id="48f61-104">You can select any WPF control types which are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48f61-105">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="48f61-105">Prerequisites</span></span>

<span data-ttu-id="48f61-106">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="48f61-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="48f61-107">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="48f61-107">Create the project</span></span>

<span data-ttu-id="48f61-108">Откройте Visual Studio и создайте новый проект Windows Forms приложения в Visual Basic или Visual C# с именем `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="48f61-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="48f61-109">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="48f61-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="48f61-110">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="48f61-110">Create the WPF control types</span></span>

<span data-ttu-id="48f61-111">После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="48f61-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="48f61-112">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="48f61-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="48f61-113">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="48f61-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="48f61-114">Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="48f61-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="48f61-115">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="48f61-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="48f61-116">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="48f61-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="48f61-117">Добавьте элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и задайте для свойства <xref:System.Windows.Controls.TextBox.Text%2A> **размещенное содержимое**.</span><span class="sxs-lookup"><span data-stu-id="48f61-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="48f61-118">Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="48f61-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="48f61-119">Используйте имя по умолчанию для этого типа элемента управления (`UserControl2.xaml`).</span><span class="sxs-lookup"><span data-stu-id="48f61-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="48f61-120">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="48f61-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="48f61-121">Добавьте элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и установите значение свойства <xref:System.Windows.Controls.TextBox.Text%2A> в **размещенное содержимое 2**.</span><span class="sxs-lookup"><span data-stu-id="48f61-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48f61-122">Обычно размещается более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="48f61-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="48f61-123">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="48f61-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="48f61-124">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="48f61-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="48f61-125">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="48f61-125">Select WPF controls</span></span>

<span data-ttu-id="48f61-126">Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="48f61-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="48f61-127">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="48f61-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="48f61-128">На **панели элементов**дважды щелкните `UserControl1`, чтобы создать экземпляр `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="48f61-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="48f61-129">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="48f61-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="48f61-130">На панели смарт-тегов для `elementHost1`откройте раскрывающийся список **выберите размещенное содержимое** .</span><span class="sxs-lookup"><span data-stu-id="48f61-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="48f61-131">В раскрывающемся списке выберите **UserControl2** .</span><span class="sxs-lookup"><span data-stu-id="48f61-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="48f61-132">В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="48f61-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="48f61-133">В окне **Свойства** убедитесь, что для свойства <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> задано значение **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="48f61-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="48f61-134">Из **панели элементов**в группе **взаимодействие WPF** перетащите элемент управления <xref:System.Windows.Forms.Integration.ElementHost> на форму.</span><span class="sxs-lookup"><span data-stu-id="48f61-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="48f61-135">Имя по умолчанию для нового элемента управления — `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="48f61-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="48f61-136">На панели смарт-тегов для `elementHost2`откройте раскрывающийся список **выберите размещенное содержимое** .</span><span class="sxs-lookup"><span data-stu-id="48f61-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="48f61-137">Выберите элемент **UserControl1** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="48f61-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="48f61-138">В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="48f61-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="48f61-139">См. также</span><span class="sxs-lookup"><span data-stu-id="48f61-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="48f61-140">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="48f61-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="48f61-141">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="48f61-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="48f61-142">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="48f61-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
