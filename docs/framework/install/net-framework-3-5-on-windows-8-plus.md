---
title: "Установка платформы .NET Framework 3.5 в Windows 8, Windows 8.1 и Windows 10 | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 3.5, installing on Windows 8
- Windows 8, installing .NET Framework 3.5
ms.assetid: 3eab3eb4-4573-42ac-98f8-36fb2c22c7d5
caps.latest.revision: 69
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f48ef7a29e05824834395fdd9fd850a017a5f7e6
ms.contentlocale: ru-ru
ms.lasthandoff: 05/11/2017

---
# <a name="installing-the-net-framework-35-on-windows-8-windows-81-and-windows-10"></a>Установка платформы .NET Framework 3.5 в Windows 8, Windows 8.1 и Windows 10
Платформа .NET Framework является неотъемлемой частью многих приложений, запущенных на Windows и предоставляет общие функциональные возможности для запуска этих приложений. Платформа.NET Framework предоставляет разработчикам согласованную модель программирования для создания приложений. Если используется операционная система Windows,то платформа .NET Framework, возможно, уже установлена на компьютере. В частности, версия [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] входит в состав [!INCLUDE[win8](../../../includes/win8-md.md)], версия [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] входит в состав [!INCLUDE[win81](../../../includes/win81-md.md)] и версия [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] входит в состав Windows 10.  
  
 Однако платформа .NET Framework 3.5 не устанавливается автоматически вместе с [!INCLUDE[win8](../../../includes/win8-md.md)], [!INCLUDE[win81](../../../includes/win81-md.md)] или Windows 10, и ее необходимо включить отдельно, чтобы зависящие от нее приложения работали. Для этого следует использовать Центр обновления Windows, который можно открыть одним из трех способов. Во всех случаях требуется подключение к Интернету.  
  
-   [Установка платформы .NET Framework 3.5 по запросу](#OnDemand)  
  
-   [Включение платформы .NET Framework 3.5 в панели управления](#ControlPanel)  
  
-   [Загрузка установщика .NET Framework 3.5](http://www.microsoft.com/en-us/download/details.aspx?id=21) (Примечание. В этом случае не происходит непосредственная загрузка .NET Framework. Это установщик, который вызывает Центр обновления Windows.)  
  
 Во время установки могут возникнуть ошибки 0x800f0906, 0x800f0907 или 0x800f081f. В этом случае см. статью [Ошибка установки .NET Framework 3.5: 0x800f0906, 0x800f0907 или 0x800f081f](https://support.microsoft.com/en-us/kb/2734782). Обратите внимание, что их можно устранить, установив [обновление системы безопасности 3005628](https://support.microsoft.com/kb/3005628).  
  
 Если ни один из указанных способов не подходит или у вас нет подключения к Интернету, необходимо использовать установочный носитель Windows. Подробные сведения о разрешении для кода ошибки 0x800f0906 см. в разделе "Метод 3" в [статье об ошибках установки .NET Framework 3.5](https://support.microsoft.com/en-us/kb/2734782). Если нет установочного носителя, см. раздел [Создание установочного носителя Windows 8.1](http://windows.microsoft.com/en-US/windows-8/create-reset-refresh-media?woldogcb=0).  
  
 Важные примечания:  
  
-   В общем случае не рекомендуется удалять какие-либо версии платформы .NET Framework, установленные на компьютере. Различные приложения зависят от разных версий платформы, при этом на один компьютер можно загрузить несколько версий платформы .NET Framework одновременно.  
  
-   Платформа .NET Framework 3.5 также используется приложениями, созданными для версий 2.0 и 3.0.  
  
-   Установка языкового пакета Windows до установки .NET Framework 3.5 может вызвать сбой установки .NET Framework 3.5. При установке .NET Framework 3.5 после языкового пакета Windows возникает ошибка.  
  
-   Компонент Windows CardSpace не поддерживается .NET Framework 3.5 в [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
-   К сожалению, сложности, связанные с установкой платформы .NET Framework 3.5, не позволяют применять отдельный автономный установщик, который может выполняться независимо от Центра обновления Windows. Если все остальные способы завершаются ошибкой, необходимо использовать установочный носитель, как описано выше.  
  
<a name="OnDemand"></a>   
## <a name="install-the-net-framework-35-on-demand"></a>Установка платформы .NET Framework 3.5 по запросу  
 Если приложению требуется .NET Framework 3.5 и оно не находит эту версию на компьютере, во время установки или при первом запуске приложения отображается следующее диалоговое окно. Выберите в окне **Установить этот компонент** , чтобы включить .NET Framework 3.5. Для использования этого варианта требуется подключение к Интернету.  
  
 ![Диалоговое окно установки версии 3.5 в Windows 8](../../../docs/framework/deployment/media/installdialog.png "installdialog")  
  
<a name="ControlPanel"></a>   
## <a name="enable-the-net-framework-35-in-control-panel"></a>Включение платформы .NET Framework 3.5 в панели управления  
 Вы можете самостоятельно включить .NET Framework 3.5 через панель управления. Для использования этого варианта требуется подключение к Интернету.  
  
1.  Нажмите клавишу ![с логотипом Windows](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") на клавиатуре, введите "Компоненты Windows" и нажмите клавишу ВВОД. Появится диалоговое окно **Включение или отключение компонентов Windows** . Или откройте панель управления, щелкните элементы «Программы», а затем в разделе «Программы и компоненты» щелкните ссылку «Включение или отключение компонентов Windows».  
  
2.  Установите флажок **.NET Framework 3.5 (включает .NET 2.0 и 3.0)** , нажмите кнопку "OK" и перезагрузите компьютер при появлении соответствующего запроса.  
  
 Дочерние элементы, активирующие Windows Communication Foundation (WCF) HTTP, предназначены для разработчиков, которым необходимы функции сопоставления обработчика и скриптов WCF. В других случаях их выбирать не требуется.  
  
 В следующем видео показано, как это сделать:  
  
 ![Установка платформы .NET Framework в Windows 8 или 8.1](../../../docs/framework/get-started/media/clr-net35-win8.png "CLR_NET35_Win8")  
  
## <a name="see-also"></a>См. также  
 [Руководство по установке](../../../docs/framework/get-started/index.md)
