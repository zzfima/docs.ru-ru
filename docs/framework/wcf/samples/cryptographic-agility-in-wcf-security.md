---
title: "Криптографическая гибкость в системе безопасности WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# Криптографическая гибкость в системе безопасности WCF
Данный образец показывает, как задавать стандартный или пользовательский алгоритм для быстрого внедрения криптографических функций в клиент и службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  Образец состоит из следующих проектов.  
  
 Служба  
 Это саморазмещаемая служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которая реализует интерфейс `ICalculator` и защищает конечную точку с использованием привязки <xref:System.ServiceModel.WsHttpBinding>, когда механизмы безопасного сеанса и надежного сеанса отключены.  Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.  
  
 Клиент  
 Это клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который обращается к службе после успешной проверки подлинности.  Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой.  Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.  
  
### Использование этого образца  
  
1.  Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] решение CryptoAgility.sln.  
  
2.  Чтобы построить решение, нажмите CTRL\+SHIFT\+B.  
  
3.  Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], перейдите в каталог \\WCF\\Basic\\Security\\CryptoAgility\\Service\\bin и запустите файл service.exe с административными привилегиями, щелкнув правой кнопкой мыши файл service.exe и выбрав пункт **Запуск от имени администратора**.  
  
4.  Перейдите в каталог \\WCF\\Basic\\Security\\CryptoAgility\\Client\\bin и запустите файл client.exe обычным образом.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## См. также  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)