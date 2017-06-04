---
title: "Устранение неполадок, связанных с установкой | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Устранение неполадок, связанных с установкой
В этом разделе описано, как устранять неполадки установки [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Некоторые разделы реестра Windows Communication Foundation невозможно восстановить с помощью операции восстановления MSI в .NET Framework 3.0  
 Если удалить какие\-либо разделы реестра из следующего списка:  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelService 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelOperation 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ServiceModelEndpoint 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SMSvcHost 3.0.0.0  
  
-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSDTC Bridge 3.0.0.0  
  
 их невозможно будет восстановить с помощью функции восстановления установщика .NET Framework 3.0, запускаемого из компонента **Установка и удаление программ** в **Панели управления**.Чтобы правильно восстановить эти разделы, необходимо удалить платформу .NET Framework 3.0, а затем установить ее снова.  
  
## Повреждение службы WMI блокирует установку поставщика инструментария WMI для Windows Communication Foundation во время установки пакета .NET Framework 3.0  
 Повреждение службы WMI может заблокировать установку поставщика инструментария WMI для Windows Communication Foundation.Во время установки установщику Windows Communication Foundation не удается зарегистрировать MOF\-файл WCF с помощью компонента mofcomp.exe.Ниже приведен список признаков возникновения такой ситуации.  
  
1.  Установка .NET Framework 3.0 завершается успешно, но поставщик инструментария WMI для WCF не зарегистрирован.  
  
2.  В журнале событий приложения появляется запись об ошибке, связанной с проблемами при регистрации поставщика инструментария WMI для WCF или при запуске средства mofcomp.exe.  
  
3.  В файле журнала установки с именем dd\_wcf\_retCA\* в каталоге %temp% пользователя содержатся сведения о том, что не удалось зарегистрировать поставщик инструментария WMI для WCF.  
  
4.  В журнале событий или в файле журнала трассировки установки может быть зарегистрировано исключение, например одно из приведенных ниже.  
  
     ServiceModelReg \[11:09:59:046\]: System.ApplicationException: Неожиданный результат 3, ожидается E:\\WINDOWS\\system32\\wbem\\mofcomp.exe с «E:\\WINDOWS\\Microsoft.NET\\Framework\\v3.0\\Windows Communication Foundation\\ServiceModel.mof»  
  
     или  
  
     ServiceModelReg \[07:19:33:843\]: System.TypeInitializationException: Инициализатор типа 'System.Management.ManagementPath' выдал исключение.\-\-\-\> System.Runtime.InteropServices.COMException \(0x80040154\): Сбой при получении фабрики класса COM для компонента с CLSID {CF4CC405\-E2C5\-4DDD\-B3CE\-5E7582D8C9FA} в результате следующей ошибки: 80040154.  
  
     или  
  
     ServiceModelReg \[07:19:32:750\]: System.IO.FileNotFoundException: Невозможно загрузить файл или сборку 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe' или один из зависимых от них компонентов.Не удается найти указанный файл.  
  
     Имя файла: 'C:\\WINDOWS\\system32\\wbem\\mofcomp.exe  
  
 Чтобы решить описанную выше проблему, необходимо выполнить следующие действия.  
  
1.  Запустите [Утилиту диагностики WMI версии 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) для восстановления службы WMI.[!INCLUDE[crabout](../../../includes/crabout-md.md)] использовании этого средства см. раздел [Утилита диагностики WMI](http://go.microsoft.com/fwlink/?LinkId=94686).  
  
 Восстановите установку .NET Framework 3.0 с помощью компонента **Установка и удаление программ** в **Панели управления** или удалите и заново установите .NET Framework 3.0.  
  
## Восстановление .NET Framework 3.0, после того как в процессе установки .NET Framework 3.5 из файла machine.config будут удалены элементы конфигурации, добавленные .NET Framework 3.5  
 В случае восстановления .NET Framework 3.0 после установки [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] из файла machine.config удаляются элементы конфигурации, добавленные [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].Однако файл web.config остается без изменений.Чтобы обойти эту проблему, можно впоследствии восстановить [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] с помощью ARP или воспользоваться средством [Программа регистрации служб WorkFlow \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) с параметром командной строки `/c`.  
  
 Средство [Программа регистрации служб WorkFlow \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) можно найти в каталоге %windir%\\Microsoft.NET\\framework\\v3.5\\ или %windir%\\Microsoft.NET\\framework64\\v3.5\\.  
  
## Правильная настройка узла WCF\/WF в службах IIS после установки .NET Framework 3.5  
 Если при установке [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] не удается задать дополнительные параметры служб IIS, связанные с [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], в журнал установки заносится сообщение об ошибке, а установка продолжается.Все попытки запуска приложений WorkflowServices будут неудачными, поскольку отсутствуют обязательные параметры конфигурации.Например, не удастся загрузить службы правил или XOML.  
  
 Для исправления этой проблемы используйте [Программа регистрации служб WorkFlow \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) с `/c` параметром для правильной настройки на компьютере IIS карт скриптов.Средство [Программа регистрации служб WorkFlow \(WFServicesReg.exe\)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) можно найти в каталоге %windir%\\Microsoft.NET\\framework\\v3.5\\ или %windir%\\Microsoft.NET\\framework64\\v3.5\\.  
  
## Не удалось загрузить "System.ServiceModel.Activation.HttpModule" из сборки "System.ServiceModel, Version 3.0.0.0, Culture\=neutral, PublicKeyToken\=b77a5c561934e089".  
 Это ошибка возникает, если [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] установлено, и затем включена активация [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Чтобы устранить проблему, выполните следующую команду в командной строке [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]:  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## См. также  
 [Инструкции по установке](../../../docs/framework/wcf/samples/set-up-instructions.md)