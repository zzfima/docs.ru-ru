---
title: Пример локализации гибридного приложения
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 281afad0c0de856ca67abc74c65aff0e7afc3e01
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976501"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="94257-102">Пример локализации гибридного приложения</span><span class="sxs-lookup"><span data-stu-id="94257-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="94257-103">В этом пошаговом руководстве показано, как локализовать элементы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в гибридном приложении на основе [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94257-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="94257-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="94257-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="94257-105">Создание проекта [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] узла.</span><span class="sxs-lookup"><span data-stu-id="94257-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

- <span data-ttu-id="94257-106">Добавление локализуемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="94257-106">Adding localizable content.</span></span>

- <span data-ttu-id="94257-107">Включение локализации.</span><span class="sxs-lookup"><span data-stu-id="94257-107">Enabling localization.</span></span>

- <span data-ttu-id="94257-108">Назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="94257-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="94257-109">Использование средства LocBaml для создания вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="94257-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="94257-110">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [Локализация примера гибридного приложения](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="94257-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="94257-111">Закончив, вы получите локализованное гибридное приложение.</span><span class="sxs-lookup"><span data-stu-id="94257-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94257-112">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="94257-112">Prerequisites</span></span>

<span data-ttu-id="94257-113">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="94257-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="94257-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="94257-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="94257-115">Создание ведущего проекта Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94257-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="94257-116">Первым шагом является создание проекта приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и Добавление элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с содержимым, которое будет локализовано.</span><span class="sxs-lookup"><span data-stu-id="94257-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="94257-117">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="94257-117">To create the host project</span></span>

1. <span data-ttu-id="94257-118">Создайте проект **приложения WPF** с именем `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="94257-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="94257-119">(**Файл** > **Новый** > **проект** > **Visual C#**  или **Visual Basic** > **классическое** **приложение WPF**).</span><span class="sxs-lookup"><span data-stu-id="94257-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="94257-120">Добавьте в проект элемент <xref:System.Windows.Controls.UserControl> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]с именем `SimpleControl`.</span><span class="sxs-lookup"><span data-stu-id="94257-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="94257-121">Используйте элемент управления <xref:System.Windows.Forms.Integration.ElementHost>, чтобы поместить элемент `SimpleControl` в форму.</span><span class="sxs-lookup"><span data-stu-id="94257-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="94257-122">Дополнительные сведения см. [в разделе Пошаговое руководство. Размещение трехмерного составного элемента управления WPF в Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="94257-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="94257-123">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="94257-123">Adding Localizable Content</span></span>

<span data-ttu-id="94257-124">Далее предстоит добавить элемент управления Label [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] и задать содержимое элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для локализуемой строки.</span><span class="sxs-lookup"><span data-stu-id="94257-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="94257-125">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="94257-125">To add localizable content</span></span>

1. <span data-ttu-id="94257-126">В **Обозреватель решений**дважды щелкните **SimpleControl. XAML** , чтобы открыть его в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="94257-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="94257-127">Задайте содержимое элемента управления <xref:System.Windows.Controls.Button> с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="94257-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="94257-128">В **Обозреватель решений**дважды щелкните **Form1** , чтобы открыть его в конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94257-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="94257-129">Откройте **панель элементов** и дважды щелкните **подпись** , чтобы добавить в форму элемент управления "надпись".</span><span class="sxs-lookup"><span data-stu-id="94257-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="94257-130">Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="94257-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="94257-131">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="94257-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="94257-132">Элемент `SimpleControl` и элемент управления Label отображают текст **"Hello"** .</span><span class="sxs-lookup"><span data-stu-id="94257-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="94257-133">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="94257-133">Enabling Localization</span></span>

<span data-ttu-id="94257-134">Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.</span><span class="sxs-lookup"><span data-stu-id="94257-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="94257-135">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="94257-135">To enable localization</span></span>

1. <span data-ttu-id="94257-136">В **Обозреватель решений**дважды щелкните **Form1.CS** , чтобы открыть его в конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="94257-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="94257-137">В окне **Свойства** задайте для свойства **localizable** формы значение `true`.</span><span class="sxs-lookup"><span data-stu-id="94257-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="94257-138">В окне **Свойства** задайте для свойства **язык** значение **Испанский (Испания)** .</span><span class="sxs-lookup"><span data-stu-id="94257-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="94257-139">В конструкторе Windows Forms выберите элемент управления label.</span><span class="sxs-lookup"><span data-stu-id="94257-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="94257-140">В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> значение `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="94257-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="94257-141">Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="94257-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="94257-142">В **Обозреватель решений**щелкните правой кнопкой мыши **Form1.CS** и выберите пункт **Просмотреть код** , чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="94257-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="94257-143">Скопируйте следующий код в конструктор `Form1`, предшествующий вызову `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="94257-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="94257-144">В **Обозреватель решений**щелкните правой кнопкой мыши **LocalizingWpfInWf** и выберите команду **Выгрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="94257-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="94257-145">Имя проекта помечено как **(недоступно)** .</span><span class="sxs-lookup"><span data-stu-id="94257-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="94257-146">Щелкните правой кнопкой мыши **LocalizingWpfInWf**и выберите **изменить LocalizingWpfInWf. csproj**.</span><span class="sxs-lookup"><span data-stu-id="94257-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="94257-147">Файл проекта откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="94257-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="94257-148">Скопируйте следующую строку в первую `PropertyGroup` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="94257-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="94257-149">Сохраните файл проекта и закройте его.</span><span class="sxs-lookup"><span data-stu-id="94257-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="94257-150">В **Обозреватель решений**щелкните правой кнопкой мыши **LocalizingWpfInWf** и выберите **Перезагрузить проект**.</span><span class="sxs-lookup"><span data-stu-id="94257-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="94257-151">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="94257-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="94257-152">Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="94257-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="94257-153">Приложение MsBuild. exe автоматически назначает идентификаторы ресурсов при указании параметра `updateuid`.</span><span class="sxs-lookup"><span data-stu-id="94257-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="94257-154">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="94257-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="94257-155">В меню Пуск откройте Командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94257-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="94257-156">Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.</span><span class="sxs-lookup"><span data-stu-id="94257-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="94257-157">В **Обозреватель решений**дважды щелкните **SimpleControl. XAML** , чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="94257-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="94257-158">Вы увидите, что команда `msbuild` добавила атрибут `Uid` ко всем элементам.</span><span class="sxs-lookup"><span data-stu-id="94257-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="94257-159">Это облегчает локализацию через назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="94257-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="94257-160">Нажмите клавишу **F6** , чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="94257-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="94257-161">Использование LocBaml для создания вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="94257-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="94257-162">Локализованное содержимое хранится в *вспомогательной сборке*с ресурсами только для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="94257-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="94257-163">Используйте программу командной строки LocBaml. exe для создания локализованной сборки для содержимого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="94257-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="94257-164">Создание вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="94257-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="94257-165">Скопируйте файл LocBaml.exe в папку проекта obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="94257-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="94257-166">Дополнительные сведения см. в разделе [Локализация приложения](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="94257-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="94257-167">В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.</span><span class="sxs-lookup"><span data-stu-id="94257-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="94257-168">Откройте файл TEMP. csv в Visual Studio или другом текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="94257-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="94257-169">Замените строку `"Hello"` на ее Испанский перевод, `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="94257-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="94257-170">Сохраните файл temp.csv.</span><span class="sxs-lookup"><span data-stu-id="94257-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="94257-171">Используйте приведенную ниже команду для создания локализованного файла ресурса.</span><span class="sxs-lookup"><span data-stu-id="94257-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="94257-172">Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="94257-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="94257-173">Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="94257-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="94257-174">Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="94257-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="94257-175">Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES.</span><span class="sxs-lookup"><span data-stu-id="94257-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="94257-176">Замените существующий файл.</span><span class="sxs-lookup"><span data-stu-id="94257-176">Replace the existing file.</span></span>

8. <span data-ttu-id="94257-177">Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="94257-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="94257-178">Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.</span><span class="sxs-lookup"><span data-stu-id="94257-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="94257-179">В приложении выводятся локализованные строки вместо английских строк.</span><span class="sxs-lookup"><span data-stu-id="94257-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="94257-180">См. также</span><span class="sxs-lookup"><span data-stu-id="94257-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="94257-181">Локализация приложения</span><span class="sxs-lookup"><span data-stu-id="94257-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="94257-182">[Пошаговое руководство. Локализация Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="94257-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="94257-183">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94257-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
