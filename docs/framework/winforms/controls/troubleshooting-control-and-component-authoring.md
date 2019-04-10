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
ms.openlocfilehash: 3ae8a889bf69913d234e31804335ddb08560c30c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343419"
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="2e85f-102">Разрешение вопросов, связанных с созданием элементов управления и компонентов</span><span class="sxs-lookup"><span data-stu-id="2e85f-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="2e85f-103">В этом разделе перечислены распространенные проблемы, возникающие при разработке компонентов и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="2e85f-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="2e85f-104">Дополнительные сведения см. в разделе [Программирование с использованием компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2e85f-104">For more information, see [Programming with Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
-   <span data-ttu-id="2e85f-105">Не удается добавить элемент управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="2e85f-105">Cannot Add Control to Toolbox</span></span>  
  
-   <span data-ttu-id="2e85f-106">Не удается выполнить отладку пользовательского элемента управления или компонента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e85f-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
-   <span data-ttu-id="2e85f-107">Событие в производном элементе управления или компоненте вызывается дважды</span><span class="sxs-lookup"><span data-stu-id="2e85f-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
-   <span data-ttu-id="2e85f-108">Ошибка во время разработки. «Не удалось создать компонент "*имя компонента*"»</span><span class="sxs-lookup"><span data-stu-id="2e85f-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
-   <span data-ttu-id="2e85f-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="2e85f-109">STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="2e85f-110">Значок компонента не отображается на панели элементов</span><span class="sxs-lookup"><span data-stu-id="2e85f-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="2e85f-111">Не удается добавить элемент управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="2e85f-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="2e85f-112">Если вы хотите добавить на **панель элементов** настраиваемый элемент управления, созданный в другом проекте, или сторонний элемент управления, это необходимо сделать вручную.</span><span class="sxs-lookup"><span data-stu-id="2e85f-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="2e85f-113">Если ваш элемент управления или компонент уже находится в текущем проекте, он отобразится на **панели элементов** автоматически.</span><span class="sxs-lookup"><span data-stu-id="2e85f-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="2e85f-114">Дополнительные сведения см. в разделе [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="2e85f-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="2e85f-115">Добавление элемента управления на панель элементов</span><span class="sxs-lookup"><span data-stu-id="2e85f-115">To add a control to the Toolbox</span></span>  
  
1. <span data-ttu-id="2e85f-116">Щелкните **панель инструментов** правой кнопкой мыши и выберите команду **Выбрать элементы**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2. <span data-ttu-id="2e85f-117">Добавьте компонент в диалоговом окне **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    -   <span data-ttu-id="2e85f-118">Чтобы добавить компонент или элемент управления .NET Framework, откройте вкладку **Компоненты .NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="2e85f-119">— или —</span><span class="sxs-lookup"><span data-stu-id="2e85f-119">– or –</span></span>  
  
    -   <span data-ttu-id="2e85f-120">Чтобы добавить COM-компонент или элемент управления ActiveX, откройте вкладку **COM-компоненты**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3. <span data-ttu-id="2e85f-121">Если элемент управления указан в диалоговом окне, выделите его и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="2e85f-122">Элемент управления будет добавлен на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-122">The control is added to the **Toolbox**.</span></span>  
  
4. <span data-ttu-id="2e85f-123">Если элемент управления не указан в диалоговом окне, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2e85f-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="2e85f-124">Нажмите кнопку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-124">Click the **Browse** button.</span></span>  
  
    2.  <span data-ttu-id="2e85f-125">Найдите папку с DLL-файлом, содержащим ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="2e85f-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3.  <span data-ttu-id="2e85f-126">Выберите этот DLL-файл и нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="2e85f-127">Элемент управления отобразится в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="2e85f-127">Your control appears in the dialog box.</span></span>  
  
    4.  <span data-ttu-id="2e85f-128">Выберите элемент управления и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="2e85f-129">Элемент управления будет добавлен на **панель элементов**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="2e85f-130">Не удается выполнить отладку пользовательского элемента управления или компонента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e85f-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="2e85f-131">Если элемент управления является производным от <xref:System.Windows.Forms.UserControl> класса, можно отлаживать его поведение во время выполнения с использованием тестового контейнера.</span><span class="sxs-lookup"><span data-stu-id="2e85f-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="2e85f-132">Дополнительные сведения см. в разделе [Как Тестирование во время выполнения поведения элемента UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="2e85f-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="2e85f-133">Другие настраиваемые элементы управления и компоненты не являются автономными проектами</span><span class="sxs-lookup"><span data-stu-id="2e85f-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="2e85f-134">и должны размещаться в приложении, таком как проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2e85f-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="2e85f-135">Для выполнения отладки элемент управления или компонент необходимо добавить в проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2e85f-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="2e85f-136">Отладка элемента управления или компонента</span><span class="sxs-lookup"><span data-stu-id="2e85f-136">To debug a control or component</span></span>  
  
1. <span data-ttu-id="2e85f-137">В меню **Сборка** выберите пункт **Сборка решения**, чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="2e85f-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2. <span data-ttu-id="2e85f-138">В меню **Файл** выберите пункт **Добавить**, и затем **Новый проект**, чтобы добавить в приложение тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="2e85f-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3. <span data-ttu-id="2e85f-139">В диалоговом окне **Добавление нового проекта** выберите в качестве типа проекта **Приложение Windows**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4. <span data-ttu-id="2e85f-140">В **обозревателе решений** щелкните узел **Ссылки** для своего нового проекта правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="2e85f-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="2e85f-141">В контекстном меню выберите пункт **Добавить ссылку**, чтобы добавить ссылку на проект, содержащий элемент управления или компонент.</span><span class="sxs-lookup"><span data-stu-id="2e85f-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5. <span data-ttu-id="2e85f-142">Создайте экземпляр элемента управления или компонента в тестовом проекте.</span><span class="sxs-lookup"><span data-stu-id="2e85f-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="2e85f-143">Если компонент находится на **панели элементов**, его можно перетащить в область конструктора или создать экземпляр программными средствами, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="2e85f-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="2e85f-144">После этого отладку элемента управления или компонента можно выполнить в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="2e85f-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="2e85f-145">Дополнительные сведения об отладке см. в разделе [отладки в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) и [Пошаговое руководство: Отладка пользовательских Windows Forms элементы управления во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="2e85f-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="2e85f-146">Событие в производном элементе управления или компоненте вызывается дважды</span><span class="sxs-lookup"><span data-stu-id="2e85f-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="2e85f-147">Это может быть связано с дублированием предложения `Handles`.</span><span class="sxs-lookup"><span data-stu-id="2e85f-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="2e85f-148">Дополнительные сведения см. в разделе [Устранение неполадок, связанных с унаследованными обработчиками событий в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="2e85f-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="2e85f-149">Ошибка во время разработки. «Не удалось создать компонент 'Имя компонента'»</span><span class="sxs-lookup"><span data-stu-id="2e85f-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="2e85f-150">Компонент или элемент управления должен предоставлять конструктор по умолчанию без параметров.</span><span class="sxs-lookup"><span data-stu-id="2e85f-150">Your component or control must provide a default constructor with no parameters.</span></span> <span data-ttu-id="2e85f-151">Если в среде разработки создается экземпляр компонента или элемента управления, он не пытается предоставить какие-либо параметры для перегрузок конструктора, принимающих параметры.</span><span class="sxs-lookup"><span data-stu-id="2e85f-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="2e85f-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="2e85f-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="2e85f-153"><xref:System.STAThreadAttribute> Информирует общеязыковой среды выполнения (CLR) о том, что Windows Forms использует модель однопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="2e85f-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="2e85f-154">Если не применить этот атрибут к методу `Main` приложения Windows Forms, может возникнуть непредусмотренное поведение.</span><span class="sxs-lookup"><span data-stu-id="2e85f-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="2e85f-155">Например, фоновые изображения может отображаться для элементов управления, например <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="2e85f-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="2e85f-156">Некоторым элементам управления этот атрибут может требоваться также для правильного выполнения операций автозаполнения и перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2e85f-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="2e85f-157">Значок компонента не отображается на панели элементов</span><span class="sxs-lookup"><span data-stu-id="2e85f-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="2e85f-158">При использовании <xref:System.Drawing.ToolboxBitmapAttribute> для сопоставления значка с настраиваемым, растровое изображение не отображается в панели элементов для автоматически созданных компонентов.</span><span class="sxs-lookup"><span data-stu-id="2e85f-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="2e85f-159">Чтобы увидеть растровое изображение, перезагрузите элемент управления с помощью диалогового окна **Выбор элементов панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="2e85f-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="2e85f-160">Дополнительные сведения см. в разделе [Как Предоставление точечного рисунка панели элементов для элемента управления](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span><span class="sxs-lookup"><span data-stu-id="2e85f-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e85f-161">См. также</span><span class="sxs-lookup"><span data-stu-id="2e85f-161">See also</span></span>

- [<span data-ttu-id="2e85f-162">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2e85f-162">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="2e85f-163">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="2e85f-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="2e85f-164">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="2e85f-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="2e85f-165">Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="2e85f-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="2e85f-166">Создание компонентов</span><span class="sxs-lookup"><span data-stu-id="2e85f-166">Component Authoring</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/5dya64wy(v=vs.120))
- [<span data-ttu-id="2e85f-167">Устранение неполадок, возникающих в режиме разработки</span><span class="sxs-lookup"><span data-stu-id="2e85f-167">Troubleshooting Design-Time Development</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
