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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129246"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="b0a98-102">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="b0a98-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="b0a98-103">Предоставляет методы, позволяющие основному приложению настраивать пользовательские дампы стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b0a98-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0a98-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b0a98-104">Methods</span></span>  
  
|<span data-ttu-id="b0a98-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b0a98-105">Method</span></span>|<span data-ttu-id="b0a98-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b0a98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0a98-107">Метод BeginCustomDump</span><span class="sxs-lookup"><span data-stu-id="b0a98-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="b0a98-108">Задает конфигурацию пользовательских дампов стека для отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="b0a98-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="b0a98-109">Метод EndCustomDump</span><span class="sxs-lookup"><span data-stu-id="b0a98-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="b0a98-110">Очищает конфигурацию пользовательского дампа стека, которая была задана предыдущим вызовом `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="b0a98-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="b0a98-111">Метод GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="b0a98-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="b0a98-112">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="b0a98-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0a98-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="b0a98-113">Remarks</span></span>  
 <span data-ttu-id="b0a98-114">Метод `BeginCustomDump` задает конфигурацию дампа пользовательского стека.</span><span class="sxs-lookup"><span data-stu-id="b0a98-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="b0a98-115">Метод `EndCustomDump` очищает конфигурацию дампа пользовательского стека и освобождает любое связанное состояние.</span><span class="sxs-lookup"><span data-stu-id="b0a98-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="b0a98-116">Он должен вызываться после завершения пользовательского дампа.</span><span class="sxs-lookup"><span data-stu-id="b0a98-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b0a98-117">Сбой вызова `EndCustomDump` приводит к утечке памяти.</span><span class="sxs-lookup"><span data-stu-id="b0a98-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a98-118">Требования</span><span class="sxs-lookup"><span data-stu-id="b0a98-118">Requirements</span></span>  
 <span data-ttu-id="b0a98-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a98-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a98-120">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b0a98-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0a98-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b0a98-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0a98-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a98-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a98-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b0a98-123">See also</span></span>

- [<span data-ttu-id="b0a98-124">Перечисление ECustomDumpItemKind</span><span class="sxs-lookup"><span data-stu-id="b0a98-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="b0a98-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b0a98-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
