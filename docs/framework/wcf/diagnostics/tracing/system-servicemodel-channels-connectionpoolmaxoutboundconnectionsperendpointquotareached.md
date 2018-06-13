---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 9dd2ba5a3e94ff794d4b8a8775944355b105f790
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33482012"
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="ebd6a-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="ebd6a-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="ebd6a-103">Службе протокола WS-AT не удалось включить в список транзакцию, используя предоставленный контекст координации.</span><span class="sxs-lookup"><span data-stu-id="ebd6a-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ebd6a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ebd6a-104">Description</span></span>  
 <span data-ttu-id="ebd6a-105">Регистрируется, если координатору MSDTC не удалось включить в список транзакцию для заданного протокола 2pc.</span><span class="sxs-lookup"><span data-stu-id="ebd6a-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="ebd6a-106">Это может произойти, если транзакция больше не существует, включение в список уже запрещено или если уже имеется слишком много перечислений.</span><span class="sxs-lookup"><span data-stu-id="ebd6a-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ebd6a-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ebd6a-107">Troubleshooting</span></span>  
 <span data-ttu-id="ebd6a-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="ebd6a-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd6a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ebd6a-109">See Also</span></span>  
 [<span data-ttu-id="ebd6a-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ebd6a-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="ebd6a-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ebd6a-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="ebd6a-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ebd6a-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
