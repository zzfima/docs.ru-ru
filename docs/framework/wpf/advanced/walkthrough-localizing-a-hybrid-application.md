---
title: Пример локализации гибридного приложения
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 69aa5ae145ffe378b7a4547e5a33826965bf7894
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111118"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="af738-102">Пример локализации гибридного приложения</span><span class="sxs-lookup"><span data-stu-id="af738-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="af738-103">В этом пошаговом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] показании показано, как локализовать элементы в гибридном приложении на базе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="af738-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a Windows Forms-based hybrid application.</span></span>

<span data-ttu-id="af738-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="af738-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="af738-105">Создание принимающего проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="af738-105">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="af738-106">Добавление локализуемого содержимого.</span><span class="sxs-lookup"><span data-stu-id="af738-106">Adding localizable content.</span></span>

- <span data-ttu-id="af738-107">Включение локализации.</span><span class="sxs-lookup"><span data-stu-id="af738-107">Enabling localization.</span></span>

- <span data-ttu-id="af738-108">Назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="af738-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="af738-109">Использование средства LocBaml для создания вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="af738-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="af738-110">Для полного перечисления кода задач, иллюстрированных в этом пошаговом шаге, [см.](https://go.microsoft.com/fwlink/?LinkID=160015)</span><span class="sxs-lookup"><span data-stu-id="af738-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="af738-111">Закончив, вы получите локализованное гибридное приложение.</span><span class="sxs-lookup"><span data-stu-id="af738-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="af738-112">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="af738-112">Prerequisites</span></span>

<span data-ttu-id="af738-113">Для выполнения этого пошагового руководства требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="af738-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="af738-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="af738-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="af738-115">Создание ведущего проекта Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af738-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="af738-116">Первым шагом является создание проекта приложения Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms и добавление элемента с контентом, который вы будете локализовать.</span><span class="sxs-lookup"><span data-stu-id="af738-116">The first step is to create the Windows Forms application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="af738-117">Создание ведущего проекта</span><span class="sxs-lookup"><span data-stu-id="af738-117">To create the host project</span></span>

1. <span data-ttu-id="af738-118">Создайте проект приложения `LocalizingWpfInWf` **WPF** под названием .</span><span class="sxs-lookup"><span data-stu-id="af738-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="af738-119">(**Файл** > **новый** > **проект** > **Визуальный C или** **Визуальный Базовый** > **Классический настольный WPF** > **приложение**).</span><span class="sxs-lookup"><span data-stu-id="af738-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="af738-120">Добавьте [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> элемент, вызванный `SimpleControl` в проект.</span><span class="sxs-lookup"><span data-stu-id="af738-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="af738-121">Используйте <xref:System.Windows.Forms.Integration.ElementHost> элемент управления, чтобы поместить `SimpleControl` элемент на форму.</span><span class="sxs-lookup"><span data-stu-id="af738-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="af738-122">Для получения дополнительной информации [см.](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="af738-122">For more information, see [Walkthrough: Hosting a 3D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="af738-123">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="af738-123">Adding Localizable Content</span></span>

<span data-ttu-id="af738-124">Далее вы добавите элемент управления меткой Windows Forms и установите [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] содержимое элемента в локализуемую строку.</span><span class="sxs-lookup"><span data-stu-id="af738-124">Next, you will add a Windows Forms label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="af738-125">Добавление локализуемого содержимого</span><span class="sxs-lookup"><span data-stu-id="af738-125">To add localizable content</span></span>

1. <span data-ttu-id="af738-126">В **Solution Explorer**, дважды щелкните **SimpleControl.xaml,** чтобы открыть его в WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="af738-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the WPF Designer.</span></span>

2. <span data-ttu-id="af738-127">Установите содержимое <xref:System.Windows.Controls.Button> элемента управления, используя следующий код.</span><span class="sxs-lookup"><span data-stu-id="af738-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="af738-128">В **Solution Explorer**, дважды нажмите **Form1,** чтобы открыть его в Windows Forms Designer.</span><span class="sxs-lookup"><span data-stu-id="af738-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="af738-129">Откройте **Toolbox** и дважды щелкните **этикетку,** чтобы добавить элемент управления этикеткой в форму.</span><span class="sxs-lookup"><span data-stu-id="af738-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="af738-130">Задайте для его свойства <xref:System.Windows.Forms.Control.Text%2A> значение `"Hello"`.</span><span class="sxs-lookup"><span data-stu-id="af738-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="af738-131">Нажмите **F5,** чтобы построить и запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="af738-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="af738-132">И `SimpleControl` элемент, и элемент управления отображением текста **"Hello".**</span><span class="sxs-lookup"><span data-stu-id="af738-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="af738-133">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="af738-133">Enabling Localization</span></span>

<span data-ttu-id="af738-134">Конструктор Windows Forms предоставляет параметры для включения локализации во вспомогательной сборке.</span><span class="sxs-lookup"><span data-stu-id="af738-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="af738-135">Включение локализации</span><span class="sxs-lookup"><span data-stu-id="af738-135">To enable localization</span></span>

1. <span data-ttu-id="af738-136">В **Solution Explorer**, дважды нажмите **Form1.cs,** чтобы открыть его в Windows Forms Designer.</span><span class="sxs-lookup"><span data-stu-id="af738-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="af738-137">В окне **Свойств** установить значение **локального** свойства формы. `true`</span><span class="sxs-lookup"><span data-stu-id="af738-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="af738-138">В окне **Свойства** установите стоимость **языковой** недвижимости на **испанский язык (Испания).**</span><span class="sxs-lookup"><span data-stu-id="af738-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="af738-139">В конструкторе Windows Forms выберите элемент управления label.</span><span class="sxs-lookup"><span data-stu-id="af738-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="af738-140">В окне **Свойств** установить <xref:System.Windows.Forms.Control.Text%2A> значение `"Hola"`свойства .</span><span class="sxs-lookup"><span data-stu-id="af738-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="af738-141">Новый файл ресурсов с именем Form1.es-ES.resx будет добавлен в проект.</span><span class="sxs-lookup"><span data-stu-id="af738-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="af738-142">В **Solution Explorer**, правой кнопкой мыши **Form1.cs** и нажмите **View Code,** чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="af738-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="af738-143">Копируйте следующий `Form1` код в конструкторе, `InitializeComponent`предшествуя вызову.</span><span class="sxs-lookup"><span data-stu-id="af738-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="af738-144">В **Solution Explorer**, правой кнопкой **локализованияWpfInWf** и нажмите **Разгрузить проекта**.</span><span class="sxs-lookup"><span data-stu-id="af738-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="af738-145">Название проекта помечено **(недоступно).**</span><span class="sxs-lookup"><span data-stu-id="af738-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="af738-146">Нажмите правой кнопкой **локализованияWpfInWf**, и нажмите **Edit LocalizingWpfWf.csproj**.</span><span class="sxs-lookup"><span data-stu-id="af738-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="af738-147">Файл проекта откроется в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="af738-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="af738-148">Копируйте следующую строку в первую `PropertyGroup` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="af738-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="af738-149">Сохраните файл проекта и закройте его.</span><span class="sxs-lookup"><span data-stu-id="af738-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="af738-150">В **Solution Explorer**, правой кнопкой **локализованияWpfInWf** и нажмите **Reload Project**.</span><span class="sxs-lookup"><span data-stu-id="af738-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="af738-151">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="af738-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="af738-152">Вы можете сопоставить локализуемое содержимое со сборками ресурсов с помощью идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="af738-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="af738-153">Приложение MsBuild.exe автоматически назначает идентификаторы ресурсов при указании опции. `updateuid`</span><span class="sxs-lookup"><span data-stu-id="af738-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="af738-154">Назначение идентификаторов ресурсов</span><span class="sxs-lookup"><span data-stu-id="af738-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="af738-155">Из меню «Пуск» откройте командный запрос разработчика для визуальной студии.</span><span class="sxs-lookup"><span data-stu-id="af738-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="af738-156">Используйте приведенную ниже команду для назначения идентификаторов ресурсов вашему локализуемому содержимому.</span><span class="sxs-lookup"><span data-stu-id="af738-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="af738-157">В **Solution Explorer**, дважды щелкните **SimpleControl.xaml,** чтобы открыть его в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="af738-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="af738-158">Вы увидите, `msbuild` что команда `Uid` добавила атрибут ко всем элементам.</span><span class="sxs-lookup"><span data-stu-id="af738-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="af738-159">Это облегчает локализацию через назначение идентификаторов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="af738-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="af738-160">Нажмите клавишу **F6**, чтобы построить решение.</span><span class="sxs-lookup"><span data-stu-id="af738-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="af738-161">Использование LocBaml для создания вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="af738-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="af738-162">Локализованное содержимое хранится в *спутниковой сборке*только для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="af738-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="af738-163">Используйте инструмент командной строки LocBaml.exe для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создания локализованной сборки для вашего содержимого.</span><span class="sxs-lookup"><span data-stu-id="af738-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="af738-164">Создание вспомогательной сборки</span><span class="sxs-lookup"><span data-stu-id="af738-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="af738-165">Скопируйте файл LocBaml.exe в папку проекта obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="af738-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="af738-166">Для получения дополнительной информации [см.](how-to-localize-an-application.md)</span><span class="sxs-lookup"><span data-stu-id="af738-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="af738-167">В окне командной строки используйте приведенную ниже команду для извлечения строк ресурсов во временный файл.</span><span class="sxs-lookup"><span data-stu-id="af738-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="af738-168">Откройте файл temp.csv с Visual Studio или другим текстовым редактором.</span><span class="sxs-lookup"><span data-stu-id="af738-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="af738-169">Замените `"Hello"` строку с `"Hola"`испанским переводом, .</span><span class="sxs-lookup"><span data-stu-id="af738-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="af738-170">Сохраните файл temp.csv.</span><span class="sxs-lookup"><span data-stu-id="af738-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="af738-171">Используйте приведенную ниже команду для создания локализованного файла ресурса.</span><span class="sxs-lookup"><span data-stu-id="af738-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="af738-172">Файл LocalizingWpfInWf.g.es-ES.resources создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="af738-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="af738-173">Используйте приведенную ниже команду для создания локализованной вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="af738-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="af738-174">Файл LocalizingWpfInWf.resources.dll создается в папке obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="af738-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="af738-175">Скопируйте файл LocalizingWpfInWf.resources.dll в папку проекта bin\Debug\es-ES.</span><span class="sxs-lookup"><span data-stu-id="af738-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="af738-176">Замените существующий файл.</span><span class="sxs-lookup"><span data-stu-id="af738-176">Replace the existing file.</span></span>

8. <span data-ttu-id="af738-177">Запустите файл LocalizingWpfInWf.exe, который находится в папке проекта bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="af738-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="af738-178">Не выполняйте повторную сборку приложения, чтобы не перезаписать вспомогательную сборку.</span><span class="sxs-lookup"><span data-stu-id="af738-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="af738-179">В приложении выводятся локализованные строки вместо английских строк.</span><span class="sxs-lookup"><span data-stu-id="af738-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="af738-180">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="af738-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="af738-181">Локализация приложения</span><span class="sxs-lookup"><span data-stu-id="af738-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="af738-182">[Пошаговое руководство. Локализация форм Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="af738-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="af738-183">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af738-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
