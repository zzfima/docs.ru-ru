---
title: Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7463f9cfc37c2bf4f271f6e59896a7d77f3f65cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772948"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
Вы можете интегрировать существующие приложения Message Queuing (MSMQ) с приложениями Windows Communication Foundation (WCF), используя привязку интеграции MSMQ для преобразования сообщений MSMQ и из сообщения WCF. Это позволяет вызывать принимающие приложения MSMQ из клиентов WCF, а также вызывать службы WCF из отправляющих приложений MSMQ.  
  
 В этом разделе описано, мы расскажем, как использовать <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для взаимодействия с использованием очередей между (1) клиентом WCF и службой приложения MSMQ, написанные с использованием System.Messaging и (2) клиентом приложения MSMQ и службой WCF.  
  
 Полный пример, демонстрирующий вызов принимающего приложения MSMQ из клиента WCF, см. в разделе [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образца.  
  
 Полный пример, демонстрирующий вызов службы WCF из клиента MSMQ, см. в разделе [служба очереди сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) образца.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Создание службы WCF, получающей сообщения от клиента MSMQ  
  
1. Определите интерфейс, определяющий контракт службы для службы WCF, которая получает сообщения из очереди от передающего приложения MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2. Реализуйте интерфейс и примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3. Создайте файл конфигурации, задающий привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  

4. Создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, использующий настроенную привязку.  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>Создание клиента WCF, передающего сообщения в принимающее приложение MSMQ  
  
1. Определите интерфейс, определяющий контракт службы для клиента WCF, что отправляет в очередь сообщений в принимающее приложения MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2. Определите класс клиента, который клиент WCF использует для вызова принимающего приложения MSMQ.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3. Создайте конфигурацию, которая задает использование привязки MsmqIntegrationBinding.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4. Создайте экземпляр класса клиента и вызовите метод, определенный службой приема сообщений.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения об очередях](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Практическое руководство. Обмен сообщениями с конечными точками WCF в очереди](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [Установка системы очередей сообщений (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [Безопасность сообщений при использовании очереди сообщений](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
