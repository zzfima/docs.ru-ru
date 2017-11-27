---
title: "Настройка приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f22fac02616070ecd6498ad0e158782001681ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-your-application"></a>Настройка приложения
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует систему конфигурации .NET и позволяет настраивать службы и на компьютере, и в области приложений.  
  
 Параметры конфигурации, определяемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], находятся в группе разделов `<system.serviceModel>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] том, как настроить службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], см. в следующих разделах:  
  
-   [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]в разделе параметров приложения в файлах конфигурации .NET, [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Использование редактора конфигураций  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы с помощью графического интерфейса пользователя. С помощью этого средства можно управлять параметрами привязок, поведений, служб и диагностики [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без непосредственного изменения XML-файлов конфигурации.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проект службы в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], щелкните его правой кнопкой мыши **обозревателе решений** и выберите **изменить конфигурацию WCF** пункт контекстного меню. Будет запущен [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Если изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проекта веб-службы в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] щелкнув его в **обозревателе решений**, обратите внимание, что **изменить конфигурацию WCF** отсутствует пункт контекстного меню . Чтобы обойти эту проблему, щелкните **средства** меню и выберите **Редактор конфигураций служб WCF**. После этого щелкните правой кнопкой мыши файл конфигурации и использовать **изменить конфигурацию WCF** пункт контекстного меню.  
  
## <a name="see-also"></a>См. также  
 [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
