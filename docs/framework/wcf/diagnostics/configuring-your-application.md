---
title: Настройка приложения
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: e096f4b64ada8b142e8b82c8877eec7f1b84637c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939816"
---
# <a name="configuring-your-application"></a>Настройка приложения
Windows Communication Foundation (WCF) использует систему конфигурации .NET и позволяет настраивать службы как на уровне компьютера, так и в области приложения.  
  
 Параметры конфигурации, определенные WCF, находятся в `<system.serviceModel>` группе разделов. Дополнительные сведения о настройке службы WCF см. в следующих разделах:  
  
- [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
  
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`. Дополнительные сведения о параметрах приложения в файлах конфигурации .NET см. в разделе [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159).  
  
## <a name="using-the-configuration-editor"></a>Использование редактора конфигураций  
 [Средство редактора конфигурации WCF (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для служб WCF с помощью графического пользовательского интерфейса. С помощью этого средства можно управлять параметрами для привязок, поведения, служб и диагностики WCF без непосредственного редактирования XML-файлов конфигурации.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации проекта службы WCF в Visual Studio, щелкните его правой кнопкой мыши в **Обозреватель решений** и выберите пункт изменить пункт контекстного меню для **WCF config** . Запустится [средство редактора конфигурации (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
> Если вы изменяете файл конфигурации проекта веб-службы WCF в Visual Studio, щелкнув его правой кнопкой мыши в **Обозреватель решений**, обратите внимание на отсутствие пункта контекстного меню **изменить WCF config** . Чтобы решить эту проблему, в меню **Сервис** выберите пункт **Редактор конфигурации службы WCF**. После этого можно щелкнуть правой кнопкой мыши файл конфигурации и выбрать пункт меню изменить контекст в **WCF** .  
  
## <a name="see-also"></a>См. также

- [Редактор конфигурации (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)
- [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
