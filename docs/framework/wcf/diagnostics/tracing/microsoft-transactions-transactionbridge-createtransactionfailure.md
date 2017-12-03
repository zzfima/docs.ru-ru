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
ms.openlocfilehash: 1366c1a1fc8e3f040ae1bb0c0fa69c0bf3d61d6a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a><span data-ttu-id="2e785-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span><span class="sxs-lookup"><span data-stu-id="2e785-102">Microsoft.Transactions.TransactionBridge.CreateTransactionFailure</span></span>
<span data-ttu-id="2e785-103">Невозможно создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="2e785-103">A transaction could not be created.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e785-104">Описание</span><span class="sxs-lookup"><span data-stu-id="2e785-104">Description</span></span>  
 <span data-ttu-id="2e785-105">Данная трассировка создается, если MSDTC не может создать транзакцию.</span><span class="sxs-lookup"><span data-stu-id="2e785-105">This trace is generated when MSDTC is unable to create a transaction.</span></span> <span data-ttu-id="2e785-106">Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.</span><span class="sxs-lookup"><span data-stu-id="2e785-106">This can be due to low resources, insufficient log space, or other errors.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2e785-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="2e785-107">Troubleshooting</span></span>  
 <span data-ttu-id="2e785-108">Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="2e785-108">Inspect the status string within the trace message to determine if any actionable item exists.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e785-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2e785-109">See Also</span></span>  
 [<span data-ttu-id="2e785-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2e785-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2e785-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2e785-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2e785-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2e785-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
