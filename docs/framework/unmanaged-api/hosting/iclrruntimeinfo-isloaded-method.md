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
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136361"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="adf58-102">Метод ICLRRuntimeInfo::IsLoaded</span><span class="sxs-lookup"><span data-stu-id="adf58-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="adf58-103">Указывает, загружается ли в процесс общеязыковая среда выполнения (CLR), связанная с интерфейсом [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="adf58-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="adf58-104">Среду выполнения можно загрузить без запуска.</span><span class="sxs-lookup"><span data-stu-id="adf58-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adf58-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adf58-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="adf58-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="adf58-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="adf58-107">окне Обработчик процесса.</span><span class="sxs-lookup"><span data-stu-id="adf58-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="adf58-108">[out] `true`, если среда CLR загружена в процесс; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="adf58-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adf58-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="adf58-109">Return Value</span></span>  
 <span data-ttu-id="adf58-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="adf58-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="adf58-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adf58-111">HRESULT</span></span>|<span data-ttu-id="adf58-112">Описание</span><span class="sxs-lookup"><span data-stu-id="adf58-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adf58-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="adf58-113">S_OK</span></span>|<span data-ttu-id="adf58-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="adf58-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="adf58-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="adf58-115">E_POINTER</span></span>|<span data-ttu-id="adf58-116">Параметр `pbLoaded` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="adf58-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adf58-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="adf58-117">Remarks</span></span>  
 <span data-ttu-id="adf58-118">Этот метод обеспечивает обратную совместимость со следующими функциями и интерфейсами:</span><span class="sxs-lookup"><span data-stu-id="adf58-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="adf58-119">Интерфейс [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) (в API размещения .NET Framework версии 1).</span><span class="sxs-lookup"><span data-stu-id="adf58-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="adf58-120">Интерфейс [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) (в API размещения .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="adf58-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="adf58-121">Нерекомендуемые функции `CorBindTo*` (см. раздел [нерекомендуемые функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) в API размещения .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="adf58-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="adf58-122">Узел может вызвать одну из устаревших функций `CorBindTo*`, таких как функция [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) , для создания экземпляра конкретной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="adf58-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="adf58-123">Затем узел может вызвать метод [ICLRMetaHost::-Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) и указать тот же номер версии для получения интерфейса [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="adf58-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="adf58-124">Если узел затем вызывает метод `IsLoaded` для возвращенного интерфейса [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) , `pbLoaded` возвращает `true`; в противном случае возвращается `false`.</span><span class="sxs-lookup"><span data-stu-id="adf58-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adf58-125">Требования</span><span class="sxs-lookup"><span data-stu-id="adf58-125">Requirements</span></span>  
 <span data-ttu-id="adf58-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adf58-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adf58-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="adf58-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="adf58-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="adf58-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adf58-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adf58-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf58-130">См. также</span><span class="sxs-lookup"><span data-stu-id="adf58-130">See also</span></span>

- [<span data-ttu-id="adf58-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="adf58-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="adf58-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="adf58-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="adf58-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="adf58-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
