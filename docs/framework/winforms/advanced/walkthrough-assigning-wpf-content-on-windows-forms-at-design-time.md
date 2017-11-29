---
title: "Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fa9e40a0a32d0bc9484a86da0f94d62f5c25aa7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-assigning-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="fc683-102">Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="fc683-102">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="fc683-103">В этом пошаговом руководстве показано, как выбрать типы элементов управления Windows Presentation Foundation (WPF), которые будут отображаться в форме.</span><span class="sxs-lookup"><span data-stu-id="fc683-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="fc683-104">Можно выбрать любые типы элементов управления WPF, включенные в проект.</span><span class="sxs-lookup"><span data-stu-id="fc683-104">You can select any WPF control types which are included in your project.</span></span>  
  
 <span data-ttu-id="fc683-105">В этом пошаговом руководстве выполняются следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="fc683-105">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="fc683-106">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="fc683-106">Create the project.</span></span>  
  
-   <span data-ttu-id="fc683-107">Создание типов элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="fc683-107">Create the WPF control types.</span></span>  
  
-   <span data-ttu-id="fc683-108">Выбор элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="fc683-108">Select WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc683-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="fc683-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fc683-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="fc683-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fc683-111">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fc683-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fc683-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="fc683-112">Prerequisites</span></span>  
 <span data-ttu-id="fc683-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="fc683-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="fc683-114">.</span><span class="sxs-lookup"><span data-stu-id="fc683-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="fc683-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="fc683-115">Creating the Project</span></span>  
 <span data-ttu-id="fc683-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fc683-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc683-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fc683-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="fc683-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="fc683-118">To create the project</span></span>  
  
-   <span data-ttu-id="fc683-119">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `SelectingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="fc683-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="fc683-120">Создание типов элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-120">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="fc683-121">После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="fc683-121">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="fc683-122">Создание типов элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-122">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="fc683-123">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="fc683-123">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="fc683-124">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="fc683-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="fc683-125">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="fc683-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="fc683-126">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="fc683-126">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="fc683-127">Дополнительные сведения см. в разделе [как: Выбор и перемещение элементов в рабочей области конструирования](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="fc683-127">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="fc683-128">В **свойства** задайте значение <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="fc683-128">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="fc683-129">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и задать значение <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content**.</span><span class="sxs-lookup"><span data-stu-id="fc683-129">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
5.  <span data-ttu-id="fc683-130">Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="fc683-130">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="fc683-131">Используйте имя по умолчанию для этого типа элемента управления (`UserControl2.xaml`).</span><span class="sxs-lookup"><span data-stu-id="fc683-131">Use the default name for the control type, `UserControl2.xaml`.</span></span>  
  
6.  <span data-ttu-id="fc683-132">В **свойства** задайте значение <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="fc683-132">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
7.  <span data-ttu-id="fc683-133">Добавить <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления <xref:System.Windows.Controls.UserControl> и задать значение <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content 2**.</span><span class="sxs-lookup"><span data-stu-id="fc683-133">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>  
  
 <span data-ttu-id="fc683-134">**Примечание** как правило, требуется размещать более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="fc683-134">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="fc683-135">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется в данном случае только в иллюстративных целях.</span><span class="sxs-lookup"><span data-stu-id="fc683-135">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
1.  <span data-ttu-id="fc683-136">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="fc683-136">Build the project.</span></span>  
  
## <a name="selecting-wpf-controls"></a><span data-ttu-id="fc683-137">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-137">Selecting WPF Controls</span></span>  
 <span data-ttu-id="fc683-138">Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="fc683-138">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>  
  
#### <a name="to-select-wpf-controls"></a><span data-ttu-id="fc683-139">Выбор элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-139">To select WPF controls</span></span>  
  
1.  <span data-ttu-id="fc683-140">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fc683-140">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="fc683-141">В **элементов**, дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="fc683-141">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="fc683-142">Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="fc683-142">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="fc683-143">В панели смарт-тега для `elementHost1`откройте **выбрать размещенное содержимое** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fc683-143">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>  
  
4.  <span data-ttu-id="fc683-144">Выберите **UserControl2** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fc683-144">Select **UserControl2** from the drop-down list box.</span></span>  
  
     <span data-ttu-id="fc683-145">В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.</span><span class="sxs-lookup"><span data-stu-id="fc683-145">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>  
  
5.  <span data-ttu-id="fc683-146">В **свойства** окна, убедитесь, что <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству **UserControl2**.</span><span class="sxs-lookup"><span data-stu-id="fc683-146">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>  
  
6.  <span data-ttu-id="fc683-147">Из **элементов**в **взаимодействие с WPF** группы, перетащите <xref:System.Windows.Forms.Integration.ElementHost> в форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fc683-147">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>  
  
     <span data-ttu-id="fc683-148">Имя по умолчанию для нового элемента управления — `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="fc683-148">The default name for the new control is `elementHost2`.</span></span>  
  
7.  <span data-ttu-id="fc683-149">В панели смарт-тега для `elementHost2`откройте **выбрать размещенное содержимое** раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fc683-149">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>  
  
8.  <span data-ttu-id="fc683-150">Выберите **UserControl1** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="fc683-150">Select **UserControl1** from the drop-down list.</span></span>  
  
9. <span data-ttu-id="fc683-151">В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="fc683-151">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc683-152">См. также</span><span class="sxs-lookup"><span data-stu-id="fc683-152">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="fc683-153">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="fc683-153">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="fc683-154">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-154">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="fc683-155">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="fc683-155">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
