---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02cdc8ceb8cc667cb4160f0333ffea511dcfbd23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="80ece-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="80ece-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>
<span data-ttu-id="80ece-103">Невозможно создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="80ece-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="80ece-104">Описание</span><span class="sxs-lookup"><span data-stu-id="80ece-104">Description</span></span>  
 <span data-ttu-id="80ece-105">Данная трассировка создается, если MSDTC не может создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="80ece-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="80ece-106">Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.</span><span class="sxs-lookup"><span data-stu-id="80ece-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="80ece-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="80ece-107">Troubleshooting</span></span>  
 <span data-ttu-id="80ece-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="80ece-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ece-109">См. также</span><span class="sxs-lookup"><span data-stu-id="80ece-109">See Also</span></span>  
 [<span data-ttu-id="80ece-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="80ece-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="80ece-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="80ece-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="80ece-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="80ece-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
