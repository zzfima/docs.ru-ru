---
title: Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7858ffd708c78d6397d533f613ccc2ea78d6cbed
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658526"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="19293-102">Пошаговое руководство. Размещение содержимого WPF на Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="19293-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="19293-103">В этой статье показано, как использовать функции макета Windows Forms, такие как привязка и линии привязки, для упорядочения элементов управления Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="19293-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19293-104">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="19293-104">Prerequisites</span></span>

<span data-ttu-id="19293-105">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="19293-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="19293-106">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="19293-106">Create the project</span></span>

<span data-ttu-id="19293-107">Откройте Visual Studio и создайте новый проект Windows Forms приложения в Visual Basic или Visual C# с именем `ArrangeElementHost`.</span><span class="sxs-lookup"><span data-stu-id="19293-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="19293-108">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="19293-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="19293-109">Создание элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="19293-109">Create the WPF control</span></span>

<span data-ttu-id="19293-110">После добавления в проект элемента управления WPF можно разместить его в форме.</span><span class="sxs-lookup"><span data-stu-id="19293-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="19293-111">Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="19293-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="19293-112">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="19293-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="19293-113">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF на Windows Forms во время](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)разработки.</span><span class="sxs-lookup"><span data-stu-id="19293-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="19293-114">Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.</span><span class="sxs-lookup"><span data-stu-id="19293-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="19293-115">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.</span><span class="sxs-lookup"><span data-stu-id="19293-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="19293-116">Присвойте <xref:System.Windows.Controls.Control.Background%2A> свойству значение **Blue**.</span><span class="sxs-lookup"><span data-stu-id="19293-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="19293-117">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="19293-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="19293-118">Размещение элементов управления WPF на панели макета</span><span class="sxs-lookup"><span data-stu-id="19293-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="19293-119">Элементы управления WPF можно использовать на панели макета так же, как и другие элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="19293-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="19293-120">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="19293-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="19293-121">В **области элементов**перетащите <xref:System.Windows.Forms.TableLayoutPanel> элемент управления на форму.</span><span class="sxs-lookup"><span data-stu-id="19293-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="19293-122">На панели смарт-тегов элементауправлениявыберитеудалитьпоследнюю<xref:System.Windows.Forms.TableLayoutPanel> строку.</span><span class="sxs-lookup"><span data-stu-id="19293-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="19293-123">Увеличьте высоту и ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="19293-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="19293-124">В **области элементов**дважды щелкните `UserControl1` , чтобы `UserControl1` создать экземпляр в первой ячейке <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="19293-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="19293-125">Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="19293-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="19293-126">В **области элементов**дважды щелкните `UserControl1` , чтобы создать другой экземпляр во <xref:System.Windows.Forms.TableLayoutPanel> второй ячейке элемента управления.</span><span class="sxs-lookup"><span data-stu-id="19293-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="19293-127">В окне **Структура документа** выберите `tableLayoutPanel1`.</span><span class="sxs-lookup"><span data-stu-id="19293-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="19293-128">В окне **Свойства** присвойте <xref:System.Windows.Forms.Control.Padding%2A> свойству значение **10, 10, 10, 10**.</span><span class="sxs-lookup"><span data-stu-id="19293-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="19293-129">Размер обоих элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится в соответствии с новой структурой.</span><span class="sxs-lookup"><span data-stu-id="19293-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="19293-130">Использование линий привязки для выровняйте элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="19293-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="19293-131">Линии привязки позволяют легко выравнивать элементы управления в форме.</span><span class="sxs-lookup"><span data-stu-id="19293-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="19293-132">Линии привязки также можно использовать для выравнивания элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="19293-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="19293-133">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)помощью линий привязки.</span><span class="sxs-lookup"><span data-stu-id="19293-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="19293-134">Перетащите экземпляр `UserControl1` из **области элементов**в форму и поместите его в пространство под <xref:System.Windows.Forms.TableLayoutPanel> элементом управления.</span><span class="sxs-lookup"><span data-stu-id="19293-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="19293-135">Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="19293-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="19293-136">С помощью линий привязки выровняйте левый край `elementHost3` относительно левого края элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="19293-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="19293-137">С помощью линий привязки установите для `elementHost3` ту же ширину, что и для элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="19293-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="19293-138">Перемещайте `elementHost3` в сторону элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления не появится центральная линия привязки.</span><span class="sxs-lookup"><span data-stu-id="19293-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="19293-139">В окне **Свойства** задайте для свойства Margin значение **20, 20, 20, 20**.</span><span class="sxs-lookup"><span data-stu-id="19293-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="19293-140">Перемещайте `elementHost3` от элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления снова не появится центральная линия привязки.</span><span class="sxs-lookup"><span data-stu-id="19293-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="19293-141">Теперь центральная линия привязки указывает на поле шириной в 20 точек.</span><span class="sxs-lookup"><span data-stu-id="19293-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="19293-142">Перейти `elementHost3` вправо до тех пор, пока его левый элемент не будет сопоставлен с левым `elementHost1`ребром.</span><span class="sxs-lookup"><span data-stu-id="19293-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="19293-143">Изменяйте ширину элемента `elementHost3` до тех пор, пока его правый край не будет выровнен относительно правого края элемента управления `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="19293-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="19293-144">Привязка и закрепление элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="19293-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="19293-145">Поведение размещенного в форме элемента управления WPF при привязке и закреплении не отличается от поведения других элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="19293-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="19293-146">Выберите `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="19293-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="19293-147">В окне **Свойства** задайте <xref:System.Windows.Forms.Control.Anchor%2A> для свойства значение **сверху, снизу, слева, справа**.</span><span class="sxs-lookup"><span data-stu-id="19293-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="19293-148">Увеличьте размер элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="19293-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="19293-149">Элемент управления `elementHost1` заполнит всю ячейку.</span><span class="sxs-lookup"><span data-stu-id="19293-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="19293-150">Выберите `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="19293-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="19293-151">В окне **Свойства** присвойте <xref:System.Windows.Forms.Control.Dock%2A> свойству <xref:System.Windows.Forms.DockStyle.Fill>значение.</span><span class="sxs-lookup"><span data-stu-id="19293-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="19293-152">Элемент управления `elementHost2` заполнит всю ячейку.</span><span class="sxs-lookup"><span data-stu-id="19293-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="19293-153">Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="19293-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="19293-154">Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Top>.</span><span class="sxs-lookup"><span data-stu-id="19293-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="19293-155">Выберите `elementHost3`.</span><span class="sxs-lookup"><span data-stu-id="19293-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="19293-156">Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="19293-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="19293-157">Элемент управления `elementHost3` заполнит все оставшееся пространство в форме.</span><span class="sxs-lookup"><span data-stu-id="19293-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="19293-158">Измените размер формы.</span><span class="sxs-lookup"><span data-stu-id="19293-158">Resize the form.</span></span>

    <span data-ttu-id="19293-159">Размер всех трех элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="19293-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="19293-160">Дополнительные сведения см. в разделе [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)управления TableLayoutPanel.</span><span class="sxs-lookup"><span data-stu-id="19293-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="19293-161">См. также</span><span class="sxs-lookup"><span data-stu-id="19293-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="19293-162">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="19293-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="19293-163">Практическое руководство. Выровняйте элемент управления по краям форм во время разработки</span><span class="sxs-lookup"><span data-stu-id="19293-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="19293-164">Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="19293-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="19293-165">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="19293-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="19293-166">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="19293-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="19293-167">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="19293-167">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
