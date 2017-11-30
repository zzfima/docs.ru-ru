---
title: "Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd16f13bd77127953bdd17b258c7be518088f899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="d62f0-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="d62f0-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="d62f0-103">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="d62f0-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d62f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d62f0-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d62f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d62f0-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="d62f0-106">[in] Поток сборки должны быть оценены.</span><span class="sxs-lookup"><span data-stu-id="d62f0-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d62f0-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="d62f0-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="d62f0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает текущую версию среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d62f0-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="d62f0-109">[out] Буфер, содержащий данные идентификации непрозрачный сборки.</span><span class="sxs-lookup"><span data-stu-id="d62f0-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="d62f0-110">[in, out] Размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="d62f0-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d62f0-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d62f0-111">Return Value</span></span>  
  
|<span data-ttu-id="d62f0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d62f0-112">HRESULT</span></span>|<span data-ttu-id="d62f0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d62f0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d62f0-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d62f0-114">S_OK</span></span>|<span data-ttu-id="d62f0-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d62f0-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="d62f0-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d62f0-116">E_INVALIDARG</span></span>|<span data-ttu-id="d62f0-117">Предоставленный `pStream` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="d62f0-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="d62f0-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d62f0-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d62f0-119">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="d62f0-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="d62f0-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d62f0-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d62f0-121">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="d62f0-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d62f0-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d62f0-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d62f0-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="d62f0-123">The call timed out.</span></span>|  
|<span data-ttu-id="d62f0-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d62f0-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d62f0-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="d62f0-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d62f0-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d62f0-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d62f0-127">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="d62f0-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d62f0-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d62f0-128">E_FAIL</span></span>|<span data-ttu-id="d62f0-129">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="d62f0-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d62f0-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="d62f0-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d62f0-131">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d62f0-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d62f0-132">Требования</span><span class="sxs-lookup"><span data-stu-id="d62f0-132">Requirements</span></span>  
 <span data-ttu-id="d62f0-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d62f0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d62f0-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d62f0-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d62f0-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d62f0-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d62f0-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d62f0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d62f0-137">См. также</span><span class="sxs-lookup"><span data-stu-id="d62f0-137">See Also</span></span>  
 [<span data-ttu-id="d62f0-138">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d62f0-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="d62f0-139">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d62f0-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
