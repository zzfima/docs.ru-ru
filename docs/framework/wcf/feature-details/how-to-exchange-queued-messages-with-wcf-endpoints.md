---
title: "Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF
Очереди обеспечивают возможность надежного обмена сообщениями между клиентом и службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], даже если служба недоступна в процессе взаимодействия. В процедурах ниже показана методика обеспечения устойчивого взаимодействия между клиентом и службой за счет использования стандартной поставленной в очередь привязки при реализации службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 В этом разделе описывается использование <xref:System.ServiceModel.NetMsmqBinding> для взаимодействия с использованием очередей между [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>Использование очередей в службе WCF.  
  
1.  Определите контракт службы, используя интерфейс, отмеченный атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Пометьте операции в интерфейсе, которые являются частью контракта службы с <xref:System.ServiceModel.OperationContractAttribute> и задайте их как односторонние, так как ответ в метод не возвращается. Следующий код представляет пример контракта службы и определение его операций.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  Необходимо определить контракты данных для определяемых пользователем типов, если их передает контракт службы. В следующем коде показано два контракта данных - `PurchaseOrder` и `PurchaseOrderLineItem`. Эти два типа определяют данные, отправляемые службе. (Обратите внимание, что классы, определяющие этот контракт данных, определяют и число методов. Эти методы не являются частью контракта данных. Частью контракта данных являются только члены, объявленные с атрибутом `DataMember`.)  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  Реализуйте методы контракта службы, определенные в интерфейсе в классе.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     Обратите внимание <xref:System.ServiceModel.OperationBehaviorAttribute> на `SubmitPurchaseOrder` метод. Это значит, что данная операция должна вызываться в рамках транзакции, которая автоматически завершается при завершении метода.  
  
4.  Создание транзакционной очереди с помощью <xref:System.Messaging>. Вместо этого можно создать очередь с использованием консоли управления (MMC) «Очередь сообщений Майкрософт (MSMQ)». В этом случае убедитесь, что создается очередь транзакций.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  Определение <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая задает адрес службы и использует стандартную <xref:System.ServiceModel.NetMsmqBinding> привязки. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конфигурации, в разделе [Настройка приложений Windows Communication Foundation](http://msdn.microsoft.com/ru-ru/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
  
  
6.  Создайте узел для `OrderProcessing` службу с помощью <xref:System.ServiceModel.ServiceHost> , считывает сообщения из очереди и обрабатывает их. Откройте узел службы для обеспечения доступности службы. Выведите для пользователя сообщение о том, что нужно нажать любую клавишу для завершения службы. Вызовите метод `ReadLine`, чтобы включить ожидания нажатия клавиши, а затем закройте службу.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>Создание клиента для службы в очереди  
  
1.  В следующем примере показано, как запустить ведущее приложение и использовать программу Svcutil.exe для создания клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  Определение <xref:System.ServiceModel.Description.ServiceEndpoint> в конфигурации, которая указывает адрес и использует стандартную <xref:System.ServiceModel.NetMsmqBinding> привязки, как показано в следующем примере.  
  
  
  
3.  Создайте область транзакции для записи в очередь транзакций, вызовите операцию `SubmitPurchaseOrder` и закройте клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], как показано в следующем примере.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>Пример  
 В следующих примерах показан код службы, ведущее приложение, файл App.config и код клиента для этого примера.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.NetMsmqBinding>   
 [Привязка MSMQ с поддержкой транзакций](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)   
 [Очереди в WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)   
 [Практическое руководство: обмен сообщениями с конечными точками WCF и приложениями очереди сообщений](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Windows Communication Foundation для очереди сообщений](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)   
 [Установка очереди сообщений (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)   
 [Примеры привязки интеграции очереди сообщений](http://msdn.microsoft.com/ru-ru/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)   
 [Сообщения очереди в Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)   
 [Безопасность сообщений через очереди сообщений](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)