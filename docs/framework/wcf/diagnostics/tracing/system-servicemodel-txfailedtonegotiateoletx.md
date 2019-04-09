---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097568"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="dec19-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="dec19-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="dec19-103">Согласование протокола OleTransactions невозможно завершить для заданного контекста координации.</span><span class="sxs-lookup"><span data-stu-id="dec19-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dec19-104">Описание</span><span class="sxs-lookup"><span data-stu-id="dec19-104">Description</span></span>  
 <span data-ttu-id="dec19-105">Трассируется, если входящая транзакция с информацией OleTx не может использовать прикрепленную информацию OleTx и вместо этого использует WS-AT.</span><span class="sxs-lookup"><span data-stu-id="dec19-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="dec19-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="dec19-106">Troubleshooting</span></span>  
 <span data-ttu-id="dec19-107">Показывает возможную проблему обмена данными MSDTC RPC между компьютерами.</span><span class="sxs-lookup"><span data-stu-id="dec19-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="dec19-108">Появление большого количества таких трассировок в журнале может привести к значительному снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="dec19-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="dec19-109">Если информация OleTx не требуется, установите `OleTxUpgradeEnabled` на значение 0 в конфигурации реестра WS-AT.</span><span class="sxs-lookup"><span data-stu-id="dec19-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec19-110">См. также</span><span class="sxs-lookup"><span data-stu-id="dec19-110">See also</span></span>

- [<span data-ttu-id="dec19-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="dec19-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="dec19-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="dec19-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="dec19-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="dec19-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
