---
title: Метод ICLRRuntimeHost::GetCurrentAppDomainId
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
ms.openlocfilehash: 1b7d321eec2bbc2beb47c5de034bb4ef5d534c9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120470"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="b9443-102">Метод ICLRRuntimeHost::GetCurrentAppDomainId</span><span class="sxs-lookup"><span data-stu-id="b9443-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="b9443-103">Возвращает числовой идентификатор <xref:System.AppDomain>, который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b9443-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9443-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9443-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9443-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9443-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="b9443-106">заполняет Числовой идентификатор <xref:System.AppDomain>, который выполняется в данный момент.</span><span class="sxs-lookup"><span data-stu-id="b9443-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9443-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9443-107">Return Value</span></span>  
  
|<span data-ttu-id="b9443-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9443-108">HRESULT</span></span>|<span data-ttu-id="b9443-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b9443-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9443-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9443-110">S_OK</span></span>|<span data-ttu-id="b9443-111">`GetCurrentAppDomainId` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b9443-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="b9443-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9443-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9443-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b9443-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9443-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9443-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9443-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b9443-115">The call timed out.</span></span>|  
|<span data-ttu-id="b9443-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9443-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9443-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b9443-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9443-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9443-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9443-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b9443-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9443-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9443-120">E_FAIL</span></span>|<span data-ttu-id="b9443-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b9443-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9443-122">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b9443-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9443-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b9443-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9443-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="b9443-124">Remarks</span></span>  
 <span data-ttu-id="b9443-125">Параметру `pdwAppDomainId` присваивается значение свойства <xref:System.AppDomain.Id%2A> <xref:System.AppDomain>, в котором выполняется текущий поток.</span><span class="sxs-lookup"><span data-stu-id="b9443-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9443-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b9443-126">Requirements</span></span>  
 <span data-ttu-id="b9443-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9443-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9443-128">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b9443-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9443-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b9443-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9443-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9443-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9443-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b9443-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="b9443-132">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b9443-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
