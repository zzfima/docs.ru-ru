---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674774"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a><span data-ttu-id="65610-102">System.ServiceModel.Channels.MsmqMessageRejected</span><span class="sxs-lookup"><span data-stu-id="65610-102">System.ServiceModel.Channels.MsmqMessageRejected</span></span>
<span data-ttu-id="65610-103">MSMQ отклонила сообщение.</span><span class="sxs-lookup"><span data-stu-id="65610-103">MSMQ rejected the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="65610-104">Описание</span><span class="sxs-lookup"><span data-stu-id="65610-104">Description</span></span>  
 <span data-ttu-id="65610-105">Данная трассировка показывает, что сообщение MSMQ было отклонено. </span><span class="sxs-lookup"><span data-stu-id="65610-105">This trace indicates that an MSMQ message was rejected.</span></span>  
  
 <span data-ttu-id="65610-106">Сообщения МСМЗ могут быть отклонены, когда Windows Communication Foundation (WCF) (используется либо с NetMsmqBinding, либо msmqIntegrationBinding) не может их обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="65610-106">MSMQ messages can be rejected when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="65610-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="65610-107">Such messages are referred to as poison messages.</span></span> <span data-ttu-id="65610-108">Подозрительное сообщение отклоняется, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="65610-108">A poison message is rejected when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="65610-109">Отклоненное сообщение возвращается в [очередь отправителя Dead-Letter](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span><span class="sxs-lookup"><span data-stu-id="65610-109">A rejected message is delivered back to the sender’s [Dead-Letter Queue](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures).</span></span>  
  
 <span data-ttu-id="65610-110">Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)</span><span class="sxs-lookup"><span data-stu-id="65610-110">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
 <span data-ttu-id="65610-111">Для получения более подробной информации о том, что означает отклоненное сообщение в МСМЗ, [см.](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="65610-111">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65610-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65610-112">See also</span></span>

- [<span data-ttu-id="65610-113">Трассировки</span><span class="sxs-lookup"><span data-stu-id="65610-113">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="65610-114">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="65610-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="65610-115">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="65610-115">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="65610-116">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="65610-116">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="65610-117">[МзМаркСообщение](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="65610-117">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
