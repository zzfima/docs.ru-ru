---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1dd58fdbdbdcf2f7bf8f69b86276a24c17df79e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="4ab4a-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="4ab4a-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="4ab4a-103">Служба протокола WS-AT получила ошибку от своего координатора в ответ на сообщение о регистрации.</span><span class="sxs-lookup"><span data-stu-id="4ab4a-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="4ab4a-104">Описание</span><span class="sxs-lookup"><span data-stu-id="4ab4a-104">Description</span></span>  
 <span data-ttu-id="4ab4a-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager из-за того, что возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="4ab4a-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="4ab4a-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="4ab4a-106">Troubleshooting</span></span>  
 <span data-ttu-id="4ab4a-107">Проверьте возвращаемую ошибку в сообщении трассировки.</span><span class="sxs-lookup"><span data-stu-id="4ab4a-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ab4a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4ab4a-108">See Also</span></span>  
 [<span data-ttu-id="4ab4a-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="4ab4a-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="4ab4a-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="4ab4a-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="4ab4a-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="4ab4a-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
