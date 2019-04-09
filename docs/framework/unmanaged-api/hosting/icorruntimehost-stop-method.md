---
title: Метод ICorRuntimeHost::Stop
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c59a0c5ef1e89c2853a566bd3b587d15a1ed80c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119266"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="3c379-102">Метод ICorRuntimeHost::Stop</span><span class="sxs-lookup"><span data-stu-id="3c379-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="3c379-103">Останавливает выполнение кода в среде выполнения для текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="3c379-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c379-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c379-104">Syntax</span></span>  
  
```  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3c379-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3c379-105">Return Value</span></span>  
  
|<span data-ttu-id="3c379-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c379-106">HRESULT</span></span>|<span data-ttu-id="3c379-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3c379-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c379-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c379-108">S_OK</span></span>|<span data-ttu-id="3c379-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="3c379-109">The operation was successful.</span></span>|  
|<span data-ttu-id="3c379-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3c379-110">S_FALSE</span></span>|<span data-ttu-id="3c379-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="3c379-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3c379-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c379-112">E_FAIL</span></span>|<span data-ttu-id="3c379-113">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="3c379-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3c379-114">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="3c379-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3c379-115">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c379-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c379-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c379-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c379-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="3c379-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c379-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c379-118">Remarks</span></span>  
 <span data-ttu-id="3c379-119">Обычно нет необходимости вызывать `Stop` метод, так как код прекращает выполнение при завершении процесса.</span><span class="sxs-lookup"><span data-stu-id="3c379-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c379-120">После вызова `Stop`, среда CLR не могут повторно инициализироваться в один процесс.</span><span class="sxs-lookup"><span data-stu-id="3c379-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c379-121">Требования</span><span class="sxs-lookup"><span data-stu-id="3c379-121">Requirements</span></span>  
 <span data-ttu-id="3c379-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c379-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c379-123">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c379-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c379-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c379-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c379-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3c379-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c379-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3c379-126">See also</span></span>

- [<span data-ttu-id="3c379-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="3c379-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
