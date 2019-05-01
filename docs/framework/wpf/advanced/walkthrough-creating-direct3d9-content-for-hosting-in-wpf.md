---
title: Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 160395b84ef7ca447d162ceff34752113a1d59a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031204"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="9c8ad-102">Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF</span><span class="sxs-lookup"><span data-stu-id="9c8ad-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="9c8ad-103">В этом пошаговом руководстве демонстрируется создание содержимого Direct3D9 для размещения в приложении Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9c8ad-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="9c8ad-104">Дополнительные сведения о размещении содержимого Direct3D9 в WPF-приложениях, см. в разделе [взаимодействие WPF и Direct3D9](wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="9c8ad-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="9c8ad-105">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="9c8ad-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="9c8ad-106">Создайте проект Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-106">Create a Direct3D9 project.</span></span>

- <span data-ttu-id="9c8ad-107">Настройка проекта Direct3D9 для размещения в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="9c8ad-108">Когда вы закончите, вы получите библиотеку DLL, содержащую содержимого Direct3D9 для использования в приложении WPF.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9c8ad-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9c8ad-109">Prerequisites</span></span>
 <span data-ttu-id="9c8ad-110">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="9c8ad-111">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-111">Visual Studio 2010.</span></span>

- <span data-ttu-id="9c8ad-112">DirectX SDK, 9 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="9c8ad-113">Создание проекта Direct3D9</span><span class="sxs-lookup"><span data-stu-id="9c8ad-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="9c8ad-114">Первый шаг — создание и настройка проекта Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="9c8ad-115">Чтобы создать проект Direct3D9</span><span class="sxs-lookup"><span data-stu-id="9c8ad-115">To create the Direct3D9 project</span></span>

1. <span data-ttu-id="9c8ad-116">Создание проекта Win32 в C++ с именем `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="9c8ad-117">Мастер приложений Win32 открывает и отображает экран приветствия.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2. <span data-ttu-id="9c8ad-118">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-118">Click **Next**.</span></span>

     <span data-ttu-id="9c8ad-119">На экране параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-119">The Application Settings screen appears.</span></span>

3. <span data-ttu-id="9c8ad-120">В **тип приложения:** выберите **DLL** параметр.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-120">In the **Application type:** section, select the **DLL** option.</span></span>

4. <span data-ttu-id="9c8ad-121">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-121">Click **Finish**.</span></span>

     <span data-ttu-id="9c8ad-122">Создается проект D3DContent.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-122">The D3DContent project is generated.</span></span>

5. <span data-ttu-id="9c8ad-123">В обозревателе решений щелкните правой кнопкой мыши проект D3DContent и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="9c8ad-124">**Свойств D3dcontent** откроется диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6. <span data-ttu-id="9c8ad-125">Выберите **C/C++** узла.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-125">Select the **C/C++** node.</span></span>

7. <span data-ttu-id="9c8ad-126">В **Дополнительные каталоги включаемых файлов** укажите расположение с DirectX включать папку.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="9c8ad-127">Находится в папке по умолчанию для этой папки %ProgramFiles%\Microsoft DirectX SDK (*версии*) \Include.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8. <span data-ttu-id="9c8ad-128">Дважды щелкните **компоновщика** узел, чтобы развернуть его.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="9c8ad-129">В **Дополнительные каталоги библиотек** укажите расположение папки библиотек DirectX.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="9c8ad-130">Находится в папке по умолчанию для этой папки %ProgramFiles%\Microsoft DirectX SDK (*версии*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="9c8ad-131">Выберите **ввода** узла.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="9c8ad-132">В **Дополнительные зависимости** поле, добавьте `d3d9.lib` и `d3dx9.lib` файлы.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="9c8ad-133">В обозревателе решений добавьте новый файл определения модуля (.def) с именем `D3DContent.def` в проект.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="9c8ad-134">Создание содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="9c8ad-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="9c8ad-135">Чтобы получить наилучшую производительность, содержимого Direct3D9 необходимо использовать определенные параметры.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="9c8ad-136">Приведенный ниже показано, как создать Direct3D9 поверхности, которая имеет лучшие характеристики производительности.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="9c8ad-137">Дополнительные сведения см. в разделе [рекомендации по ускорению взаимодействием Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="9c8ad-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="9c8ad-138">Создание содержимого Direct3D9</span><span class="sxs-lookup"><span data-stu-id="9c8ad-138">To create the Direct3D9 content</span></span>

1. <span data-ttu-id="9c8ad-139">С помощью обозревателя решений, добавьте в проект с именем следующие три класса C++.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="9c8ad-140">`CRenderer` (с виртуальным деструктором)</span><span class="sxs-lookup"><span data-stu-id="9c8ad-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2. <span data-ttu-id="9c8ad-141">Откройте Renderer.h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. <span data-ttu-id="9c8ad-142">Откройте Renderer.cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. <span data-ttu-id="9c8ad-143">Откройте RendererManager.h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. <span data-ttu-id="9c8ad-144">Откройте RendererManager.cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. <span data-ttu-id="9c8ad-145">Откройте TriangleRenderer.h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. <span data-ttu-id="9c8ad-146">Откройте TriangleRenderer.cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. <span data-ttu-id="9c8ad-147">Откройте файл stdafx.h в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="9c8ad-148">Откройте dllmain.cpp в редакторе кода и замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="9c8ad-149">Откройте D3DContent.def в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="9c8ad-150">Замените автоматически созданный код следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-150">Replace the automatically generated code with the following code.</span></span>

    ```
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

12. <span data-ttu-id="9c8ad-151">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c8ad-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9c8ad-152">Next Steps</span></span>

- <span data-ttu-id="9c8ad-153">Размещение содержимого Direct3D9 в WPF-приложение.</span><span class="sxs-lookup"><span data-stu-id="9c8ad-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="9c8ad-154">Дополнительные сведения см. в разделе [Пошаговое руководство: Размещение содержимого Direct3D9 в WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="9c8ad-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c8ad-155">См. также</span><span class="sxs-lookup"><span data-stu-id="9c8ad-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="9c8ad-156">Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF</span><span class="sxs-lookup"><span data-stu-id="9c8ad-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="9c8ad-157">Пошаговое руководство: Размещение содержимого Direct3D9 в WPF</span><span class="sxs-lookup"><span data-stu-id="9c8ad-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](walkthrough-hosting-direct3d9-content-in-wpf.md)
