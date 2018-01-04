---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41cb1b301d3abc6a15992f36929416053ffa6069
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a><span data-ttu-id="bb246-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="bb246-102">Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure</span></span>
<span data-ttu-id="bb246-103">Службе протокола WS-AT не удалось включить в список транзакцию, используя предоставленный контекст координации.</span><span class="sxs-lookup"><span data-stu-id="bb246-103">The WS-AT protocol service failed to enlist on a transaction using the provided coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="bb246-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="bb246-104">Description</span></span>  
 <span data-ttu-id="bb246-105">Регистрируется, если координатору MSDTC не удалось включить в список транзакцию для заданного протокола 2pc.</span><span class="sxs-lookup"><span data-stu-id="bb246-105">Traced when MSDTC is unable to enlist on a transaction for a given 2pc protocol.</span></span>  <span data-ttu-id="bb246-106">Это может произойти, если транзакция больше не существует, включение в список уже запрещено или если уже имеется слишком много перечислений.</span><span class="sxs-lookup"><span data-stu-id="bb246-106">This can happen because the transaction no longer exists, enlisting is no longer allowed, or too many enlistments are already present.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="bb246-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="bb246-107">Troubleshooting</span></span>  
 <span data-ttu-id="bb246-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="bb246-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb246-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bb246-109">See Also</span></span>  
 [<span data-ttu-id="bb246-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="bb246-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="bb246-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="bb246-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="bb246-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="bb246-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
