---
title: Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 462220b526db90d3acfa90a28f9bfd56dbe813e2
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991396"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF
В этом пошаговом руководстве показано, как создать содержимое Direct3D9, которое подходит для размещения в приложении Windows Presentation Foundation (WPF). Дополнительные сведения о размещении содержимого Direct3D9 в приложениях WPF см. в разделе [взаимодействие WPF и Direct3D9](wpf-and-direct3d9-interoperation.md).

 В руководстве выполняются следующие задачи:

- Создайте проект Direct3D9.

- Настройка проекта Direct3D9 для размещения в приложении WPF.

 По завершении у вас будет библиотека DLL, содержащая содержимое Direct3D9 для использования в приложении WPF.

## <a name="prerequisites"></a>Предварительные требования
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.

- Visual Studio 2010.

- Пакет SDK для DirectX 9 или более поздней версии.

## <a name="creating-the-direct3d9-project"></a>Создание проекта Direct3D9
 Первым шагом является создание и Настройка проекта Direct3D9.

#### <a name="to-create-the-direct3d9-project"></a>Создание проекта Direct3D9

1. Создайте новый проект Win32 в C++ с именем `D3DContent`.

     Откроется мастер приложений Win32 и отобразится экран приветствия.

2. Нажмите кнопку **Далее**.

     Появится экран параметры приложения.

3. В разделе **Application Type: (тип приложения** ) выберите параметр **DLL** .

4. Нажмите кнопку **Готово**.

     Создается проект D3DContent.

5. В обозреватель решений щелкните правой кнопкой мыши проект D3DContent и выберите пункт **Свойства**.

     Откроется диалоговое окно **страницы свойств D3DContent** .

6. Выберите узел **C/C++**  .

7. В поле **Дополнительные каталоги включаемых** данных укажите расположение папки с DirectX include. Расположение по умолчанию для этой папки —%ProgramFiles%\Microsoft DirectX SDK (*версия*) \инклуде.

8. Дважды щелкните узел **компоновщика** , чтобы развернуть его.

9. В поле **Дополнительные каталоги библиотек** укажите расположение папки библиотеки DirectX. Расположение по умолчанию для этой папки —%ProgramFiles%\Microsoft DirectX SDK (*версия*) \Lib\x86.

10. Выберите **входной** узел.

11. В поле **Дополнительные зависимости** добавьте `d3d9.lib` файлы и `d3dx9.lib` .

12. В Обозреватель решений добавьте новый файл определения модуля (DEF) с именем `D3DContent.def` в проект.

## <a name="creating-the-direct3d9-content"></a>Создание содержимого Direct3D9
 Чтобы обеспечить максимальную производительность, содержимое Direct3D9 должно использовать определенные параметры. В следующем коде показано, как создать поверхность Direct3D9 с лучшими характеристиками производительности. Дополнительные сведения см. в разделе [вопросы производительности для совместимости с Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>Создание содержимого Direct3D9

1. С помощью обозреватель решений добавьте в C++ проект три класса с именем:

     `CRenderer`(с виртуальным деструктором)

     `CRendererManager`

     `CTriangleRenderer`

2. Откройте модуль подготовки отчетов. h в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. Откройте модуль подготовки отчетов. cpp в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. Откройте Рендерерманажер. h в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. Откройте Рендерерманажер. cpp в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. Откройте Трианглерендерер. h в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. Откройте Трианглерендерер. cpp в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. Откройте файл stdafx. h в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. Откройте DllMain. cpp в редакторе кода и замените автоматически созданный код следующим кодом.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. Откройте D3DContent. DEF в редакторе кода.

11. Замените автоматически созданный код следующим кодом.

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

12. Выполните построение проекта.

## <a name="next-steps"></a>Следующие шаги

- Размещение содержимого Direct3D9 в приложении WPF. Дополнительные сведения см. в разделе [Пошаговое руководство: Размещение содержимого Direct3D9 в WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Interop.D3DImage>
- [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Пошаговое руководство: Размещение содержимого Direct3D9 в WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
