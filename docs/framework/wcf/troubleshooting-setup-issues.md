---
title: Устранение неполадок с установкой
ms.date: 03/30/2017
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
ms.openlocfilehash: 0270bd8c1006b39805e3486c4fef0cb379089ea8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43390083"
---
# <a name="troubleshooting-setup-issues"></a>Устранение неполадок с установкой
В этом разделе описывается устранение неполадок Windows Communication Foundation (WCF) неполадки установки.  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a>Некоторые разделы реестра Windows Communication Foundation невозможно восстановить с помощью операции восстановления MSI в .NET Framework 3.0  
 Если удалить какие-либо разделы реестра из следующего списка:  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0  
  
-   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0  
  
 Ключи повторно не создаются при выполнении восстановления с помощью установщика .NET Framework 3.0, запускаемого из **Add/Remove Programs** приложения в **панели управления**. Чтобы правильно восстановить эти разделы, необходимо удалить платформу .NET Framework 3.0, а затем установить ее снова.  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a>Повреждение службы WMI блокирует установку поставщика инструментария WMI для Windows Communication Foundation во время установки пакета .NET Framework 3.0  
 Повреждение службы WMI может заблокировать установку поставщика инструментария WMI для Windows Communication Foundation. Во время установки установщику Windows Communication Foundation не удается зарегистрировать MOF-файл WCF с помощью компонента mofcomp.exe. Ниже приведен список признаков возникновения такой ситуации.  
  
1.  Установка .NET Framework 3.0 завершается успешно, но поставщик инструментария WMI для WCF не зарегистрирован.  
  
2.  В журнале событий приложения появляется запись об ошибке, связанной с проблемами при регистрации поставщика инструментария WMI для WCF или при запуске средства mofcomp.exe.  
  
3.  В файле журнала установки с именем dd_wcf_retCA* в каталоге %temp% пользователя содержатся сведения о том, что не удалось зарегистрировать поставщик инструментария WMI для WCF.  
  
4.  В журнале событий или в файле журнала трассировки установки может быть зарегистрировано исключение, например одно из приведенных ниже.  
  
     ServiceModelReg [11:09:59:046]: System.ApplicationException: Неожиданный результат 3, ожидается E:\WINDOWS\system32\wbem\mofcomp.exe с «E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof»  
  
     или  
  
     ServiceModelReg [07:19:33:843]: System.TypeInitializationException: Инициализатор типа 'System.Management.ManagementPath' выдал исключение. ---> System.Runtime.InteropServices.COMException (0x80040154): Сбой при получении фабрики класса COM для компонента с CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} в результате следующей ошибки: 80040154.  
  
     или  
  
     ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Невозможно загрузить файл или сборку 'C:\WINDOWS\system32\wbem\mofcomp.exe' или один из зависимых от них компонентов. Не удается найти указанный файл.  
  
     Имя файла: 'C:\WINDOWS\system32\wbem\mofcomp.exe  
  
 Чтобы решить описанную выше проблему, необходимо выполнить следующие действия.  
  
1.  Запустите [диагностики WMI Diagnosis Utility, версии 2.0](https://go.microsoft.com/fwlink/?LinkId=94685) для восстановления службы WMI. Дополнительные сведения об использовании этого инструмента см. в разделе [WMI Diagnosis Utility](https://go.microsoft.com/fwlink/?LinkId=94686) раздела.  
  
 Восстановите установку .NET Framework 3.0 с помощью **Add/Remove Programs** приложения находятся в **панели управления**, или удалите и переустановите .NET Framework 3.0.  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a>Восстановление .NET Framework 3.0, после того как в процессе установки .NET Framework 3.5 из файла machine.config будут удалены элементы конфигурации, добавленные .NET Framework 3.5  
 В случае восстановления .NET Framework 3.0 после установки [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] из файла machine.config удаляются элементы конфигурации, добавленные [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. Однако файл web.config остается без изменений. Обойти это можно исправить [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] после этого с помощью ARP или воспользоваться [программа регистрации служб WorkFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) с `/c` переключения.  
  
 [Программа регистрации служб workFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) можно найти в %windir%\Microsoft.NET\framework\v3.5\ или %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a>Правильная настройка узла WCF/WF в службах IIS после установки .NET Framework 3.5  
 Когда [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] установки не удается настроить дополнительные параметры конфигурации IIS, относящиеся к WCF, он регистрирует ошибку в журнале установки и по-прежнему. Все попытки запуска приложений WorkflowServices будут неудачными, поскольку отсутствуют обязательные параметры конфигурации. Например, не удастся загрузить службы правил или XOML.  
  
 Чтобы обойти эту проблему, запустите [программа регистрации служб WorkFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) с `/c` для правильной настройки сопоставления скриптов IIS на компьютере. [Программа регистрации служб workFlow (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) можно найти в %windir%\Microsoft.NET\framework\v3.5\ или %windir%\Microsoft.NET\framework64\v3.5\  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a>Не удалось загрузить "System.ServiceModel.Activation.HttpModule" из сборки "System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089".  
 Эта ошибка возникает, если [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] установлен и затем включен Активация WCF HTTP. Чтобы устранить проблему, выполните следующую команду в командной строке [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a>См. также  
 [Инструкции по настройке](../../../docs/framework/wcf/samples/set-up-instructions.md)
