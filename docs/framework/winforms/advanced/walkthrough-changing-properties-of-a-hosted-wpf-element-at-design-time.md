---
title: "Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 027fb2efaff5cfdd4d6962798a85923631fa4e9b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="5f318-102">Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки</span><span class="sxs-lookup"><span data-stu-id="5f318-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="5f318-103">В этом пошаговом руководстве показано, как изменить значения свойств элемента управления Windows Presentation Foundation (WPF), размещенного на форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5f318-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="5f318-104">В этом пошаговом руководстве будут выполнены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="5f318-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5f318-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="5f318-105">Create the project.</span></span>  
  
-   <span data-ttu-id="5f318-106">Создание элемента управления WPF.</span><span class="sxs-lookup"><span data-stu-id="5f318-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="5f318-107">Размещение элементов управления WPF в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5f318-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="5f318-108">Изменение значений свойств с использованием конструктора WPF для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f318-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f318-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5f318-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5f318-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5f318-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5f318-111">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5f318-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5f318-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="5f318-112">Prerequisites</span></span>  
 <span data-ttu-id="5f318-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="5f318-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="5f318-114">.</span><span class="sxs-lookup"><span data-stu-id="5f318-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5f318-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="5f318-115">Creating the Project</span></span>  
 <span data-ttu-id="5f318-116">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5f318-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f318-117">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5f318-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="5f318-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="5f318-118">To create the project</span></span>  
  
-   <span data-ttu-id="5f318-119">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="5f318-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="5f318-120">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="5f318-121">После добавления в проект элемента управления WPF можно разместить его в форме.</span><span class="sxs-lookup"><span data-stu-id="5f318-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="5f318-122">Создание элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="5f318-123">Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="5f318-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="5f318-124">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="5f318-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="5f318-125">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="5f318-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="5f318-126">В **свойства** задайте значение <xref:System.Windows.Controls.Control.Background%2A> свойства `Blue`.</span><span class="sxs-lookup"><span data-stu-id="5f318-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="5f318-127">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="5f318-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="5f318-128">Изменение значений свойств элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="5f318-129">Смарт-тег <xref:System.Windows.Forms.Integration.ElementHost> упрощает изменение свойств размещенного WPF-содержимого с помощью конструктора WPF.</span><span class="sxs-lookup"><span data-stu-id="5f318-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="5f318-130">Размещение элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="5f318-131">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5f318-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="5f318-132">В **элементов**в **пользовательские элементы управления WPF** дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.</span><span class="sxs-lookup"><span data-stu-id="5f318-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="5f318-133">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="5f318-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="5f318-134">В **задачи ElementHost** смарт-тега, выберите **редактировать содержимое**.</span><span class="sxs-lookup"><span data-stu-id="5f318-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="5f318-135">Файл UserControl1.xaml откроется в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="5f318-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="5f318-136">В **свойства** задайте значение <xref:System.Windows.Controls.Control.Background%2A> свойства `Red`.</span><span class="sxs-lookup"><span data-stu-id="5f318-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="5f318-137">Перестройте проект.</span><span class="sxs-lookup"><span data-stu-id="5f318-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="5f318-138">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5f318-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="5f318-139">Экземпляр `UserControl1` имеет красный фон.</span><span class="sxs-lookup"><span data-stu-id="5f318-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f318-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5f318-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="5f318-141">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="5f318-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="5f318-142">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="5f318-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="5f318-143">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="5f318-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="5f318-144">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="5f318-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="5f318-145">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="5f318-146">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="5f318-146">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
