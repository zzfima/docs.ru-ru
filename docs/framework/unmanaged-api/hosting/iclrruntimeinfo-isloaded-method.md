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
ms.openlocfilehash: 5ff1723cb481ee946e0c5c433009d3d6d7460cf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="6dcc9-102">Метод ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="6dcc9-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="6dcc9-103">Указывает ли общеязыковой среды выполнения (CLR), связанные с [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="6dcc9-104">Среда выполнения может быть загружен без ее запуск.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dcc9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dcc9-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dcc9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dcc9-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="6dcc9-107">[in] Дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="6dcc9-108">[out] `true` Если CLR загружается в процесс; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dcc9-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6dcc9-109">Return Value</span></span>  
 <span data-ttu-id="6dcc9-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6dcc9-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6dcc9-111">HRESULT</span></span>|<span data-ttu-id="6dcc9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6dcc9-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6dcc9-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dcc9-113">S_OK</span></span>|<span data-ttu-id="6dcc9-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="6dcc9-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6dcc9-115">E_POINTER</span></span>|<span data-ttu-id="6dcc9-116">Параметр `pbLoaded` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dcc9-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="6dcc9-117">Remarks</span></span>  
 <span data-ttu-id="6dcc9-118">Этот метод обеспечивает обратную совместимость со следующими функциями и интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="6dcc9-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="6dcc9-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) интерфейса (API размещения платформы .NET Framework версии 1).</span><span class="sxs-lookup"><span data-stu-id="6dcc9-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="6dcc9-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) интерфейс (в платформе .NET Framework 2.0, API размещения).</span><span class="sxs-lookup"><span data-stu-id="6dcc9-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="6dcc9-121">Не рекомендуется `CorBindTo*` функции (см. [устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в API размещения платформы .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="6dcc9-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="6dcc9-122">Узел может вызвать одну из устаревших `CorBindTo*` функции, например [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) функции для создания экземпляра определенной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="6dcc9-123">Узел может затем вызвать метод [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) метод и указать тот же номер версии, чтобы получить [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="6dcc9-124">Если затем основное приложение вызывает `IsLoaded` метод в возвращенном [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, `pbLoaded` возвращает `true`; в противном случае он возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="6dcc9-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dcc9-125">Требования</span><span class="sxs-lookup"><span data-stu-id="6dcc9-125">Requirements</span></span>  
 <span data-ttu-id="6dcc9-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dcc9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dcc9-127">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6dcc9-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6dcc9-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dcc9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dcc9-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dcc9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dcc9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6dcc9-130">See Also</span></span>  
 [<span data-ttu-id="6dcc9-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="6dcc9-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="6dcc9-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6dcc9-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6dcc9-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="6dcc9-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
