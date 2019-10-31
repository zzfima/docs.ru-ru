---
title: Метод ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: dfdcb9b8aedeb3ccbbd27864e79ce43338942922
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133362"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="a0ad3-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="a0ad3-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="a0ad3-103">Выгружает указанный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ad3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0ad3-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ad3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0ad3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a0ad3-106">окне Указатель типа <xref:System._AppDomain?displayProperty=nameWithType>, представляющий домен для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ad3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a0ad3-107">Return Value</span></span>  
  
|<span data-ttu-id="a0ad3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0ad3-108">HRESULT</span></span>|<span data-ttu-id="a0ad3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a0ad3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0ad3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0ad3-110">S_OK</span></span>|<span data-ttu-id="a0ad3-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-111">The operation was successful.</span></span>|  
|<span data-ttu-id="a0ad3-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a0ad3-112">S_FALSE</span></span>|<span data-ttu-id="a0ad3-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a0ad3-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0ad3-114">E_FAIL</span></span>|<span data-ttu-id="a0ad3-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a0ad3-116">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="a0ad3-117">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0ad3-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0ad3-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0ad3-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a0ad3-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0ad3-120">Требования</span><span class="sxs-lookup"><span data-stu-id="a0ad3-120">Requirements</span></span>  
 <span data-ttu-id="a0ad3-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0ad3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0ad3-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a0ad3-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0ad3-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0ad3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0ad3-124">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a0ad3-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ad3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a0ad3-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="a0ad3-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a0ad3-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
