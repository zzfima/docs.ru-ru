---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 7e7bd48d206456af6a5a8662516c4d9c82b3ed2f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615947"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a><span data-ttu-id="e5ec5-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span><span class="sxs-lookup"><span data-stu-id="e5ec5-102">System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed</span></span>
<span data-ttu-id="e5ec5-103">Не удается переместить или удалить сообщение.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-103">Cannot move or delete message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="e5ec5-104">Описание</span><span class="sxs-lookup"><span data-stu-id="e5ec5-104">Description</span></span>  
 <span data-ttu-id="e5ec5-105">Эта трассировка показывает, что при попытке переместить, удалить или отклонить сообщение MSMQ произошел сбой.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-105">The trace indicates that a failure occurred when attempting to move, delete, or reject an MSMQ message.</span></span>  
  
 <span data-ttu-id="e5ec5-106">Сообщения MSMQ используются в Windows Communication Foundation (WCF) (при использовании с привязкой NetMsmqBinding или MsmqIntegrationBinding). Эта трассировка относится к выбранному значению `ReceiveErrorHandling` свойство класса NetMsmqBinding или MsmqIntegrationBinding.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-106">MSMQ messages are employed by Windows Communication Foundation (WCF) (when used with either the NetMsmqBinding or the MsmqIntegrationBinding).This trace is related to the chosen value of the `ReceiveErrorHandling` property on the NetMsmqBinding or MsmqIntegrationBinding.</span></span>  
  
 <span data-ttu-id="e5ec5-107">Эта трассировка не указывает на общий сбой системы.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-107">This trace is not indicative of an overall system failure.</span></span> <span data-ttu-id="e5ec5-108">Однако она показывает, что выбранное средство удаления подозрительного сообщения не подходит для сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-108">However, it indicates that the chosen poison message disposition failed for a message.</span></span> <span data-ttu-id="e5ec5-109">См. в разделе [обработка подозрительных сообщений](https://go.microsoft.com/fwlink/?LinkID=99546) узнать больше о при сообщения становятся подозрительными и как настроить службу для их правильной обработки.</span><span class="sxs-lookup"><span data-stu-id="e5ec5-109">See [Poison-Message Handling](https://go.microsoft.com/fwlink/?LinkID=99546) for more details on when messages become poison and how to configure your service to handle them appropriately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ec5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ec5-110">See Also</span></span>  
 [<span data-ttu-id="e5ec5-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="e5ec5-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="e5ec5-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="e5ec5-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="e5ec5-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="e5ec5-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
