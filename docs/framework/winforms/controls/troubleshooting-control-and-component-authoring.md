---
title: Разрешение вопросов, связанных с созданием элементов управления и компонентов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9ee9df41e6f0a4e37164760a2e40740e31530121
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459075"
---
# <a name="troubleshoot-control-and-component-authoring"></a><span data-ttu-id="09ab4-102">Устранение неполадок с созданием элементов управления и компонентов</span><span class="sxs-lookup"><span data-stu-id="09ab4-102">Troubleshoot Control and Component Authoring</span></span>

<span data-ttu-id="09ab4-103">В этом разделе перечислены следующие распространенные проблемы, возникающие при разработке компонентов и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="09ab4-103">This topic lists the following common problems that arise when developing components and controls:</span></span>

- <span data-ttu-id="09ab4-104">Не удается добавить элемент управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="09ab4-104">Cannot Add Control to Toolbox</span></span>

- <span data-ttu-id="09ab4-105">Не удается выполнить отладку пользовательского элемента управления или компонента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09ab4-105">Cannot Debug the Windows Forms User Control or Component</span></span>

- <span data-ttu-id="09ab4-106">Событие в производном элементе управления или компоненте вызывается дважды</span><span class="sxs-lookup"><span data-stu-id="09ab4-106">Event Is Raised Twice in Inherited Control or Component</span></span>

- <span data-ttu-id="09ab4-107">Ошибка времени разработки: "Не удалось создать компонент *имя компонента*"</span><span class="sxs-lookup"><span data-stu-id="09ab4-107">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>

- <span data-ttu-id="09ab4-108">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="09ab4-108">STAThreadAttribute</span></span>

- <span data-ttu-id="09ab4-109">Значок компонента не отображается на панели элементов</span><span class="sxs-lookup"><span data-stu-id="09ab4-109">Component Icon Does Not Appear in Toolbox</span></span>

## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="09ab4-110">Не удается добавить элемент управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="09ab4-110">Cannot Add Control to Toolbox</span></span>

<span data-ttu-id="09ab4-111">Если вы хотите добавить на **панель элементов** настраиваемый элемент управления, созданный в другом проекте, или сторонний элемент управления, это необходимо сделать вручную.</span><span class="sxs-lookup"><span data-stu-id="09ab4-111">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="09ab4-112">Если ваш элемент управления или компонент уже находится в текущем проекте, он отобразится на **панели элементов** автоматически.</span><span class="sxs-lookup"><span data-stu-id="09ab4-112">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="09ab4-113">Дополнительные сведения см. в разделе [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="09ab4-113">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="09ab4-114">Добавление элемента управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="09ab4-114">To add a control to the Toolbox</span></span>

1. <span data-ttu-id="09ab4-115">Щелкните **панель инструментов** правой кнопкой мыши и выберите команду **Выбрать элементы**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-115">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>

2. <span data-ttu-id="09ab4-116">Добавьте компонент в диалоговом окне **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-116">In the **Choose Toolbox Items** dialog box, add the component:</span></span>

    - <span data-ttu-id="09ab4-117">Чтобы добавить компонент или элемент управления .NET Framework, откройте вкладку **Компоненты .NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-117">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>

         <span data-ttu-id="09ab4-118">— или —</span><span class="sxs-lookup"><span data-stu-id="09ab4-118">– or –</span></span>

    - <span data-ttu-id="09ab4-119">Чтобы добавить COM-компонент или элемент управления ActiveX, откройте вкладку **COM-компоненты**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-119">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>

3. <span data-ttu-id="09ab4-120">Если элемент управления указан в диалоговом окне, выделите его и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-120">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>

     <span data-ttu-id="09ab4-121">Элемент управления будет добавлен на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-121">The control is added to the **Toolbox**.</span></span>

4. <span data-ttu-id="09ab4-122">Если элемент управления не указан в диалоговом окне, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="09ab4-122">If your control is not listed in the dialog box, do the following:</span></span>

    1. <span data-ttu-id="09ab4-123">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-123">Click the **Browse** button.</span></span>

    2. <span data-ttu-id="09ab4-124">Найдите папку с DLL-файлом, содержащим ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="09ab4-124">Browse to the folder that contains the .dll file that contains your control.</span></span>

    3. <span data-ttu-id="09ab4-125">Выберите этот DLL-файл и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-125">Select the .dll file and click **Open**.</span></span>

         <span data-ttu-id="09ab4-126">Элемент управления отобразится в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="09ab4-126">Your control appears in the dialog box.</span></span>

    4. <span data-ttu-id="09ab4-127">Выберите элемент управления и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-127">Confirm that your control is selected, and then click **OK**.</span></span>

         <span data-ttu-id="09ab4-128">Элемент управления будет добавлен на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-128">Your control is added to the **Toolbox**.</span></span>

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="09ab4-129">Не удается выполнить отладку пользовательского элемента управления или компонента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09ab4-129">Cannot Debug the Windows Forms User Control or Component</span></span>

<span data-ttu-id="09ab4-130">Если элемент управления является производным от класса <xref:System.Windows.Forms.UserControl>, можно отладить его поведение во время выполнения с тестовым контейнером.</span><span class="sxs-lookup"><span data-stu-id="09ab4-130">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="09ab4-131">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="09ab4-131">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="09ab4-132">Другие настраиваемые элементы управления и компоненты не являются автономными проектами</span><span class="sxs-lookup"><span data-stu-id="09ab4-132">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="09ab4-133">и должны размещаться в приложении, таком как проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="09ab4-133">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="09ab4-134">Для выполнения отладки элемент управления или компонент необходимо добавить в проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="09ab4-134">To debug a control or component, you must add it to a Windows Forms project.</span></span>

### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="09ab4-135">Отладка элемента управления или компонента</span><span class="sxs-lookup"><span data-stu-id="09ab4-135">To debug a control or component</span></span>

1. <span data-ttu-id="09ab4-136">В меню **Сборка** выберите пункт **Сборка решения**, чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="09ab4-136">From the **Build** menu, click **Build Solution** to build your solution.</span></span>

2. <span data-ttu-id="09ab4-137">В меню **Файл** выберите пункт **Добавить**, и затем **Новый проект**, чтобы добавить в приложение тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="09ab4-137">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>

3. <span data-ttu-id="09ab4-138">В диалоговом окне **Добавление нового проекта** выберите в качестве типа проекта **Приложение Windows**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-138">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>

4. <span data-ttu-id="09ab4-139">В **обозревателе решений** щелкните узел **Ссылки** для своего нового проекта правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="09ab4-139">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="09ab4-140">В контекстном меню выберите пункт **Добавить ссылку**, чтобы добавить ссылку на проект, содержащий элемент управления или компонент.</span><span class="sxs-lookup"><span data-stu-id="09ab4-140">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>

5. <span data-ttu-id="09ab4-141">Создайте экземпляр элемента управления или компонента в тестовом проекте.</span><span class="sxs-lookup"><span data-stu-id="09ab4-141">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="09ab4-142">Если компонент находится на **панели элементов**, его можно перетащить в область конструктора или создать экземпляр программными средствами, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="09ab4-142">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   <span data-ttu-id="09ab4-143">После этого отладку элемента управления или компонента можно выполнить в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="09ab4-143">You can now debug your control or component as usual.</span></span>

<span data-ttu-id="09ab4-144">Дополнительные сведения об отладке см. в разделах [Отладка в Visual Studio](/visualstudio/debugger/debugger-feature-tour) и [Пошаговое руководство: отладка пользовательского управления Windows Forms во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="09ab4-144">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="09ab4-145">Событие в производном элементе управления или компоненте вызывается дважды</span><span class="sxs-lookup"><span data-stu-id="09ab4-145">Event Is Raised Twice in Inherited Control or Component</span></span>

<span data-ttu-id="09ab4-146">Это может быть связано с дублированием предложения `Handles`.</span><span class="sxs-lookup"><span data-stu-id="09ab4-146">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="09ab4-147">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с унаследованными обработчиками событий в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="09ab4-147">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="09ab4-148">Ошибка времени разработки: "Не удалось создать компонент 'имя компонента'"</span><span class="sxs-lookup"><span data-stu-id="09ab4-148">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>

<span data-ttu-id="09ab4-149">Компонент или элемент управления должен предоставлять конструктор без параметров без аргументов.</span><span class="sxs-lookup"><span data-stu-id="09ab4-149">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="09ab4-150">Если в среде разработки создается экземпляр компонента или элемента управления, он не пытается предоставить какие-либо параметры для перегрузок конструктора, принимающих параметры.</span><span class="sxs-lookup"><span data-stu-id="09ab4-150">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>

## <a name="stathreadattribute"></a><span data-ttu-id="09ab4-151">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="09ab4-151">STAThreadAttribute</span></span>

<span data-ttu-id="09ab4-152"><xref:System.STAThreadAttribute> информирует среду CLR о том, что Windows Forms использует модель однопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="09ab4-152">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="09ab4-153">Если не применить этот атрибут к методу `Main` приложения Windows Forms, может возникнуть непредусмотренное поведение.</span><span class="sxs-lookup"><span data-stu-id="09ab4-153">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="09ab4-154">Например, фоновые изображения могут не отображаться для таких элементов управления, как <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="09ab4-154">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="09ab4-155">Некоторым элементам управления этот атрибут может требоваться также для правильного выполнения операций автозаполнения и перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="09ab4-155">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>

## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="09ab4-156">Значок компонента не отображается на панели элементов</span><span class="sxs-lookup"><span data-stu-id="09ab4-156">Component Icon Does Not Appear in Toolbox</span></span>

<span data-ttu-id="09ab4-157">При использовании <xref:System.Drawing.ToolboxBitmapAttribute> для связывания значка с пользовательским компонентом точечный рисунок не отображается на панели элементов для автоматически сформированных компонентов.</span><span class="sxs-lookup"><span data-stu-id="09ab4-157">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="09ab4-158">Чтобы увидеть растровое изображение, перезагрузите элемент управления с помощью диалогового окна **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="09ab4-158">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="09ab4-159">Дополнительные сведения см. в разделе [Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span><span class="sxs-lookup"><span data-stu-id="09ab4-159">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09ab4-160">См. также</span><span class="sxs-lookup"><span data-stu-id="09ab4-160">See also</span></span>

- [<span data-ttu-id="09ab4-161">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="09ab4-161">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="09ab4-162">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="09ab4-162">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="09ab4-163">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="09ab4-163">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="09ab4-164">Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="09ab4-164">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
