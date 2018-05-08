---
title: Криптографическая гибкость в системе безопасности WCF
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5fa4c3cf45eb17822effaa9284864274923b2504
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cryptographic-agility-in-wcf-security"></a>Криптографическая гибкость в системе безопасности WCF
В этом примере показано, как задать в стандартный или пользовательский алгоритм для быстрого внедрения криптографических функций в Windows Communication Foundation (WCF) клиента и службы. Образец состоит из следующих проектов.  
  
 Служба  
 Это саморазмещаемая [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службу, которая реализует `ICalculator` интерфейса и защищает конечную точку с использованием <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> с безопасного сеанса и надежного сеанса отключены. Служба определяет пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.  
  
 Клиент  
 Это клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который обращается к службе после успешной проверки подлинности. Он вызывает операции, предоставляемые интерфейсом `ICalculator` и реализуемые службой. Клиент также определяет тот же пользовательский класс `SecurityAlgorithmSuite`, который задает алгоритмы шифрования, используемые для защиты сообщений.  
  
### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] решение CryptoAgility.sln.  
  
2.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
3.  Откройте [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] и перейдите в каталог \WCF\Basic\Security\CryptoAgility\Service\bin и запустите файл service.exe с правами администратора, щелкнув правой кнопкой мыши service.exe и выбрав **Запуск от имени администратора**.  
  
4.  Перейдите в каталог \WCF\Basic\Security\CryptoAgility\Client\bin и запустите файл client.exe обычным образом.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>См. также  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)
