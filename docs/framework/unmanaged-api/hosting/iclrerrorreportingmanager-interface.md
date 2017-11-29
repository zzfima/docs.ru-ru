---
title: "Интерфейс ICLRErrorReportingManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="82844-102">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="82844-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="82844-103">Предоставляет методы, позволяющие основному приложению настроить пользовательские дампы стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="82844-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82844-104">Методы</span><span class="sxs-lookup"><span data-stu-id="82844-104">Methods</span></span>  
  
|<span data-ttu-id="82844-105">Метод</span><span class="sxs-lookup"><span data-stu-id="82844-105">Method</span></span>|<span data-ttu-id="82844-106">Описание</span><span class="sxs-lookup"><span data-stu-id="82844-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82844-107">Метод BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="82844-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="82844-108">Указывает конфигурацию пользовательских дампов стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="82844-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="82844-109">EndCustomDump-метод</span><span class="sxs-lookup"><span data-stu-id="82844-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="82844-110">Очищает конфигурацию пользовательского дампа стека, заданные с предыдущими вызовами метода `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="82844-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="82844-111">Getbucketparametersforcurrentexception-метод</span><span class="sxs-lookup"><span data-stu-id="82844-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="82844-112">Получает блок Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="82844-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82844-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="82844-113">Remarks</span></span>  
 <span data-ttu-id="82844-114">`BeginCustomDump` Метод задает конфигурацию пользовательского дампа стека.</span><span class="sxs-lookup"><span data-stu-id="82844-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="82844-115">`EndCustomDump` Метод очищает конфигурацию пользовательского дампа стека и освобождает все связанные состояния.</span><span class="sxs-lookup"><span data-stu-id="82844-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="82844-116">Он должен вызываться после завершения пользовательского дампа.</span><span class="sxs-lookup"><span data-stu-id="82844-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82844-117">Сбой при вызове `EndCustomDump` вызывает утечку памяти.</span><span class="sxs-lookup"><span data-stu-id="82844-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82844-118">Требования</span><span class="sxs-lookup"><span data-stu-id="82844-118">Requirements</span></span>  
 <span data-ttu-id="82844-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82844-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82844-120">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="82844-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82844-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="82844-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82844-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82844-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82844-123">См. также</span><span class="sxs-lookup"><span data-stu-id="82844-123">See Also</span></span>  
 [<span data-ttu-id="82844-124">Ecustomdumpitemkind-перечисление</span><span class="sxs-lookup"><span data-stu-id="82844-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [<span data-ttu-id="82844-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="82844-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
