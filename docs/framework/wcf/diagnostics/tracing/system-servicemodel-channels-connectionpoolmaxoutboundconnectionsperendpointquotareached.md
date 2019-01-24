---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 4f51777ae690178b83d353f72e63a6f2958b1592
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674587"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="8ebc6-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="8ebc6-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="8ebc6-103">Службе протокола WS-AT не удалось включить в список транзакцию, используя предоставленный контекст координации.</span><span class="sxs-lookup"><span data-stu-id="8ebc6-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8ebc6-104">Описание</span><span class="sxs-lookup"><span data-stu-id="8ebc6-104">Description</span></span>  
 <span data-ttu-id="8ebc6-105">Регистрируется, если координатору MSDTC не удалось включить в список транзакцию для заданного протокола 2pc.</span><span class="sxs-lookup"><span data-stu-id="8ebc6-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="8ebc6-106">Это может произойти, если транзакция больше не существует, включение в список уже запрещено или если уже имеется слишком много перечислений.</span><span class="sxs-lookup"><span data-stu-id="8ebc6-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="8ebc6-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="8ebc6-107">Troubleshooting</span></span>  
 <span data-ttu-id="8ebc6-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="8ebc6-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebc6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8ebc6-109">See also</span></span>
- [<span data-ttu-id="8ebc6-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="8ebc6-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="8ebc6-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="8ebc6-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="8ebc6-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="8ebc6-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
