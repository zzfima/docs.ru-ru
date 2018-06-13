---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: fe88e70ab4955305d78baa1158cd73a93ba2ed2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33476324"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="ec469-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="ec469-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="ec469-103">Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="ec469-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="ec469-104">Поэтому транзакция была прервана.</span><span class="sxs-lookup"><span data-stu-id="ec469-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec469-105">Описание</span><span class="sxs-lookup"><span data-stu-id="ec469-105">Description</span></span>  
 <span data-ttu-id="ec469-106">Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки.</span><span class="sxs-lookup"><span data-stu-id="ec469-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="ec469-107">Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.</span><span class="sxs-lookup"><span data-stu-id="ec469-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ec469-108">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ec469-108">Troubleshooting</span></span>  
 <span data-ttu-id="ec469-109">Получение этого сообщения об ошибке может указывать на то, что постоянный участник (включая подчиненные диспетчеры транзакций) был восстановлен после ошибки, однако ему не известен точный результат транзакции, и он запросил ее состояние.</span><span class="sxs-lookup"><span data-stu-id="ec469-109">Receiving this error can indiate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure, however it is unsure of the transaction outcome and request its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec469-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ec469-110">See Also</span></span>  
 [<span data-ttu-id="ec469-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ec469-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ec469-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ec469-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ec469-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ec469-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
