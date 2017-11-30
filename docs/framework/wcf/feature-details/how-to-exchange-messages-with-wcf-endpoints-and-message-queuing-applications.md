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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d09b8e662b2876fa5d5c5246ea7e7a4998cde9ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="6e473-102">Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="6e473-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="6e473-103">Существующие приложения MSMQ можно интегрировать с приложениями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], используя привязку интеграции MSMQ для преобразования сообщений MSMQ в сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и наоборот.</span><span class="sxs-lookup"><span data-stu-id="6e473-103">You can integrate existing Message Queuing (MSMQ) applications with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications by using the MSMQ integration binding to convert MSMQ messages to and from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messages.</span></span> <span data-ttu-id="6e473-104">Это позволяет вызывать принимающие приложения MSMQ из клиентов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], а также вызывать службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] из отправляющих приложений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6e473-104">This allows you to call into MSMQ receiver applications from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients as well as call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="6e473-105">В этом разделе рассматривается, как использовать привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для взаимодействия с использованием очередей между (1) клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и службой приложения MSMQ, созданной с помощью System.Messaging, и (2) клиентом приложения MSMQ и службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6e473-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="6e473-106">Полный пример, демонстрирующий вызов принимающее приложение MSMQ из [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] клиента, в разделе [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образца.</span><span class="sxs-lookup"><span data-stu-id="6e473-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="6e473-107">Полный пример, демонстрирующий вызов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы от клиента MSMQ см. в разделе [служба очередей сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) образца.</span><span class="sxs-lookup"><span data-stu-id="6e473-107">For a complete sample that demonstrates how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="6e473-108">Создание службы WCF, получающей сообщения от клиента MSMQ</span><span class="sxs-lookup"><span data-stu-id="6e473-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="6e473-109">Определите интерфейс, который задает контракт службы для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], принимающей сообщения с использованием очередей от передающего приложения MSMQ, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6e473-109">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="6e473-110">Реализуйте интерфейс и примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6e473-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="6e473-111">Создайте файл конфигурации, задающий привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="6e473-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="6e473-112">Создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, использующий настроенную привязку.</span><span class="sxs-lookup"><span data-stu-id="6e473-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="6e473-113">Создание клиента WCF, передающего сообщения в принимающее приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="6e473-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="6e473-114">Определите интерфейс, который задает контракт службы для клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], передающего сообщения с использованием очередей в принимающее приложения MSMQ, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="6e473-114">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="6e473-115">Определите класс клиента, используемый клиентом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для вызова принимающего приложения MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6e473-115">Define a client class that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="6e473-116">Создайте конфигурацию, которая задает использование привязки MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="6e473-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="6e473-117">Создайте экземпляр класса клиента и вызовите метод, определенный службой приема сообщений.</span><span class="sxs-lookup"><span data-stu-id="6e473-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="6e473-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6e473-118">See Also</span></span>  
 [<span data-ttu-id="6e473-119">Общие сведения об очередях</span><span class="sxs-lookup"><span data-stu-id="6e473-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="6e473-120">Как: обмен сообщениями с конечными точками WCF в очереди</span><span class="sxs-lookup"><span data-stu-id="6e473-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="6e473-121">Windows Communication Foundation для очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="6e473-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="6e473-122">Установка очереди сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="6e473-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="6e473-123">В Windows Communication Foundation очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="6e473-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="6e473-124">Безопасность сообщений через очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="6e473-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
