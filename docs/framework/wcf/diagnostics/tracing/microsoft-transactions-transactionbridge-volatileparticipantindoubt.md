---
title: Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt
ms.date: 03/30/2017
ms.assetid: 3e8fc825-9f22-47e7-9c16-d64ef291c932
ms.openlocfilehash: b25debfd9b1e6de6b93fd4dfa8b96925718d9d87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550842"
---
# <a name="microsofttransactionstransactionbridgevolatileparticipantindoubt"></a><span data-ttu-id="a2cf7-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span><span class="sxs-lookup"><span data-stu-id="a2cf7-102">Microsoft.Transactions.TransactionBridge.VolatileParticipantInDoubt</span></span>
<span data-ttu-id="a2cf7-103">Служба протокола WS-AT получила сообщение "Готово" или "Повторная отправка" от неопознанного неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="a2cf7-103">The WS-AT protocol service received a Prepared or Replay message from an unrecognized volatile participant.</span></span> <span data-ttu-id="a2cf7-104">Ошибка, возвращенная участнику, оповещает о том, что результат транзакции не известен.</span><span class="sxs-lookup"><span data-stu-id="a2cf7-104">A fault was returned to the participant, declares that the transaction's outcome is in doubt.</span></span>  
  
## <a name="description"></a><span data-ttu-id="a2cf7-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="a2cf7-105">Description</span></span>  
 <span data-ttu-id="a2cf7-106">Трассируется, когда локальный диспетчер транзакций получает сообщение "Готово" или "Повторная отправка" от уже забытого неустойчивого перечисления.</span><span class="sxs-lookup"><span data-stu-id="a2cf7-106">Traced when the local Transaction Manager receives a Prepared or Replay message from a Volatile enlistment that it has already forgotten.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="a2cf7-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="a2cf7-107">Troubleshooting</span></span>  
 <span data-ttu-id="a2cf7-108">Выявите возможные причины поздних сообщений, поступающих от неустойчивого участника.</span><span class="sxs-lookup"><span data-stu-id="a2cf7-108">Investigate potential causes of late messages coming from the Volatile participant.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cf7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="a2cf7-109">See also</span></span>
- [<span data-ttu-id="a2cf7-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="a2cf7-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="a2cf7-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="a2cf7-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="a2cf7-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="a2cf7-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
