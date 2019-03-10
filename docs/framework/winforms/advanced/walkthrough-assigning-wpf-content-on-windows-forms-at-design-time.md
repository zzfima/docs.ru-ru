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
ms.openlocfilehash: 364cfe521a1e141bdfcfb3cfc47170714d010a87
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707928"
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="1c614-102">Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="1c614-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="1c614-103">В этом пошаговом руководстве показано, как выбрать типы элементов управления Windows Presentation Foundation (WPF), которые будут отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="1c614-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="1c614-104">Можно выбрать любые типы элементов управления WPF, включенные в проект.</span><span class="sxs-lookup"><span data-stu-id="1c614-104">You can select any WPF control types which are included in your project.</span></span>

 <span data-ttu-id="1c614-105">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="1c614-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="1c614-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="1c614-106">Create the project.</span></span>

-   <span data-ttu-id="1c614-107">Создание типов элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="1c614-107">Create the WPF control types.</span></span>

-   <span data-ttu-id="1c614-108">Выбор элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="1c614-108">Select WPF controls.</span></span>

> [!NOTE]
>  <span data-ttu-id="1c614-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="1c614-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1c614-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="1c614-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1c614-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="1c614-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1c614-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="1c614-112">Prerequisites</span></span>  
 <span data-ttu-id="1c614-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="1c614-113">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="1c614-114">Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="1c614-114">Visual Studio 2012.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="1c614-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1c614-115">Creating the Project</span></span>  
 <span data-ttu-id="1c614-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1c614-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c614-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c614-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="1c614-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1c614-118">To create the project</span></span>  
  
-   <span data-ttu-id="1c614-119">Создание нового проекта приложения Windows Forms в Visual Basic или Visual C# с именем `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="1c614-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="1c614-120">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1c614-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="1c614-121">После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="1c614-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="1c614-122">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1c614-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="1c614-123">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="1c614-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="1c614-124">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="1c614-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="1c614-125">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="1c614-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="1c614-126">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="1c614-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="1c614-127">Дополнительные сведения см. в разделе [Как Выберите и перемещать элементы в области конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1c614-127">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="1c614-128">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="1c614-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="1c614-129">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content**.</span><span class="sxs-lookup"><span data-stu-id="1c614-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="1c614-130">Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="1c614-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="1c614-131">Используйте имя по умолчанию для этого типа элемента управления (`UserControl2.xaml`).</span><span class="sxs-lookup"><span data-stu-id="1c614-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="1c614-132">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="1c614-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="1c614-133">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и установите для параметра <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="1c614-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="1c614-134">**Примечание** в общем случае следует размещать более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="1c614-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="1c614-135">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="1c614-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="1c614-136">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="1c614-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="1c614-137">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1c614-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="1c614-138">Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="1c614-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="1c614-139">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1c614-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="1c614-140">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1c614-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="1c614-141">В **элементов**, дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="1c614-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="1c614-142">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="1c614-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="1c614-143">В панели смарт-тега для `elementHost1`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1c614-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="1c614-144">Выберите **UserControl2** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1c614-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="1c614-145">В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="1c614-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="1c614-146">В **свойства** окна, убедитесь, что <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="1c614-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="1c614-147">Из **элементов**в **взаимодействие с WPF** группе, перетащите <xref:System.Windows.Forms.Integration.ElementHost> на форму.</span><span class="sxs-lookup"><span data-stu-id="1c614-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="1c614-148">Имя по умолчанию для нового элемента управления — `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="1c614-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="1c614-149">В панели смарт-тега для `elementHost2`откройте **выбрать размещенное содержимое** стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1c614-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="1c614-150">Выберите **UserControl1** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="1c614-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="1c614-151">В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="1c614-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c614-152">См. также</span><span class="sxs-lookup"><span data-stu-id="1c614-152">See also</span></span>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1c614-153">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="1c614-153">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="1c614-154">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="1c614-154">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="1c614-155">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1c614-155">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
