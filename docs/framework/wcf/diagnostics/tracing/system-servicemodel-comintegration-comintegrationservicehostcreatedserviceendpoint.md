---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674780"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="ed42b-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="ed42b-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="ed42b-103">Не удается переместить или удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="ed42b-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ed42b-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ed42b-104">Description</span></span>  
 <span data-ttu-id="ed42b-105">Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="ed42b-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="ed42b-106">Сообщения МСМЗ используются Фондом связи Windows (WCF) (при использовании либо с NetMsmqBinding, либо с MsmqIntegrationBinding). Этот след связан с выбранной `ReceiveErrorHandling` стоимостью свойства на NetMsmqBinding или MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="ed42b-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="ed42b-107">Эта трассировка не указывает на общий сбой системы.</span><span class="sxs-lookup"><span data-stu-id="ed42b-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="ed42b-108">Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.</span><span class="sxs-lookup"><span data-stu-id="ed42b-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="ed42b-109">Для получения дополнительной информации о том, когда сообщения становятся ядом и как настроить свой сервис для их надлежащей обработки, [см.](../../feature-details/poison-message-handling.md)</span><span class="sxs-lookup"><span data-stu-id="ed42b-109">For more information on when messages become poison and how to configure your service to handle them appropriately, see [Poison-Message Handling](../../feature-details/poison-message-handling.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed42b-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ed42b-110">See also</span></span>

- [<span data-ttu-id="ed42b-111">Трассировки</span><span class="sxs-lookup"><span data-stu-id="ed42b-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ed42b-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ed42b-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ed42b-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ed42b-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
