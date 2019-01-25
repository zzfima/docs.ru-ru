---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: 0ed3a9a1c16247f94c739a43d84d51e4750b3c2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597662"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="ac55f-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="ac55f-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="ac55f-103">Возникает при невозможности правильного закрытия службы или при прерывании службы.</span><span class="sxs-lookup"><span data-stu-id="ac55f-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ac55f-104">Описание:</span><span class="sxs-lookup"><span data-stu-id="ac55f-104">Description</span></span>  
 <span data-ttu-id="ac55f-105">Данный код ошибки отображается только в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="ac55f-105">This error code only appears in the log file.</span></span> <span data-ttu-id="ac55f-106">Как правило, он указывает на наличие программной ошибки, например при попытке закрыть службу после того, как был вызван метод Abort.</span><span class="sxs-lookup"><span data-stu-id="ac55f-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ac55f-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="ac55f-107">Troubleshooting</span></span>  
 <span data-ttu-id="ac55f-108">Проверьте исходный код приложения.</span><span class="sxs-lookup"><span data-stu-id="ac55f-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac55f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ac55f-109">See also</span></span>
- [<span data-ttu-id="ac55f-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ac55f-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="ac55f-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ac55f-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ac55f-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ac55f-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
