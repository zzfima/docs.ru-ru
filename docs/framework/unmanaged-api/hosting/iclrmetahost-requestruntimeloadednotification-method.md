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
ms.openlocfilehash: 23f868bba2dc058d99f1c5c09e9b311b1ff3634a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140900"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="99e3e-102">Метод ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="99e3e-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="99e3e-103">Предоставляет функцию обратного вызова, которая гарантированно будет вызываться при первой загрузке версии среды CLR, но еще не запущена.</span><span class="sxs-lookup"><span data-stu-id="99e3e-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="99e3e-104">Этот метод заменяет функцию [локкклрверсион](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="99e3e-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e3e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99e3e-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99e3e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="99e3e-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="99e3e-107">окне Функция обратного вызова, которая вызывается при загрузке новой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="99e3e-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99e3e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="99e3e-108">Return Value</span></span>  
 <span data-ttu-id="99e3e-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="99e3e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="99e3e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99e3e-110">HRESULT</span></span>|<span data-ttu-id="99e3e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="99e3e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99e3e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="99e3e-112">S_OK</span></span>|<span data-ttu-id="99e3e-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="99e3e-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="99e3e-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="99e3e-114">E_POINTER</span></span>|<span data-ttu-id="99e3e-115">Параметр `pCallbackFunction` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="99e3e-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e3e-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="99e3e-116">Remarks</span></span>  
 <span data-ttu-id="99e3e-117">Обратный вызов работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99e3e-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="99e3e-118">Обратный вызов вызывается, только если среда выполнения загружается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="99e3e-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="99e3e-119">Обратный вызов не вызывается для повторных загрузок одной и той же среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="99e3e-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="99e3e-120">Для невходных загрузок среды выполнения вызовы функции обратного вызова сериализуются.</span><span class="sxs-lookup"><span data-stu-id="99e3e-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="99e3e-121">Функция обратного вызова имеет следующий прототип:</span><span class="sxs-lookup"><span data-stu-id="99e3e-121">The callback function has the following prototype:</span></span>  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="99e3e-122">Прототипы функций обратного вызова имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="99e3e-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="99e3e-123">`pfnCallbackThreadSet`.</span><span class="sxs-lookup"><span data-stu-id="99e3e-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="99e3e-124">`pfnCallbackThreadUnset`.</span><span class="sxs-lookup"><span data-stu-id="99e3e-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="99e3e-125">Если узел намеревается загрузить или вызвать повторную загрузку другой среды выполнения, параметры `pfnCallbackThreadSet` и `pfnCallbackThreadUnset`, предоставляемые функцией обратного вызова, должны использоваться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99e3e-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="99e3e-126">`pfnCallbackThreadSet` должен вызываться потоком, который может вызвать загрузку среды выполнения до того, как будет предпринята такая нагрузка.</span><span class="sxs-lookup"><span data-stu-id="99e3e-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="99e3e-127">`pfnCallbackThreadUnset` должны вызываться, когда поток больше не будет вызывать такую нагрузку во время выполнения (и до возврата из начального обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="99e3e-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="99e3e-128">`pfnCallbackThreadSet` и `pfnCallbackThreadUnset` не являются недопустимыми.</span><span class="sxs-lookup"><span data-stu-id="99e3e-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99e3e-129">Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` вне области действия параметра `pCallbackFunction`.</span><span class="sxs-lookup"><span data-stu-id="99e3e-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e3e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="99e3e-130">Requirements</span></span>  
 <span data-ttu-id="99e3e-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99e3e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e3e-132">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="99e3e-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="99e3e-133">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99e3e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99e3e-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99e3e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e3e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="99e3e-135">See also</span></span>

- [<span data-ttu-id="99e3e-136">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="99e3e-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="99e3e-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="99e3e-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
