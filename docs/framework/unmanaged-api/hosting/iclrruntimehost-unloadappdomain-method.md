---
title: Метод ICLRRuntimeHost::UnloadAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.UnloadAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type:
- apiref
ms.openlocfilehash: 2a6dc878f156d5d18970fed72c9722bab60f9ba8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120407"
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="f9247-102">Метод ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="f9247-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="f9247-103">Выгружает управляемые <xref:System.AppDomain>, соответствующие указанному числовому идентификатору.</span><span class="sxs-lookup"><span data-stu-id="f9247-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9247-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9247-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9247-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9247-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="f9247-106">окне Числовой идентификатор домена приложения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="f9247-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="f9247-107">[in] `true`, чтобы указать, что общеязыковая среда выполнения (CLR) должна ожидать завершения выполнения текущего потока приложения перед попыткой выгрузить домен приложения.</span><span class="sxs-lookup"><span data-stu-id="f9247-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9247-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f9247-108">Return Value</span></span>  
  
|<span data-ttu-id="f9247-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f9247-109">HRESULT</span></span>|<span data-ttu-id="f9247-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f9247-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f9247-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9247-111">S_OK</span></span>|<span data-ttu-id="f9247-112">`UnloadAppDomain` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="f9247-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="f9247-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f9247-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f9247-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f9247-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f9247-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f9247-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f9247-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="f9247-116">The call timed out.</span></span>|  
|<span data-ttu-id="f9247-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f9247-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f9247-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="f9247-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f9247-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f9247-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f9247-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="f9247-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f9247-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f9247-121">E_FAIL</span></span>|<span data-ttu-id="f9247-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="f9247-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f9247-123">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f9247-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f9247-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f9247-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9247-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="f9247-125">Remarks</span></span>  
 <span data-ttu-id="f9247-126">Вы можете получить числовой идентификатор домена приложения, в котором выполняется текущий поток, вызвав [жеткуррентаппдомаинид](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="f9247-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="f9247-127">Этот идентификатор соответствует свойству <xref:System.AppDomain.Id%2A> типа управляемого <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="f9247-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9247-128">Требования</span><span class="sxs-lookup"><span data-stu-id="f9247-128">Requirements</span></span>  
 <span data-ttu-id="f9247-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9247-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9247-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f9247-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9247-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f9247-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9247-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9247-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9247-133">См. также</span><span class="sxs-lookup"><span data-stu-id="f9247-133">See also</span></span>

- [<span data-ttu-id="f9247-134">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="f9247-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
