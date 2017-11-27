---
title: "Транспорты в Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 115e2a69c7d990c7d4c59634644fb557e83ad405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="transports-in-windows-communication-foundation"></a>Транспорты в Windows Communication Foundation
Транспортный уровень является самым нижним уровнем стека каналов. Основными типами транспорта, используемыми в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], являются протоколы HTTP, HTTPS, TCP и именованные каналы. В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит дополнительные типы транспорта. Сведения о транспорта очереди сообщений (MSMQ) см. в разделе [очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Сведения о транспорта одноранговая сеть, в разделе [-одноранговые сети](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.  
  
 [Выбор кодировщика сообщений](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.  
  
 [Потоковую передачу](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Описывается настройка транспортного уровня для выполнения потоковой передачи.  
  
 [Настройка HTTP и HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Описывается настройка элементов привязки транспорта HTTP и HTTPS.  
  
 [Как: заменить WCF URL резервирование на ограниченное резервирование](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 Описывает использование ограниченных резервирований URL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Квоты транспорта](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Рассматриваются вопросы задания квот, доступных на транспортном уровне.  
  
 [Работа с NAT и брандмауэров](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).  
  
 [Общий доступ к портам Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 Описывается использование компонента общего доступа к портам Net.TCP системы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
