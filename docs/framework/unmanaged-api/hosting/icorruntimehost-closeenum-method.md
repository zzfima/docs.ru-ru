---
title: Метод ICorRuntimeHost::CloseEnum
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f150fe80302cd03e872ca8bdf5d172caae1ce599
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230776"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="10dc6-102">Метод ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="10dc6-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="10dc6-103">Сбрасывает перечислитель доменов в начало списка доменов.</span><span class="sxs-lookup"><span data-stu-id="10dc6-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10dc6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10dc6-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10dc6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10dc6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="10dc6-106">[in] Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="10dc6-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10dc6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10dc6-107">Return Value</span></span>  
  
|<span data-ttu-id="10dc6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10dc6-108">HRESULT</span></span>|<span data-ttu-id="10dc6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="10dc6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10dc6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="10dc6-110">S_OK</span></span>|<span data-ttu-id="10dc6-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="10dc6-111">The operation was successful.</span></span>|  
|<span data-ttu-id="10dc6-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="10dc6-112">S_FALSE</span></span>|<span data-ttu-id="10dc6-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="10dc6-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="10dc6-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10dc6-114">E_FAIL</span></span>|<span data-ttu-id="10dc6-115">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="10dc6-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="10dc6-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="10dc6-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="10dc6-117">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10dc6-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="10dc6-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10dc6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10dc6-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="10dc6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10dc6-120">Требования</span><span class="sxs-lookup"><span data-stu-id="10dc6-120">Requirements</span></span>  
 <span data-ttu-id="10dc6-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10dc6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10dc6-122">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10dc6-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10dc6-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10dc6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10dc6-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="10dc6-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10dc6-125">См. также</span><span class="sxs-lookup"><span data-stu-id="10dc6-125">See also</span></span>

- [<span data-ttu-id="10dc6-126">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="10dc6-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="10dc6-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="10dc6-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
