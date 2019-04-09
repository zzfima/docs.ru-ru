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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 571a676496683ba3251f13c41600bb017e1ced5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156108"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="a74ab-102">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="a74ab-102">LockClrVersion Function</span></span>
<span data-ttu-id="a74ab-103">Позволяет основному приложению определить, какую версию общеязыковой среды выполнения (CLR), которая будет использоваться в процессе до явной инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a74ab-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="a74ab-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a74ab-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a74ab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a74ab-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a74ab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a74ab-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="a74ab-107">[in] Функция, которая вызывается средой CLR при инициализации.</span><span class="sxs-lookup"><span data-stu-id="a74ab-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="a74ab-108">[in] Функция, которая вызывается узлом для сообщать среде CLR, инициализация выполняется запуск.</span><span class="sxs-lookup"><span data-stu-id="a74ab-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="a74ab-109">[in] Функция, которая вызывается узлом для сообщать среде CLR, инициализация завершена.</span><span class="sxs-lookup"><span data-stu-id="a74ab-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a74ab-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a74ab-110">Return Value</span></span>  
 <span data-ttu-id="a74ab-111">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="a74ab-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a74ab-112">Код возврата</span><span class="sxs-lookup"><span data-stu-id="a74ab-112">Return code</span></span>|<span data-ttu-id="a74ab-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a74ab-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a74ab-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a74ab-114">S_OK</span></span>|<span data-ttu-id="a74ab-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="a74ab-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a74ab-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a74ab-116">E_INVALIDARG</span></span>|<span data-ttu-id="a74ab-117">Один или несколько аргументов имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="a74ab-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a74ab-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="a74ab-118">Remarks</span></span>  
 <span data-ttu-id="a74ab-119">Узел вызывает метод `LockClrVersion` перед инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a74ab-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> `LockClrVersion` <span data-ttu-id="a74ab-120">принимает три параметра, все из которых являются обратные вызовы типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="a74ab-120">takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="a74ab-121">Этот тип определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="a74ab-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="a74ab-122">При инициализации среды выполнения, выполняются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a74ab-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="a74ab-123">Узел вызывает метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из функций инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="a74ab-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="a74ab-124">Кроме того узел может инициализировать среду выполнения, с помощью активации COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="a74ab-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="a74ab-125">Среда выполнения вызывает функцию, указанную аргументом `hostCallback` параметра.</span><span class="sxs-lookup"><span data-stu-id="a74ab-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="a74ab-126">Функцию, указанную аргументом `hostCallback` затем выполняет следующую последовательность вызовов:</span><span class="sxs-lookup"><span data-stu-id="a74ab-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="a74ab-127">Функцию, указанную аргументом `pBeginHostSetup` параметра.</span><span class="sxs-lookup"><span data-stu-id="a74ab-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   `CorBindToRuntimeEx` <span data-ttu-id="a74ab-128">(или другую функцию инициализации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="a74ab-128">(or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="a74ab-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="a74ab-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="a74ab-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="a74ab-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="a74ab-131">Функцию, указанную аргументом `pEndHostSetup` параметра.</span><span class="sxs-lookup"><span data-stu-id="a74ab-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="a74ab-132">Все вызовы из `pBeginHostSetup` для `pEndHostSetup` должно находиться на одном потоке или нити с использованием одного логического стека.</span><span class="sxs-lookup"><span data-stu-id="a74ab-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="a74ab-133">Этот поток может отличаться от потока, на котором `hostCallback` вызывается.</span><span class="sxs-lookup"><span data-stu-id="a74ab-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a74ab-134">Требования</span><span class="sxs-lookup"><span data-stu-id="a74ab-134">Requirements</span></span>  
 <span data-ttu-id="a74ab-135">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a74ab-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a74ab-136">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a74ab-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a74ab-137">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a74ab-137">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a74ab-138">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a74ab-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a74ab-139">См. также</span><span class="sxs-lookup"><span data-stu-id="a74ab-139">See also</span></span>

- [<span data-ttu-id="a74ab-140">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="a74ab-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
