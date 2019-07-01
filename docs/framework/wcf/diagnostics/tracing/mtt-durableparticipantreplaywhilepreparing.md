---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486767"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="d6e7c-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="d6e7c-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="d6e7c-103">Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="d6e7c-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="d6e7c-104">Поэтому транзакция была прервана.</span><span class="sxs-lookup"><span data-stu-id="d6e7c-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d6e7c-105">Описание</span><span class="sxs-lookup"><span data-stu-id="d6e7c-105">Description</span></span>  
 <span data-ttu-id="d6e7c-106">Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки.</span><span class="sxs-lookup"><span data-stu-id="d6e7c-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="d6e7c-107">Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.</span><span class="sxs-lookup"><span data-stu-id="d6e7c-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d6e7c-108">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d6e7c-108">Troubleshooting</span></span>

<span data-ttu-id="d6e7c-109">Такая ошибка может указывать, что постоянный участник (включая подчиненные диспетчеры транзакций) был восстановлен после сбоя; Тем не менее результат транзакции не известен и запрашивает его состояние.</span><span class="sxs-lookup"><span data-stu-id="d6e7c-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e7c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d6e7c-110">See also</span></span>

- [<span data-ttu-id="d6e7c-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d6e7c-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d6e7c-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d6e7c-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d6e7c-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d6e7c-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
