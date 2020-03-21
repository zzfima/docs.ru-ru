---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674814"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a><span data-ttu-id="93caf-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span><span class="sxs-lookup"><span data-stu-id="93caf-102">System.ServiceModel.Channels.MsmqPoisonMessageRejected</span></span>
<span data-ttu-id="93caf-103">Подозрительное сообщение отклонено.</span><span class="sxs-lookup"><span data-stu-id="93caf-103">Poison message rejected.</span></span>  
  
## <a name="description"></a><span data-ttu-id="93caf-104">Описание</span><span class="sxs-lookup"><span data-stu-id="93caf-104">Description</span></span>  

 <span data-ttu-id="93caf-105">Указывает, что было обнаружено и отклонено подозрительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="93caf-105">The trace indicates that a poison message was encountered and subsequently rejected.</span></span> <span data-ttu-id="93caf-106">Возникает, если свойство `ReceiveErrorHandling` объекта NetMsmqBinding или MsmqIntegrationBinding имеет значение `Reject`.</span><span class="sxs-lookup"><span data-stu-id="93caf-106">This occurs when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Reject`.</span></span> <span data-ttu-id="93caf-107">Отклоненное сообщение возвращается в [очередь отправителя Dead-Letter](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span><span class="sxs-lookup"><span data-stu-id="93caf-107">A rejected message is delivered back to the sender’s [Dead-Letter Queue](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md).</span></span>  
  
 <span data-ttu-id="93caf-108">Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)</span><span class="sxs-lookup"><span data-stu-id="93caf-108">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span> <span data-ttu-id="93caf-109">Для получения более подробной информации о том, что означает отклоненное сообщение в МСМЗ, [см.](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="93caf-109">For more information on what a rejected message means in MSMQ, see [MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93caf-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93caf-110">See also</span></span>

- [<span data-ttu-id="93caf-111">Трассировки</span><span class="sxs-lookup"><span data-stu-id="93caf-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="93caf-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="93caf-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="93caf-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="93caf-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="93caf-114">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="93caf-114">Poison-Message Handling</span></span>](../../feature-details/poison-message-handling.md)
- <span data-ttu-id="93caf-115">[МзМаркСообщение](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span><span class="sxs-lookup"><span data-stu-id="93caf-115">[MQMarkMessageRejected](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))</span></span>
