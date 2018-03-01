---
title: "Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f1a5d70807541a0a3faf6bc99a3ced42827efd72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF
В этом пошаговом руководстве показано, как создать содержимое Direct3D9, которая подходит для размещения в приложении Windows Presentation Foundation (WPF). Дополнительные сведения о размещении содержимого Direct3D9 в приложениях WPF см. в разделе [WPF и взаимодействие Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 В руководстве выполняются следующие задачи:  
  
-   Создайте проект Direct3D9.  
  
-   Настройка проекта Direct3D9 для размещения в приложении WPF.  
  
 Когда вы закончите, будет иметь библиотеку DLL с содержимым Direct3D9 для использования в приложении WPF.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   Позже пакет SDK DirectX 9or.  
  
## <a name="creating-the-direct3d9-project"></a>Создание проекта Direct3D9  
 Первым шагом является создание и настройка проекта Direct3D9.  
  
#### <a name="to-create-the-direct3d9-project"></a>Чтобы создать проект Direct3D9  
  
1.  Создание нового проекта Win32 в C++ с именем `D3DContent`.  
  
     Мастер приложений Win32 открывает и отображает экран приветствия.  
  
2.  Нажмите кнопку **Далее**.  
  
     Появится экран настройки приложения.  
  
3.  В **типа приложения:** выберите **DLL** параметр.  
  
4.  Нажмите кнопку **Готово**.  
  
     Создается проект D3DContent.  
  
5.  В обозревателе решений щелкните правой кнопкой мыши проект D3DContent и выберите **свойства**.  
  
     **Свойств D3dcontent** откроется диалоговое окно.  
  
6.  Выберите **C/C++** узла.  
  
7.  В **Дополнительные каталоги включаемых файлов** укажите расположение с DirectX включать папку. Расположение по умолчанию эта папка находится в %ProgramFiles%\Microsoft пакет SDK DirectX (*версии*) \Include.  
  
8.  Дважды щелкните **компоновщика** узел, чтобы развернуть его.  
  
9. В **Дополнительные каталоги библиотек** укажите расположение папки с библиотеками DirectX. Расположение по умолчанию эта папка находится в %ProgramFiles%\Microsoft пакет SDK DirectX (*версии*) \Lib\x86.  
  
10. Выберите **ввода** узла.  
  
11. В **Дополнительные зависимости** поля, добавьте `d3d9.lib` и `d3dx9.lib` файлов.  
  
12. В обозревателе решений добавьте новый файл определения модуля (.def) с именем `D3DContent.def` в проект.  
  
## <a name="creating-the-direct3d9-content"></a>Создание содержимого Direct3D9  
 Для обеспечения оптимальной производительности, содержимое Direct3D9 необходимо использовать отдельные параметры. Следующий код показывает создание Direct3D9 поверхности, которая имеет лучшие характеристики производительности. Дополнительные сведения см. в разделе [вопросы производительности Direct3D9 и взаимодействие с WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### <a name="to-create-the-direct3d9-content"></a>Создание содержимого Direct3D9  
  
1.  С помощью обозревателя решений, добавьте в проект, со следующими именами трех классов C++.  
  
     `CRenderer`(с виртуальным деструктором)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  Откройте Renderer.h в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  Откройте Renderer.cpp в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  Откройте RendererManager.h в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  Откройте RendererManager.cpp в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  Откройте TriangleRenderer.h в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  Откройте TriangleRenderer.cpp в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  Откройте файл stdafx.h в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. Откройте dllmain.cpp в редакторе кода и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. Откройте D3DContent.def в редакторе кода.  
  
11. Замените автоматически созданный код следующим кодом.  
  
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
  
12. Выполните построение проекта.  
  
## <a name="next-steps"></a>Следующие шаги  
  
-   Разместить содержимое Direct3D9 в приложении WPF. Дополнительные сведения см. в разделе [Пошаговое руководство: размещение Direct3D9 содержимого в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.D3DImage>  
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
