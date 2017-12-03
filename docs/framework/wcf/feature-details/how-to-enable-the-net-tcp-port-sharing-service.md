---
title: "Практическое руководство. Включение службы совместного использования портов Net.TCP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a64c72a8f69abc220a311c2a204074ea83d0f58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a>Практическое руководство. Включение службы совместного использования портов Net.TCP
Чтобы упростить совместное использование портов TCP в нескольких процессах, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует службу совместного использования портов Net.TCP Windows. Эта служба устанавливается как часть [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], однако из соображений безопасности служба не включается по умолчанию и перед первым использованием должна быть включена вручную. В настоящем разделе описывается настройка службы совместного использования портов Net.TCP с помощью оснастки консоли управления (MMC).  
  
 После включения служба совместного использования портов Net.TCP и запустить его вручную, см. раздел [как: Настройка службы WCF на совместное использование портов](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md) сведения о том, как настроить службу для использования этой службы.  
  
 Образец использует совместное использование порта net.tcp:// см [пример совместного использования портов Net.TCP](../../../../docs/framework/wcf/samples/net-tcp-port-sharing-sample.md).  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a>Включение службы совместного использования портов Net.TCP с помощью консоли управления (MMC)  
  
1.  Из меню «Пуск», откройте консоль управления служб либо откройте окно командной строки и введите `services.msc` или выполнить и введя `services.msc` в поле «Открыть».  
  
2.  В **имя** столбец из списка служб, щелкните правой кнопкой мыши **доступа к портам NET.TCP**и выберите **свойства** в меню.  
  
3.  Чтобы включить вручную при запуске службы, в **свойства** выберите **Общие** вкладку и в **тип запуска** выберите вручную, а затем щелкните **Применить**.  
  
4.  Чтобы запустить службу, в области состояния службы, нажмите кнопку **запустить** кнопки. Состояние службы теперь будет показано как "Работает".  
  
5.  Чтобы получить список служб, нажмите кнопку **ОК**и закройте консоль MMC.  
  
## <a name="example"></a>Пример  
  
## <a name="see-also"></a>См. также  
 [Общий доступ к портам Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 [Настройка службы совместного использования портов Net.TCP](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
