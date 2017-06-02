---
title: "Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
Существующие приложения MSMQ можно интегрировать с приложениями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], используя привязку интеграции MSMQ для преобразования сообщений MSMQ в сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и наоборот. Это позволяет вызывать принимающие приложения MSMQ из клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также вызывать службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] из отправляющих приложений MSMQ.  
  
 В этом разделе рассматривается, как использовать <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для взаимодействия с использованием очередей между (1 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиентом и службой приложения MSMQ с помощью System.Messaging и (2) клиентом приложения MSMQ и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы.  
  
 Полный пример, демонстрирующий вызов принимающего приложения MSMQ из [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образца.  
  
 Полный пример, демонстрирующий вызов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы от клиента MSMQ см. в разделе [очереди сообщений в Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) образца.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>Создание службы WCF, получающей сообщения от клиента MSMQ  
  
1.  Определите интерфейс, который задает контракт службы для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], принимающей сообщения с использованием очередей от передающего приложения MSMQ, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  Реализуйте интерфейс и примените <xref:System.ServiceModel.ServiceBehaviorAttribute> атрибута к классу, как показано в следующем примере кода.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  Создайте файл конфигурации, который определяет <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.  
  
  
  
4.  Создать экземпляр <xref:System.ServiceModel.ServiceHost> объект, использующий настроенную привязку.  
  
  
  
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
 [Практическое руководство: обмен сообщениями с конечными точками WCF в очереди](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)   
 [Windows Communication Foundation для очереди сообщений](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)   
 [Установка очереди сообщений (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)   
 [Сообщения очереди в Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)   
 [Безопасность сообщений через очереди сообщений](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)