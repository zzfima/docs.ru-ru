---
title: Настройка приложения
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 94bf5f4bbee8bb8bb462c4bf91be75d1627ec567
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087174"
---
# <a name="configuring-your-application"></a>Настройка приложения
Windows Communication Foundation (WCF) использует систему конфигурации .NET и позволяет настраивать службы в области компьютера и приложения.  
  
 Параметры конфигурации, определенные WCF, находятся в `<system.serviceModel>` группы разделов. Дополнительные сведения о том, как настроить службу WCF см. в разделах:  
  
-   [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`. Дополнительные сведения о параметрах приложения в файлах конфигурации .NET см. в разделе [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Использование редактора конфигураций  
 WCF [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для служб WCF, с помощью графического интерфейса. При помощи этого средства можно управлять параметрами для привязок, поведений, служб и диагностики WCF без непосредственного редактирования XML-файлов конфигурации.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации проекта службы WCF в Visual Studio, щелкните правой кнопкой мыши в **обозревателе решений** и выберите **изменить конфигурацию WCF** пункт контекстного меню. Это откроет [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  Если изменить файл конфигурации проекта веб-службы WCF в Visual Studio щелкните правой кнопкой мыши в **обозревателе решений**, обратите внимание, что **изменить конфигурацию WCF** отсутствует пункт контекстного меню. Чтобы решить эту проблему, щелкните **средства** меню и выберите **Редактор конфигураций служб WCF**. После этого щелкните правой кнопкой мыши файл конфигурации и использовать **изменить конфигурацию WCF** пункт контекстного меню.  
  
## <a name="see-also"></a>См. также

- [Средство редактирования конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
