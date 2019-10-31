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
ms.openlocfilehash: e2eddfab68e5c9e2ebffe2c96c9348f3cd799c7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127752"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="52151-102">Метод ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="52151-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="52151-103">Сбрасывает перечислитель домена обратно в начало списка доменов.</span><span class="sxs-lookup"><span data-stu-id="52151-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52151-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52151-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52151-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="52151-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="52151-106">окне Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="52151-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52151-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="52151-107">Return Value</span></span>  
  
|<span data-ttu-id="52151-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52151-108">HRESULT</span></span>|<span data-ttu-id="52151-109">Описание</span><span class="sxs-lookup"><span data-stu-id="52151-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52151-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52151-110">S_OK</span></span>|<span data-ttu-id="52151-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="52151-111">The operation was successful.</span></span>|  
|<span data-ttu-id="52151-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="52151-112">S_FALSE</span></span>|<span data-ttu-id="52151-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="52151-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="52151-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52151-114">E_FAIL</span></span>|<span data-ttu-id="52151-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="52151-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="52151-116">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="52151-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="52151-117">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52151-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52151-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52151-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52151-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="52151-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52151-120">Требования</span><span class="sxs-lookup"><span data-stu-id="52151-120">Requirements</span></span>  
 <span data-ttu-id="52151-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52151-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52151-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="52151-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52151-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="52151-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52151-124">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="52151-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52151-125">См. также</span><span class="sxs-lookup"><span data-stu-id="52151-125">See also</span></span>

- [<span data-ttu-id="52151-126">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="52151-126">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="52151-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="52151-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
