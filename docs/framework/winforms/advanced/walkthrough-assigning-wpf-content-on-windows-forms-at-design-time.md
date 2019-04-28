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
ms.openlocfilehash: b4efef869c96ddb4e58445e45ecad12b5658f9f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61748894"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="09419-102">Пошаговое руководство. Назначение содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="09419-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="09419-103">В этом пошаговом руководстве показано, как выбрать типы элементов управления Windows Presentation Foundation (WPF), которые будут отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="09419-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="09419-104">Можно выбрать любые типы элементов управления WPF, включенные в проект.</span><span class="sxs-lookup"><span data-stu-id="09419-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="09419-105">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="09419-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="09419-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="09419-106">Create the project.</span></span>

- <span data-ttu-id="09419-107">Создание типов элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="09419-107">Create the WPF control types.</span></span>

- <span data-ttu-id="09419-108">Выбор элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="09419-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="09419-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="09419-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="09419-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="09419-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="09419-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="09419-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="09419-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="09419-112">Prerequisites</span></span>  
 <span data-ttu-id="09419-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="09419-113">You need the following components to complete this walkthrough:</span></span>  
  
- <span data-ttu-id="09419-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="09419-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="09419-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="09419-115">Creating the Project</span></span>  
 <span data-ttu-id="09419-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="09419-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09419-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="09419-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="09419-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="09419-118">To create the project</span></span>  
  
- <span data-ttu-id="09419-119">Создание нового проекта приложения Windows Forms в Visual Basic или Visual C# с именем `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="09419-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="09419-120">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="09419-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="09419-121">После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="09419-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="09419-122">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="09419-122">To create WPF control types</span></span>  
  
1. <span data-ttu-id="09419-123">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="09419-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="09419-124">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="09419-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="09419-125">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="09419-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="09419-126">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="09419-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="09419-127">Дополнительные сведения см. в разделе [Как Выберите и перемещать элементы в области конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="09419-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="09419-128">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="09419-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4. <span data-ttu-id="09419-129">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content**.</span><span class="sxs-lookup"><span data-stu-id="09419-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5. <span data-ttu-id="09419-130">Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="09419-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="09419-131">Используйте имя по умолчанию для этого типа элемента управления (`UserControl2.xaml`).</span><span class="sxs-lookup"><span data-stu-id="09419-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6. <span data-ttu-id="09419-132">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="09419-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7. <span data-ttu-id="09419-133">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="09419-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="09419-134">**Примечание** в общем случае следует размещать более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="09419-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="09419-135">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="09419-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1. <span data-ttu-id="09419-136">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="09419-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="09419-137">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="09419-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="09419-138">Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="09419-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="09419-139">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="09419-139">To select WPF controls</span></span>  
  
1. <span data-ttu-id="09419-140">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="09419-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="09419-141">В **элементов**, дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="09419-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="09419-142">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="09419-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3. <span data-ttu-id="09419-143">В панели смарт-тега для `elementHost1`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="09419-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4. <span data-ttu-id="09419-144">Выберите **UserControl2** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="09419-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="09419-145">В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="09419-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5. <span data-ttu-id="09419-146">В **свойства** окна, убедитесь, что <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="09419-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6. <span data-ttu-id="09419-147">Из **элементов**в **взаимодействие с WPF** группе, перетащите <xref:System.Windows.Forms.Integration.ElementHost> на форму.</span><span class="sxs-lookup"><span data-stu-id="09419-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="09419-148">Имя по умолчанию для нового элемента управления — `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="09419-148">The default name for the new control is `elementHost2`.</span></span>  
  
7. <span data-ttu-id="09419-149">В панели смарт-тега для `elementHost2`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="09419-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8. <span data-ttu-id="09419-150">Выберите **UserControl1** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="09419-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="09419-151">В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="09419-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09419-152">См. также</span><span class="sxs-lookup"><span data-stu-id="09419-152">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="09419-153">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="09419-153">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="09419-154">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="09419-154">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="09419-155">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="09419-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
