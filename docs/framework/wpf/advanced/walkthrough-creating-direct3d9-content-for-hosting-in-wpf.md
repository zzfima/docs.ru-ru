---
title: Создание содержимого Direct3D9 для размещения
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 847ee74da5b295c2c9d3824b3df74f94bc98a4db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727921"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="52b02-102">Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF</span><span class="sxs-lookup"><span data-stu-id="52b02-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="52b02-103">В этом пошаговом руководстве показано, как создать содержимое Direct3D9, которое подходит для размещения в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="52b02-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="52b02-104">Дополнительные сведения о размещении содержимого Direct3D9 в приложениях WPF см. в разделе [взаимодействие WPF и Direct3D9](wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="52b02-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="52b02-105">В этом пошаговом руководстве будут выполнены следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="52b02-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="52b02-106">Создайте проект Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="52b02-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="52b02-107">Настройка проекта Direct3D9 для размещения в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="52b02-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="52b02-108">По завершении у вас будет библиотека DLL, содержащая содержимое Direct3D9 для использования в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="52b02-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52b02-109">предварительные требования</span><span class="sxs-lookup"><span data-stu-id="52b02-109">Prerequisites</span></span>
 <span data-ttu-id="52b02-110">Для выполнения этого пошагового руководства требуются следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="52b02-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="52b02-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="52b02-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="52b02-112">Пакет SDK для DirectX 9 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="52b02-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="52b02-113">Создание проекта Direct3D9</span><span class="sxs-lookup"><span data-stu-id="52b02-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="52b02-114">Первым шагом является создание и Настройка проекта Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="52b02-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="52b02-115">Создание проекта Direct3D9</span><span class="sxs-lookup"><span data-stu-id="52b02-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="52b02-116">Создайте новый проект Win32 в C++ именованном `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="52b02-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="52b02-117">Откроется мастер приложений Win32 и отобразится экран приветствия.</span><span class="sxs-lookup"><span data-stu-id="52b02-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="52b02-118">Щелкните **Далее**.</span><span class="sxs-lookup"><span data-stu-id="52b02-118">Click **Next**.</span></span>

     <span data-ttu-id="52b02-119">Появится экран параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="52b02-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="52b02-120">В разделе **Application Type: (тип приложения** ) выберите параметр **DLL** .</span><span class="sxs-lookup"><span data-stu-id="52b02-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="52b02-121">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="52b02-121">Click **Finish**.</span></span>

     <span data-ttu-id="52b02-122">Создается проект D3DContent.</span><span class="sxs-lookup"><span data-stu-id="52b02-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="52b02-123">В обозреватель решений щелкните правой кнопкой мыши проект D3DContent и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="52b02-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="52b02-124">Откроется диалоговое окно **страницы свойств D3DContent** .</span><span class="sxs-lookup"><span data-stu-id="52b02-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="52b02-125">Выберите узел **C/C++**  .</span><span class="sxs-lookup"><span data-stu-id="52b02-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="52b02-126">В поле **Дополнительные каталоги включаемых** данных укажите расположение папки с DirectX include.</span><span class="sxs-lookup"><span data-stu-id="52b02-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="52b02-127">Расположение по умолчанию для этой папки —%ProgramFiles%\Microsoft DirectX SDK (*версия*) \инклуде.</span><span class="sxs-lookup"><span data-stu-id="52b02-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="52b02-128">Дважды щелкните узел **компоновщика** , чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="52b02-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="52b02-129">В поле **Дополнительные каталоги библиотек** укажите расположение папки библиотеки DirectX.</span><span class="sxs-lookup"><span data-stu-id="52b02-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="52b02-130">Расположение по умолчанию для этой папки —%ProgramFiles%\Microsoft DirectX SDK (*версия*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="52b02-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="52b02-131">Выберите **входной** узел.</span><span class="sxs-lookup"><span data-stu-id="52b02-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="52b02-132">В поле **Дополнительные зависимости** добавьте файлы `d3d9.lib` и `d3dx9.lib`.</span><span class="sxs-lookup"><span data-stu-id="52b02-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="52b02-133">В обозреватель решений добавьте в проект новый файл определения модуля (DEF) с именем `D3DContent.def`.</span><span class="sxs-lookup"><span data-stu-id="52b02-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="52b02-134">Создание содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="52b02-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="52b02-135">Чтобы обеспечить максимальную производительность, содержимое Direct3D9 должно использовать определенные параметры.</span><span class="sxs-lookup"><span data-stu-id="52b02-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="52b02-136">В следующем коде показано, как создать поверхность Direct3D9 с лучшими характеристиками производительности.</span><span class="sxs-lookup"><span data-stu-id="52b02-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="52b02-137">Дополнительные сведения см. в разделе [вопросы производительности для совместимости с Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="52b02-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="52b02-138">Создание содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="52b02-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="52b02-139">С помощью обозреватель решений добавьте в C++ проект три класса с именем:</span><span class="sxs-lookup"><span data-stu-id="52b02-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="52b02-140">`CRenderer` (с виртуальным деструктором)</span><span class="sxs-lookup"><span data-stu-id="52b02-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="52b02-141">Откройте модуль подготовки отчетов. h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="52b02-142">Откройте модуль подготовки отчетов. cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="52b02-143">Откройте Рендерерманажер. h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="52b02-144">Откройте Рендерерманажер. cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="52b02-145">Откройте Трианглерендерер. h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="52b02-146">Откройте Трианглерендерер. cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="52b02-147">Откройте файл stdafx. h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="52b02-148">Откройте DllMain. cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="52b02-149">Откройте D3DContent. DEF в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="52b02-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="52b02-150">Замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="52b02-150">Replace the automatically generated code with the following code.</span></span>

    ```cpp
    LIBRARY "D3DContent"

    EXPORTS

    SetSize
    SetAlpha
    SetNumDesiredSamples
    SetAdapter

    GetBackBufferNoRef
    Render
    Destroy
    ```

12. <span data-ttu-id="52b02-151">Создайте проект.</span><span class="sxs-lookup"><span data-stu-id="52b02-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="52b02-152">Next Steps</span><span class="sxs-lookup"><span data-stu-id="52b02-152">Next Steps</span></span>

- <span data-ttu-id="52b02-153">Размещение содержимого Direct3D9 в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="52b02-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="52b02-154">Дополнительные сведения см. [в разделе Пошаговое руководство. размещение содержимого Direct3D9 в WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="52b02-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="52b02-155">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="52b02-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="52b02-156">Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF</span><span class="sxs-lookup"><span data-stu-id="52b02-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="52b02-157">Пошаговое руководство. Размещение содержимого Direct3D9 в WPF</span><span class="sxs-lookup"><span data-stu-id="52b02-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
