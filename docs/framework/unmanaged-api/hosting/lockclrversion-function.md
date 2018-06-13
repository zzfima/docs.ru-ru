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
ms.openlocfilehash: 6956d73be0380baef96d94584f007e0683331784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446096"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="83eb6-102">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="83eb6-102">LockClrVersion Function</span></span>
<span data-ttu-id="83eb6-103">Предоставляет узлу возможность определить, какая версия среды common language runtime (CLR), которая будет использоваться в процессе до явной инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="83eb6-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="83eb6-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83eb6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83eb6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83eb6-105">Syntax</span></span>  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="83eb6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="83eb6-106">Parameters</span></span>  
 `hostCallback`  
 <span data-ttu-id="83eb6-107">[in] Функция, вызываемая при инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="83eb6-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="83eb6-108">[in] Функция, вызываемая узлом сообщать среде CLR, инициализация выполняется запуск.</span><span class="sxs-lookup"><span data-stu-id="83eb6-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="83eb6-109">[in] Функция, вызываемая узлом сообщать среде CLR, инициализация завершена.</span><span class="sxs-lookup"><span data-stu-id="83eb6-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83eb6-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83eb6-110">Return Value</span></span>  
 <span data-ttu-id="83eb6-111">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="83eb6-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="83eb6-112">Код возврата</span><span class="sxs-lookup"><span data-stu-id="83eb6-112">Return code</span></span>|<span data-ttu-id="83eb6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="83eb6-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="83eb6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="83eb6-114">S_OK</span></span>|<span data-ttu-id="83eb6-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="83eb6-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="83eb6-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="83eb6-116">E_INVALIDARG</span></span>|<span data-ttu-id="83eb6-117">Один или несколько аргументов имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="83eb6-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83eb6-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="83eb6-118">Remarks</span></span>  
 <span data-ttu-id="83eb6-119">Узел вызывает метод `LockClrVersion` перед инициализацией среды CLR.</span><span class="sxs-lookup"><span data-stu-id="83eb6-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="83eb6-120">`LockClrVersion` принимает три параметра, все из которых являются обратными вызовами типа [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="83eb6-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="83eb6-121">Этот тип определяется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="83eb6-121">This type is defined as follows.</span></span>  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="83eb6-122">При инициализации среды выполнения, выполняются следующие действия:</span><span class="sxs-lookup"><span data-stu-id="83eb6-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1.  <span data-ttu-id="83eb6-123">Узел вызывает метод [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или одну из функций инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="83eb6-123">The host calls [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="83eb6-124">Кроме того узел может инициализировать среду выполнения, с помощью активации COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="83eb6-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2.  <span data-ttu-id="83eb6-125">Среда выполнения вызывает функции, указанной `hostCallback` параметра.</span><span class="sxs-lookup"><span data-stu-id="83eb6-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3.  <span data-ttu-id="83eb6-126">Функции, указанной `hostCallback` затем вызывает следующую последовательность вызовов:</span><span class="sxs-lookup"><span data-stu-id="83eb6-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    -   <span data-ttu-id="83eb6-127">Функции, указанной `pBeginHostSetup` параметра.</span><span class="sxs-lookup"><span data-stu-id="83eb6-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    -   <span data-ttu-id="83eb6-128">`CorBindToRuntimeEx` (или другую функцию инициализации среды выполнения).</span><span class="sxs-lookup"><span data-stu-id="83eb6-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    -   <span data-ttu-id="83eb6-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="83eb6-129">[ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    -   <span data-ttu-id="83eb6-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="83eb6-130">[ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).</span></span>  
  
    -   <span data-ttu-id="83eb6-131">Функции, указанной `pEndHostSetup` параметра.</span><span class="sxs-lookup"><span data-stu-id="83eb6-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="83eb6-132">Все вызовы из `pBeginHostSetup` для `pEndHostSetup` должно находиться на одном потоке или нити с использованием одного логического стека.</span><span class="sxs-lookup"><span data-stu-id="83eb6-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="83eb6-133">Этот поток может отличаться от потока, на котором `hostCallback` вызывается.</span><span class="sxs-lookup"><span data-stu-id="83eb6-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83eb6-134">Требования</span><span class="sxs-lookup"><span data-stu-id="83eb6-134">Requirements</span></span>  
 <span data-ttu-id="83eb6-135">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83eb6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83eb6-136">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83eb6-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83eb6-137">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83eb6-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83eb6-138">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83eb6-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83eb6-139">См. также</span><span class="sxs-lookup"><span data-stu-id="83eb6-139">See Also</span></span>  
 [<span data-ttu-id="83eb6-140">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="83eb6-140">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
