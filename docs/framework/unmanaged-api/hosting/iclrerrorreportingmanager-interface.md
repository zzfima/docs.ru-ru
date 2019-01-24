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
ms.openlocfilehash: d10fe0240073464e3c2677343288e5379840885d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732795"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="e8403-102">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="e8403-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="e8403-103">Предоставляет методы, позволяющие узла настроить пользовательские дампы стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e8403-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8403-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e8403-104">Methods</span></span>  
  
|<span data-ttu-id="e8403-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e8403-105">Method</span></span>|<span data-ttu-id="e8403-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="e8403-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8403-107">Метод BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="e8403-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="e8403-108">Указывает конфигурацию пользовательских дампов стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="e8403-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="e8403-109">Метод EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="e8403-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="e8403-110">Удаляет конфигурацию пользовательского дампа стека, установленное с предыдущими вызовами `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="e8403-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="e8403-111">Метод GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="e8403-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="e8403-112">Возвращает сегмент Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="e8403-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8403-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8403-113">Remarks</span></span>  
 <span data-ttu-id="e8403-114">`BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="e8403-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="e8403-115">`EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека и освобождает все связанные состояния.</span><span class="sxs-lookup"><span data-stu-id="e8403-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="e8403-116">Он должен вызываться после завершения пользовательского дампа.</span><span class="sxs-lookup"><span data-stu-id="e8403-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8403-117">Сбой при вызове `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="e8403-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8403-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e8403-118">Requirements</span></span>  
 <span data-ttu-id="e8403-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8403-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8403-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8403-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8403-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8403-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8403-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8403-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8403-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e8403-123">See also</span></span>
- [<span data-ttu-id="e8403-124">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="e8403-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="e8403-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e8403-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
