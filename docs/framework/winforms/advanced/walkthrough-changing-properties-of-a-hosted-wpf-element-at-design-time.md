---
title: Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: 15cab9266af5840aa4b37a62b71bd5010b7a859a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43535646"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="e2713-102">Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки</span><span class="sxs-lookup"><span data-stu-id="e2713-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="e2713-103">В этом пошаговом руководстве показано, как изменить значения свойств элемента управления Windows Presentation Foundation (WPF), размещенного на форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2713-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="e2713-104">В этом пошаговом руководстве будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="e2713-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e2713-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="e2713-105">Create the project.</span></span>  
  
-   <span data-ttu-id="e2713-106">Создание элемента управления WPF.</span><span class="sxs-lookup"><span data-stu-id="e2713-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="e2713-107">Размещение элементов управления WPF в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2713-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="e2713-108">Изменение значений свойств с использованием конструктора WPF для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2713-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2713-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e2713-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e2713-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e2713-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e2713-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e2713-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2713-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="e2713-112">Prerequisites</span></span>  
 <span data-ttu-id="e2713-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="e2713-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="e2713-114">.</span><span class="sxs-lookup"><span data-stu-id="e2713-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="e2713-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="e2713-115">Creating the Project</span></span>  
 <span data-ttu-id="e2713-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2713-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2713-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e2713-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="e2713-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="e2713-118">To create the project</span></span>  
  
-   <span data-ttu-id="e2713-119">Создание нового проекта приложения Windows Forms в Visual Basic или Visual C# с именем `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="e2713-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="e2713-120">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="e2713-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="e2713-121">После добавления в проект элемента управления WPF можно разместить его в форме.</span><span class="sxs-lookup"><span data-stu-id="e2713-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="e2713-122">Создание элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e2713-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="e2713-123">Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="e2713-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="e2713-124">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="e2713-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="e2713-125">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="e2713-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="e2713-126">В **свойства** окна, установите для параметра <xref:System.Windows.Controls.Control.Background%2A> свойства `Blue`.</span><span class="sxs-lookup"><span data-stu-id="e2713-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="e2713-127">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="e2713-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="e2713-128">Изменение значений свойств элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="e2713-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="e2713-129">Смарт-тег <xref:System.Windows.Forms.Integration.ElementHost> упрощает изменение свойств размещенного WPF-содержимого с помощью конструктора WPF.</span><span class="sxs-lookup"><span data-stu-id="e2713-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="e2713-130">Размещение элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="e2713-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="e2713-131">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2713-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="e2713-132">В **элементов**в **пользовательские элементы управления WPF** дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="e2713-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="e2713-133">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="e2713-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="e2713-134">В **задачи ElementHost** смарт-тега выберите **редактировать содержимое**.</span><span class="sxs-lookup"><span data-stu-id="e2713-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="e2713-135">Файл UserControl1.xaml откроется в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="e2713-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="e2713-136">В **свойства** окна, установите для параметра <xref:System.Windows.Controls.Control.Background%2A> свойства `Red`.</span><span class="sxs-lookup"><span data-stu-id="e2713-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="e2713-137">Перестройте проект.</span><span class="sxs-lookup"><span data-stu-id="e2713-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="e2713-138">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e2713-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="e2713-139">Экземпляр `UserControl1` имеет красный фон.</span><span class="sxs-lookup"><span data-stu-id="e2713-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2713-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e2713-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="e2713-141">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="e2713-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="e2713-142">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="e2713-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="e2713-143">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="e2713-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="e2713-144">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="e2713-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="e2713-145">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e2713-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="e2713-146">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2713-146">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
