---
title: Настройка приложения
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 6fc33e7b114bb78f823575a2b456d601ae75db94
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937641"
---
# <a name="configuring-your-application"></a>Настройка приложения
Windows Communication Foundation (WCF) использует систему конфигурации .NET и позволяет настраивать службы как на уровне компьютера, так и в области приложения.  
  
 Параметры конфигурации, определенные WCF, находятся в группе разделов `<system.serviceModel>`. Дополнительные сведения о настройке службы WCF см. в следующих разделах:  
  
- [Настройка служб](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`. Дополнительные сведения о параметрах приложения в файлах конфигурации .NET см. в разделе [\<appSettings >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).  
  
## <a name="using-the-configuration-editor"></a>Использование редактора конфигураций  
 [Средство редактора конфигурации WCF (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации для служб WCF с помощью графического пользовательского интерфейса. С помощью этого средства можно управлять параметрами для привязок, поведения, служб и диагностики WCF без непосредственного редактирования XML-файлов конфигурации.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации проекта службы WCF в Visual Studio, щелкните его правой кнопкой мыши в **Обозреватель решений** и выберите пункт изменить пункт контекстного меню для **WCF config** . Запустится [средство редактора конфигурации (SvcConfigEditor. exe)](../configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
> Если вы изменяете файл конфигурации проекта веб-службы WCF в Visual Studio, щелкнув его правой кнопкой мыши в **Обозреватель решений**, обратите внимание на отсутствие пункта контекстного меню **изменить WCF config** . Чтобы решить эту проблему, в меню **Сервис** выберите пункт **Редактор конфигурации службы WCF**. После этого можно щелкнуть правой кнопкой мыши файл конфигурации и выбрать пункт меню изменить контекст в **WCF** .  
  
## <a name="see-also"></a>См. также:

- [Редактор конфигурации (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)
- [Настройка служб](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
