---
title: "Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [взаимодействие с WPF], создание содержимого Direct3D9"
  - "WPF, создание содержимого Direct3D9"
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF
В этом пошаговом руководстве показано, как создать содержимое Direct3D9, которое можно разместить в приложении Windows Presentation Foundation \(WPF\).  Дополнительные сведения о размещении содержимого Direct3D9 в приложениях WPF см. в разделе [Взаимодействие WPF и Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 В данном пошаговом руководстве выполняются следующие задачи.  
  
-   Создание проекта Direct3D9.  
  
-   Настройка проекта Direct3D9 для размещения в приложении WPF.  
  
 В итоге будет получен файл DLL с содержимым Direct3D9 для использования в приложении WPF.  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 или более поздняя версия.  
  
## Создание проекта Direct3D9  
 Сначала создайте и настройте проект Direct3D9.  
  
#### Создание проекта Direct3D9  
  
1.  Создайте новый проект Win32 в C\+\+ с именем `D3DContent`.  
  
     Откроется мастер приложений Win32 и окно приветствия.  
  
2.  Нажмите кнопку **Далее**.  
  
     Откроется окно "Параметры приложения".  
  
3.  В разделе **Тип приложения:** выберите параметр **DLL**.  
  
4.  Нажмите кнопку **Готово**.  
  
     Будет создан проект D3DContent.  
  
5.  В обозревателе решений щелкните правой кнопкой проект D3DContent и выберите **Свойства**.  
  
     Откроется диалоговое окно **Страницы свойств D3DContent**.  
  
6.  Выберите узел **C\/C\+\+**.  
  
7.  В поле **Дополнительные каталоги включения** укажите местоположение папки с DirectX.  Папка по умолчанию %ProgramFiles%\\Microsoft DirectX SDK \(*версия*\)\\Include.  
  
8.  Дважды щелкните узел **Linker** и разверните его.  
  
9. В поле **Дополнительные каталоги библиотек** укажите местоположение папки с библиотеками DirectX.  Папка по умолчанию %ProgramFiles%\\Microsoft DirectX SDK \(*версия*\)\\Lib\\x86.  
  
10. Выберите узел **Input**.  
  
11. В поле **Дополнительные зависимости** добавьте файлы `d3d9.lib` и `d3dx9.lib`.  
  
12. В обозревателе решений добавьте в проект новый файл определения модуля \(DEF\) с именем `D3DContent.def`.  
  
## Создание содержимого Direct3D9  
 Чтобы добиться лучшей производительности, содержимое Direct3D9 должно использовать определенные параметры.  В следующем коде показано, как создать поверхность Direct3D9, имеющую лучшие характеристики производительности.  Дополнительные сведения см. в разделе [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### Создание содержимого Direct3D9  
  
1.  С помощью обозревателя решений добавьте в проект три класса C\+\+ со следующими именами.  
  
     `CRenderer` \(с виртуальным деструктором\)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  В редакторе кода откройте Renderer.h и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  В редакторе кода откройте Renderer.cpp и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  В редакторе кода откройте RendererManager.h и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  В редакторе кода откройте RendererManager.cpp и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  В редакторе кода откройте TriangleRenderer.h и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  В редакторе кода откройте TriangleRenderer.cpp и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  В редакторе кода откройте stdafx.h и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. В редакторе кода откройте dllmain.cpp и замените автоматически созданный код следующим кодом.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. В редакторе кода откройте D3DContent.def.  
  
11. Замените автоматически создаваемый код на следующий код.  
  
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
  
## Следующие действия  
  
-   Разместите содержимое Direct3D9 в приложении WPF.  Дополнительные сведения см. в разделе [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## См. также  
 <xref:System.Windows.Interop.D3DImage>   
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Пошаговое руководство. Размещение содержимого Direct3D9 в WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)