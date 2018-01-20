---
title: "Пример. Отладка пользовательских элементов управления Windows Forms во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4dfdc102a5aeb2e3eaccde28a8ce57a1878141e4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="f72d7-102">Пример. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="f72d7-103">При создании пользовательского элемента управления, вы обнаружите его необходимо выполнить отладку его поведение во время разработки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="f72d7-104">Это особенно важно при создании пользовательского конструктора для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="f72d7-105">Дополнительные сведения см. в разделе [Пошаговое руководство: создание Windows Forms управления, принимает преимущества от возможности Visual Studio во время разработки](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="f72d7-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="f72d7-106">Пользовательские элементы управления с помощью Visual Studio можно отлаживать так же образом, как и любые другие классы платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f72d7-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="f72d7-107">Различие заключается в том, что необходимо отладить отдельный экземпляр Visual Studio, на котором выполняется код элемента управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="f72d7-108">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="f72d7-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="f72d7-109">Создание проекта Windows Forms для размещения пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="f72d7-110">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="f72d7-111">Добавление свойства в элемент управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="f72d7-112">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="f72d7-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="f72d7-113">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="f72d7-114">Отладка пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="f72d7-115">Когда вы закончите, необходимо понимание задачи, необходимые для отладки поведения пользовательского элемента управления во время разработки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f72d7-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="f72d7-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f72d7-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="f72d7-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f72d7-118">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f72d7-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f72d7-119">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="f72d7-119">Creating the Project</span></span>  
 <span data-ttu-id="f72d7-120">Первым шагом является создание проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="f72d7-120">The first step is to create the application project.</span></span> <span data-ttu-id="f72d7-121">Этот проект будет использован для построения приложения, на котором размещается пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f72d7-122">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="f72d7-122">To create the project</span></span>  
  
-   <span data-ttu-id="f72d7-123">Создайте проект приложения Windows, называется «DebuggingExample».</span><span class="sxs-lookup"><span data-stu-id="f72d7-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="f72d7-124">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="f72d7-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="f72d7-125">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="f72d7-126">Следующим шагом является создание проекта библиотеки элементов управления и настроить пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="f72d7-127">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="f72d7-128">Добавить **библиотеки элементов управления Windows** проекта в решение.</span><span class="sxs-lookup"><span data-stu-id="f72d7-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="f72d7-129">Добавьте новый **UserControl** DebugControlLibrary проект.</span><span class="sxs-lookup"><span data-stu-id="f72d7-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="f72d7-130">Дополнительные сведения см. в разделе [NIB: Практическое: Добавление новых элементов проекта](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="f72d7-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="f72d7-131">Предоставьте новый исходный файл базовое имя «DebugControl».</span><span class="sxs-lookup"><span data-stu-id="f72d7-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="f72d7-132">С помощью **обозревателе решений**, удалите элемент управления проекта по умолчанию путем удаления файла с базовым именем «`UserControl1`».</span><span class="sxs-lookup"><span data-stu-id="f72d7-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="f72d7-133">Дополнительные сведения см. в разделе [NIB: Практическое: удаление, Delete и исключить элементы](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="f72d7-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="f72d7-134">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="f72d7-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="f72d7-135">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="f72d7-135">Checkpoint</span></span>  
 <span data-ttu-id="f72d7-136">На этом этапе можно увидеть пользовательского элемента управления в **элементов**.</span><span class="sxs-lookup"><span data-stu-id="f72d7-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="f72d7-137">Чтобы проверить состояние</span><span class="sxs-lookup"><span data-stu-id="f72d7-137">To check your progress</span></span>  
  
-   <span data-ttu-id="f72d7-138">Найти новая вкладка называется **компоненты DebugControlLibrary** и установите его.</span><span class="sxs-lookup"><span data-stu-id="f72d7-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="f72d7-139">При его открытии, появится в списке управления **DebugControl** со значком по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f72d7-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="f72d7-140">Добавление свойства в элемент управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="f72d7-141">Чтобы продемонстрировать выполнение кода пользовательского элемента управления во время разработки, будет добавить свойство и установите точку останова в коде, который реализует свойство.</span><span class="sxs-lookup"><span data-stu-id="f72d7-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="f72d7-142">Добавление свойства в элемент управления</span><span class="sxs-lookup"><span data-stu-id="f72d7-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="f72d7-143">Откройте **DebugControl** в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="f72d7-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="f72d7-144">Добавьте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="f72d7-144">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="f72d7-145">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="f72d7-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="f72d7-146">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="f72d7-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="f72d7-147">Для отладки поведения пользовательского элемента управления во время разработки, вы разместите экземпляр класса пользовательского элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="f72d7-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="f72d7-148">Добавление пользовательского элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="f72d7-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="f72d7-149">В проекте «DebuggingExample», откройте форму Form1 в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="f72d7-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="f72d7-150">В **элементов**откройте **DebugControlLibrary компоненты** а перетащите **DebugControl** экземпляр в форму.</span><span class="sxs-lookup"><span data-stu-id="f72d7-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="f72d7-151">Найти `DemoString` пользовательское свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="f72d7-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="f72d7-152">Обратите внимание, что его значение можно изменить, как и любого другого свойства.</span><span class="sxs-lookup"><span data-stu-id="f72d7-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="f72d7-153">Также Обратите внимание, что при `DemoString` выбрано свойство, строка описания свойства отображается в нижней части **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="f72d7-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="f72d7-154">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="f72d7-155">Для отладки поведения пользовательского элемента управления во время разработки, необходимо отладить отдельный экземпляр Visual Studio, на котором выполняется код элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="f72d7-156">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="f72d7-157">Щелкните правой кнопкой мыши **DebugControlLibrary** проекта в **обозревателе решений** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="f72d7-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="f72d7-158">В **DebugControlLibrary** вкладки свойств, выберите **отладки** вкладки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="f72d7-159">В **действие при запуске** выберите **запуск внешней программы**.</span><span class="sxs-lookup"><span data-stu-id="f72d7-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="f72d7-160">Можно отладка отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) чтобы выбрать Интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f72d7-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="f72d7-161">Имя исполняемого файла — **devenv.exe**, и если установлен в расположение по умолчанию, его путь — 9.0\Common7\IDE\devenv.exe %programfiles%\Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f72d7-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="f72d7-162">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="f72d7-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="f72d7-163">Щелкните правой кнопкой мыши **DebugControlLibrary** проект и выберите **Назначить запускаемым проектом** , чтобы включить конфигурацию отладки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="f72d7-164">Отладка пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="f72d7-165">Теперь все готово для отладки пользовательского элемента управления во время их выполнения в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="f72d7-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="f72d7-166">При запуске сеанса отладки будет создан новый экземпляр Visual Studio, и он будет использоваться для загрузки решения «DebuggingExample».</span><span class="sxs-lookup"><span data-stu-id="f72d7-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="f72d7-167">При открытии форму Form1 в **конструктор форм**, будет создан и запущен экземпляр пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="f72d7-168">Для отладки пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="f72d7-169">Откройте **DebugControl** исходный файл в **редактор кода** и установить точку останова на `Set` доступа `DemoString` свойство.</span><span class="sxs-lookup"><span data-stu-id="f72d7-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="f72d7-170">Нажмите клавишу F5 для запуска сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="f72d7-171">Обратите внимание, что создается новый экземпляр Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f72d7-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="f72d7-172">Может различать экземпляры двумя способами:</span><span class="sxs-lookup"><span data-stu-id="f72d7-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="f72d7-173">Экземпляр отладки имеет слово **под управлением** в своем заголовке.</span><span class="sxs-lookup"><span data-stu-id="f72d7-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="f72d7-174">У экземпляра отладки **запустить** кнопку на его **отладки** инструментов отключена</span><span class="sxs-lookup"><span data-stu-id="f72d7-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="f72d7-175">Точка останова устанавливается в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="f72d7-176">В новом экземпляре Visual Studio откройте решение «DebuggingExample».</span><span class="sxs-lookup"><span data-stu-id="f72d7-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="f72d7-177">Решение можно легко найти, выбрав **последние проекты** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="f72d7-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="f72d7-178">Файл решения «DebuggingExample.sln» будут указаны как список последних использовавшихся файлов.</span><span class="sxs-lookup"><span data-stu-id="f72d7-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="f72d7-179">Откройте форму Form1 в **конструктор форм** и выберите **DebugControl** элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="f72d7-180">Измените значение `DemoString` свойства.</span><span class="sxs-lookup"><span data-stu-id="f72d7-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="f72d7-181">Обратите внимание, что при фиксации изменений отладки экземпляр Visual Studio получает фокус выполнение останавливается в точке останова.</span><span class="sxs-lookup"><span data-stu-id="f72d7-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="f72d7-182">Можно пошагово выполнить метод доступа свойства так же, как к любой другой код.</span><span class="sxs-lookup"><span data-stu-id="f72d7-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="f72d7-183">При завершении сеанса отладки можно остановить закрыв второй экземпляр Visual Studio или нажав **остановить отладку** кнопки в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f72d7-184">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f72d7-184">Next Steps</span></span>  
 <span data-ttu-id="f72d7-185">Теперь, когда можно отлаживать пользовательских элементов управления во время разработки, существует множество возможностей для расширения элемента управления взаимодействием с Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="f72d7-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="f72d7-186">Можно использовать <xref:System.ComponentModel.Component.DesignMode%2A> свойство <xref:System.ComponentModel.Component> для написания кода, который будет выполняться только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="f72d7-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="f72d7-187">Дополнительные сведения см. в разделе <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f72d7-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="f72d7-188">Существует несколько атрибутов можно применять к свойствам элемента управления для управления взаимодействием элемента управления с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="f72d7-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="f72d7-189">Можно найти эти атрибуты в <xref:System.ComponentModel?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f72d7-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="f72d7-190">Можно написать пользовательский конструктор для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f72d7-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="f72d7-191">Это дает полный контроль над разработкой с помощью расширяемой инфраструктуры конструкторов в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f72d7-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="f72d7-192">Дополнительные сведения см. в разделе [Пошаговое руководство: создание Windows Forms управления, принимает преимущества от возможности Visual Studio во время разработки](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="f72d7-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72d7-193">См. также</span><span class="sxs-lookup"><span data-stu-id="f72d7-193">See Also</span></span>  
 [<span data-ttu-id="f72d7-194">Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="f72d7-195">Как: доступ к службам времени разработки</span><span class="sxs-lookup"><span data-stu-id="f72d7-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="f72d7-196">Практическое руководство. Доступ к поддержке во время разработки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f72d7-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
