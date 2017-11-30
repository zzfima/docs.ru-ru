---
title: "Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ae86989489ec4c50a4234eeb4a0950a71e53b0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="c15fd-102">Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="c15fd-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="c15fd-103">В этом пошаговом руководстве показано, как использовать возможности структуры Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c15fd-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>  
  
 <span data-ttu-id="c15fd-104">В этом пошаговом руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c15fd-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c15fd-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="c15fd-105">Create the project.</span></span>  
  
-   <span data-ttu-id="c15fd-106">создание элемента управления WPF;</span><span class="sxs-lookup"><span data-stu-id="c15fd-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="c15fd-107">размещение элементов управления WPF на панели макета;</span><span class="sxs-lookup"><span data-stu-id="c15fd-107">Host WPF controls in a layout panel.</span></span>  
  
-   <span data-ttu-id="c15fd-108">использование линий привязки для выравнивания элементов управления WPF;</span><span class="sxs-lookup"><span data-stu-id="c15fd-108">Use snaplines to align WPF controls.</span></span>  
  
-   <span data-ttu-id="c15fd-109">привязка и закрепление элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="c15fd-109">Anchor and dock WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15fd-110">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c15fd-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c15fd-111">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c15fd-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c15fd-112">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c15fd-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c15fd-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c15fd-113">Prerequisites</span></span>  
 <span data-ttu-id="c15fd-114">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="c15fd-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="c15fd-115">.</span><span class="sxs-lookup"><span data-stu-id="c15fd-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c15fd-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c15fd-116">Creating the Project</span></span>  
 <span data-ttu-id="c15fd-117">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c15fd-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15fd-118">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c15fd-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="c15fd-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c15fd-119">To create the project</span></span>  
  
-   <span data-ttu-id="c15fd-120">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="c15fd-121">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="c15fd-122">После добавления в проект элемента управления WPF можно разместить его в форме.</span><span class="sxs-lookup"><span data-stu-id="c15fd-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="c15fd-123">Создание элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-123">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="c15fd-124">Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="c15fd-125">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="c15fd-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="c15fd-126">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c15fd-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="c15fd-127">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="c15fd-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="c15fd-128">Дополнительные сведения см. в разделе [как: Выбор и перемещение элементов в рабочей области конструирования](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="c15fd-128">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="c15fd-129">В **свойства** задайте значение <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `200`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="c15fd-130">Задайте для свойства <xref:System.Windows.Controls.Control.Background%2A> значение `Blue`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5.  <span data-ttu-id="c15fd-131">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="c15fd-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="c15fd-132">Размещение элементов управления WPF на панели макета</span><span class="sxs-lookup"><span data-stu-id="c15fd-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="c15fd-133">Элементы управления WPF можно использовать на панели макета так же, как и другие элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c15fd-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="c15fd-134">Размещение элементов управления WPF на панели макета</span><span class="sxs-lookup"><span data-stu-id="c15fd-134">To host WPF controls in a layout panel</span></span>  
  
1.  <span data-ttu-id="c15fd-135">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c15fd-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="c15fd-136">В **элементов**, перетащите <xref:System.Windows.Forms.TableLayoutPanel> в форму элемент управления.</span><span class="sxs-lookup"><span data-stu-id="c15fd-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3.  <span data-ttu-id="c15fd-137">На <xref:System.Windows.Forms.TableLayoutPanel> панель смарт-тегов элемента управления, выберите **удалить последнюю строку**.</span><span class="sxs-lookup"><span data-stu-id="c15fd-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4.  <span data-ttu-id="c15fd-138">Увеличьте высоту и ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5.  <span data-ttu-id="c15fd-139">В **элементов**, дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в первую ячейку <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c15fd-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="c15fd-140">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6.  <span data-ttu-id="c15fd-141">В **элементов**, дважды щелкните `UserControl1` для создания другого экземпляра в во вторую ячейку <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c15fd-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="c15fd-142">В **Структура документа** выберите `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="c15fd-143">Дополнительные сведения см. в разделе [окно структуры документа](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span><span class="sxs-lookup"><span data-stu-id="c15fd-143">For more information, see [Document Outline Window](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span></span>  
  
8.  <span data-ttu-id="c15fd-144">В **свойства** задайте значение <xref:System.Windows.Forms.Control.Padding%2A> свойства `10, 10, 10, 10`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="c15fd-145">Размер обоих элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится в соответствии с новой структурой.</span><span class="sxs-lookup"><span data-stu-id="c15fd-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="c15fd-146">Выравнивание элементов управления WPF с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="c15fd-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="c15fd-147">Линии привязки позволяют легко выравнивать элементы управления в форме.</span><span class="sxs-lookup"><span data-stu-id="c15fd-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="c15fd-148">Линии привязки также можно использовать для выравнивания элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="c15fd-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="c15fd-149">Дополнительные сведения см. в разделе [Пошаговое руководство: упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="c15fd-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="c15fd-150">Выравнивание элементов управления WPF с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="c15fd-150">To use snaplines to align WPF controls</span></span>  
  
1.  <span data-ttu-id="c15fd-151">Из **элементов**, перетащите экземпляр `UserControl1` в форму и поместите его под <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c15fd-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="c15fd-152">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2.  <span data-ttu-id="c15fd-153">С помощью линий привязки выровняйте левый край `elementHost3` относительно левого края элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="c15fd-154">С помощью линий привязки установите для `elementHost3` ту же ширину, что и для элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="c15fd-155">Перемещайте `elementHost3` в сторону элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления не появится центральная линия привязки.</span><span class="sxs-lookup"><span data-stu-id="c15fd-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5.  <span data-ttu-id="c15fd-156">В **свойства** задайте значение свойства поля для `20, 20, 20, 20`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6.  <span data-ttu-id="c15fd-157">Перемещайте `elementHost3` от элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления снова не появится центральная линия привязки.</span><span class="sxs-lookup"><span data-stu-id="c15fd-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="c15fd-158">Теперь центральная линия привязки указывает на поле шириной в 20 точек.</span><span class="sxs-lookup"><span data-stu-id="c15fd-158">The center snapline now indicates a margin of 20.</span></span>  
  
7.  <span data-ttu-id="c15fd-159">Перемещайте элемент управления `elementHost3` вправо до тех пор, пока его левый край не будет выровнен относительно левого края элемента управления `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8.  <span data-ttu-id="c15fd-160">Изменяйте ширину элемента `elementHost3` до тех пор, пока его правый край не будет выровнен относительно правого края элемента управления `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="c15fd-161">Привязка и закрепление элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="c15fd-162">Поведение размещенного в форме элемента управления WPF при привязке и закреплении не отличается от поведения других элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c15fd-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="c15fd-163">Привязка и закрепление элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-163">To anchor and dock WPF controls</span></span>  
  
1.  <span data-ttu-id="c15fd-164">Выберите `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-164">Select `elementHost1`.</span></span>  
  
2.  <span data-ttu-id="c15fd-165">В **свойства** задайте <xref:System.Windows.Forms.Control.Anchor%2A> свойства **верхнего, нижнего, Left, Right**.</span><span class="sxs-lookup"><span data-stu-id="c15fd-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3.  <span data-ttu-id="c15fd-166">Увеличьте размер элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="c15fd-167">Элемент управления `elementHost1` заполнит всю ячейку.</span><span class="sxs-lookup"><span data-stu-id="c15fd-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4.  <span data-ttu-id="c15fd-168">Выберите `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-168">Select `elementHost2`.</span></span>  
  
5.  <span data-ttu-id="c15fd-169">В **свойства** задайте значение <xref:System.Windows.Forms.Control.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="c15fd-170">Элемент управления `elementHost2` заполнит всю ячейку.</span><span class="sxs-lookup"><span data-stu-id="c15fd-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6.  <span data-ttu-id="c15fd-171">Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="c15fd-172">Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8.  <span data-ttu-id="c15fd-173">Выберите `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="c15fd-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="c15fd-174">Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c15fd-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="c15fd-175">Элемент управления `elementHost3` заполнит все оставшееся пространство в форме.</span><span class="sxs-lookup"><span data-stu-id="c15fd-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="c15fd-176">Измените размер формы.</span><span class="sxs-lookup"><span data-stu-id="c15fd-176">Resize the form.</span></span>  
  
     <span data-ttu-id="c15fd-177">Размер всех трех элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c15fd-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="c15fd-178">Дополнительные сведения см. в разделе [как: привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span><span class="sxs-lookup"><span data-stu-id="c15fd-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15fd-179">См. также</span><span class="sxs-lookup"><span data-stu-id="c15fd-179">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c15fd-180">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="c15fd-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="c15fd-181">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="c15fd-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="c15fd-182">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="c15fd-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="c15fd-183">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="c15fd-183">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="c15fd-184">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-184">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="c15fd-185">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="c15fd-185">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
