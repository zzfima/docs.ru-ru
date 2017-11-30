---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8550c30f74968d4f58d9a2fd1deac69bf9d3abe7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="325de-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="325de-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="325de-103">Возникает при невозможности правильного закрытия службы или при прерывании службы.</span><span class="sxs-lookup"><span data-stu-id="325de-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="325de-104">Описание</span><span class="sxs-lookup"><span data-stu-id="325de-104">Description</span></span>  
 <span data-ttu-id="325de-105">Данный код ошибки отображается только в файле журнала.</span><span class="sxs-lookup"><span data-stu-id="325de-105">This error code only appears in the log file.</span></span> <span data-ttu-id="325de-106">Как правило, он указывает на наличие программной ошибки, например при попытке закрыть службу после того, как был вызван метод Abort.</span><span class="sxs-lookup"><span data-stu-id="325de-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="325de-107">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="325de-107">Troubleshooting</span></span>  
 <span data-ttu-id="325de-108">Проверьте исходный код приложения.</span><span class="sxs-lookup"><span data-stu-id="325de-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325de-109">См. также</span><span class="sxs-lookup"><span data-stu-id="325de-109">See Also</span></span>  
 [<span data-ttu-id="325de-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="325de-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="325de-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="325de-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="325de-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="325de-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
