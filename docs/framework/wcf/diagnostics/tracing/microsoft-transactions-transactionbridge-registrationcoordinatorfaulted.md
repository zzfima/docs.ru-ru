---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: f634816b2459d2e0b6137e2e87fef907824af017
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163037"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="d1312-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="d1312-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="d1312-103">Служба протокола WS-AT получила ошибку от своего координатора в ответ на сообщение о регистрации.</span><span class="sxs-lookup"><span data-stu-id="d1312-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d1312-104">Описание</span><span class="sxs-lookup"><span data-stu-id="d1312-104">Description</span></span>  
 <span data-ttu-id="d1312-105">Трассируется, если локальному диспетчеру TransactionManager не удается выполнить регистрацию в вышестоящем диспетчере TransactionManager из-за того, что возвращена ошибка.</span><span class="sxs-lookup"><span data-stu-id="d1312-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="d1312-106">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="d1312-106">Troubleshooting</span></span>  
 <span data-ttu-id="d1312-107">Проверьте возвращаемую ошибку в сообщении трассировки.</span><span class="sxs-lookup"><span data-stu-id="d1312-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1312-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d1312-108">See also</span></span>

- [<span data-ttu-id="d1312-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d1312-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d1312-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d1312-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d1312-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d1312-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
