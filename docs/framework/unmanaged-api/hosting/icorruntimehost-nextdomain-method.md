---
title: Метод ICorRuntimeHost::NextDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139514"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="e96e1-102">Метод ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="e96e1-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="e96e1-103">Возвращает указатель интерфейса на следующий домен в перечислении.</span><span class="sxs-lookup"><span data-stu-id="e96e1-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e96e1-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e96e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e96e1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e96e1-106">окне Перечислитель, полученный при вызове [енумдомаинс](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="e96e1-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="e96e1-107">заполняет Указатель интерфейса на тип <xref:System._AppDomain?displayProperty=nameWithType>, представляющий следующий домен в перечислении, или значение null, если другие домены не существуют.</span><span class="sxs-lookup"><span data-stu-id="e96e1-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e96e1-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e96e1-108">Return Value</span></span>  
  
|<span data-ttu-id="e96e1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e96e1-109">HRESULT</span></span>|<span data-ttu-id="e96e1-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e96e1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e96e1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e96e1-111">S_OK</span></span>|<span data-ttu-id="e96e1-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="e96e1-112">The operation was successful.</span></span>|  
|<span data-ttu-id="e96e1-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e96e1-113">S_FALSE</span></span>|<span data-ttu-id="e96e1-114">Не удалось завершить операцию, или в перечислении больше нет доменов.</span><span class="sxs-lookup"><span data-stu-id="e96e1-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="e96e1-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e96e1-115">E_FAIL</span></span>|<span data-ttu-id="e96e1-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e96e1-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e96e1-117">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e96e1-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e96e1-118">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e96e1-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e96e1-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e96e1-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e96e1-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e96e1-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e96e1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e96e1-121">Requirements</span></span>  
 <span data-ttu-id="e96e1-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96e1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96e1-123">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e96e1-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e96e1-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e96e1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e96e1-125">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e96e1-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96e1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e96e1-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="e96e1-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e96e1-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
