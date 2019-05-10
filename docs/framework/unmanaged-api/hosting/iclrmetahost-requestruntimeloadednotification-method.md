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
ms.openlocfilehash: 87afb19736a484d24bde56cc34854dcd26c6b53b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64755699"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="60076-102">Метод ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="60076-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="60076-103">Предоставляет функцию обратного вызова, которая гарантированно вызывается при первой загрузке версия CLR (CLR), но еще не запущен.</span><span class="sxs-lookup"><span data-stu-id="60076-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="60076-104">Этот метод заменяет [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="60076-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60076-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60076-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60076-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="60076-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="60076-107">[in] Функция обратного вызова, который вызывается при загрузке новой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="60076-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60076-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="60076-108">Return Value</span></span>  
 <span data-ttu-id="60076-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="60076-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="60076-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="60076-110">HRESULT</span></span>|<span data-ttu-id="60076-111">Описание</span><span class="sxs-lookup"><span data-stu-id="60076-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="60076-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="60076-112">S_OK</span></span>|<span data-ttu-id="60076-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="60076-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="60076-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="60076-114">E_POINTER</span></span>|<span data-ttu-id="60076-115">Параметр `pCallbackFunction` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="60076-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60076-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="60076-116">Remarks</span></span>  
 <span data-ttu-id="60076-117">Функция обратного вызова работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60076-117">The callback works in the following way:</span></span>  
  
- <span data-ttu-id="60076-118">Функция обратного вызова вызывается только в том случае, когда среда выполнения загружается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="60076-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
- <span data-ttu-id="60076-119">Функция обратного вызова не вызывается для реентерабельных загрузок ту же среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="60076-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
- <span data-ttu-id="60076-120">Для загрузки среды выполнения не допускающий повторные входы сериализуются вызовы функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="60076-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="60076-121">Функция обратного вызова имеет следующий прототип:</span><span class="sxs-lookup"><span data-stu-id="60076-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="60076-122">Прототипы функции обратного вызова, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60076-122">The callback function prototypes are as follows:</span></span>  
  
- <span data-ttu-id="60076-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="60076-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- <span data-ttu-id="60076-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="60076-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="60076-125">Если основное приложение намеревается загрузить или вызывать другой среды выполнения должен быть загружен в виде реентерабельным, `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` параметры, предоставляемые в обратном вызове, необходимо использовать функцию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="60076-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
- <span data-ttu-id="60076-126">`pfnCallbackThreadSet` должен вызываться потоком, который может вызвать загрузку среды выполнения, до попытки такой загрузки.</span><span class="sxs-lookup"><span data-stu-id="60076-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
- <span data-ttu-id="60076-127">`pfnCallbackThreadUnset` должен вызываться, когда поток больше не вызывает загрузку среды выполнения (и перед возвратом из начальной обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="60076-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
- <span data-ttu-id="60076-128">`pfnCallbackThreadSet` и `pfnCallbackThreadUnset` оба являются не допускающий повторные входы.</span><span class="sxs-lookup"><span data-stu-id="60076-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60076-129">Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` выходит за рамки `pCallbackFunction` параметра.</span><span class="sxs-lookup"><span data-stu-id="60076-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60076-130">Требования</span><span class="sxs-lookup"><span data-stu-id="60076-130">Requirements</span></span>  
 <span data-ttu-id="60076-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60076-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60076-132">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="60076-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="60076-133">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60076-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60076-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60076-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60076-135">См. также</span><span class="sxs-lookup"><span data-stu-id="60076-135">See also</span></span>

- [<span data-ttu-id="60076-136">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="60076-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="60076-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="60076-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
