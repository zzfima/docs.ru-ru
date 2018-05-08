---
title: Средства Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, tools
- Windows Communication Foundation, tools
ms.assetid: 399a47b4-bfea-434b-8e83-f76b5063d79d
ms.openlocfilehash: 7d42ab9711a8d0b46ec3d35eec979e276a8c74a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-communication-foundation-tools"></a>Средства Windows Communication Foundation
Инструменты Microsoft Windows Communication Foundation (WCF) предназначены для упрощения создания, развертывания и управления [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] приложений. Данный раздел содержит подробные сведения об этих средствах. Обратите внимание, что некоторые средства могут не поддерживаться.  
  
 Все инструменты можно запускать из командной строки.  
  
 В следующей таблице представлены средства и их краткое описание.  
  
|Средство|Описание|  
|----------|-----------------|  
|[Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)|Создает код модели службы из документов метаданных и документы метаданных из кода модели службы.|  
|[Средство поиска закрытых ключей (FindPrivateKey.exe)](../../../docs/framework/wcf/find-private-key-tool-findprivatekey-exe.md)|Извлекает закрытый ключ из указанного хранилища.|  
|[Средство регистрации ServiceModel (ServiceModelReg.exe)](../../../docs/framework/wcf/servicemodelreg-exe.md)|Управляет регистрацией и отменой регистрации ServiceModel на одном компьютере.|  
|[Средство настройки модели служб COM+ (ComSvcConfig.exe)](../../../docs/framework/wcf/com-service-model-configuration-tool-comsvcconfig-exe.md)|Настраивает интерфейсы COM+ для предоставления в качестве веб-служб.|  
|[Редактор конфигурации (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)|Создает и изменяет параметры конфигурации служб WCF.|  
|[Средство просмотра трассировки служб (SvcTraceViewer.exe)](../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)|Служит для просмотра, группировки и фильтрации сообщений трассировки в целях диагностики, устранения и проверки неисправностей служб WCF.|  
|[Служебная программа конфигурации WS-AtomicTransaction (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)|Настраивает основные параметры поддержки WS-AtomicTransaction с помощью программы командной строки.|  
|[Оснастка консоли MMC для конфигурации WS-AtomicTransaction](../../../docs/framework/wcf/ws-atomictransaction-configuration-mmc-snap-in.md)|Настраивает основные параметры поддержки WS-AtomicTransaction с помощью оснастки консоли MMC.|  
|[Средство регистрации служб рабочих процессов (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md)|Регистрирует службу Windows Workflow.|  
|[Узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)|Размещает службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], содержащиеся в DLL-файлах.|  
|[Тестовый клиент WCF (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)|Средство графического пользовательского интерфейса позволяет ввести параметры произвольного типа, отправить их в службу и просмотреть ответ, возвращенный службой.|  
|[Средство для первоочередного назначения контрактов](../../../docs/framework/wcf/contract-first-tool.md)|Задача сборки Visual Studio, создающая классы кода из контрактов данных XSD.|  
  
 Все вышеуказанные средства, кроме ServiceModelReg.exe, WsatConfig.exe и ComSvcConfig.exe, поставляются с Windows SDK и находятся в папке C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.  Остальные три средства находятся в папке C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation.
