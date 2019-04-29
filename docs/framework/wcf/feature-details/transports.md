---
title: Транспорты в Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933735"
---
# <a name="transports-in-windows-communication-foundation"></a>Транспорты в Windows Communication Foundation
Транспортный уровень является самым нижним уровнем стека каналов. Основными транспортами, используемыми в Windows Communication Foundation (WCF) являются HTTP, HTTPS, TCP и именованные каналы. В подразделах данного раздела рассматриваются выбор типа транспорта среди названных выше типов, настройка транспорта и задание свойств настройки.  
  
 WCF содержит дополнительные типы транспорта. Сведения о транспорта очереди сообщений (MSMQ), см. в разделе [очереди и надежные сеансы](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md). Сведения о транспорта peer-to-peer, см. в разделе [сети Peer-to-Peer](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Выбор транспорта](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 Описываются три основных типа транспорта и рассматриваются вопросы выбора транспорта.  
  
 [Выбор кодировщика сообщений](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 Описываются факторы, которые необходимо принять во внимание при выборе элемента привязки для кодирования сообщений.  
  
 [Потоковая передача сообщений](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 Описывается настройка транспортного уровня для выполнения потоковой передачи.  
  
 [Настройка HTTP и HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 Описывается настройка элементов привязки транспорта HTTP и HTTPS.  
  
 [Практическое руководство. Заменить WCF URL резервирование на ограниченное резервирование](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 В этой статье описывается использование WCFURL ограниченные резервирования.  
  
 [Квоты транспорта](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 Рассматриваются вопросы задания квот, доступных на транспортном уровне.  
  
 [Работа со средствами NAT и брандмауэрами](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 Описывается настройка транспортного уровня при отправке или получении сообщений за брандмауэром или при использовании преобразования сетевых адресов (NAT).  
  
 [Совместное использование портов Net.TCP](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 В этой статье описывается использование компонент совместного использования портов Net.TCP WCF.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Привязки](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
