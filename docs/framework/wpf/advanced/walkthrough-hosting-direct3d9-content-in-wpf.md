---
title: Пошаговое руководство. Размещение содержимого Direct3D9 в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 5e7edfbeb9a3cddcdcd81d9c87e5e85bfc947339
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44069530"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Пошаговое руководство. Размещение содержимого Direct3D9 в WPF
В этом пошаговом руководстве показано, как размещение содержимого Direct3D9 в приложении Windows Presentation Foundation (WPF).  
  
 В руководстве выполняются следующие задачи:  
  
-   Создание проекта WPF для размещения содержимого Direct3D9.  
  
-   Импорт содержимого Direct3D9.  
  
-   Отображение содержимого Direct3D9 с помощью <xref:System.Windows.Interop.D3DImage> класса.  
  
 Когда вы закончите, будет известно о размещении содержимого Direct3D9 в WPF-приложение.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK, 9 или более поздней версии.  
  
-   Библиотеку DLL, содержащую содержимого Direct3D9 в WPF-совместимом формате. Дополнительные сведения см. в разделе [взаимодействие WPF и Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) и [Пошаговое руководство: создание Direct3D9 содержимого для размещения в WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Создание проекта WPF  
 Первым шагом является создание проекта приложения WPF.  
  
#### <a name="to-create-the-wpf-project"></a>Создание проекта WPF  
  
-   Создание нового проекта приложения WPF в Visual C# с именем `D3DHost`. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     Файл MainWindow.xaml откроется в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>Импорт содержимого Direct3D9  
 Импорт содержимого Direct3D9 из неуправляемой библиотеки DLL с помощью `DllImport` атрибута.  
  
#### <a name="to-import-direct3d9-content"></a>Для импорта содержимого Direct3D9  
  
1.  Откройте файл MainWindow.xaml.cs в редакторе кода.  
  
2.  Замените автоматически созданный код следующим кодом.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Размещение содержимого Direct3D9  
 Наконец, используйте <xref:System.Windows.Interop.D3DImage> класса для размещения содержимого Direct3D9.  
  
#### <a name="to-host-the-direct3d9-content"></a>Для размещения содержимого Direct3D9  
  
1.  В файле MainWindow.xaml замените автоматически созданный XAML следующий XAML.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Выполните построение проекта.  
  
3.  Скопируйте библиотеку DLL, содержащую содержимого Direct3D9 в папку bin/Debug.  
  
4.  Нажмите клавишу F5, чтобы запустить проект.  
  
     Содержимое Direct3D9 в WPF-приложении.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Interop.D3DImage>  
 [Вопросы производительности, связанные с взаимодействием Direct3D9 и WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
