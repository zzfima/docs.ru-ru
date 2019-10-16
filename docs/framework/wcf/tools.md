---
title: Средства Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, tools
- Windows Communication Foundation, tools
ms.assetid: 399a47b4-bfea-434b-8e83-f76b5063d79d
ms.openlocfilehash: edd54c93207456156ef2520a00ad567cd087d89c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321369"
---
# <a name="windows-communication-foundation-tools"></a>Средства Windows Communication Foundation
Средства Microsoft Windows Communication Foundation (WCF) предназначены для облегчения создания, развертывания и управления приложениями WCF. Данный раздел содержит подробные сведения об этих средствах. Обратите внимание, что некоторые средства могут не поддерживаться.  
  
 Все инструменты можно запускать из командной строки.  
  
 В следующей таблице представлены средства и их краткое описание.  
  
|Средство|Описание|  
|----------|-----------------|  
|[Служебная программа для метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)|Создает код модели службы из документов метаданных и документы метаданных из кода модели службы.|  
|[Средство поиска закрытых ключей (FindPrivateKey.exe)](find-private-key-tool-findprivatekey-exe.md)|Извлекает закрытый ключ из указанного хранилища.|  
|[Средство регистрации ServiceModel (ServiceModelReg.exe)](servicemodelreg-exe.md)|Управляет регистрацией и отменой регистрации ServiceModel на одном компьютере.|  
|[Средство настройки модели служб COM+ (ComSvcConfig.exe)](com-service-model-configuration-tool-comsvcconfig-exe.md)|Настраивает интерфейсы COM+ для предоставления в качестве веб-служб.|  
|[Редактор конфигурации (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)|Создает и изменяет параметры конфигурации служб WCF.|  
|[Средство просмотра трассировки служб (SvcTraceViewer.exe)](service-trace-viewer-tool-svctraceviewer-exe.md)|Служит для просмотра, группировки и фильтрации сообщений трассировки в целях диагностики, устранения и проверки неисправностей служб WCF.|  
|[Служебная программа конфигурации WS-AtomicTransaction (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)|Настраивает основные параметры поддержки WS-AtomicTransaction с помощью программы командной строки.|  
|[Оснастка консоли MMC для конфигурации WS-AtomicTransaction](ws-atomictransaction-configuration-mmc-snap-in.md)|Настраивает основные параметры поддержки WS-AtomicTransaction с помощью оснастки консоли MMC.|  
|[Средство регистрации служб рабочих процессов (WFServicesReg.exe)](workflow-service-registration-tool-wfservicesreg-exe.md)|Регистрирует службу Windows Workflow.|  
|[Узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)|Размещает службы WCF, содержащиеся в файлах библиотек (*. dll)|  
|[Тестовый клиент WCF (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)|Средство графического пользовательского интерфейса позволяет ввести параметры произвольного типа, отправить их в службу и просмотреть ответ, возвращенный службой.|  
|[Средство для первоочередного назначения контрактов](contract-first-tool.md)|Задача сборки Visual Studio, создающая классы кода из контрактов данных XSD.|  
  
 Все вышеуказанные средства, кроме ServiceModelReg.exe, WsatConfig.exe и ComSvcConfig.exe, поставляются с Windows SDK и находятся в папке C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin.  Остальные три средства находятся в папке C:\Windows\Microsoft.NET\Framework\v3.0\Windows Communication Foundation.
