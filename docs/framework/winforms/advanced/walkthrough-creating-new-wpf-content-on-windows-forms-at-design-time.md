---
title: "Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cfbe9957fa8d18f839ae656ca721c4ee88475a5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="457d3-102">Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="457d3-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="457d3-103">В этом разделе показано, как создать элемент управления Windows Presentation Foundation (WPF) для использования в приложениях на основе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="457d3-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="457d3-104">В этом пошаговом руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="457d3-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="457d3-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="457d3-105">Create the project.</span></span>  
  
-   <span data-ttu-id="457d3-106">создание элемента управления WPF;</span><span class="sxs-lookup"><span data-stu-id="457d3-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="457d3-107">добавление нового элемента управления WPF в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="457d3-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="457d3-108">Элемент управления WPF размещается в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="457d3-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457d3-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="457d3-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="457d3-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="457d3-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="457d3-111">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="457d3-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="457d3-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="457d3-112">Prerequisites</span></span>  
 <span data-ttu-id="457d3-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="457d3-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="457d3-114">.</span><span class="sxs-lookup"><span data-stu-id="457d3-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="457d3-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="457d3-115">Creating the Project</span></span>  
 <span data-ttu-id="457d3-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="457d3-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457d3-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="457d3-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="457d3-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="457d3-118">To create the project</span></span>  
  
-   <span data-ttu-id="457d3-119">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `HostingWpf`.</span><span class="sxs-lookup"><span data-stu-id="457d3-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="457d3-120">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="457d3-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="457d3-121">Создать элемент управления WPF и добавить его в проект можно так же легко, как добавить в проект любой другой элемент.</span><span class="sxs-lookup"><span data-stu-id="457d3-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="457d3-122">Конструктор Windows Forms работает с элементами управления особого типа с именем *составного элемента управления*, или *пользовательский элемент управления*.</span><span class="sxs-lookup"><span data-stu-id="457d3-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="457d3-123">Подробнее о пользовательских элементах управления WPF см. в разделе <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="457d3-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="457d3-124">Тип <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> для элементов управления WPF отличается от типа пользовательских элементов управления, предоставляемого Windows Forms, который также называется <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="457d3-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="457d3-125">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="457d3-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="457d3-126">В **обозревателе решений**, добавьте новый **Библиотека пользовательских элементов управления WPF** проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="457d3-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="457d3-127">Используйте имя по умолчанию для библиотеки элементов управления (`WpfControlLibrary1`).</span><span class="sxs-lookup"><span data-stu-id="457d3-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="457d3-128">Имя элемента управления по умолчанию — `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="457d3-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="457d3-129">В результате добавления нового элемента управления происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="457d3-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="457d3-130">Добавляется файл UserControl1.xaml.</span><span class="sxs-lookup"><span data-stu-id="457d3-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="457d3-131">Добавляется файл UserControl1.xaml.cs или UserControl1.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="457d3-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="457d3-132">Этот файл содержит код программной части для обработчиков событий и иных реализованных компонентов.</span><span class="sxs-lookup"><span data-stu-id="457d3-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="457d3-133">Добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="457d3-134">Файл UserControl1.xaml открывается в [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="457d3-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="457d3-135">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="457d3-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="457d3-136">Дополнительные сведения см. в разделе [как: Выбор и перемещение элементов в рабочей области конструирования](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="457d3-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="457d3-137">В **свойства** задайте значение <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="457d3-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="457d3-138">Из **элементов**, перетащите <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> управления на поверхность разработки.</span><span class="sxs-lookup"><span data-stu-id="457d3-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="457d3-139">В **свойства** задайте значение <xref:System.Windows.Controls.TextBox.Text%2A> свойства **Hosted Content**.</span><span class="sxs-lookup"><span data-stu-id="457d3-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="457d3-140">Обычно размещается более сложное содержимое WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="457d3-141">Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> используется здесь в целях наглядности.</span><span class="sxs-lookup"><span data-stu-id="457d3-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="457d3-142">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="457d3-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="457d3-143">Добавление элемента управления WPF в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="457d3-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="457d3-144">Новый элемент управления WPF готов к использованию в форме.</span><span class="sxs-lookup"><span data-stu-id="457d3-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="457d3-145">Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> используется в формах Windows Forms для размещения содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="457d3-146">Добавление элемента управления WPF в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="457d3-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="457d3-147">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="457d3-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="457d3-148">В **элементов**, найдите вкладку **пользовательские элементы управления WPF WPFUserControlLibrary**.</span><span class="sxs-lookup"><span data-stu-id="457d3-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="457d3-149">Перетащите экземпляр `UserControl1` в форму.</span><span class="sxs-lookup"><span data-stu-id="457d3-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="457d3-150">Для размещения элемента управления WPF на форме будет автоматически создан элемент управления <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="457d3-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="457d3-151"><xref:System.Windows.Forms.Integration.ElementHost> Элемент управления называется `elementHost1` и **свойства** окна, можно увидеть его <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> свойству **UserControl1**.</span><span class="sxs-lookup"><span data-stu-id="457d3-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="457d3-152">В проект добавляются ссылки на сборки WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="457d3-153">Элемент управления `elementHost1` имеет панель смарт-тегов, на которой приводятся имеющиеся параметры размещения.</span><span class="sxs-lookup"><span data-stu-id="457d3-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="457d3-154">В **задачи ElementHost** смарт-тега, выберите **закрепление в родительском контейнере**.</span><span class="sxs-lookup"><span data-stu-id="457d3-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="457d3-155">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="457d3-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="457d3-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="457d3-156">Next Steps</span></span>  
 <span data-ttu-id="457d3-157">Windows Forms и WPF — это разные технологии, но они предназначены для тесного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="457d3-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="457d3-158">Следующие приемы расширяют возможности по настройке внешнего вида и поведения приложений:</span><span class="sxs-lookup"><span data-stu-id="457d3-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="457d3-159">Размещение элемента управления Windows Forms на странице WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="457d3-160">Дополнительные сведения см. в разделе [Пошаговое руководство: размещение элемента управления Windows Forms в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="457d3-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="457d3-161">Применение стилей оформления Windows Forms к содержимому WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="457d3-162">Дополнительные сведения см. в разделе [Практическое руководство. Включение визуальных стилей в гибридном приложении](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span><span class="sxs-lookup"><span data-stu-id="457d3-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="457d3-163">Изменение стиля оформления содержимого WPF.</span><span class="sxs-lookup"><span data-stu-id="457d3-163">Change the style of your WPF content.</span></span> <span data-ttu-id="457d3-164">Дополнительные сведения см. в разделе [Пошаговое руководство: Задание стиля содержимого WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span><span class="sxs-lookup"><span data-stu-id="457d3-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457d3-165">См. также</span><span class="sxs-lookup"><span data-stu-id="457d3-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="457d3-166">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="457d3-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="457d3-167">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="457d3-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="457d3-168">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="457d3-168">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
