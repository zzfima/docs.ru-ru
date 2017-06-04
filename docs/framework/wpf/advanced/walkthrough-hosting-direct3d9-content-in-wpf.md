---
title: "Пошаговое руководство. Размещение содержимого Direct3D9 в WPF | Microsoft Docs"
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
  - "Direct3D9 [взаимодействие с WPF], размещение содержимого Direct3D9"
  - "WPF, размещение содержимого Direct3D9"
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Пошаговое руководство. Размещение содержимого Direct3D9 в WPF
В этом пошаговом руководстве показано, как разместить содержимое Direct3D9 в приложении Windows Presentation Foundation \(WPF\).  
  
 В данном пошаговом руководстве выполняются следующие задачи.  
  
-   Создание проекта WPF для размещения содержимого Direct3D9.  
  
-   Импорт содержимого Direct3D9.  
  
-   Отображение содержимого Direct3D9 с помощью класса <xref:System.Windows.Interop.D3DImage>.  
  
 По окончании вы будете знать, как разместить содержимое Direct3D9 в приложении WPF.  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 или более поздняя версия.  
  
-   Файл DLL с содержимым Direct3D9 в формате, совместимом с WPF.  Дополнительные сведения см. в разделах [Взаимодействие WPF и Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) и [Пошаговое руководство. Создание содержимого Direct3D9 для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## Создание проекта WPF  
 Первым этапом является создание проекта для приложения WPF.  
  
#### Создание проекта WPF  
  
-   Создайте новый проект приложения WPF в Visual C\# с именем `D3DHost`.  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](http://msdn.microsoft.com/ru-ru/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     Файл MainWindow.xaml будет открыт в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## Импорт содержимого Direct3D9  
 Импортируйте содержимое Direct3D9 из неуправляемо библиотеки DLL с помощью атрибута `DllImport`.  
  
#### Импорт содержимого Direct3D9  
  
1.  В редакторе кода откройте файл MainWindow.xaml.cs.  
  
2.  Замените автоматически создаваемый код на следующий код.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## Размещение содержимого Direct3D9  
 Наконец, используйте класс <xref:System.Windows.Interop.D3DImage>, чтобы разместить содержимое Direct3D9.  
  
#### Размещение содержимого Direct3D9  
  
1.  В файле MainWindow.xaml замените автоматически созданную разметку XAML следующей разметкой XAML.  
  
     [!code-xml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Выполните построение проекта.  
  
3.  Скопируйте библиотеку DLL с содержимым Direct3D9 в папку bin\/Debug.  
  
4.  Чтобы запустить проект, нажмите клавишу F5.  
  
     Содержимое Direct3D9 будет отображено в приложении WPF.  
  
## См. также  
 <xref:System.Windows.Interop.D3DImage>   
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)