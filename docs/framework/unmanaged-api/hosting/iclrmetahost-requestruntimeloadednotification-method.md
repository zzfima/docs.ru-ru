---
title: "Метод ICLRMetaHost::RequestRuntimeLoadedNotification"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b7866270d8c9234a375401dfd05b504a06ddbf4b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="b35a8-102">Метод ICLRMetaHost::RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="b35a8-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="b35a8-103">Предоставляет функции обратного вызова, которое гарантированно вызывается при первой загрузке версия CLR (CLR), но еще не запущена.</span><span class="sxs-lookup"><span data-stu-id="b35a8-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="b35a8-104">Этот метод заменяет [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="b35a8-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b35a8-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b35a8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b35a8-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="b35a8-107">[in] Функция обратного вызова, который вызывается при загрузке новой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b35a8-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b35a8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b35a8-108">Return Value</span></span>  
 <span data-ttu-id="b35a8-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b35a8-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b35a8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b35a8-110">HRESULT</span></span>|<span data-ttu-id="b35a8-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b35a8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b35a8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b35a8-112">S_OK</span></span>|<span data-ttu-id="b35a8-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b35a8-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="b35a8-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b35a8-114">E_POINTER</span></span>|<span data-ttu-id="b35a8-115">Параметр `pCallbackFunction` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="b35a8-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b35a8-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="b35a8-116">Remarks</span></span>  
 <span data-ttu-id="b35a8-117">Функция обратного вызова работает следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b35a8-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="b35a8-118">Обратный вызов выполняется только в том случае, когда среда выполнения загружается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="b35a8-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="b35a8-119">Функция обратного вызова не вызывается для реентерабельным загружает ту же среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="b35a8-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="b35a8-120">Для загрузки среды выполнения не допускающий повторные входы сериализуются вызовы функции обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="b35a8-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="b35a8-121">Функция обратного вызова имеет следующий прототип:</span><span class="sxs-lookup"><span data-stu-id="b35a8-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="b35a8-122">Прототипы функции обратного вызова, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b35a8-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="b35a8-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="b35a8-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="b35a8-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="b35a8-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="b35a8-125">Если узел пытается загрузить или вызывать другой среды выполнения реентерабельным способом `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` параметры, которые указаны в функции обратного вызова необходимо использовать функцию следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b35a8-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="b35a8-126">`pfnCallbackThreadSet`должен вызываться потоком, который может вызвать загрузку среды выполнения, до попытки такой загрузки.</span><span class="sxs-lookup"><span data-stu-id="b35a8-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="b35a8-127">`pfnCallbackThreadUnset`должен быть вызван, когда поток больше не вызывает загрузку среды выполнения (и до возврата из предыдущего обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="b35a8-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="b35a8-128">`pfnCallbackThreadSet`и `pfnCallbackThreadUnset` являются допускает повторные входы.</span><span class="sxs-lookup"><span data-stu-id="b35a8-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b35a8-129">Хост-приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` за пределами области `pCallbackFunction` параметра.</span><span class="sxs-lookup"><span data-stu-id="b35a8-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35a8-130">Требования</span><span class="sxs-lookup"><span data-stu-id="b35a8-130">Requirements</span></span>  
 <span data-ttu-id="b35a8-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35a8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35a8-132">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b35a8-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b35a8-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b35a8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b35a8-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35a8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35a8-135">См. также</span><span class="sxs-lookup"><span data-stu-id="b35a8-135">See Also</span></span>  
 [<span data-ttu-id="b35a8-136">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="b35a8-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="b35a8-137">Размещение</span><span class="sxs-lookup"><span data-stu-id="b35a8-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
