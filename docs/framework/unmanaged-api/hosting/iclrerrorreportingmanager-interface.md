---
title: Интерфейс ICLRErrorReportingManager
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a9d9cff0360e4eb27584fe0f22c1c20396ff8f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966247"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="3709b-102">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="3709b-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="3709b-103">Предоставляет методы, позволяющие основному приложению настраивать пользовательские дампы стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3709b-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3709b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3709b-104">Methods</span></span>  
  
|<span data-ttu-id="3709b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3709b-105">Method</span></span>|<span data-ttu-id="3709b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3709b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3709b-107">Метод BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="3709b-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="3709b-108">Задает конфигурацию пользовательских дампов стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3709b-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="3709b-109">Метод EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="3709b-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="3709b-110">Очищает конфигурацию пользовательского дампа стека, которая была задана предыдущим вызовом метода `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="3709b-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="3709b-111">Метод GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="3709b-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="3709b-112">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="3709b-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3709b-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="3709b-113">Remarks</span></span>  
 <span data-ttu-id="3709b-114">`BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="3709b-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="3709b-115">`EndCustomDump` Метод очищает конфигурацию дампа пользовательского стека и освобождает любое связанное состояние.</span><span class="sxs-lookup"><span data-stu-id="3709b-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="3709b-116">Он должен вызываться после завершения пользовательского дампа.</span><span class="sxs-lookup"><span data-stu-id="3709b-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3709b-117">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="3709b-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3709b-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3709b-118">Requirements</span></span>  
 <span data-ttu-id="3709b-119">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3709b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3709b-120">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3709b-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3709b-121">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3709b-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3709b-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3709b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3709b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3709b-123">See also</span></span>

- [<span data-ttu-id="3709b-124">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="3709b-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="3709b-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="3709b-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
