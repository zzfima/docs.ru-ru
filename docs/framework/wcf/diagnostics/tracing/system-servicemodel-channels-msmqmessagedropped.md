---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 3fa5ec62c5e8ac83f3f81fb406499b7e596b3dac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969511"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a><span data-ttu-id="1e707-102">System.ServiceModel.Channels.MsmqMessageDropped</span><span class="sxs-lookup"><span data-stu-id="1e707-102">System.ServiceModel.Channels.MsmqMessageDropped</span></span>
<span data-ttu-id="1e707-103">Сообщение удалено из очереди MSMQ.</span><span class="sxs-lookup"><span data-stu-id="1e707-103">MSMQ dropped the message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e707-104">Описание</span><span class="sxs-lookup"><span data-stu-id="1e707-104">Description</span></span>  
 <span data-ttu-id="1e707-105">Данная трассировка указывает, что сообщение MSMQ было удалено.</span><span class="sxs-lookup"><span data-stu-id="1e707-105">The trace indicates that an MSMQ message was dropped.</span></span> <span data-ttu-id="1e707-106">Сообщения MSMQ может быть удален, когда Windows Communication Foundation (WCF) (используется с классом NetMsmqBinding или MsmqIntegrationBinding) не может их обработать.</span><span class="sxs-lookup"><span data-stu-id="1e707-106">MSMQ messages can be dropped when Windows Communication Foundation (WCF) (used with either the NetMsmqBinding or MsmqIntegrationBinding) is unable to process them.</span></span> <span data-ttu-id="1e707-107">Такие сообщения считаются подозрительными.</span><span class="sxs-lookup"><span data-stu-id="1e707-107">Such messages are referred to as poison messages.</span></span>  
  
 <span data-ttu-id="1e707-108">Подозрительное сообщение отбрасывается, если свойству `ReceiveErrorHandling` класса NetMsmqBinding или класса MsmqIntegrationBinding присвоено значение `Drop`.</span><span class="sxs-lookup"><span data-stu-id="1e707-108">A poison message is dropped when the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding is set to `Drop`.</span></span> <span data-ttu-id="1e707-109">Такое сообщение удаляется из очереди, и восстановить его после этого невозможно.</span><span class="sxs-lookup"><span data-stu-id="1e707-109">A dropped message is removed from the queue and is no longer recoverable.</span></span>  
  
 <span data-ttu-id="1e707-110">См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="1e707-110">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e707-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1e707-111">See also</span></span>

- [<span data-ttu-id="1e707-112">Трассировка</span><span class="sxs-lookup"><span data-stu-id="1e707-112">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1e707-113">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="1e707-113">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1e707-114">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="1e707-114">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
- [<span data-ttu-id="1e707-115">Обработка подозрительных сообщений</span><span class="sxs-lookup"><span data-stu-id="1e707-115">Poison-Message Handling</span></span>](https://go.microsoft.com/fwlink/?LinkID=99546)
