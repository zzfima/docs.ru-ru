---
title: "Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fa6f9d0b9631420013593cb44903b5451549e8c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
Существующие приложения MSMQ можно интегрировать с приложениями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], используя привязку интеграции MSMQ для преобразования сообщений MSMQ в сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и наоборот. Это позволяет вызывать принимающие приложения MSMQ из клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также вызывать службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] из отправляющих приложений MSMQ.  
  
 В этом разделе рассматривается, как использовать привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для взаимодействия с использованием очередей между (1) клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службой приложения MSMQ, созданной с помощью System.Messaging, и (2) клиентом приложения MSMQ и службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Полный пример, демонстрирующий вызов принимающее приложение MSMQ из [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образца.  
  
 Полный пример, демонстрирующий вызов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы от клиента MSMQ см. в разделе [служба очередей сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) образца.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Создание службы WCF, получающей сообщения от клиента MSMQ  
  
1.  Определите интерфейс, который задает контракт службы для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], принимающей сообщения с использованием очередей от передающего приложения MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  Реализуйте интерфейс и примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  Создайте файл конфигурации, задающий привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  
  
  
  
4.  Создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, использующий настроенную привязку.  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Создание клиента WCF, передающего сообщения в принимающее приложение MSMQ  
  
1.  Определите интерфейс, который задает контракт службы для клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], передающего сообщения с использованием очередей в принимающее приложения MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  Определите класс клиента, используемый клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для вызова принимающего приложения MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  Создайте конфигурацию, которая задает использование привязки MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  Создайте экземпляр класса клиента и вызовите метод, определенный службой приема сообщений.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об очередях](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [Установка системы очередей сообщений (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [Безопасность сообщений при использовании очереди сообщений](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
