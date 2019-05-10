---
title: Метод ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 156906a84013148a4afe3d0687e8d136ca819c8a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584407"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="f87c5-102">Метод ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="f87c5-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="f87c5-103">Указывает, связан ли общеязыковой среды выполнения (CLR) [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="f87c5-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="f87c5-104">Среда выполнения может быть загружен без ее запуск.</span><span class="sxs-lookup"><span data-stu-id="f87c5-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87c5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f87c5-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f87c5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f87c5-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="f87c5-107">[in] Дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="f87c5-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="f87c5-108">[out] `true` Если CLR загружаются в процесс, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="f87c5-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f87c5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f87c5-109">Return Value</span></span>  
 <span data-ttu-id="f87c5-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f87c5-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f87c5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f87c5-111">HRESULT</span></span>|<span data-ttu-id="f87c5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f87c5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f87c5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f87c5-113">S_OK</span></span>|<span data-ttu-id="f87c5-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f87c5-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f87c5-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f87c5-115">E_POINTER</span></span>|<span data-ttu-id="f87c5-116">Параметр `pbLoaded` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f87c5-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f87c5-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f87c5-117">Remarks</span></span>  
 <span data-ttu-id="f87c5-118">Этот метод обеспечивает обратную совместимость с следующие функции и интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="f87c5-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="f87c5-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейс (в API размещения платформы .NET Framework версии 1).</span><span class="sxs-lookup"><span data-stu-id="f87c5-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="f87c5-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс (в платформе .NET Framework 2.0, интерфейс API размещения).</span><span class="sxs-lookup"><span data-stu-id="f87c5-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="f87c5-121">Не рекомендуется `CorBindTo*` функции (см. в разделе [устаревшей функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в .NET Framework 2.0, интерфейс API размещения).</span><span class="sxs-lookup"><span data-stu-id="f87c5-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="f87c5-122">Узел может вызвать одну из устаревших `CorBindTo*` функции, такие как [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) функции для создания экземпляра определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f87c5-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="f87c5-123">Узел может затем вызвать метод [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) метод и указать тот же номер версии, чтобы получить [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f87c5-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="f87c5-124">Если узел, затем вызывает метод `IsLoaded` метод возвращенного [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, `pbLoaded` возвращает `true`; в противном случае он возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="f87c5-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f87c5-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f87c5-125">Requirements</span></span>  
 <span data-ttu-id="f87c5-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87c5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87c5-127">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f87c5-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f87c5-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f87c5-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f87c5-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87c5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87c5-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f87c5-130">See also</span></span>

- [<span data-ttu-id="f87c5-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f87c5-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f87c5-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f87c5-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f87c5-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="f87c5-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
