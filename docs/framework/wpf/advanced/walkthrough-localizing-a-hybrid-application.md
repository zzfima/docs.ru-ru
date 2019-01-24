---
title: Пошаговое руководство. Локализация гибридного приложения
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 3d658d0dfb07a636a7338c69cae93b7e8a54383e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613874"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="80c8e-102">Пошаговое руководство. Локализация гибридного приложения</span><span class="sxs-lookup"><span data-stu-id="80c8e-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="80c8e-103">В этом пошаговом руководстве показано, как локализовать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементов в [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-гибридные приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="80c8e-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="80c8e-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="80c8e-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="80c8e-105">Создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] узла проекта.</span><span class="sxs-lookup"><span data-stu-id="80c8e-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

-   <span data-ttu-id="80c8e-106">Добавление локализуемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="80c8e-106">Adding localizable content.</span></span>

-   <span data-ttu-id="80c8e-107">Включение локализации.</span><span class="sxs-lookup"><span data-stu-id="80c8e-107">Enabling localization.</span></span>

-   <span data-ttu-id="80c8e-108">Назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="80c8e-108">Assigning resource identifiers.</span></span>

-   <span data-ttu-id="80c8e-109">Использование средства LocBaml для создания вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="80c8e-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="80c8e-110">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. в разделе [локализация гибридного приложения образец](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="80c8e-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="80c8e-111">Закончив, вы получите локализованное гибридное приложение.</span><span class="sxs-lookup"><span data-stu-id="80c8e-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80c8e-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="80c8e-112">Prerequisites</span></span>

<span data-ttu-id="80c8e-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="80c8e-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="80c8e-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="80c8e-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="80c8e-115">Создание ведущего проекта Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c8e-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="80c8e-116">Первым шагом является создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] приложения проекта и добавьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент содержимого, которое будет локализовано.</span><span class="sxs-lookup"><span data-stu-id="80c8e-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="80c8e-117">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="80c8e-117">To create the host project</span></span>

1.  <span data-ttu-id="80c8e-118">Создание **приложение WPF** проект с именем `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="80c8e-119">(**Файл** > **новый** > **проекта** > **Visual C#** или **Visual Basic**   >  **Классический рабочий стол** > **приложение WPF**).</span><span class="sxs-lookup"><span data-stu-id="80c8e-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2.  <span data-ttu-id="80c8e-120">Добавить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> элемент с именем `SimpleControl` в проект.</span><span class="sxs-lookup"><span data-stu-id="80c8e-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3.  <span data-ttu-id="80c8e-121">Используйте <xref:System.Windows.Forms.Integration.ElementHost> элементу управления размещение `SimpleControl` элемент на форме.</span><span class="sxs-lookup"><span data-stu-id="80c8e-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="80c8e-122">Дополнительные сведения см. в разделе [Пошаговое руководство: Размещение составного элемента управления WPF, трехмерного в Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="80c8e-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="80c8e-123">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="80c8e-123">Adding Localizable Content</span></span>

<span data-ttu-id="80c8e-124">Далее вы добавите [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] метки элемента управления и задайте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое элемента Локализованная строка.</span><span class="sxs-lookup"><span data-stu-id="80c8e-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="80c8e-125">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="80c8e-125">To add localizable content</span></span>

1.  <span data-ttu-id="80c8e-126">В **обозревателе решений**, дважды щелкните **SimpleControl.xaml** чтобы открыть его в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80c8e-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2.  <span data-ttu-id="80c8e-127">Установка содержимого для <xref:System.Windows.Controls.Button> управления, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="80c8e-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3.  <span data-ttu-id="80c8e-128">В **обозревателе решений**, дважды щелкните **Form1** чтобы открыть его в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80c8e-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4.  <span data-ttu-id="80c8e-129">Откройте **элементов** и дважды щелкните **метка** для добавления в форму элемент управления label.</span><span class="sxs-lookup"><span data-stu-id="80c8e-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="80c8e-130">Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5.  <span data-ttu-id="80c8e-131">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="80c8e-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="80c8e-132">Оба `SimpleControl` отображать текст, элемент и элемент управления label **«Hello»**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="80c8e-133">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="80c8e-133">Enabling Localization</span></span>

<span data-ttu-id="80c8e-134">Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.</span><span class="sxs-lookup"><span data-stu-id="80c8e-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="80c8e-135">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="80c8e-135">To enable localization</span></span>

1.  <span data-ttu-id="80c8e-136">В **обозревателе решений**, дважды щелкните **Form1.cs** чтобы открыть его в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80c8e-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2.  <span data-ttu-id="80c8e-137">В **свойства** окна, задайте для свойства формы **Localizable** свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3.  <span data-ttu-id="80c8e-138">В **свойства** окна, установите для параметра **языка** свойства **испанский (Испания)**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4.  <span data-ttu-id="80c8e-139">В конструкторе Windows Forms выберите элемент управления label.</span><span class="sxs-lookup"><span data-stu-id="80c8e-139">In the Windows Forms Designer, select the label control.</span></span>

5.  <span data-ttu-id="80c8e-140">В **свойства** окна, установите для параметра <xref:System.Windows.Forms.Control.Text%2A> свойства `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="80c8e-141">Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="80c8e-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6.  <span data-ttu-id="80c8e-142">В **обозревателе решений**, щелкните правой кнопкой мыши **Form1.cs** и нажмите кнопку **Просмотр кода** чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="80c8e-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7.  <span data-ttu-id="80c8e-143">Скопируйте следующий код в `Form1` конструктор, предшествующий вызову `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8.  <span data-ttu-id="80c8e-144">В **обозревателе решений**, щелкните правой кнопкой мыши **LocalizingWpfInWf** и нажмите кнопку **выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="80c8e-145">Имя проекта помечается **(недоступно)**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="80c8e-146">Щелкните правой кнопкой мыши **LocalizingWpfInWf**и нажмите кнопку **изменить LocalizingWpfInWf.csproj**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="80c8e-147">Файл проекта откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="80c8e-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="80c8e-148">Скопируйте следующую строку в первый `PropertyGroup` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="80c8e-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="80c8e-149">Сохраните файл проекта и закройте его.</span><span class="sxs-lookup"><span data-stu-id="80c8e-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="80c8e-150">В **обозревателе решений**, щелкните правой кнопкой мыши **LocalizingWpfInWf** и нажмите кнопку **перезагрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="80c8e-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="80c8e-151">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="80c8e-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="80c8e-152">Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="80c8e-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="80c8e-153">Приложение MsBuild.exe автоматически назначает идентификаторы ресурсов при указании `updateuid` параметр.</span><span class="sxs-lookup"><span data-stu-id="80c8e-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="80c8e-154">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="80c8e-154">To assign resource identifiers</span></span>

1.  <span data-ttu-id="80c8e-155">Из меню "Пуск" откройте командную строку разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80c8e-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2.  <span data-ttu-id="80c8e-156">Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.</span><span class="sxs-lookup"><span data-stu-id="80c8e-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3.  <span data-ttu-id="80c8e-157">В **обозревателе решений**, дважды щелкните **SimpleControl.xaml** чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="80c8e-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="80c8e-158">Вы увидите, что `msbuild` команды добавил `Uid` атрибута ко всем элементам.</span><span class="sxs-lookup"><span data-stu-id="80c8e-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="80c8e-159">Это облегчает локализацию через назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="80c8e-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4.  <span data-ttu-id="80c8e-160">Нажмите клавишу **F6** для сборки решения.</span><span class="sxs-lookup"><span data-stu-id="80c8e-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="80c8e-161">Использование LocBaml для создания вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="80c8e-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="80c8e-162">Локализованное содержимое хранится в содержащей только ресурсы *вспомогательную сборку*.</span><span class="sxs-lookup"><span data-stu-id="80c8e-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="80c8e-163">Используйте средство командной строки LocBaml.exe, чтобы создать локализованную сборку для вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимого.</span><span class="sxs-lookup"><span data-stu-id="80c8e-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="80c8e-164">Создание вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="80c8e-164">To produce a satellite assembly</span></span>

1.  <span data-ttu-id="80c8e-165">Скопируйте файл LocBaml.exe в папку проекта obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="80c8e-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="80c8e-166">Дополнительные сведения см. в разделе [локализация приложения](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="80c8e-166">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>

2.  <span data-ttu-id="80c8e-167">В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.</span><span class="sxs-lookup"><span data-stu-id="80c8e-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3.  <span data-ttu-id="80c8e-168">Откройте файл temp.csv с помощью Visual Studio или другого текстового редактора.</span><span class="sxs-lookup"><span data-stu-id="80c8e-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="80c8e-169">Замените строку `"Hello"` на ее испанский перевод `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="80c8e-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4.  <span data-ttu-id="80c8e-170">Сохраните файл temp.csv.</span><span class="sxs-lookup"><span data-stu-id="80c8e-170">Save the temp.csv file.</span></span>

5.  <span data-ttu-id="80c8e-171">Используйте приведенную ниже команду для создания локализованного файла ресурса.</span><span class="sxs-lookup"><span data-stu-id="80c8e-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="80c8e-172">Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="80c8e-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6.  <span data-ttu-id="80c8e-173">Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="80c8e-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="80c8e-174">Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="80c8e-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7.  <span data-ttu-id="80c8e-175">Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES.</span><span class="sxs-lookup"><span data-stu-id="80c8e-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="80c8e-176">Замените существующий файл.</span><span class="sxs-lookup"><span data-stu-id="80c8e-176">Replace the existing file.</span></span>

8.  <span data-ttu-id="80c8e-177">Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="80c8e-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="80c8e-178">Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.</span><span class="sxs-lookup"><span data-stu-id="80c8e-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="80c8e-179">В приложении выводятся локализованные строки вместо английских строк.</span><span class="sxs-lookup"><span data-stu-id="80c8e-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="80c8e-180">См. также</span><span class="sxs-lookup"><span data-stu-id="80c8e-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="80c8e-181">Локализация приложения</span><span class="sxs-lookup"><span data-stu-id="80c8e-181">Localize an Application</span></span>](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)
- [<span data-ttu-id="80c8e-182">Пошаговое руководство: Локализация форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c8e-182">Walkthrough: Localizing Windows Forms</span></span>](https://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)
- [<span data-ttu-id="80c8e-183">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="80c8e-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
