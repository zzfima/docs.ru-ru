---
title: Функция LockClrVersion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133779"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="ef82b-102">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="ef82b-102">LockClrVersion Function</span></span>
<span data-ttu-id="ef82b-103">Позволяет узлу определить, какая версия среды CLR будет использоваться в процессе перед явной инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ef82b-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="ef82b-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ef82b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef82b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef82b-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef82b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef82b-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="ef82b-107">окне Функция, вызываемая средой CLR при инициализации.</span><span class="sxs-lookup"><span data-stu-id="ef82b-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="ef82b-108">окне Функция, вызываемая узлом для информирования среды CLR о начале инициализации.</span><span class="sxs-lookup"><span data-stu-id="ef82b-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="ef82b-109">окне Функция, вызываемая узлом для информирования среды CLR о завершении инициализации.</span><span class="sxs-lookup"><span data-stu-id="ef82b-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef82b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef82b-110">Return Value</span></span>  
 <span data-ttu-id="ef82b-111">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="ef82b-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ef82b-112">Код возврата</span><span class="sxs-lookup"><span data-stu-id="ef82b-112">Return code</span></span>|<span data-ttu-id="ef82b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ef82b-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ef82b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef82b-114">S_OK</span></span>|<span data-ttu-id="ef82b-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ef82b-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="ef82b-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ef82b-116">E_INVALIDARG</span></span>|<span data-ttu-id="ef82b-117">Один или несколько аргументов имеют значение null.</span><span class="sxs-lookup"><span data-stu-id="ef82b-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef82b-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="ef82b-118">Remarks</span></span>  
 <span data-ttu-id="ef82b-119">Узел вызывает `LockClrVersion` перед инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ef82b-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="ef82b-120">`LockClrVersion` принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="ef82b-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="ef82b-121">Этот тип определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ef82b-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="ef82b-122">При инициализации среды выполнения выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ef82b-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="ef82b-123">Узел вызывает [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из других функций инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef82b-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="ef82b-124">Кроме того, узел может инициализировать среду выполнения с помощью активации объекта COM.</span><span class="sxs-lookup"><span data-stu-id="ef82b-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="ef82b-125">Среда выполнения вызывает функцию, указанную параметром `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="ef82b-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="ef82b-126">Функция, указанная `hostCallback`, затем выполняет следующую последовательность вызовов:</span><span class="sxs-lookup"><span data-stu-id="ef82b-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="ef82b-127">Функция, заданная параметром `pBeginHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="ef82b-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="ef82b-128">`CorBindToRuntimeEx` (или другую функцию инициализации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="ef82b-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="ef82b-129">[ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="ef82b-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="ef82b-130">[ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="ef82b-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="ef82b-131">Функция, заданная параметром `pEndHostSetup`.</span><span class="sxs-lookup"><span data-stu-id="ef82b-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="ef82b-132">Все вызовы от `pBeginHostSetup` к `pEndHostSetup` должны выполняться в одном потоке или Fiber с одним и тем же логическим стеком.</span><span class="sxs-lookup"><span data-stu-id="ef82b-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="ef82b-133">Этот поток может отличаться от потока, в котором вызывается `hostCallback`.</span><span class="sxs-lookup"><span data-stu-id="ef82b-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef82b-134">Требования</span><span class="sxs-lookup"><span data-stu-id="ef82b-134">Requirements</span></span>  
 <span data-ttu-id="ef82b-135">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef82b-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef82b-136">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef82b-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef82b-137">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef82b-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef82b-138">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef82b-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef82b-139">См. также</span><span class="sxs-lookup"><span data-stu-id="ef82b-139">See also</span></span>

- [<span data-ttu-id="ef82b-140">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ef82b-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
