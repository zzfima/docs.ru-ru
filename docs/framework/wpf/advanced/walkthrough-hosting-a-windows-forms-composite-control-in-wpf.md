---
title: Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e30b1bb45cc2dae2783cddf54dda400b742cdf73
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920326"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="1ca63-102">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="1ca63-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
<span data-ttu-id="1ca63-103">Служба [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет среду с широкими возможностями для создания приложений.</span><span class="sxs-lookup"><span data-stu-id="1ca63-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] provides a rich environment for creating applications.</span></span> <span data-ttu-id="1ca63-104">Однако при наличии значительных инвестиций в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] код может оказаться более эффективным, чтобы повторно использовать по крайней мере часть этого кода в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], а не переписывать его с нуля.</span><span class="sxs-lookup"><span data-stu-id="1ca63-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="1ca63-105">Наиболее распространенный сценарий заключается в наличии существующих элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1ca63-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="1ca63-106">В некоторых случаях, возможно, у вас даже нет доступа к исходному коду для этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="1ca63-107">предоставляет простую процедуру размещения таких элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении.</span><span class="sxs-lookup"><span data-stu-id="1ca63-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1ca63-108">Например, можно использовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для большей части программирования при размещении специализированных элементов управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="1ca63-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="1ca63-109">В этом пошаговом руководстве описано приложение, в котором размещен Windows Forms составной элемент управления для выполнения ввода данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении.</span><span class="sxs-lookup"><span data-stu-id="1ca63-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1ca63-110">Составной элемент управления упакован в библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="1ca63-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="1ca63-111">Эта общая процедура может быть расширена для более сложных приложений и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="1ca63-112">Это пошаговое руководство призвано стать практически идентичным по внешнему виду и функциональности для [пошагового руководства: размещение составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1ca63-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="1ca63-113">Основным отличием является то, что сценарий размещения выполняется в обратном порядке.</span><span class="sxs-lookup"><span data-stu-id="1ca63-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="1ca63-114">Пошаговое руководство состоит из двух разделов.</span><span class="sxs-lookup"><span data-stu-id="1ca63-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="1ca63-115">В первом разделе кратко описывается реализация составного элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1ca63-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="1ca63-116">Во втором разделе подробно рассматривается размещение составного элемента управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложении, получение событий из элемента управления и доступ к некоторым свойствам элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="1ca63-117">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="1ca63-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="1ca63-118">Реализация составного элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1ca63-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="1ca63-119">Реализация ведущего приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="1ca63-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="1ca63-120">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Пример размещения Windows Forms составного элемента управления в WPF](https://go.microsoft.com/fwlink/?LinkID=159999).</span><span class="sxs-lookup"><span data-stu-id="1ca63-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1ca63-121">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="1ca63-121">Prerequisites</span></span>  

<span data-ttu-id="1ca63-122">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ca63-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="1ca63-123">Реализация составного элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ca63-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="1ca63-124">Windows Forms составной элемент управления, используемый в этом примере, представляет собой простую форму ввода данных.</span><span class="sxs-lookup"><span data-stu-id="1ca63-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="1ca63-125">Эта форма принимает имя и адрес пользователя и затем использует пользовательское событие для возвращения сведений в основное приложение.</span><span class="sxs-lookup"><span data-stu-id="1ca63-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="1ca63-126">На приведенном ниже рисунке показан отображаемый элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="1ca63-127">На следующем рисунке показан Windows Forms составной элемент управления:</span><span class="sxs-lookup"><span data-stu-id="1ca63-127">The following image shows a Windows Forms composite control:</span></span>  

 ![Снимок экрана, на котором показан простой элемент управления Windows Forms.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="1ca63-129">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1ca63-129">Creating the Project</span></span>  
 <span data-ttu-id="1ca63-130">Для запуска проекта выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1ca63-130">To start the project:</span></span>  
  
1. <span data-ttu-id="1ca63-131">Запустите Visual Studio и откройте диалоговое окно **Создание проекта** .</span><span class="sxs-lookup"><span data-stu-id="1ca63-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="1ca63-132">В категории окно выберите шаблон **Библиотека элементов управления Windows Forms** .</span><span class="sxs-lookup"><span data-stu-id="1ca63-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="1ca63-133">Присвойте проекту имя `MyControls`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="1ca63-134">В качестве расположения укажите папку верхнего уровня с удобным именем, например `WpfHostingWindowsFormsControl`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="1ca63-135">Позже ведущее приложение будет помещено в эту папку.</span><span class="sxs-lookup"><span data-stu-id="1ca63-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="1ca63-136">Нажмите кнопку **ОК**, чтобы создать проект.</span><span class="sxs-lookup"><span data-stu-id="1ca63-136">Click **OK** to create the project.</span></span> <span data-ttu-id="1ca63-137">Проект по умолчанию содержит один элемент управления с именем `UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="1ca63-138">В обозреватель решений переименуйте `UserControl1` в `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="1ca63-139">Проект должен иметь ссылки на перечисленные ниже системные библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="1ca63-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="1ca63-140">Если какие-либо из этих библиотек DLL не включены по умолчанию, добавьте их в проект.</span><span class="sxs-lookup"><span data-stu-id="1ca63-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="1ca63-141">Система</span><span class="sxs-lookup"><span data-stu-id="1ca63-141">System</span></span>  
  
- <span data-ttu-id="1ca63-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="1ca63-142">System.Data</span></span>  
  
- <span data-ttu-id="1ca63-143">System.Drawing;</span><span class="sxs-lookup"><span data-stu-id="1ca63-143">System.Drawing</span></span>  
  
- <span data-ttu-id="1ca63-144">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="1ca63-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="1ca63-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="1ca63-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="1ca63-146">Добавление элементов управления на форму</span><span class="sxs-lookup"><span data-stu-id="1ca63-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="1ca63-147">Чтобы добавить элементы управления в форму, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1ca63-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="1ca63-148">Откройте `MyControl1` в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="1ca63-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="1ca63-149">Добавьте пять элементов управления <xref:System.Windows.Forms.Label> и их соответствующие элементы управления <xref:System.Windows.Forms.TextBox>, а также их размер и расположение, как показано на предыдущем рисунке в форме.</span><span class="sxs-lookup"><span data-stu-id="1ca63-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="1ca63-150">В этом примере элементы управления <xref:System.Windows.Forms.TextBox> называются:</span><span class="sxs-lookup"><span data-stu-id="1ca63-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="1ca63-151">Добавьте два элемента управления <xref:System.Windows.Forms.Button> с меткой **ОК** и **Отмена**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="1ca63-152">В этом примере имена кнопок `btnOK` и `btnCancel`соответственно.</span><span class="sxs-lookup"><span data-stu-id="1ca63-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="1ca63-153">Реализация соответствующего кода</span><span class="sxs-lookup"><span data-stu-id="1ca63-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="1ca63-154">Откройте форму в представлении кода.</span><span class="sxs-lookup"><span data-stu-id="1ca63-154">Open the form in code view.</span></span> <span data-ttu-id="1ca63-155">Элемент управления возвращает собранные данные на узел путем вызова пользовательского события `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="1ca63-156">Данные содержатся в объекте аргумента события.</span><span class="sxs-lookup"><span data-stu-id="1ca63-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="1ca63-157">В следующем коде показано объявление события и делегата.</span><span class="sxs-lookup"><span data-stu-id="1ca63-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="1ca63-158">Добавьте следующий код в класс `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="1ca63-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="1ca63-159">Класс `MyControlEventArgs` содержит сведения, которые будут возвращены узлу.</span><span class="sxs-lookup"><span data-stu-id="1ca63-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="1ca63-160">Добавьте в форму следующий класс.</span><span class="sxs-lookup"><span data-stu-id="1ca63-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="1ca63-161">Когда пользователь нажимает кнопку **ОК** или **Отмена** , обработчики <xref:System.Windows.Forms.Control.Click> событий создают объект `MyControlEventArgs`, содержащий данные, и вызывает событие `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="1ca63-162">Единственное различие между двумя обработчиками — это свойство `IsOK` аргумента события.</span><span class="sxs-lookup"><span data-stu-id="1ca63-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="1ca63-163">Это свойство позволяет основному приложению определить, какая кнопка была нажата.</span><span class="sxs-lookup"><span data-stu-id="1ca63-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="1ca63-164">Он имеет значение `true` для кнопки **ОК** и `false` для кнопки **Отмена** .</span><span class="sxs-lookup"><span data-stu-id="1ca63-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="1ca63-165">В следующем примере кода показаны два обработчика кнопок.</span><span class="sxs-lookup"><span data-stu-id="1ca63-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="1ca63-166">Добавьте следующий код в класс `MyControl1` .</span><span class="sxs-lookup"><span data-stu-id="1ca63-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="1ca63-167">Присвоение сборке строгого имени и построение сборки</span><span class="sxs-lookup"><span data-stu-id="1ca63-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="1ca63-168">Чтобы на эту сборку ссылалось приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], оно должно иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="1ca63-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="1ca63-169">Чтобы создать строгое имя, создайте файл ключа с помощью программы Sn. exe и добавьте его в проект.</span><span class="sxs-lookup"><span data-stu-id="1ca63-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="1ca63-170">Откройте командную строку Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ca63-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="1ca63-171">Для этого в меню " **Пуск** " выберите **все программы/Microsoft Visual Studio 2010/инструменты Visual Studio/Командная строка Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="1ca63-172">Откроется окно консоли с настраиваемыми переменными среды.</span><span class="sxs-lookup"><span data-stu-id="1ca63-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="1ca63-173">В командной строке выполните команду `cd`, чтобы открыть папку проекта.</span><span class="sxs-lookup"><span data-stu-id="1ca63-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="1ca63-174">Создайте файл ключа с именем MyControls.snk, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="1ca63-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="1ca63-175">Чтобы включить файл ключа в проект, щелкните правой кнопкой мыши имя проекта в обозреватель решений а затем выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="1ca63-176">В конструкторе проектов перейдите на вкладку **Подписывание** , установите флажок **подписать сборку** и перейдите к файлу ключа.</span><span class="sxs-lookup"><span data-stu-id="1ca63-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="1ca63-177">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="1ca63-177">Build the solution.</span></span> <span data-ttu-id="1ca63-178">В результате сборки будет создана библиотека DLL с именем MyControls.dll.</span><span class="sxs-lookup"><span data-stu-id="1ca63-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="1ca63-179">Реализация ведущего приложения WPF</span><span class="sxs-lookup"><span data-stu-id="1ca63-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="1ca63-180">Ведущее приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="1ca63-181">Приложение обрабатывает событие `OnButtonClick` для получения данных из элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="1ca63-182">Он также содержит коллекцию переключателей, которые позволяют изменять некоторые свойства элемента управления из [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="1ca63-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="1ca63-183">Ниже показано готовое приложение.</span><span class="sxs-lookup"><span data-stu-id="1ca63-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="1ca63-184">На следующем рисунке показано полное приложение, включая элемент управления, внедренный в приложение WPF:</span><span class="sxs-lookup"><span data-stu-id="1ca63-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![Снимок экрана, на котором показан элемент управления, внедренный в страницу WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="1ca63-186">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="1ca63-186">Creating the Project</span></span>
 <span data-ttu-id="1ca63-187">Для запуска проекта выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1ca63-187">To start the project:</span></span>

1. <span data-ttu-id="1ca63-188">Откройте Visual Studio и выберите **создать проект**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="1ca63-189">В категории окно выберите шаблон **приложение WPF** .</span><span class="sxs-lookup"><span data-stu-id="1ca63-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="1ca63-190">Присвойте проекту имя `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="1ca63-191">В качестве расположения укажите ту же папку верхнего уровня, в которой содержится проект MyControls.</span><span class="sxs-lookup"><span data-stu-id="1ca63-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="1ca63-192">Нажмите кнопку **ОК**, чтобы создать проект.</span><span class="sxs-lookup"><span data-stu-id="1ca63-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="1ca63-193">Также необходимо добавить ссылки на библиотеку DLL, содержащую `MyControl1` и другие сборки.</span><span class="sxs-lookup"><span data-stu-id="1ca63-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="1ca63-194">Щелкните правой кнопкой мыши имя проекта в обозреватель решений и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="1ca63-195">Перейдите на вкладку **Обзор** и перейдите в папку, содержащую файл MyControls. dll.</span><span class="sxs-lookup"><span data-stu-id="1ca63-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="1ca63-196">В данном пошаговом руководстве это папка MyControls\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="1ca63-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="1ca63-197">Выберите файл MyControls. dll и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="1ca63-198">Добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="1ca63-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="1ca63-199">Реализация базового макета</span><span class="sxs-lookup"><span data-stu-id="1ca63-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="1ca63-200">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ведущего приложения реализуется в файле MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="1ca63-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="1ca63-201">Этот файл содержит [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] разметку, определяющую макет, и размещает элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1ca63-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="1ca63-202">Приложение состоит из трех областей:</span><span class="sxs-lookup"><span data-stu-id="1ca63-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="1ca63-203">Панель **свойства элемента управления** , которая содержит коллекцию переключателей, которые можно использовать для изменения различных свойств размещенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="1ca63-204">**Данные из панели управления** , которая содержит несколько <xref:System.Windows.Controls.TextBlock> элементов, отображающих данные, возвращаемые размещенным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="1ca63-205">Размещенный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ca63-205">The hosted control itself.</span></span>

 <span data-ttu-id="1ca63-206">Базовый макет показан в следующем XAML-коде.</span><span class="sxs-lookup"><span data-stu-id="1ca63-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="1ca63-207">Разметка, необходимая для размещения `MyControl1`, пропущена в этом примере, но будет обсуждаться далее.</span><span class="sxs-lookup"><span data-stu-id="1ca63-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="1ca63-208">Замените XAML-код в файле MainWindow.xaml следующим.</span><span class="sxs-lookup"><span data-stu-id="1ca63-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="1ca63-209">Если вы используете Visual Basic, измените класс на `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="1ca63-210">Первый элемент <xref:System.Windows.Controls.StackPanel> содержит несколько наборов элементов управления <xref:System.Windows.Controls.RadioButton>, которые позволяют изменять различные свойства по умолчанию размещенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="1ca63-211">За ним следует элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, в котором размещается `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="1ca63-212">Последний элемент <xref:System.Windows.Controls.StackPanel> содержит несколько элементов <xref:System.Windows.Controls.TextBlock>, которые отображают данные, возвращаемые размещаемым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="1ca63-213">Упорядочивание элементов и параметров атрибутов <xref:System.Windows.Controls.DockPanel.Dock%2A> и <xref:System.Windows.FrameworkElement.Height%2A> внедряет размещаемый элемент управления в окно без пропусков или искажений.</span><span class="sxs-lookup"><span data-stu-id="1ca63-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="1ca63-214">Размещение элемента управления</span><span class="sxs-lookup"><span data-stu-id="1ca63-214">Hosting the Control</span></span>
 <span data-ttu-id="1ca63-215">В следующей измененной версии предыдущего кода XAML основное внимание уделяется элементам, необходимым для размещения `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="1ca63-216">Атрибут сопоставления пространства имен `xmlns` создает ссылку на `MyControls` пространство имен, содержащее размещенный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="1ca63-217">Это сопоставление позволяет представлять `MyControl1` в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] как `<mcl:MyControl1>`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="1ca63-218">Два элемента в коде XAML обрабатывают размещение:</span><span class="sxs-lookup"><span data-stu-id="1ca63-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="1ca63-219">`WindowsFormsHost` представляет элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost>, позволяющий размещать элемент управления Windows Forms в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ca63-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="1ca63-220">`mcl:MyControl1`, представляющий `MyControl1`, добавляется в дочернюю коллекцию элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="1ca63-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="1ca63-221">В результате этот Windows Forms элемент управления отображается как часть окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], и вы можете взаимодействовать с элементом управления из приложения.</span><span class="sxs-lookup"><span data-stu-id="1ca63-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="1ca63-222">Реализация файла кода программной части</span><span class="sxs-lookup"><span data-stu-id="1ca63-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="1ca63-223">Файл кода программной части MainWindow. XAML. vb или MainWindow.xaml.cs содержит процедурный код, реализующий функциональные возможности [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], обсуждаемого в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="1ca63-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="1ca63-224">Основные задачи</span><span class="sxs-lookup"><span data-stu-id="1ca63-224">The primary tasks are:</span></span>

- <span data-ttu-id="1ca63-225">Присоединение обработчика событий к `OnButtonClick`ному событию `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="1ca63-226">Изменение различных свойств `MyControl1`в зависимости от того, как задается коллекция переключателей.</span><span class="sxs-lookup"><span data-stu-id="1ca63-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="1ca63-227">Отображение данных, собранных с помощью элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="1ca63-228">Инициализация приложения</span><span class="sxs-lookup"><span data-stu-id="1ca63-228">Initializing the Application</span></span>
 <span data-ttu-id="1ca63-229">Код инициализации содержится в обработчике событий для события <xref:System.Windows.FrameworkElement.Loaded> окна и прикрепляет обработчик событий к событию `OnButtonClick` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="1ca63-230">В файле MainWindow. XAML. vb или MainWindow.xaml.cs добавьте следующий код в класс `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="1ca63-231">Поскольку [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], описанный ранее, добавил `MyControl1` в коллекцию дочерних элементов <xref:System.Windows.Forms.Integration.WindowsFormsHost>, можно привести <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>, чтобы получить ссылку на `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="1ca63-232">Затем эту ссылку можно использовать для присоединения обработчика событий к `OnButtonClick`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="1ca63-233">Помимо предоставления ссылки на сам элемент управления, <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет ряд свойств элемента управления, которыми можно управлять из приложения.</span><span class="sxs-lookup"><span data-stu-id="1ca63-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="1ca63-234">Код инициализации назначает эти значения закрытым глобальным переменным для последующего использования в приложении.</span><span class="sxs-lookup"><span data-stu-id="1ca63-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="1ca63-235">Чтобы можно было легко получить доступ к типам в `MyControls` библиотеке DLL, добавьте в начало файла следующую инструкцию `Imports` или `using`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="1ca63-236">Обработка события OnButtonClick</span><span class="sxs-lookup"><span data-stu-id="1ca63-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="1ca63-237">`MyControl1` вызывает событие `OnButtonClick`, когда пользователь нажимает одну из кнопок элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="1ca63-238">Добавьте следующий код в класс `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="1ca63-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="1ca63-239">Данные в текстовых полях упаковываются в объект `MyControlEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="1ca63-240">Если пользователь нажмет кнопку **ОК** , обработчик событий извлекает данные и отображает их на панели ниже `MyControl1`.</span><span class="sxs-lookup"><span data-stu-id="1ca63-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="1ca63-241">Изменение свойств элемента управления</span><span class="sxs-lookup"><span data-stu-id="1ca63-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="1ca63-242">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет несколько свойств размещенного элемента управления по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1ca63-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="1ca63-243">В результате можно изменить внешний вид элемента управления, чтобы он более полно соответствовал стилю приложения.</span><span class="sxs-lookup"><span data-stu-id="1ca63-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="1ca63-244">Наборы переключателей на левой панели позволяют пользователю изменять некоторые свойства цвета и шрифта.</span><span class="sxs-lookup"><span data-stu-id="1ca63-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="1ca63-245">Каждый набор кнопок имеет обработчик события <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, который обнаруживает выбор переключателя пользователем и изменяет соответствующее свойство элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="1ca63-246">Добавьте следующий код в класс `MainWindow` .</span><span class="sxs-lookup"><span data-stu-id="1ca63-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="1ca63-247">Выполните сборку и запуск приложения.</span><span class="sxs-lookup"><span data-stu-id="1ca63-247">Build and run the application.</span></span> <span data-ttu-id="1ca63-248">Добавьте текст в составной элемент управления Windows Forms и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ca63-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="1ca63-249">Этот текст появится в метках.</span><span class="sxs-lookup"><span data-stu-id="1ca63-249">The text appears in the labels.</span></span> <span data-ttu-id="1ca63-250">Щелкайте различные переключатели, чтобы увидеть соответствующий эффект в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="1ca63-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ca63-251">См. также</span><span class="sxs-lookup"><span data-stu-id="1ca63-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="1ca63-252">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1ca63-252">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="1ca63-253">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="1ca63-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="1ca63-254">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1ca63-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
