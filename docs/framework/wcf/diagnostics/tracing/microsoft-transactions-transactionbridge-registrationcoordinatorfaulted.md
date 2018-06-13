---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: e1cb43a9336c2536a3b0372387fd956708be78a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33475924"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="452a3-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="452a3-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="452a3-103">Служба протокола WS-AT получила ошибку от своего координатора в ответ на сообщение о регистрации.</span><span class="sxs-lookup"><span data-stu-id="452a3-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="452a3-104">Описание</span><span class="sxs-lookup"><span data-stu-id="452a3-104">Description</span></span>  
 <span data-ttu-id="452a3-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager из-за того, что возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="452a3-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="452a3-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="452a3-106">Troubleshooting</span></span>  
 <span data-ttu-id="452a3-107">Проверьте возвращаемую ошибку в сообщении трассировки.</span><span class="sxs-lookup"><span data-stu-id="452a3-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452a3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="452a3-108">See Also</span></span>  
 [<span data-ttu-id="452a3-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="452a3-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="452a3-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="452a3-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="452a3-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="452a3-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
