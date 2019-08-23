---
title: Метод ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 539f69c33b67ad1a8a514062c5d777deaced1599
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965003"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="f7b7b-102">Метод ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="f7b7b-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="f7b7b-103">Предоставляет функцию обратного вызова, которая гарантированно будет вызываться при первой загрузке версии среды CLR, но еще не запущена.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="f7b7b-104">Этот метод заменяет функцию [локкклрверсион](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f7b7b-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b7b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7b7b-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7b7b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7b7b-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="f7b7b-107">окне Функция обратного вызова, которая вызывается при загрузке новой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7b7b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f7b7b-108">Return Value</span></span>  
 <span data-ttu-id="f7b7b-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f7b7b-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7b7b-110">HRESULT</span></span>|<span data-ttu-id="f7b7b-111">Описание</span><span class="sxs-lookup"><span data-stu-id="f7b7b-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7b7b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7b7b-112">S_OK</span></span>|<span data-ttu-id="f7b7b-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f7b7b-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f7b7b-114">E_POINTER</span></span>|<span data-ttu-id="f7b7b-115">Параметр `pCallbackFunction` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b7b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7b7b-116">Remarks</span></span>  
 <span data-ttu-id="f7b7b-117">Обратный вызов работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="f7b7b-118">Обратный вызов вызывается, только если среда выполнения загружается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="f7b7b-119">Обратный вызов не вызывается для повторных загрузок одной и той же среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="f7b7b-120">Для невходных загрузок среды выполнения вызовы функции обратного вызова сериализуются.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="f7b7b-121">Функция обратного вызова имеет следующий прототип:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="f7b7b-122">Прототипы функций обратного вызова имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="f7b7b-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="f7b7b-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="f7b7b-125">Если узел намеревается загрузить или вызвать повторную загрузку другой среды выполнения, `pfnCallbackThreadSet` параметры и `pfnCallbackThreadUnset` , предоставленные в функции обратного вызова, должны использоваться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f7b7b-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="f7b7b-126">`pfnCallbackThreadSet`должен вызываться потоком, который может вызвать загрузку среды выполнения до того, как будет предпринята такая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="f7b7b-127">`pfnCallbackThreadUnset`должен вызываться, когда поток больше не будет вызывать такую нагрузку во время выполнения (и до возврата из начального обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="f7b7b-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="f7b7b-128">`pfnCallbackThreadSet`и `pfnCallbackThreadUnset` не являются недопустимыми для повторного входа.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7b7b-129">Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` `pCallbackFunction` вне области действия параметра.</span><span class="sxs-lookup"><span data-stu-id="f7b7b-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b7b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="f7b7b-130">Requirements</span></span>  
 <span data-ttu-id="f7b7b-131">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b7b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b7b-132">**Заголовок.** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="f7b7b-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f7b7b-133">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f7b7b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7b7b-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b7b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b7b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="f7b7b-135">See also</span></span>

- [<span data-ttu-id="f7b7b-136">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="f7b7b-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="f7b7b-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="f7b7b-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
