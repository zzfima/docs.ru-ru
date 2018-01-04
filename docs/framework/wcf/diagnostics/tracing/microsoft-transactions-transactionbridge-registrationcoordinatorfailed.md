---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 583aa5685ee3da768bea06333b90817d5e17e838
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="edf79-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="edf79-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="edf79-103">Сбой службы протокола WS-AT при отправке сообщения Register своему координатору</span><span class="sxs-lookup"><span data-stu-id="edf79-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="edf79-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="edf79-104">Description</span></span>  
 <span data-ttu-id="edf79-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager по причине невозможности отправить сообщение.</span><span class="sxs-lookup"><span data-stu-id="edf79-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="edf79-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="edf79-106">Troubleshooting</span></span>  
 <span data-ttu-id="edf79-107">Проверить сообщение трассировки на исключение, приводящее к сбою отправки сообщения</span><span class="sxs-lookup"><span data-stu-id="edf79-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf79-108">См. также</span><span class="sxs-lookup"><span data-stu-id="edf79-108">See Also</span></span>  
 [<span data-ttu-id="edf79-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="edf79-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="edf79-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="edf79-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="edf79-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="edf79-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
