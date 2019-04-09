---
title: Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
ms.openlocfilehash: 7fdcebe7ab9ee82a7283add9e0200af2ea5c94bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198976"
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="24f6b-102">Практическое руководство. Обмен сообщениями с конечными точками WCF и приложениями очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="24f6b-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="24f6b-103">Вы можете интегрировать существующие приложения Message Queuing (MSMQ) с приложениями Windows Communication Foundation (WCF), используя привязку интеграции MSMQ для преобразования сообщений MSMQ и из сообщения WCF.</span><span class="sxs-lookup"><span data-stu-id="24f6b-103">You can integrate existing Message Queuing (MSMQ) applications with Windows Communication Foundation (WCF) applications by using the MSMQ integration binding to convert MSMQ messages to and from WCF messages.</span></span> <span data-ttu-id="24f6b-104">Это позволяет вызывать принимающие приложения MSMQ из клиентов WCF, а также вызывать службы WCF из отправляющих приложений MSMQ.</span><span class="sxs-lookup"><span data-stu-id="24f6b-104">This allows you to call into MSMQ receiver applications from WCF clients as well as call into WCF services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="24f6b-105">В этом разделе описано, мы расскажем, как использовать <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> для взаимодействия с использованием очередей между (1) клиентом WCF и службой приложения MSMQ, написанные с использованием System.Messaging и (2) клиентом приложения MSMQ и службой WCF.</span><span class="sxs-lookup"><span data-stu-id="24f6b-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a WCF client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a WCF service.</span></span>  
  
 <span data-ttu-id="24f6b-106">Полный пример, демонстрирующий вызов принимающего приложения MSMQ из клиента WCF, см. в разделе [Windows Communication Foundation для Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) образца.</span><span class="sxs-lookup"><span data-stu-id="24f6b-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a WCF client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="24f6b-107">Полный пример, демонстрирующий вызов службы WCF из клиента MSMQ, см. в разделе [служба очереди сообщений Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) образца.</span><span class="sxs-lookup"><span data-stu-id="24f6b-107">For a complete sample that demonstrates how to call a WCF service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="24f6b-108">Создание службы WCF, получающей сообщения от клиента MSMQ</span><span class="sxs-lookup"><span data-stu-id="24f6b-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="24f6b-109">Определите интерфейс, определяющий контракт службы для службы WCF, которая получает сообщения из очереди от передающего приложения MSMQ, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="24f6b-109">Define an interface that defines the service contract for the WCF service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="24f6b-110">Реализуйте интерфейс и примените атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> к классу, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="24f6b-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="24f6b-111">Создайте файл конфигурации, задающий привязку <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span><span class="sxs-lookup"><span data-stu-id="24f6b-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  

4.  <span data-ttu-id="24f6b-112">Создайте экземпляр объекта <xref:System.ServiceModel.ServiceHost>, использующий настроенную привязку.</span><span class="sxs-lookup"><span data-stu-id="24f6b-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  

### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="24f6b-113">Создание клиента WCF, передающего сообщения в принимающее приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="24f6b-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="24f6b-114">Определите интерфейс, определяющий контракт службы для клиента WCF, что отправляет в очередь сообщений в принимающее приложения MSMQ, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="24f6b-114">Define an interface that defines the service contract for the WCF client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="24f6b-115">Определите класс клиента, который клиент WCF использует для вызова принимающего приложения MSMQ.</span><span class="sxs-lookup"><span data-stu-id="24f6b-115">Define a client class that the WCF client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="24f6b-116">Создайте конфигурацию, которая задает использование привязки MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="24f6b-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="24f6b-117">Создайте экземпляр класса клиента и вызовите метод, определенный службой приема сообщений.</span><span class="sxs-lookup"><span data-stu-id="24f6b-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="24f6b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="24f6b-118">See also</span></span>

- [<span data-ttu-id="24f6b-119">Общие сведения об очередях</span><span class="sxs-lookup"><span data-stu-id="24f6b-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [<span data-ttu-id="24f6b-120">Практическое руководство. Обмен сообщениями в очереди с конечными точками WCF</span><span class="sxs-lookup"><span data-stu-id="24f6b-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [<span data-ttu-id="24f6b-121">Отправка сообщений из приложения Windows Communication Foundation в приложение MSMQ</span><span class="sxs-lookup"><span data-stu-id="24f6b-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="24f6b-122">Установка системы очередей сообщений (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="24f6b-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="24f6b-123">Передача сообщений из приложения MSMQ в приложение Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="24f6b-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="24f6b-124">Безопасность сообщений при использовании очереди сообщений</span><span class="sxs-lookup"><span data-stu-id="24f6b-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
