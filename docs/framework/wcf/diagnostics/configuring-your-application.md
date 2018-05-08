---
title: Настройка приложения
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 7dfd662fafa636e0fa97f118217ad1786d5aa444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-your-application"></a>Настройка приложения
Windows Communication Foundation (WCF) использует систему конфигурации .NET и позволяет настраивать службы в пределах компьютера и приложения.  
  
 Параметры конфигурации, определяемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], находятся в группе разделов `<system.serviceModel>`. Дополнительные сведения о настройке [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы, см. в следующих разделах:  
  
-   [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`. Дополнительные сведения о параметрах приложений, в файлах конфигурации .NET см. в разделе [ \<appSettings >](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Использование редактора конфигураций  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы с помощью графического интерфейса пользователя. С помощью этого средства можно управлять параметрами привязок, поведений, служб и диагностики [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без непосредственного изменения XML-файлов конфигурации.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы проекта в Visual Studio, щелкните его правой кнопкой мыши **обозревателе решений** и выберите **изменить конфигурацию WCF** пункт контекстного меню. Будет запущен [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Если изменить файл конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проекта веб-службы в Visual Studio, щелкнув его в **обозревателе решений**, обратите внимание, что **изменить конфигурацию WCF** отсутствует пункт контекстного меню. Чтобы обойти эту проблему, щелкните **средства** меню и выберите **Редактор конфигураций служб WCF**. После этого щелкните правой кнопкой мыши файл конфигурации и использовать **изменить конфигурацию WCF** пункт контекстного меню.  
  
## <a name="see-also"></a>См. также  
 [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
